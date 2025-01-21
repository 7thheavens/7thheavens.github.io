[Vultr](https://bit.ly/bewildcard) 的 VPS 云服务器因其按小时计费、全球 20 多个机房以及相对低廉的价格，受到许多用户的青睐。然而，由于 Vultr 是国外商家，且网站为英文界面，国内用户在操作时可能会遇到一些不便。本文将为您详细讲解 Vultr 的购买、使用及登录教程。

## Vultr 的优缺点

在开始教程之前，我们先简单分析一下 Vultr 的优缺点，帮助新手用户更好地了解是否适合自己：

- **优点**：
  - 按小时计费，灵活性高。
  - 全球 20 多个机房，覆盖范围广。
  - 支持多种支付方式，包括支付宝。
  - 新用户支持一个月无理由退款。

- **缺点**：
  - 国内访问速度较慢，线路未针对中国优化。
  - 晚高峰期部分机房丢包率较高。

如果您对速度要求较高，可以考虑其他服务商，例如搬瓦工（BandwagonHost）。

---

## 创建 Vultr 账号

1. 访问 [Vultr 官网](https://bit.ly/bewildcard)。
2. 输入邮箱和密码注册账号。密码需包含至少一个大写字母、一个小写字母，且长度不少于 10 位。
3. 注册后，前往邮箱完成验证。如果未收到邮件，请检查垃圾邮件或更换邮箱重新注册。

![创建 Vultr 用户](https://zhidao91.oss-cn-shanghai.aliyuncs.com/Content/2022/2022-11-28/1.jpg)

---

## 充值账户余额

1. 登录 Vultr 后，点击左侧菜单中的 **Billing**。
2. 选择支付方式（推荐使用支付宝或 PayPal），充值至少 10 美元。
3. Vultr 提供 100 美元试用金，但需充值后才能激活。

![增加 Vultr 账户余额](https://zhidao91.oss-cn-shanghai.aliyuncs.com/Content/2022/2022-11-28/2.jpg)

---

## 创建 VPS

1. 充值完成后，点击左侧菜单中的 **Products**，然后点击右上角的 “+” 按钮。
2. 选择 **Cloud Compute**（普通建站用户推荐）或 **High Frequency**（性能更高）。
3. 选择机房位置：
   - 日本和韩国机房延迟较低，但晚高峰期可能丢包。
   - $2.5/月方案仅支持 IPv6，$3.5/月方案支持 IPv4。
4. 选择操作系统：
   - 推荐 **CentOS 7 x64**，文档资料丰富。
   - Windows 系统需额外支付 License 费用，不推荐。
5. 配置完成后，点击 **Deploy Now** 创建服务器。

![创建 Vultr 服务](https://zhidao91.oss-cn-shanghai.aliyuncs.com/Content/2022/2022-11-28/3.jpg)

---

## 管理 Vultr VPS

1. 在 **Products** 页面，点击服务器名称进入管理界面。
2. 在 **Overview** 中查看服务器的 IP 地址、用户名和密码。
3. 使用 SSH 工具（如 Xshell 或 Putty）连接服务器。

![Vultr VPS 管理](https://zhidao91.oss-cn-shanghai.aliyuncs.com/Content/2022/2022-11-28/10.jpg)

---

## 销毁 Vultr VPS

1. 如果分配的 IP 无法使用，可通过销毁服务器来更换 IP。
2. 点击右侧的 **Server Destroy**，勾选确认选项后销毁服务器。
3. 注意：销毁后数据将被清空，且暂停服务不会停止计费，只有销毁服务才能停止计费。

![Vultr VPS 销毁](https://zhidao91.oss-cn-shanghai.aliyuncs.com/Content/2022/2022-11-28/11.jpg)

---

## 登录 Vultr VPS

1. 使用管理界面提供的 IP、端口、用户名和密码，通过 Xshell 登录服务器。
2. 登录后即可根据需求搭建服务。

---

## 注意事项

- Vultr 的 IP 容易被封。如果分配的 IP 无法访问中国大陆地区，可销毁服务并重新创建，直到获得可用的 IP。
- 可使用工具 [IPChecker](https://bit.ly/bewildcard) 检测 IP 是否被封。

---

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)