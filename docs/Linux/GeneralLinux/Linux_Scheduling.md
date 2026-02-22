
# Linux Scheduling

## at command

| Command | When the job will run |
| --- | --- |
| at now | immediately |
| at now + 15 minutes | 15 minutes from the current time |
| at now + 4 hours | 4 hours from the current time |
| at now + 7 days | 7 days from the current time |
| at noon | At noon today (or tomorrow, if it's already past noon) |
| at now next hour | Exactly 60 minutes from now |
| at now next day | At the same time tomorrow |
| at 17:00 tomorrow | At 5:00pm tomorrow |
| at 4:45pm | At 4:45pm today (or tomorrow if it's already past 4:45pm) |
| at 3:00 Dec 28, 2018 | at 3:00am on December 28, 2018 |

## Cron job

* /etc/cron.allow: contains the names of the users who are allowed to use the crontab to submit jobs
* /etc/cron.deny: Contains the names of users who are not allowed to usse the crontab command to sumit jobs.

### Crontab format

| Field Number | meaning of field | Acceptable values |
| --- | --- | --- |
| 1 | Minute | 0-59 |
| 2 | Hour of the day | 0 -23 |
| 3 | Day of the month | 0-31 |
| 4 | Month | 1-12 (1 means January, 2 means February, and so on) or the names of onths using the first three letters -- Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dev |
| 5 | Day of the week | 0 - 6 (0 means Sunday, 1 means Monday, and so on) or the three-letter abbreviations of weekdays -- Sun, Mon, Tue, Wed, Thu, Fri, Sat |

```
crontab jobinfo

crontab -l

crontab -u username filename

crontab -u username -l

crontab -u username -r

```

| Directory Name | Script Executes |
| --- | --- |
| /etc/cron.hourly | Every hour |
| /etc/cron.daily | Each day |
| /etc/cron.weekly | weekly |
| /etc/cron.monthly | Once each month |