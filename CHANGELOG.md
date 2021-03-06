# Changelog

## v2.1.0
* Added typing proxy (https://github.com/Dragory/modmailbot/pull/48):
  * If the `typingProxy` config option is enabled, any time a user is typing to modmail in their DMs, the modmail thread will show the bot as "typing" 
  * If the `typingProxyReverse` config option is enabled, any time a moderator is typing in a modmail thread, the user will see the bot "typing" in their DMs

## v2.0.1
* The link to the current thread's log is no longer posted to the top of the thread. Use `!loglink` instead.

## v2.0.0
* Rewrote large parts of the code to be more modular and maintainable. There may be some new bugs because of this - please report them through GitHub issues if you encounter any!
* Threads, logs, and snippets are now stored in an SQLite database. The bot will migrate old data on the first run.
* Small attachments (<2MB) from users can now be relayed as Discord attachments in the modmail thread with the `relaySmallAttachmentsAsAttachments` config option. Logs will have the link as usual.
* Fixed system messages like pins in DMs being relayed to the thread
* Fixed channels sometimes being created without a category even when `newThreadCategoryId` was set
* Removed timestamps from threads by default. Logs will still have accurate timestamps. Can be re-enabled with the `threadTimestamps` config option.
* Added `!move` command to move threads between categories. Can be enabled with the `allowMove` config option, disabled by default.

## Sep 22, 2017
* Added `newThreadCategoryId` option. This option can be set to a category ID to place all new threads in that category.

## Sep 20, 2017
* Fixed crash when the bot was unable to find or create a modmail thread
* Reduced error log spam in case of network errors from Eris
* Fixed unintended error when a message was ignored due to an "accidental thread" word

## Sep 19, 2017
* Added `logChannelId` option
* Some code clean-up. Please open an issue if you encounter any bugs!
* The bot now throws an error for unknown options in `config.json` (assuming they're typos) and tells you if you haven't configured the token or mail guild id.

## Aug 3, 2017
* Fixed user nicknames not showing in new threads
* The "manageRoles" permission is no longer required to use commands on the inbox server.  
This can be configured with the `inboxServerPermission` config option.

## July 24, 2017
* Commands are now case-insensitive (so !close, !Close, and !CLOSE all work)
* The before/after prefixes in edit notifications are now the same length, making it easier to spot the edited part
* Non-ASCII names should now result in better channel names (not just "unknown")

## May 18, 2017
* Identical edits are now ignored
* New thread notification (with @ here ping) is now posted in the thread instead of the inbox server default channel
* Thread close notifications no longer ping the user who closed the thread
* Received attachments are now only linked once the bot has saved them (should fix embeds)
* Replies now use your nickname, if any
* Several messages are now ignored for thread creation ("ok", "thanks", and similar)
* Logs from !logs are now sorted in descending order (newest first)

## Feb 15, 2017
More info is now available at the beginning of modmail threads.

## Feb 10, 2017
Major rewrite. Includes anonymous replies (!ar), stability improvements, and server greeting feature.
