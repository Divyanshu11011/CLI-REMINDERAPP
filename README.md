# CLI Reminder

This command-line tool allows users to set reminders for future events or tasks. It displays a notification message at the specified time with the provided text.

## Usage

```bash
go run main.go <hh:mm> <text message>

Replace <hh:mm> with the time in 24-hour format when you want to be reminded.
Replace <text message> with the reminder message.
```
Dependencies
beeep: A cross-platform Go package for sending desktop notifications.
when: A natural language date/time parser in Go.
common and en: English language rules for the when package.
Installation
Before using the tool, make sure to install the required dependencies:

go get -u github.com/gen2brain/beeep
go get -u github.com/olebedev/when

Example
```bash

go run main.go 15:00 "Meeting with client"
This will set a reminder for 3:00 PM with the message "Meeting with client".
```

How it Works
Parses the provided time and text message.
Checks if the parsed time is in the future.
If the time is in the future:
Sets an environment variable as a marker.
Executes itself again with the marker set.
Sleeps until the reminder time.
Displays the reminder notification.
If the time is not in the future:
Prints an error message and exits.
Notes
Ensure that you have appropriate permissions to display notifications on your system.
The notification includes the message provided by the user.
The reminder will be displayed even if the terminal window is closed.
