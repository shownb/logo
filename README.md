# logo
Deutsch lernen

- 在自己的项目中，点上方 Actions 选项卡进入项目 GitHub Actions 页面, 点击绿色按钮 “I understand my workflows, go ahead and enable them” 开启自动提交功能


# secrets.RCLONE_CONF 例子
[OneDrive_local]
type = onedrive
token = {"access_token":"很长","token_type":"Bearer","refresh_token":"很臭","expiry":"2020-02-10T11:32:10.852646+08:00"}
drive_id = b!qDvcsZUTU8eoYyKmtyyP1Jc0D8urZLlkTnH1nWdJ1kbrLsvQZLzVUTpeTrc
drive_type = business

# Getting your own Client ID and Key
You can use your own Client ID if the default (client_id left blank) one doesn't work for you or you see lots of throttling. The default Client ID and Key is shared by all rclone users when performing requests.

If you are having problems with them (E.g., seeing a lot of throttling), you can get your own Client ID and Key by following the steps below:

Open https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade and then click New registration.
Enter a name for your app, choose account type Accounts in any organizational directory (Any Azure AD directory - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox), select Web in Redirect URI, then type (do not copy and paste) http://localhost:53682/ and click Register. Copy and keep the Application (client) ID under the app name for later use.
Under manage select Certificates & secrets, click New client secret. Copy and keep that secret for later use.
Under manage select API permissions, click Add a permission and select Microsoft Graph then select delegated permissions.
Search and select the following permissions: Files.Read, Files.ReadWrite, Files.Read.All, Files.ReadWrite.All, offline_access, User.Read. Once selected click Add permissions at the bottom.
Now the application is complete. Run rclone config to create or edit a OneDrive remote. Supply the app ID and password as Client ID and Secret, respectively. rclone will walk you through the remaining steps.
