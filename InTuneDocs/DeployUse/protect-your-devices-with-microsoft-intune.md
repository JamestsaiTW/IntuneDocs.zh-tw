---
# required metadata

title: 使用 Microsoft Intune 保護裝置 | Microsoft Intune
description:
keywords:
author: Robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 使用 Microsoft Intune 保護裝置
使用 Intune 保護裝置之後，您會想要確定裝置不受到未經授權存取和其他威脅。 以下是 Intune 協助達成這些目標是一些功能。

> [!TIP]
> 本主題並未完整囊括 Intune 可協助保護裝置的一切方法。 例如，您可以使用 Intune 原則來為裝置設定許多安全性設定，例如設定密碼、加密設定和硬體功能，例如藍芽與裝置相機。 若要深入了解這些設定，請參閱[透過 Microsoft Intune 管理裝置上的設定和功能](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)。

## 當使用者遭到鎖定而無法使用其裝置時重設密碼
保護行動裝置上的公司資料時，第一步就是要求密碼才能使用裝置，因此，您有時必須[重設密碼](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)或協助員工執行這項操作，包括從遠端移除密碼或設定暫時密碼。 如果裝置遺失或遭竊，您也可以[從遠端鎖定裝置](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)。

## 為 Windows 裝置多加一層保護
[Multi-Factor Authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) 可以更安全地在網路上驗證 Windows 和 Windows Phone 裝置的使用者。  使用 MFA 時，除了使用者名稱和密碼之外，使用者還必須透過電話或簡訊確認其身分識別。

## 控制 Windows 裝置上的 Microsoft Passport 設定
Intune 可讓您與 [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) 整合，這是使用 Active Directory 或 Azure Active Directory 帳戶取代密碼、智慧卡或虛擬智慧卡來登入 Windows 10 和更新版本的替代方法。

## 保護使用 Intune 用戶端管理的 Windows 電腦
對於您未註冊但以 Intune 電腦用戶端軟體管理的 Windows 電腦，Intune 持續支援安全性原則。 若要了解這些原則如何協助保護 Windows 電腦，請參閱[使用原則來協助保護執行 Intune 用戶端軟體的 Windows 電腦](policies-to-protect-windows-pcs-in-microsoft-intune.md).


<!--HONumber=May16_HO1-->

