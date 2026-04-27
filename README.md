# githabdownload

Hello. This bot is used to upload files from Telegram to GitHub. Also, it can receive a direct download link for a file, download it, and upload it to your GitHub, so you can then download it directly from your GitHub repo. 
In short and simple terms:

Here is how it works:
1. We Fork a specific project on GitHub (meaning we create a copy of it in our own account).
2. We configure it once to enable GitHub Actions.
3. After that, whenever we want to download a file:
   - We edit the README.md file.
   - In the commit message, we write: download: <direct_file_link>
4. GitHub itself downloads that file on its servers.
5. The downloaded file is placed inside the downloads/ folder in your repository.
6. Then, we can download the entire repository as a ZIP file to get our file.

Usage:
- Downloading files that cannot be directly accessed with the domestic intranet, especially now that the national internet is in effect.

Note: Since GitHub has storage limits, you may sometimes need to delete the repository and Fork it again.

Now, this Telegram bot performs exactly this process automatically.

Instructions to run the bot on your server:

Note: Inside the bot's code (i.e., the gitwaydownloader.py file), replace the Telegram bot token and your numeric ID in the first few lines of the code.

First, you need to install the prerequisites:
pip install -r requirements.txt

Then, run the bot:
python githabdownload.py

Done.

In-bot guide:
With the /start command, the bot provides the link to the reference repository and asks the user to Fork it. Then, it requests a GitHub Token (PAT). (A default repository link is included).

After sending the GitHub token (PAT), the bot will ask for the repository name where the downloads should be stored (in username/repo format). This refers to one of the repositories in your own account.

By submitting this information, the user's account is connected.

Other commands:

/setup command: 
If a user wants to change/update their token or repository name, they use this command.

/cancel command: 
Stops the operation if the user changes their mind while entering token or repository information.

Sending a file (Upload): 
If a user sends any file (photo, video, document, etc.) to the bot, the bot uploads it to the downloads folder in their GitHub repository and provides its link.

Downloading from a link process: 
The user sends a text link to the bot. The bot makes a commit on the user's README.md file in GitHub with the message download: <link> so that GitHub Actions downloads the file in the background and places it in the repository.

Bot Admin commands:

/stats command:
Shows the total number of users who have registered in the bot (entered their token).

/broadcast <message> command: 
Sends the message you write after this command to all users of the bot as a global broadcast.

/settemplate <new_link> command:
If the URL of the reference repository that you want users to fork changes, you can change the default link in the /start message using this command. (Example: /settemplate https://github.com/newuser/new-sandbox).

Steps to get your GitHub token:

1. Log into your GitHub account.
2. Click on your profile picture in the top right corner and select Settings.
3. In the left menu, scroll down and click on Developer settings.
4. From the left menu, click on Personal access tokens, then Tokens (classic).
5. Click on the Generate new token (classic) button.
6. In the Note section, write a custom name for the token.
7. In the Select scopes section, check the repo box (for full control of private repositories).
8. Scroll down to the bottom of the page and click Generate token.
9. Copy the generated token (this token will only be shown to you this one time).

Important Notes:

Although this bot is designed for public use, please DO NOT use the token of your main GitHub account under any circumstances; there is a risk of getting banned or others gaining access to your account.
If you want to use the project, host and run it on your own server.

Thanks to dear Sarto for this interesting idea.
Please give the project a star to support us.

Telegram Channel:
@eots1
