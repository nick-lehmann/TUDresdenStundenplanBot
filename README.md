# TUDresdenStundenplanBot

Bot reminding students of their lessons; to used in conjunction with the [Android app](https://github.com/AdrianMunozH/MyApplication).

The bot consists of two parts who are designed to play together:
- MailWatcher: Class that logs into an email account, selects the inboxs and reads new email, checking them for a json attachment. If it discovers a new, unprocessed attachment, it gives it back.
- ReminderBot: Telegram bot accepting timetable configurations received by Mailwatcher and sends reminders to registered telegram users

Credits:
-[Stackoverflow user mopsiok](https://stackoverflow.com/questions/13663672/get-the-gmail-attachment-filename-without-downloading-it), reading attachment using python imaplib
