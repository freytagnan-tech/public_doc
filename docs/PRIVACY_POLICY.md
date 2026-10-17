# Privacy Policy | 隐私政策

**Application Name / 应用名称**: 密码管理器 (密码保险箱 / VaultGuard 离线版)  
**Package Name / 应用包名**: `com.freytagnan.pwdmanager_local`  
**Effective Date / 生效日期**: October 01, 2026 / 2026年10月01日  
**Version / 版本**: 1.0 (100% Offline Standalone Edition / 纯离线单机版)

---

## 目录 / Table of Contents
1. [中文版隐私政策 (Chinese Version)](#一-中文版隐私政策)
2. [English Privacy Policy (English Version)](#ii-english-privacy-policy)

---

# 一、 中文版隐私政策

### 【引言与特别提示】
欢迎使用密码管理器（以下简称“本应用”或“我们”）。
本应用是一款专为极致数据安全而设计的“完全离线单机工具”。我们遵循“零知识架构”（Zero-Knowledge Architecture）与“隐私设计”（Privacy by Design）原则，从底层彻底杜绝任何网络通信。在技术层面，本应用不申请、不包含、亦无法使用任何操作系统网络权限，本应用及其开发者绝不会收集、存储、上传、共享或出售您的任何个人数据、账户密码或敏感凭证。

请在使用本应用前认真阅读并充分理解本《隐私政策》。您开始使用或继续使用本应用，即表示您理解并认可本政策中关于数据完全本地化、零网络上传和本地加密存储的全部声明。

### 一、 核心原则：零网络通信与物理级沙盒隔离
1. **彻底禁用网络权限**：
   本应用在 Android 系统的程序清单（AndroidManifest.xml）中，已通过系统级指令彻底剥离了网络权限（`android.permission.INTERNET` 及 `android.permission.ACCESS_NETWORK_STATE`）。Android 系统底层机制将阻断本应用发起任何网络请求，本应用不存在任何后端服务器、API 接口、云端数据库或远程中继服务。
2. **零知识与端到端本地加密**：
   您在本应用中存储的所有账户名、登录密码、TOTP/2FA 双重身份验证密钥、安全备忘及助记词，均在录入瞬间使用硬件级与工业级强密码学算法（Argon2id 密钥派生函数、XChaCha20-Poly1305 / AES-256-GCM 高强度对称加密）于设备本地加密后写入本地私有数据库（SQLite / Room）。
3. **密钥不落地**：
   用于解密主数据库的主加密密钥（Master Key）完全由您设置的主密码派生而来，仅在您解锁应用期间暂存于设备物理安全内存，并受 Android Keystore 硬件安全模块（TEE/StrongBox）保护。应用退出、超时锁定或进程终止后，解密密钥将立即从内存中进行安全擦除。除了掌握主密码的您本人外，任何第三方（包括开发者本身）均无法解密或窥探您的真实数据。

### 二、 个人信息“零收集”说明
在您使用本应用的过程中：
1. **不收集身份与账户信息**：我们不要求您注册个人账户，不收集您的手机号码、电子邮箱、姓名、身份证号等任何个人身份信息。
2. **不收集设备唯一标识符**：我们不读取亦不收集任何 IMEI、MEID、Android ID、OAID、MAC 地址、IMSI 或硬件序列号。
3. **不收集行为与日志信息**：我们不记录您的使用频率、点击习惯、停留时长或页面浏览轨迹。
4. **不收集位置信息**：我们不申请亦不使用任何 GPS、基站或 Wi-Fi 定位信息。
5. **剪贴板保护机制**：当您在应用内点击“复制密码”时，数据仅写入系统剪贴板以方便您粘贴使用。应用支持定时自动清空剪贴板机制，且应用绝不后台监听或截取您剪贴板中的外部数据。

### 三、 设备权限申请与合规使用范围
为了在完全离线的前提下为您提供便捷的安全凭证管理功能，本应用仅在特定功能场景下遵循“最小必要原则”向操作系统申请以下权限：
1. **生物识别权限（`android.permission.USE_BIOMETRIC`）**：
   - 使用场景：用于提供指纹或面容快速解锁本地密码库的功能。
   - 安全保护：生物识别匹配完全由 Android 系统底层安全硬件（TEE / 独立安全芯片）完成，本应用仅接收系统返回的认证结果，绝不触碰、获取或存储您的任何原始生物特征数据。
2. **相机权限（`android.permission.CAMERA`）**：
   - 使用场景：仅在您主动使用“扫描二维码”功能添加 2FA 双重验证密钥或识别扫码数据时调用。
   - 安全保护：图像流在设备本地内存中通过离线图像算法解析，解析完成后立即释放，本应用绝不保存、录制、截取或上传任何相机画面。
3. **振动权限（`android.permission.VIBRATE`）**：
   - 使用场景：用于在扫描成功、复制成功或长按操作时向您提供即时触觉反馈。
4. **系统通知权限（`android.permission.POST_NOTIFICATIONS`，Android 13+）**：
   - 使用场景：仅用于显示剪贴板安全倒计时、自动保存新凭证确认提示或后台超时锁定通知。
5. **系统自动填充服务（`AutofillService`）**：
   - 使用场景：用于在您浏览外部网页或登录其他应用程序时，依照您的指令协助填写对应的账号与密码。
   - 安全保护：每次填充均需通过您的生物识别或主密码校验，本应用严格遵循 Android 系统规范，绝不后台爬取或保存其他应用的非凭据页面内容。

### 四、 第三方 SDK 与依赖组件说明
1. **零商业/广告/统计 SDK**：
   本应用完全移除了所有商业推广 SDK、广告投放 SDK、用户行为分析 SDK（如友盟、Firebase Analytics、TalkingData 等）以及云推送服务。
2. **本地算法依赖**：
   本应用采用的 ML Kit 离线二维码识别模块与 Android Jetpack 基础库均以纯本地离线模式工作，不依赖任何外部云端计算或通信服务。
3. **零第三方数据共享**：
   由于本应用不收集任何数据且无联网通道，因此不存在向任何商业合作伙伴、广告商、关联方或第三方共享、转让或公开披露您数据的可能性。

### 五、 数据的自主控制、备份与彻底销毁
1. **数据完全自主掌控**：
   所有凭据数据均完整存放于您设备的私有应用沙盒目录中。您拥有对自己数据的完全掌控权，可随时在应用内进行修改、新增或删除。
2. **本地导出与备份安全**：
   - 当您使用本应用导出的明文 CSV 格式时，该文件脱离了本应用的加密沙盒环境，极易被其他具备存储权限的应用读取。请务必将导出文件存放于安全介质，并在使用后立即粉碎删除。
   - 当您使用加密备份格式（.vgvault 等）时，文件由强密码加密保护，请妥善保管备份密钥。
3. **数据的彻底销毁**：
   当您在系统设置中执行“清除应用数据”或“卸载本应用”时，操作系统将物理清除本应用私有沙盒下的全部数据库文件、加密密钥缓存及首选项配置，设备上将不残留任何历史明文或密文信息。

### 六、 未成年人个人信息保护
本应用作为通用的本地离线加密工具，不针对未成年人定向推广，亦不设账户注册系统。我们倡导未成年人在法定监护人的指导下使用本应用，以保护个人数字资产安全。

### 七、 隐私政策的更新与公布
随着操作系统的技术升级或国家法律法规的最新要求，我们可能会对本隐私政策进行修订。由于本应用不具备联网推送能力，任何政策更新都将随应用版本发布完整打包于应用内部，您可随时在“关于”或“设置”界面中查阅最新版本。

### 八、 联系我们
如果您对本《隐私政策》、数据安全或本地离线机制有任何疑问、意见或建议，您可以通过应用内“关于”页面提供的开发者信息与我们取得沟通。

---

# II. English Privacy Policy

### [INTRODUCTION & CORE STATEMENT]
Welcome to Password Manager (VaultGuard Offline Edition, hereinafter referred to as "the Application" or "we").
The Application is a "100% offline standalone utility" engineered specifically for extreme data privacy and security. We adhere to the principles of "Zero-Knowledge Architecture" and "Privacy by Design", physically preventing any network transmission at the lowest operating system level. Technically, the Application neither requests, includes, nor is capable of utilizing any operating system network permissions. The Application and its developer will never collect, store, transmit, upload, share, or sell any of your personal data, account passwords, or sensitive credentials.

Please read and fully understand this Privacy Policy before using the Application. Your installation, access, or continued use of the Application signifies your complete acceptance of and agreement with all statements herein regarding complete data localization, zero network upload, and hardware-backed local encrypted storage.

### 1. Core Principles: Zero Network Communication & Physical-Level Sandbox Isolation
1. **Absolute Removal of Network Permissions**:
   In the Android application manifest (AndroidManifest.xml), network permissions (`android.permission.INTERNET` and `android.permission.ACCESS_NETWORK_STATE`) have been stripped using system-level build directives. The underlying Android operating system physically blocks the Application from initiating any network connection. The Application has no backend servers, API endpoints, cloud databases, or remote relay services.
2. **Zero-Knowledge & Local End-to-End Encryption**:
   All account names, login passwords, TOTP/2FA dual-authentication secret keys, secure notes, and mnemonic recovery phrases you store in this Application are encrypted locally on the device at the moment of entry using hardware-grade and industrial-strength cryptographic algorithms (Argon2id key derivation function, XChaCha20-Poly1305 / AES-256-GCM authenticated symmetric encryption) before being persisted to the private local database (SQLite / Room).
3. **Encryption Keys Never Stored in Plaintext**:
   The Master Encryption Key used to decrypt the database is derived entirely from your user-created Master Password. It resides only temporarily in volatile secure RAM while the app is unlocked and is protected by the Android Keystore hardware security module (TEE/StrongBox). When the app exits, locks due to timeout, or the process terminates, the decryption key is immediately and securely wiped from RAM. No third party (including the developer) can ever decrypt or view your real data.

### 2. "Zero-Collection" Personal Data Declaration
During your use of this Application:
1. **No Identity or Account Collection**: We do not require you to create or register an account; we never collect your phone number, email address, legal name, government ID, or any other personal identity credentials.
2. **No Unique Device Identifiers**: We neither access nor collect IMEI, MEID, Android ID, OAID, MAC address, IMSI, or hardware serial numbers.
3. **No Behavior or Telemetry Logs**: We do not record your usage frequency, click patterns, dwell time, or screen navigation history.
4. **No Geolocation Data**: We do not request or utilize GPS, cell tower, or Wi-Fi positioning services.
5. **Clipboard Protection Mechanism**: When you tap "Copy Password" inside the app, the data is placed onto the system clipboard solely for your convenience in pasting. The app supports automatic timed clipboard clearing and never monitors or intercepts foreign clipboard contents in the background.

### 3. System Permissions & Minimal Privilege Scope
To deliver secure offline credential management while remaining 100% disconnected from the internet, the Application requests only minimal necessary permissions strictly when invoked by specific user actions:
1. **Biometric Authentication (`android.permission.USE_BIOMETRIC`)**:
   - Usage Scenario: Provides biometric fingerprint or face unlock for fast vault access.
   - Security Protection: Biometric matching is handled entirely by Android's hardware security enclave (TEE / dedicated security chip). The Application only receives the authentication result and never touches, accesses, or stores raw biometric templates.
2. **Camera Permission (`android.permission.CAMERA`)**:
   - Usage Scenario: Invoked only when you actively use the "Scan QR Code" feature to add 2FA authentication keys or decode QR data.
   - Security Protection: Video frames are decoded strictly in local device RAM using offline image processing algorithms and immediately released. The app never saves, records, captures, or uploads camera images.
3. **Vibration Permission (`android.permission.VIBRATE`)**:
   - Usage Scenario: Provides immediate tactile haptic feedback upon successful scan, copy, or long-press operations.
4. **Notification Permission (`android.permission.POST_NOTIFICATIONS`, Android 13+)**:
   - Usage Scenario: Used strictly to show security notifications such as clipboard clear countdowns, auto-save credential prompts, or timeout locking alerts.
5. **System Autofill Service (`AutofillService`)**:
   - Usage Scenario: Assists you in populating credentials into external browsers or applications upon your direct confirmation and authentication.
   - Security Protection: Each autofill operation requires biometric or master password verification. Adhering strictly to Android system standards, the app never scrapes or retains screen contents from third-party apps.

### 4. Third-Party SDK & Dependency Declarations
1. **Zero Commercial / Ad / Tracking SDKs**:
   The Application is completely free of commercial advertising SDKs, ad trackers, analytics SDKs (such as Umeng, Firebase Analytics, TalkingData), and cloud push services.
2. **Local Algorithm Dependencies**:
   The ML Kit offline QR recognition module and Android Jetpack libraries run strictly in local offline mode without requiring external cloud computing or network communication.
3. **Zero Third-Party Data Sharing**:
   Because the Application collects no data and lacks network capabilities, it is physically impossible to share, transfer, or disclose your data to business partners, advertisers, affiliates, or third parties.

### 5. Data Self-Sovereignty, Backup & Complete Destruction
1. **Complete Data Sovereignty**:
   All credential data is stored entirely in your device's private sandbox directory. You maintain full ownership and control over your data, with complete freedom to modify, create, or delete entries at any time.
2. **Local Export & Backup Security**:
   - When you export unencrypted CSV files, they leave the app's encrypted sandbox environment and become accessible to other apps with storage permissions. Please store plaintext exports on secure media and wipe them immediately after use.
   - When you export encrypted backup files (.vgvault), they are protected with dedicated backup encryption passwords. Please safeguard your backup credentials carefully.
3. **Complete Physical Destruction**:
   When you select "Clear App Data" or "Uninstall" in Android system settings, the operating system physically deletes all database files, cryptographic keys, and preference configurations in the private sandbox. No plaintext or ciphertext residual traces remain on the device.

### 6. Children's Privacy Protection
As a general-purpose local offline utility, this Application does not target or market to minors and maintains no account system. We encourage parents and legal guardians to instruct minors on safe credential management practices.

### 7. Privacy Policy Updates & Notice
We may update this Privacy Policy to reflect operating system updates or changing legal requirements. Because the Application has no online push capabilities, policy updates will be bundled within updated software distributions. You can review the latest version at any time in the "About" or "Settings" sections.

### 8. Contact Us
If you have any questions, comments, or suggestions regarding this Privacy Policy, data security, or our offline mechanisms, please contact us using the developer information provided on the "About" page within the Application.
