# logo
Deutsch lernen

- 在自己的项目中，点上方 Actions 选项卡进入项目 GitHub Actions 页面, 点击绿色按钮 “I understand my workflows, go ahead and enable them” 开启自动提交功能


# secrets.RCLONE_CONF 例子
[OneDrive_local]
type = onedrive
token = {"access_token":"很长","token_type":"Bearer","refresh_token":"很臭","expiry":"2020-02-10T11:32:10.852646+08:00"}
drive_id = b!qDvcsZUTU8eoYyKmtyyP1Jc0D8urZLlkTnH1nWdJ1kbrLsvQZLzVUTpeTrc
drive_type = business

# 获取client_id和client_secret
登陆 https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade
应用注册 注册一个名字 注册完会有一个client_id  
证书和密码 --> 新客户端密码 记录下来  
api权限 --> 读和写权限都需要  
再在rclone config授权，完成
