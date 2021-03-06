# SQL telegram bot

# The purpose
To send and receive messages to/from telegram bot natively with MS SQL server (by stored procedures)

# Prerequsites
* SQL Server 2016 or higher
* Registered Telegram bot [check here](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-telegram?view=azure-bot-service-4.0) via [Bot Father](https://telegram.me/botfather)


# How to install
1. Clone repo ```git clone https://github.com/gleberof/SQL-telegram-bot.git```
2. Run setup.sql (new DB \[telegram\] with all nesessary procedures will be created)
3. Send a message to your bot directly in Telegram (it will help to identify your chat ID). If you're going to use the bot within a group - you need to set up the bot as one of the admins of that group.
4. Open ```Configure.sql```. Set bot_token given by [Bot Father](https://telegram.me/botfather). It will automatically assign chat_id from the last message to the bot or chat.


# How to use
1. Send a message from SQL by ```EXEC [dbo].[usp_SendMessage] @message = N'Hello World!'```
2. Run ```Jobs.sql``` - to enable jobs 
3. Setup commands. 

Please check ```[telegram].[dbo].[commands]``` table to learn how to configure new commands (we setup few during initial [setup](#how-to-install))

![commands](https://github.com/gleberof/SQL-telagram-bot/blob/main/images/command.gif?raw=true)

4. Setup progress bar for backups. It's almost confugured and run by job (please try backup on you server)

![backup2](https://github.com/gleberof/SQL-telagram-bot/blob/main/images/backup2.gif?raw=true)

5. Execute SQL selects. It's almost ready to execute commands - put ```*``` symbol before select.

![select](https://github.com/gleberof/SQL-telagram-bot/blob/main/images/select.gif?raw=true)

6. Setup monitoring. Please check ```[telegram].[monitor].[threshold]``` to change threshold for alerts

# Contacts
Please do not hesitate to address us in case of questions if any: 
* gleberof @ gmail.com
* efremovfedorofficial @ gmail.com
