# 将羽毛球明星2048游戏上传到网站空间指南

## 准备工作

### 1. 您需要的条件
- 一个网站空间（虚拟主机、VPS或云服务器）
- 网站空间的访问信息（FTP账号、控制面板账号等）
- 基本的文件管理知识

### 2. 准备游戏文件
确保您拥有以下文件：
- `index_final.html` - 游戏主文件
- `index_simple.html` - 简化版游戏（可选）
- `SHARE_GUIDE.md` - 分享指南（可选）
- `SHARE_GUIDE_SIMPLE.html` - 简化版分享指南（可选）
- `README.md` - 游戏说明文档（可选）

## 方法一：使用FTP客户端上传（推荐）

### 1. 下载并安装FTP客户端
推荐使用以下免费FTP客户端：
- [FileZilla](https://filezilla-project.org/) (Windows, macOS, Linux)
- [Cyberduck](https://cyberduck.io/) (macOS, Windows)
- [WinSCP](https://winscp.net/) (Windows)

### 2. 连接到您的网站空间
打开FTP客户端后，输入您的网站空间信息：
- **主机名/服务器地址**：通常是您的域名（如 example.com）或服务器IP地址
- **端口**：默认为21（如果是SFTP则为22）
- **用户名**：您的FTP账号用户名
- **密码**：您的FTP账号密码

点击"连接"按钮。

### 3. 上传游戏文件
连接成功后，您会看到两个面板：
- 左侧：您的电脑文件
- 右侧：您的网站空间文件

**操作步骤**：
1. 在左侧面板中，找到存放游戏文件的文件夹（`html_artifact`）
2. 在右侧面板中，找到您网站的根目录（通常名为 `public_html`, `www`, `htdocs` 或您的域名）
3. 将左侧的游戏文件拖拽到右侧的网站根目录中
4. 等待文件上传完成（底部会显示进度）

### 4. 验证上传
上传完成后，在右侧面板中确认文件已成功上传。

## 方法二：使用网站控制面板上传

### 1. 登录到您的网站控制面板
通常您的主机提供商会给您一个控制面板地址（如 cpanel.example.com），使用您的账号密码登录。

### 2. 找到文件管理工具
不同控制面板的名称可能不同：
- **cPanel**: "文件管理器"
- **Plesk**: "文件"
- **DirectAdmin**: "文件管理器"
- **其他面板**: 通常会有类似"文件管理"的功能

### 3. 上传文件
**操作步骤**：
1. 进入网站根目录（通常是 `public_html` 或类似名称）
2. 点击"上传"按钮
3. 选择您电脑上的游戏文件（可以先将所有文件压缩为ZIP，上传后再解压）
4. 如果上传的是ZIP文件，找到并点击"解压"按钮

### 4. 创建游戏文件夹（可选）
如果您想将游戏放在单独的文件夹中：
1. 点击"新建文件夹"按钮
2. 命名文件夹（如 `badminton2048`）
3. 进入新建的文件夹
4. 上传游戏文件到这个文件夹中

## 方法三：使用命令行工具（适合高级用户）

### 1. 使用SCP命令（适用于Linux/macOS）
打开终端，运行以下命令：
```bash
# 单个文件上传
scp /path/to/your/local/file.html username@yourdomain.com:/path/to/your/website/

# 整个文件夹上传
scp -r /path/to/your/local/html_artifact username@yourdomain.com:/path/to/your/website/
```

### 2. 使用rsync命令（适用于Linux/macOS）
```bash
rsync -avz /path/to/your/local/html_artifact/ username@yourdomain.com:/path/to/your/website/badminton2048/
```

### 3. 使用PuTTY的pscp（适用于Windows）
```bash
pscp -r C:\path\to\your\local\html_artifact username@yourdomain.com:/path/to/your/website/
```

## 访问上传后的游戏

### 1. 基本访问
如果您将文件上传到网站根目录：
- 主游戏：`http://yourdomain.com/index_final.html`
- 简化版：`http://yourdomain.com/index_simple.html`

### 2. 如果您创建了单独的文件夹
- 主游戏：`http://yourdomain.com/badminton2048/index_final.html`
- 简化版：`http://yourdomain.com/badminton2048/index_simple.html`

### 3. 测试分享功能
上传完成后，测试分享功能是否正常工作：
1. 打开游戏页面
2. 点击"分享游戏到手机"按钮
3. 确认二维码能正常显示
4. 扫描二维码或复制链接，测试是否能在其他设备上访问

## 常见问题解决

### 问题1：上传后无法访问游戏
- 检查文件路径是否正确
- 确保文件权限设置正确（通常为644）
- 检查是否有拼写错误

### 问题2：二维码无法生成或扫描后无法访问
- 确保您的网站使用的是HTTP或HTTPS协议（不是本地文件）
- 检查URL是否正确
- 确保服务器支持JavaScript

### 问题3：游戏资源加载失败
- 检查浏览器控制台是否有错误
- 确认所有资源文件都已正确上传
- 检查文件路径是否正确

### 问题4：分享链接显示为本地路径（file://）
- 这是因为您在本地测试，没有上传到网站空间
- 上传到网站空间后，链接会自动变为您的网站URL

## 推荐的网站空间提供商

如果您还没有网站空间，可以考虑以下提供商：

### 国内提供商
- [阿里云](https://www.aliyun.com/)
- [腾讯云](https://cloud.tencent.com/)
- [华为云](https://www.huaweicloud.com/)
- [西部数码](https://www.west.cn/)

### 国外提供商
- [Bluehost](https://www.bluehost.com/)
- [SiteGround](https://www.siteground.com/)
- [HostGator](https://www.hostgator.com/)
- [DreamHost](https://www.dreamhost.com/)

## 进阶：绑定自定义域名

如果您有自己的域名，可以将其绑定到您的网站空间：
1. 在您的域名管理平台，将域名解析到您的网站空间IP地址
2. 在您的网站控制面板中，添加并绑定您的域名
3. 等待DNS解析生效（通常需要几分钟到几小时）

## 总结

上传游戏到网站空间的基本步骤：
1. 准备好所有游戏文件
2. 使用FTP客户端、控制面板或命令行工具上传文件
3. 测试游戏是否能正常访问
4. 测试分享功能是否正常工作

上传完成后，您就可以通过您的网站域名分享游戏了！
