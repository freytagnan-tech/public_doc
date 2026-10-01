# Privacy Policy | 隐私政策
**Application Name / 应用名称**: 密码管理器 (VaultGuard 离线版)  
**Package Name / 应用包名**: `com.freytagnan.pwdmanager_local`  
**Effective Date / 生效日期**: October 01, 2026 / 2026年10月01日  
**Version / 版本**: 1.0 (100% Offline Standalone Edition)

---

## 目录 / Table of Contents
1. [中文版隐私政策 (Chinese Version)](#一-中文版隐私政策)
2. [English Privacy Policy (English Version)](#ii-english-privacy-policy)

---

# 一、 中文版隐私政策

### 引言与核心承诺
欢迎使用“密码管理器（VaultGuard 离线版）”（以下简称“本应用”或“我们”）。我们高度尊重并严格保护所有用户的个人隐私与数据安全。
本应用遵循**“完全离线单机架构”（100% Offline Architecture）**、**“零知识证明”（Zero-Knowledge Architecture）**与**“本地硬件级端到端加密”（End-to-End Encryption, E2EE）**设计，从底层操作系统机制彻底杜绝网络外联。本应用及其开发者绝不会收集、存储、上传、共享或出售您的任何个人信息、账户凭据或使用数据。

请在使用本应用前认真阅读本政策全部内容。继续使用本应用即表示您理解并同意本政策关于数据完全本地化、零网络上传和本地加密存储的全部声明。

### 1. 核心原则：零网络通信与物理级沙盒隔离
1. **彻底剥离网络权限**：本应用在 AndroidManifest.xml 清单中通过系统级指令彻底移除了 `android.permission.INTERNET` 与 `android.permission.ACCESS_NETWORK_STATE` 权限。Android 系统将在物理层面阻断本应用发起任何网络请求，本应用不设后端服务器、远程 API 或云数据库。
2. **端到端本地加密**：您录入的所有账号名、密码、2FA 密钥、助记词及三级备注（备注1、备注2、备注3），均在写入前使用 Argon2id 密钥派生函数与 XChaCha20-Poly1305 / AES-256-GCM 高强度加密算法在设备本地加密后存入私有数据库。
3. **主密码绝对私有**：主加密密钥由您设置的主密码派生而来，仅在解锁期间暂存于设备物理安全内存，并受 Android Keystore 硬件安全芯片（TEE / StrongBox）保护，退出锁定后瞬时擦除。任何人（包括开发者）均无法在外部窥探或解密您的数据。

### 2. 个人信息“零收集”说明
在您使用本应用的过程中：
- **不收集身份信息**：不设注册账户，不收集手机号、邮箱、姓名、身份证等个人身份信息；
- **不收集设备标识**：不读取、不收集 IMEI、MEID、Android ID、OAID、MAC 地址或硬件序列号；
- **不收集行为统计**：不记录使用频率、点击轨迹或页面停留时长，无任何行为追踪探针；
- **不收集地理位置**：不申请、不调用 GPS、基站或 Wi-Fi 定位权限；
- **剪贴板安全机制**：复制密码仅用于粘贴，应用支持自动清空剪贴板，且绝不监听或截取外部剪贴板内容。

### 3. 设备系统权限申请与合规使用说明
本应用严格遵循“最小必要原则”向操作系统申请以下权限：
- **生物识别权限（`android.permission.USE_BIOMETRIC`）**：用于提供指纹或面容快速解锁。匹配由 Android 底层安全芯片完成，本应用仅接收校验结果，不接触原始生物特征。
- **相机权限（`android.permission.CAMERA`）**：仅在您主动扫码添加 TOTP 2FA 时调用，图像流在设备内存即时解码后销毁，绝不上传或持久化保存。
- **振动权限（`android.permission.VIBRATE`）**：用于操作成功（复制、扫码）时的即时触感反馈。
- **通知权限（`android.permission.POST_NOTIFICATIONS`）**：仅用于系统通知提示剪贴板安全倒计时或自动保存凭证确认。
- **系统自动填充服务（`AutofillService`）**：遵循 Android 系统规范，在您明确授权并验证指纹后协助填写外部网页或 App 的账密，绝不后台爬取其他应用界面。

### 4. 第三方 SDK 与依赖组件说明
- **零商业/广告/统计 SDK**：应用内彻底移除了所有商业广告 SDK、友盟、Firebase Analytics、TalkingData 等追踪组件及云推送服务。
- **本地算法库**：二维码识别模块（ML Kit / ZXing）完全运行于本地设备 CPU/NPU，离线运行无网络请求。

### 5. 数据的自主掌控、备份与彻底销毁
- **数据自主掌控**：数据仅存放在您设备的私有应用沙盒目录中，用户享有完全掌控权。
- **备份安全警示**：导出明文 CSV 脱离了加密沙盒环境，请妥善保管并在使用后安全粉碎；导出加密备份（.vgvault）受独立保护密码防护。
- **彻底物理销毁**：用户在系统设置中“清除应用数据”或“卸载应用”，操作系统将物理擦除所有数据库文件、密钥缓存与配置，设备无残留。

### 6. 未成年人隐私保护
本应用作为通用离线安全工具，不面向未成年人定向推广，亦无账号系统。建议未成年人在监护人指导下使用。

### 7. 政策更新与联系方式
如本政策随技术实践或法律要求发生变更，最新版本将内置于最新版应用及开源托管页面展示。如有疑问，请通过开源仓库或应用内“关于”页面提交反馈。

---

# II. English Privacy Policy

### Introduction & Core Commitment
Welcome to **VaultGuard (Offline Edition)** (hereinafter referred to as "the Application" or "we"). We are deeply committed to safeguarding your privacy and data security.
The Application is built upon a **100% Offline Standalone Architecture**, **Zero-Knowledge Design**, and **Hardware-Backed End-to-End Encryption (E2EE)**. By design, the Application is physically isolated from the internet by the underlying operating system. The Application and its developers do not collect, store, transmit, share, or sell any of your personal data, credentials, or telemetry.

Please read this Privacy Policy carefully before using the Application. By continuing to use the Application, you acknowledge and agree to this policy regarding local storage, zero network transmission, and local cryptographic isolation.

### 1. Core Principles: Zero-Network Communication & Sandbox Isolation
1. **Network Permissions Completely Removed**: The Application explicitly strips `android.permission.INTERNET` and `android.permission.ACCESS_NETWORK_STATE` from its AndroidManifest.xml. The Android OS blocks the app from making any network socket connections. The Application operates with zero remote servers, cloud databases, or telemetry backends.
2. **Local End-to-End Encryption**: All titles, accounts, passwords, 2FA keys, mnemonic seeds, and three-tier notes (Note 1, Note 2, Note 3) are encrypted on-device prior to database persistence using the **Argon2id** key derivation function and **XChaCha20-Poly1305 / AES-256-GCM** authenticated ciphers.
3. **Zero-Knowledge Key Derivation**: Your Master Encryption Key is derived in-memory solely from your Master Password, protected by the Android Keystore (TEE / StrongBox), and securely cleared from RAM when the app is locked or backgrounded. Neither the developer nor any third party possesses the keys to decrypt your vault.

### 2. Zero-Collection Declaration
During your use of the Application:
- **No Identity Information**: No account registration is required; we never collect phone numbers, emails, names, or identity credentials.
- **No Device Identifiers**: We never read or collect IMEI, MEID, Android ID, OAID, MAC addresses, or serial numbers.
- **No Analytics or Telemetry**: We do not track usage duration, click paths, or user behaviors.
- **No Geolocation Data**: We never request or access GPS, cellular, or Wi-Fi location services.
- **Clipboard Protection**: Copying passwords places text onto the system clipboard for immediate pasting. An automatic clipboard clearing timer is available, and the app never reads foreign clipboard data.

### 3. Operating System Permissions & Lawful Use
The Application requests only the minimal necessary permissions to deliver offline password management:
- **Biometric (`android.permission.USE_BIOMETRIC`)**: Used exclusively for local fingerprint or face unlock. Matching occurs strictly inside the Android hardware security module (TEE); the Application never accesses raw biometric templates.
- **Camera (`android.permission.CAMERA`)**: Used solely when you scan a QR code to import TOTP 2FA tokens. The video stream is processed in volatile memory and immediately discarded.
- **Vibration (`android.permission.VIBRATE`)**: Provides tactile feedback upon successful copy or QR scan.
- **Notifications (`android.permission.POST_NOTIFICATIONS`, Android 13+)**: Displays security reminders (e.g. clipboard wipe countdown, autofill prompts).
- **Autofill Service (`AutofillService`)**: Implements the Android Autofill API to populate credentials into apps and browsers upon user authentication. It never records non-credential screen contents.

### 4. Third-Party SDKs & Modules
- **Zero Commercial / Advertising SDKs**: The Application contains no advertising SDKs, tracking libraries (e.g. Firebase Analytics, Umeng, Adjust), or cloud push SDKs.
- **Local Libraries**: On-device barcode scanning (ML Kit / ZXing) runs offline on the device CPU/NPU without internet connectivity.

### 5. Data Control, Backup & Total Destruction
- **Complete User Ownership**: Vault databases reside inside the application's protected sandbox directory.
- **Backup Caution**: Exporting plaintext CSV removes encryption protection; store plaintext backups in an isolated physical medium. Encrypted backups (`.vgvault`) require your dedicated backup password.
- **Complete Erasure**: Uninstalling the Application or selecting "Clear Data" in Android Settings permanently wipes all local databases and keys from the device storage.

### 6. Children's Privacy
The Application is an offline utility that does not collect data or target minors. We encourage parents and guardians to guide minors in safe credential practices.

### 7. Policy Updates & Contact
Any updates to this Privacy Policy will be bundled directly into updated application packages and public documentation repositories. If you have questions, please submit feedback via our repository or the in-app "About" page.
