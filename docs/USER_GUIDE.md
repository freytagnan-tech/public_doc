# VaultGuard / 密码保险箱
## 软件介绍与官方使用说明书 | Software Introduction & User Manual
*(Version: 1.0 Offline Edition | Package: com.freytagnan.pwdmanager_local)*

---

# 📖 中文版说明书 (Chinese Edition)

## 一、 软件定位与核心理念

**VaultGuard（密码保险箱 - 离线版）** 是一款专为极致隐私和数据主权而设计的**纯本地单机高安全密码与两步验证（2FA/TOTP）管理器**。

在云端泄露事件与第三方数据收集日益频繁的今天，VaultGuard 坚持**“物理零网络（Zero-Network）”**与**“零知识证明（Zero-Knowledge）”**架构：
- **物理切断网络**：应用在操作系统底层清单中彻底剔除并阻断了 `android.permission.INTERNET` 与 `android.permission.ACCESS_NETWORK_STATE` 网络权限，无任何后台服务器、无远程 API、无分析追踪代码。
- **本地硬件加密**：主加密密钥由用户自主掌握的主密码通过 **Argon2id** 算法派生，并在设备安全硬件芯片（Android Keystore / TEE / StrongBox）保护下对所有数据进行 **XChaCha20-Poly1305 / AES-256-GCM** 工业级强加密。
- **全主权数据掌控**：所有数据均只保留在您手持设备的本地加密数据库中，除了掌握主密码的您本人，任何人（包括开发者）都无法解密或窥探。

---

## 二、 核心功能特性

1. **四维凭据类型支持**：
   - **常规账号密码**：支持标题、登录用户名/邮箱、安全密码以及专属的 3 项自定义备注（**备注1**、**备注2**、**备注3**）。
   - **API 密钥与服务 Token**：专为开发者与极客设计，便捷管理 OpenAI、AWS、GitHub、云服务器等各种生产 API 密钥与端点。
   - **密保助记词（Mnemonic Phrases）**：安全存储区块链钱包、加密资产的 12/24 位英文助记词，支持自动切词分块卡片展示。
   - **两步动态验证码（TOTP/2FA）**：基于 RFC 6238 标准的 30 秒动态令牌发生器，支持毫秒级时间进度圆环、一键复制验证码、相机直接扫码与相册图片解析导入。
2. **高熵密码生成器**：
   - 内置伪随机高熵生成引擎，支持大写字母、小写字母、数字及特殊符号组合。
   - 支持自定义密码长度（最长 64 位），并提供实时比特熵（Entropy bits）与安全评级评估。
3. **Android 系统级自动填充（Autofill Service）**：
   - 无缝集成 Android 原生自动填充框架，在浏览器或常用 App 登录时，经生物识别或主密码授权后秒级填入凭据，免去频繁手动复制切换。
4. **灵活的双轨备份与灾备**：
   - **加密数据库备份**：导出受独立安全保护密码保护的 `.vgvault` 加密备份文件，可在新设备上安全恢复。
   - **通用 CSV 导入导出**：支持与 Chrome、Bitwarden、KeePass 等工具无缝兼容的 CSV 数据互导。
5. **生物识别快速解锁**：
   - 兼容设备指纹与面容解锁（BiometricPrompt），既保障最高安全，又兼顾日常解锁便利。

---

## 三、 详细使用操作指南

### 1. 首次初始化保险箱
1. 下载并安装安装包后打开应用，系统将展示“开启您的加密空间”初始化界面。
2. **设置主密码**：主密码是保护您本地所有资产的唯一钥匙。
   - 必须满足安全合规性要求：**长度至少 10 位**，必须同时包含**大写字母、小写字母、数字以及特殊符号**，且不得包含空格。
3. **再次确认主密码**：确保两次输入的密码完全一致。
4. **勾选同意条款**：阅读《用户服务协议》与《隐私政策》后勾选同意。
5. 点击 **“生成加密数据库”**，系统将利用 Argon2id 派生数据加密密钥（DEK）并建立本地强加密 SQLite 数据库。
> **⚠️ 核心警示**：由于本应用采用纯本地零知识架构，没有云端服务器，**主密码一旦遗失将永久无法找回或重置！请务必牢记您的主密码，建议将其抄写在纸质离线介质上安全存放。**

### 2. 日常解锁与生物识别
- **密码解锁**：输入初始化时设置的主密码，点击“解锁保险箱”。
- **生物识别解锁**：在应用设置中开启“生物识别快速解锁”后，每次打开应用可直接通过指纹或面容识别一秒解锁。
- **即时锁定**：在“我的/设置”页面点击“锁定保险箱”，或将应用退到后台超时后，应用将自动清除解密内存并锁定。

### 3. 添加与管理凭据
1. 在主界面右下角点击悬浮添加按钮 **“+”** 打开新增弹窗。
2. **选择凭据类型**：常规存储密码、API 密钥、密保助记词、或两步动态验证码 (TOTP)。
3. **输入字段**：
   - **标题**：如应用名、网站名称（如：GitHub、微信、阿里云）。
   - **账户标识**：登录用户名、手机号或邮箱地址。
   - **密码/秘钥**：可手动输入，或点击 **“🎲 一键生成”** 自动派生 16 位高强度密码。
   - **三级自定义备注**：
     - **备注1**：可填写官方网址、登录入口或主域名；
     - **备注2**：可填写关联备用网址、备选服务或备忘描述；
     - **备注3**：可填写密保问题答案、交易 PIN 码、恢复手机等附加敏感信息。
4. 点击 **“保存新记录”**，数据即刻完成强加密存入本地数据库。

### 4. 两步验证码（TOTP）的导入与使用
- **扫码添加**：在添加 TOTP 时，切换至“扫码识别密钥”标签，可直接使用系统相机扫描第三方网站提供的二维码，或点击“🖼️ 从相册导入图片”自动识别。
- **手动输入**：亦可手动填入 Base32 格式的密钥字符串。
- **日常查看**：在底部导航切换至“验证”标签页，动态口令每 30 秒自动刷新，点击验证码即可一秒复制到剪贴板。

### 5. 系统自动填充配置与使用
1. 打开系统“设置” $\rightarrow$ “系统” $\rightarrow$ “语言和输入法” $\rightarrow$ “自动填充服务”。
2. 选择本应用（**安全密码箱自动填充**）。
3. 当您在任意网页或 App 的登录界面点击账号或密码输入框时，键盘上方将弹出自动填充提示，点击后验证指纹或主密码，即可自动填入凭证。

### 6. 数据备份、导出与换机迁移
- **加密备份恢复（推荐换机使用）**：
  1. 进入“我的”页面 $\rightarrow$ 找到“加密数据库备份与恢复”；
  2. 点击 **“导出加密备份”**，为当前备份设置一个专用的备份保护密码，保存生成的 `.vgvault` 加密文件；
  3. 在新设备上安装本应用，点击 **“导入加密备份”**，输入备份密码，即可无缝还原所有数据。
- **明文 CSV 导入导出**：
  - 点击“明文密码导出”，可生成通用 CSV 文件用于在电脑或其他密码管理软件中查看或迁移。
  - *注意：导出的 CSV 文件为明文存储，请务必在安全环境下操作并在转移后立即粉碎删除。*

---

## 四、 常见问题解答 (FAQ)

**Q1：应用是否真的不需要任何网络？**  
**A**：是的。本应用完全移除了 Android 系统的网络权限（`android.permission.INTERNET`）。无论手机是否开启 Wi-Fi 或移动蜂窝数据，操作系统底层都会物理禁止本应用发起任何网络请求，真正杜绝数据偷跑。

**Q2：如果我忘记了主密码，开发者能帮我恢复吗？**  
**A**：**绝对无法恢复**。因为本应用采用零知识证明设计，所有加密密钥均由您的主密码在本地内存实时派生，开发者与任何第三方均不持有您的密钥副本。如果您遗忘了主密码，没有任何人能够破解或解密您的本地数据库。

**Q3：换手机时如何迁移我的密码数据？**  
**A**：在旧手机上的“我的”页面点击“导出加密备份”，通过蓝牙、有线传输或加密 U 盘将备份文件传送到新手机，在新手机上点击“导入加密备份”输入备份密码即可完成全量迁移。

---
---

# 🌐 English User Manual

## 1. Product Overview & Core Philosophy

**VaultGuard (Offline Edition)** is an ultra-secure, standalone **Password & Two-Factor Authentication (2FA/TOTP) Manager** engineered for users who demand absolute data sovereignty and uncompromising privacy.

In an era of recurring cloud breaches and pervasive remote telemetry, VaultGuard adheres strictly to the principles of **Physical Zero-Network Isolation** and **Zero-Knowledge Architecture**:
- **Physical Network Sandbox**: The application has stripped all network permissions (`android.permission.INTERNET` and `android.permission.ACCESS_NETWORK_STATE`) from its Android manifest. The OS physically prevents the app from connecting to any network. There are zero remote servers, zero cloud databases, and zero trackers.
- **Hardware-Backed Encryption**: The master encryption key is derived locally from your master password using **Argon2id**. All sensitive data is protected via **XChaCha20-Poly1305 / AES-256-GCM** encryption and anchored by the Android Keystore (TEE / StrongBox).
- **Absolute Ownership**: All data stays exclusively on your physical device. Nobody—including the application developer—can decrypt, access, or intercept your credentials.

---

## 2. Key Features

1. **Four Versatile Credential Types**:
   - **Logins & Passwords**: Store titles, accounts/usernames, strong passwords, and 3 custom note fields (**Note 1**, **Note 2**, **Note 3**).
   - **API Keys & Tokens**: Designed for developers and engineers to manage OpenAI, AWS, GitHub, and cloud infrastructure keys.
   - **Mnemonic Phrases**: Securely store 12/24-word recovery seeds for cryptocurrency wallets with chunked visual cards.
   - **2FA / TOTP Authenticator**: RFC 6238 compliant 30-second token generator with real-time countdown ring, single-tap copy, camera scanning, and album QR decoding.
2. **High-Entropy Password Generator**:
   - Integrated cryptographically secure pseudorandom generator supporting uppercase, lowercase, digits, and special characters.
   - Real-time bit-entropy calculation and security level assessment up to 64 characters.
3. **Android System Autofill Integration**:
   - Native integration with the Android Autofill Framework. Fill in accounts and passwords into browsers and external apps instantly after biometric verification.
4. **Dual Backup & Migration Channels**:
   - **Encrypted Backup**: Export password-protected `.vgvault` encrypted files for cold storage and seamless device-to-device migration.
   - **Universal Plaintext CSV**: Export and import standard CSV files compatible with Bitwarden, KeePass, Chrome, and other password tools.
5. **Biometric Quick Unlock**:
   - Fingerprint and Facial recognition unlock via standard Android BiometricPrompt APIs.

---

## 3. Step-by-Step Instructions

### Step 1: Initial Vault Setup
1. Launch the application after installation. You will be greeted with the "Setup Your Encrypted Vault" screen.
2. **Create Master Password**: Your master password is the sole key to your vault.
   - Must fulfill security criteria: **At least 10 characters**, containing **uppercase, lowercase, numbers, and special symbols**, with no spaces.
3. **Confirm Master Password**: Re-enter the exact same password to verify.
4. **Accept Terms & Policy**: Read the User Agreement and Privacy Policy, then check the agreement box.
5. Tap **"Create Encrypted Vault"**. The app derives your local Data Encryption Key (DEK) and initializes the encrypted SQLite database.
> **⚠️ Critical Warning**: VaultGuard is a 100% offline, zero-knowledge app. **If you lose your master password, your data cannot be recovered by anyone! Keep a written offline copy in a safe location.**

### Step 2: Unlocking & Biometrics
- **Password Unlock**: Enter your master password on the lock screen and tap "Unlock Vault".
- **Biometric Unlock**: Toggle "Biometric Unlock" in settings to unlock instantly using fingerprint or face verification.
- **Locking the Vault**: Tap "Lock Vault" in the Settings tab, or exit the application to trigger automatic memory-clearing and lock.

### Step 3: Adding & Editing Credentials
1. Tap the floating **"+"** button at the bottom-right of the vault dashboard.
2. **Select Type**: Choose from Standard Password, API Key, Mnemonic Phrase, or TOTP 2FA.
3. **Fill in Details**:
   - **Title**: Service or platform name (e.g., GitHub, Google, Server-01).
   - **Account**: Username, email address, or account identifier.
   - **Secret**: Enter manually or tap **"🎲 Generate"** for a quick 16-character secure password.
   - **Custom Notes (Note 1 / Note 2 / Note 3)**:
     - **Note 1**: Primary website, login portal URL, or main note;
     - **Note 2**: Secondary endpoint, mirror URL, or platform details;
     - **Note 3**: Security answers, PINs, or confidential remarks.
4. Tap **"Save Record"** to encrypt and persist the item locally.

### Step 4: Using TOTP Two-Factor Authenticator
- **Scan QR Code**: When creating a TOTP entry, switch to "Scan QR Code" to capture using the device camera or pick an image from your photo album.
- **Manual Input**: Alternatively, paste any standard Base32 secret key.
- **Viewing Codes**: Switch to the "2FA" tab at the bottom navigation bar. Codes refresh every 30 seconds; tap the code to copy it directly.

### Step 5: Configuring System Autofill
1. Go to Android **Settings** $\rightarrow$ **System** $\rightarrow$ **Languages & input** $\rightarrow$ **Autofill service**.
2. Select **VaultGuard / 安全密码箱自动填充**.
3. When signing into any website or third-party app, tap the credentials field, verify your fingerprint, and let VaultGuard fill in your credentials automatically.

### Step 6: Backup, Export & Phone Migration
- **Encrypted Vault Backup (Recommended)**:
  1. Open the "Settings" tab $\rightarrow$ "Encrypted Database Backup & Restore".
  2. Tap **"Export Encrypted Backup"**, set a dedicated backup password, and save the generated `.vgvault` file.
  3. On your new phone, install VaultGuard, tap **"Import Encrypted Backup"**, and enter your backup password to restore everything.
- **Plaintext CSV Export**:
  - Tap "Export Plaintext CSV" to produce a standard CSV file.
  - *Caution: Plaintext CSV files are unencrypted. Store them in a secure environment and securely shred them after use.*

---

## 4. Frequently Asked Questions (FAQ)

**Q1: Does this application really have zero network access?**  
**A**: Yes. The `android.permission.INTERNET` permission is completely stripped at the operating system manifest level. Regardless of whether Wi-Fi or Cellular data is on, Android prohibits this application from making any network calls.

**Q2: If I forget my Master Password, can the developer help me recover my data?**  
**A**: **No, it is technically impossible.** VaultGuard operates on zero-knowledge cryptographic principles. All encryption keys are derived on-device in volatile RAM. No one in the world possesses a backdoor or recovery key.

**Q3: How do I transfer my vault to a new device?**  
**A**: Generate an "Encrypted Backup" on your old device, transfer the encrypted `.vgvault` file to your new device via USB or Bluetooth, and import it using your backup password.
