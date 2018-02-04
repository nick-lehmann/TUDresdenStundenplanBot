# TUDresdenStundenplanBot

Bot reminding students of their lessons; to used in conjunction with the [Android app](https://github.com/AdrianMunozH/MyApplication).

The bot consists of two parts who are designed to play together:
- MailWatcher: Class that logs into an email account, selects the inboxs and reads new email, checking them for a json attachment. If it discovers a new, unprocessed attachment, it gives it back.
- ReminderBot: Telegram bot accepting timetable configurations received by Mailwatcher and sends reminders to registered telegram users when the reminder is due (time of lesson - 10 minutes)

Checking for new timetable configruations sent via email and sending out the reminders is done in an eventloop implemented using python's networking library `twisted`. The routine is done in a 60s interval to avoid that users get a reminder twice, since the method checking if a reminder has to be sent checks only hour and minute.

If a users wishes to get lessons reminders, he or she needs to do the following steps:
- Install the telegram app and register
- Activate the sync option in the [Android app](https://github.com/AdrianMunozH/MyApplication)
- register with the telegram bot using the command shown in the settings view (`\register device_id`)

Credits:
- [Stackoverflow user mopsiok](https://stackoverflow.com/questions/13663672/get-the-gmail-attachment-filename-without-downloading-it), reading attachment using python imaplib
