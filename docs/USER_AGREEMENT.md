# User Service Agreement | 用户服务协议
**Application Name / 应用名称**: 密码管理器 (VaultGuard 离线版)  
**Package Name / 应用包名**: `com.freytagnan.pwdmanager_local`  
**Effective Date / 生效日期**: October 01, 2026 / 2026年10月01日  
**Version / 版本**: 1.0 (100% Offline Standalone Edition)

---

## 目录 / Table of Contents
1. [中文版用户服务协议 (Chinese Version)](#一-中文版用户服务协议)
2. [English User Service Agreement (English Version)](#ii-english-user-service-agreement)

---

# 一、 中文版用户服务协议

### 重要提示
欢迎使用“密码管理器（VaultGuard 离线版）”（以下简称“本软件”或“本应用”）。
本协议是您（以下称“用户”）与本软件开发者之间关于下载、安装、使用本软件所订立的具有法律效力的协议。
请您在安装或使用本软件前，仔细阅读并充分理解本协议全部条款，特别是免除或限制责任条款、主密码不可恢复性警示以及用户自担风险条款。如您不同意本协议的任何条款，请勿安装或立即卸载本软件。使用或继续使用本软件，即视为您完全认可并接受本协议的全部约束。

### 1. 服务内容与工具定位
1. **纯单机本地工具**：本软件是一款采用端到端本地强加密（E2EE）与零知识架构（Zero-Knowledge）设计的完全离线单机密码管理器。本软件为您提供本地密码、API 密钥、双重身份验证（2FA/TOTP）及密保助记词的加密存储、管理、离线导入导出及系统级安全自动填充功能。
2. **零网络与去中心化**：本软件不提供任何云端服务器托管、远程数据同步或在线账户体系。本软件在底层彻底剥离了网络权限，所有数据与密码学运算均在您本人的终端设备物理本地完成。

### 2. 主密码与安全自负责任【特别重要警示】
1. **零知识架构与不可找回原则**：本软件基于纯本地零知识证明原则设计。您的主密码是派生数据加密密钥（DEK）的唯一核心凭据，开发者不保存亦无法获取您的主密码明文或密文。**本软件不提供、亦在技术上无法提供“找回密码”、“重置密码”或“人工申诉解密”功能。**
2. **主密码保管责任**：您必须妥善保管并牢记您设置的主密码。一旦主密码遗忘、丢失或损坏，您加密存储于本软件中的所有数据将永久无法解密和恢复，开发者在技术上与法律上均无法协助您找回数据，由此产生的一切损失由您自行承担。
3. **物理与设备环境安全**：您应确保安装本软件的设备处于安全受控状态，防范设备遗失、恶意软件感染、Root/越狱提权攻击风险。若因您自身设备被攻破、锁屏密码泄露或将主密码告知他人导致的任何损失，由您自行承担。

### 3. 数据所有权、导出与备份规范
1. **数据完全所有权**：您录入、存储、导入的全部账号、密码、密钥及文字记录等数据，其所有权与控制权均完整归属于您本人。
2. **离线备份建议**：由于本软件不提供云端备份，为防范设备遗失或硬件故障导致数据丢失，建议您定期使用应用内的离线导出功能生成加密备份文件（.vgvault），并保存于安全可信的物理离线介质中。
3. **明文导出风险自负**：若您选择将本地数据导出为明文 CSV 格式，导出的文件将完全失去本软件的加密沙盒保护。您须承担导出明文文件后的保密义务，并在完成必要操作后及时进行安全粉碎或删除。

### 4. 用户使用规范与禁止行为
用户在使用本软件过程中，必须遵守法律法规，不得利用本软件从事任何违法活动，包括但不限于：
1. 存储或处理非法侵入他人计算机信息系统所获取的未授权账号、密码或敏感凭证；
2. 利用本软件从事侵犯他人知识产权、商业秘密、隐私权或其他合法权益的活动；
3. 对本软件进行反向工程、反向汇编、反编译、破解，或以其他方式试图提取源代码与内部逻辑；
4. 修改、篡改或伪造本软件运行中的指令、数据或安全特征，制作或传播带有恶意篡改的衍生版本。

### 5. 知识产权声明
本软件及其相关的一切著作权、商标权等知识产权均归开发者所有。开发者授予您一项个人的、非排他性的、不可转让且不可转授权的合法使用许可，您仅可出于个人非商业目的在单一终端设备上安装及使用本软件。

### 6. 免责声明与有限责任
1. **按“现状”提供**：在法律允许的最大限度内，本软件按“现状”（As Is）和“现有”（As Available）提供。开发者不对软件的稳定性、绝对无漏洞性或适用特定用途作出任何明示或暗示的担保。
2. **免责范围**：因用户遗忘主密码、未及时本地备份、误删数据、设备硬件损坏丢失、系统崩溃、遭受木马病毒或越狱 Root 攻击等情形导致的任何数据损失、硬件损坏或间接损失，开发者均不承担赔偿责任。
3. **赔偿限额**：在任何情况下，开发者对用户因使用本软件所遭受直接损失的累计赔偿责任，以用户向开发者实际支付的费用（如有）为上限；若本软件为免费提供，则赔偿限额为零。

### 7. 协议修改与争议管辖
1. 开发者有权根据技术演进或法律法规修改本协议，修订后的协议将完整打包于最新软件版本中。若您继续使用，即视为接受修订后的协议。
2. 本协议适用中华人民共和国大陆地区法律。因本协议产生的争议双方应友好协商，协商不成的，任何一方均可向开发者住所地有管辖权的人民法院提起诉讼。

---

# II. English User Service Agreement

### Important Notice
Welcome to **VaultGuard (Offline Edition)** (hereinafter referred to as "the Software" or "the Application").
This User Service Agreement is a legally binding agreement between you (the "User") and the developer regarding downloading, installing, and using the Software.
Please read and understand all terms carefully before installing or using the Software, especially provisions regarding limitation of liability, master password non-recoverability, and user risk assumption. If you do not agree, do not install or use the Software. By installing or continuing to use the Software, you acknowledge and agree to be bound by all terms herein.

### 1. Service Scope & Tool Classification
1. **Standalone Offline Utility**: The Software is a standalone, local password manager engineered with End-to-End Encryption (E2EE) and Zero-Knowledge Architecture. It provides offline storage, management, import/export, and system-level autofill for credentials, API tokens, 2FA/TOTP keys, and mnemonic seeds.
2. **Zero-Network & Decentralized**: The Software provides no remote server hosting, cloud database syncing, or online accounts. Network permissions have been completely stripped at the OS level; all cryptographic operations execute solely on your physical device.

### 2. Master Password & User Security Responsibility 【CRITICAL NOTICE】
1. **Zero-Knowledge Architecture & Non-Recoverability**: The Software operates on absolute zero-knowledge principles. Your Master Password is the sole source for deriving your Data Encryption Key (DEK). The developer never possesses your plaintext or ciphertext credentials. **The Software does not and cannot provide any "Forgot Password", "Password Reset", or "Customer Support Decryption" services.**
2. **Sole Responsibility for Master Password**: You must memorize and securely safeguard your Master Password. If your Master Password is forgotten, lost, or corrupted, your encrypted vault cannot be decrypted by anyone in the world. The developer has no technical or legal means to recover your data, and all associated losses are borne exclusively by you.
3. **Physical & Device Security**: You are responsible for keeping your device secure against physical theft, malware, and unauthorized root/jailbreak privilege escalation. Any loss resulting from a compromised operating system or disclosed screen credentials is your sole responsibility.

### 3. Data Ownership, Export & Backup
1. **Exclusive Data Ownership**: You retain 100% full ownership and control over all accounts, passwords, keys, and notes stored in the Software.
2. **Offline Backup Recommendation**: Because no cloud backup exists, you are strongly advised to regularly generate encrypted backups (`.vgvault`) and store them in an isolated physical medium.
3. **Plaintext Export Risks**: Choosing to export unencrypted CSV files removes all cryptographic protection. You assume full confidentiality obligations for plaintext files and must securely shred them after use.

### 4. Acceptable Use & Prohibited Activities
You agree to comply with all applicable laws and shall not use the Software to:
1. Store or process credentials obtained through unlawful computer intrusion, hacking, or credential stuffing;
2. Infringe on any third party's intellectual property, trade secrets, or privacy rights;
3. Reverse engineer, decompile, disassemble, or crack the Software;
4. Tamper with or redistribute modified binaries of the Software.

### 5. Intellectual Property
All intellectual property rights in and to the Software belong exclusively to the developer. The developer grants you a personal, non-exclusive, non-transferable, revocable license to install and use the Software for personal, non-commercial purposes on your personal devices.

### 6. Disclaimer of Warranties & Limitation of Liability
1. **"AS IS" Provision**: To the maximum extent permitted by applicable law, the Software is provided "AS IS" and "AS AVAILABLE" without warranties of any kind, whether express or implied.
2. **Exclusion of Liability**: The developer shall not be liable for any data loss, hardware damage, or indirect damages arising from forgotten master passwords, failure to maintain local backups, device loss, OS crashes, malware infections, or force majeure events.
3. **Aggregate Liability Cap**: To the maximum extent permitted by law, the developer's aggregate liability for direct damages shall not exceed the amount actually paid by you for the Software (if any); if the Software was provided free of charge, the liability limit is zero.

### 7. Modifications & Governing Law
1. The developer reserves the right to amend this Agreement in accordance with legal and technical requirements. Updated agreements will be distributed with updated software packages.
2. This Agreement is governed by the laws of the People's Republic of China. Any disputes arising herefrom shall be settled through amicable negotiation, failing which either party may submit the dispute to the competent court in the developer's jurisdiction.
