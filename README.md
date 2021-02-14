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


# Webhook
给 GitHub API 发送一个 repository dispatch event(仓库调度事件) 请求，当 API 接收到请求后就会触发相应的 work­flow 。  
Web­hook 方式灵活多变，可控性强，对于高阶用户来说是一个利器，甚至可以自己写一个触发脚本、网页或者浏览器插件来实现更高级的功能。

## 创建 token
首先需要创建 Personal access token，权限为 repo 即可。如果你不知道怎么做，可以查看官方文档中的相关介绍。to­ken 会用在 web­hook 的请求标头中，用于身份验证。

## 发送请求
通过 web­hook 来触发 GitHub Ac­tions，以下是一个使用 cURL 发送请求的例子：
### 构建request
{
    "event_type": "my_event_type",
    "client_payload": {
        "example-key": "example-value"
    }
}
那么yaml里面的变量就可以是${{ github.event.client_payload.example-key }}

```bash
curl -X POST https://api.github.com/repos/:owner/:repo/dispatches \
    -H "Accept: application/vnd.github.everest-preview+json" \
    -H "Authorization: token ACTIONS_TRIGGER_TOKEN" \
    --data '构建的request'
```
