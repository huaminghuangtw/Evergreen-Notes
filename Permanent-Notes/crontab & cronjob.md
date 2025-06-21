---
created: 2024-12-17T15:19:46
modified: 2025-06-21T09:56:04
---

# `crontab` v.s `cronjob`

**Crontab** stands for “cron table.” It is a Unix-based utility that provides a configuration file used by the **cron daemon** (`crond`), the background process that runs scheduled, automated tasks. The crontab file stores a list of cron jobs—each line represents a separate cron job.

A **cron job** is an individual task (e.g., running scripts, executing commands, etc.) specified/defined in the crontab file.

# Crontab Commands

* View current crontab entries:

	```bash
	crontab -l
	```

* Edit the crontab file:

	```bash
	crontab -e
	```

* Remove all crontab entries:

	```bash
	crontab -r
	```

# Cronjob Format

```bash
* * * * * command_to_execute
- - - - -
| | | | |
| | | | +----- Day of the week (0–7, where 0 or 7 is Sunday, 1 is Monday, etc.)
| | | +------- Month (1-12)
| | +--------- Day of the month (1-31)
| +----------- Hour (0-23)
+------------- Minute (0-59)
```

## Special Characters

* `*`: Match all possible values
* `,`: Separate multiple values
* `-`: Specify a range of values
* `/`: Specify step values

### Examples

* Run a script every minute:

	```bash
	* * * * * /path/to/script.sh
	```

* Run every hour:

	```bash
	0 * * * * /path/to/script.sh
	```

* Run daily at midnight:

	```bash
	0 0 * * * /path/to/script.sh
	```

* Run at 10:00, 12:00, and 14:00 every day:

	```bash
	0 10,12,14 * * * /path/to/script.sh
	```

* Run every Monday and Friday at 3:30 PM:

	```bash
	30 15 * * 1,5 /path/to/script.sh
	```

* Run every hour between 9 AM and 5 PM:

	```bash
	0 9-17 * * * /path/to/script.sh
	```

* Run every day from the 1st to the 15th of the month at midnight:

	```bash
	0 0 1-15 * * /path/to/script.sh
	```

* Run every 5 minutes:

	```bash
	*/5 * * * * /path/to/script.sh
	```

* Run every 2 hours:

	```bash
	0 */2 * * * /path/to/script.sh
	```

* Run every other day:

	```bash
	0 0 */2 * * /path/to/script.sh
	```

* Run every 5 minutes during working hours (9 AM to 5 PM):

	```bash
	*/5 9-17 * * * /path/to/script.sh
	```

* Run at 12:15 PM every Monday, Wednesday, and Friday:

	```bash
	15 12 * * 1,3,5 /path/to/script.sh
	```

* Run on the 1st and 15th of every month at midnight:

	```bash
	0 0 1,15 * * /path/to/script.sh
	```

## Special Strings

* **@reboot**: Run once, at startup:

	```bash
	@reboot /path/to/script.sh
	```

* **@daily** or **@midnight**: Run daily at midnight:

	```bash
	@daily /path/to/script.sh
	```

* **@hourly**: Run every hour:

	```bash
	@hourly /path/to/script.sh
	```

* **@weekly**: Run every Sunday at midnight:

	```bash
	@weekly /path/to/script.sh
	```

* **@monthly**: Run on the 1st of the month at midnight:

	```bash
	@monthly /path/to/script.sh
	```

* **@yearly** or **@annually**: Run on January 1st at midnight:

	```bash
	@yearly /path/to/script.sh
	```
