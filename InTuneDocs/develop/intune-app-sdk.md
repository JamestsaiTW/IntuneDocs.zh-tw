---
title: "Intune App SDK 優點 | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7f62c5ee18d8f69fa174f09a1c46b6925c7517c
ms.openlocfilehash: 3abf566831348de11f718370d6267e3ff4355bfb


---

# Intune App SDK 概觀
Intune App SDK 適用於 iOS 和 Android 平台，並提供 Microsoft Intune 的行動應用程式管理功能。 此外，我們盡力減少開發人員所需的程式碼變更數量。 您會發現，您可以啟用大多數 SDK 功能，而不需要變更您的應用程式行為。 為了改進使用者和 IT 系統管理員體驗，您可以利用我們的 API，針對需要應用程式參與的功能，自訂您的應用程式行為。 一旦您啟用應用程式，IT 系統管理員便可將原則部署至受 Intune 管理的應用程式，並利用這些功能來保護其公司資料。

## 一般功能

### 控制使用者移動公司文件的能力
IT 系統管理員可以控制受 Intune 管理的應用程式中公司文件的檔案重新配置。 例如，他們可以部署原則來停用檔案備份應用程式，以防止應用程式將公司資料備份到雲端。

### 設定剪貼簿限制
IT 系統管理員可以在受 Intune 管理的應用程式中設定 [剪貼簿] 行為。 例如，他們可以部署原則，讓使用者無法使用 [剪貼簿] 從受 Intune 管理的應用程式剪下/複製，並貼到未受管理的應用程式中。

### 設定螢幕擷取限制
IT 系統管理員可以在顯示受 Intune 管理的應用程式時，防止使用者擷取畫面。 套用這項限制可防止擷取及外洩機密公司內容。 這項功能僅適用於 Android 裝置。

### 強制加密已儲存的資料
IT 系統管理員可以強制執行原則，以確保應用程式儲存到裝置的資料會經過加密。

### 從遠端抹除公司資料
IT 系統管理員可以在取消註冊 Microsoft Intune 中的裝置時，從受 Intune 管理的應用程式遠端抹除公司資料。 這項功能是以身分識別為基礎，而且只會刪除與使用者之公司識別相關的檔案。 若要執行這項操作，此功能需要應用程式的參與。 應用程式可以根據使用者設定，指定應該進行抹除的身分識別。 如果沒有來自應用程式的這些指定的使用者設定，預設行為是抹除應用程式目錄，並通知使用者已移除公司資源存取權。

### 強制使用受管理的瀏覽器
IT 系統管理員可以在開啟受 Intune 管理之應用程式中的連結時，強制使用受管理的瀏覽器。 使用受 Microsoft Intune 管理的瀏覽器可協助確保在受 Intune 管理的應用程式網域內，保留出現在電子郵件中 (受 Intune 管理的郵件用戶端中) 的連結。

### 強制執行 PIN 原則
IT 系統管理員可以在受 Intune 管理的應用程式啟動時，強制執行 PIN 原則。 這項原則有助於確保向 Microsoft Intune 註冊其裝置的使用者是啟動應用程式的相同人員。 當使用者設定其 PIN 時，Intune App SDK 會使用 Azure Active Directory 依據裝置註冊認證，來驗證使用者的認證。

### 要求使用者在啟動應用程式之前先輸入認證
IT 系統管理員可以要求使用者在啟動受 Intune 管理的應用程式之前先輸入其認證。 Intune App SDK 使用 Azure Active Directory 來提供單一登入體驗，其中認證一旦輸入，便可供後續登入重複使用。 我們也支援驗證[與 Azure Active Directory 建立同盟](https://msdn.microsoft.com/library/azure/jj679342.aspx)的身分識別管理解決方案。

### 檢查裝置健全狀況和相容性
IT 系統管理員可以在使用者存取受 Intune 管理的應用程式之前，檢查裝置的健全狀況及其是否符合公司原則。 在 iOS 平台上，這項原則會檢查裝置是否已進行 JB 破解。 在 Android 平台上，這項原則會檢查裝置是否已進行 Root 破解。

## 預覽版功能
Microsoft Intune App SDK 包含數項處於「預覽」狀態的功能。 您可以開始與預覽版 API 進行整合，但僅限於測試目的。 請注意，這些預覽版功能會加入現有案例中，而不是取代現有的案例。

### Microsoft Intune App SDK 多重身分識別支援
多重身分識別支援功能允許單一應用程式中可以共存受原則管理的帳戶 (公司) 和未受管理的帳戶 (個人)。

### 多重身分識別案例的範例
許多使用者會在適用於 iOS 和 Android 的 Outlook 應用程式中，同時設定公司和個人電子郵件帳戶。 當使用者存取其公司帳戶中的資料時，IT 系統管理員必須確定會套用 MAM 原則管理。 不過，當使用者存取個人電子郵件帳戶，該資料則不在 IT 系統管理員的控制範圍內。 Microsoft Intune 藉由將管理原則的目標僅限於應用程式中的公司帳戶，來達成這項目的。 這項多重身分識別功能有助於解決組織使用同時支援個人和工作帳戶的裝置和應用程式時，所遇到的資料保護問題。

### 如何支援多重身分識別
預覽版 API 可讓您使用 [剪貼簿] 作業和檔案作業等特定資料作業，來指定使用者主體名稱 (UPN)。 Microsoft Intune App SDK 會使用 UPN 來比對用來向 Microsoft Intune 服務註冊裝置的 UPN 呼叫。 如果 UPN 相符，則會將呼叫視為「公司資料」呼叫，而且會保護資料；如果 UPN 不符，則會將呼叫視為「個人資料」呼叫，而且不會保護資料。

### 不註冊裝置的應用程式管理
許多個人裝置的使用者想查看並使用公司資料，但不想向行動裝置管理 (MDM) 產品註冊其個人裝置。 由於 MDM 註冊需要裝置的通用控制項，因此使用者會不太願意將其擁有之個人裝置的通用控制項提供給公司。

不註冊裝置的應用程式管理可讓 Microsoft Intune 服務將 MAM 原則直接部署到應用程式，而不需要依賴 MDM 通道來部署原則。 由於不需要 MDM 通道，因此也不需要 MDM 註冊。




<!--HONumber=Jul16_HO3-->

