---
title: "使用 Intune 的常見方式 | Microsoft Intune"
description: "列出 Intune 可協助的六項最常見工作"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/09/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: robstackmsft
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 39e68e467c3295f4751bf3466957a8a377a8e7d6
ms.openlocfilehash: 095be86be3658a294d3f0aab525f5e0dd29b4cfe


---

# <a name="common-ways-to-use-intune"></a>使用 Intune 的常見方式

深入實作工作時，契合貴公司的企業行動力專案關係人與業務目標很重要。  不論您是企業行動力新手，還是從另一個產品移轉而來，這一點都很要。  

對於企業行動力的需求一直在大幅進化，Microsoft 用來解決這些需求的方法有時與市場上的其他解決方案不同。  契合業務目標的最佳方式是以您想要為員工、協力廠商和 IT 部門塑造的環境，表達您的目標。  

以下簡介六個依賴 Intune 的常見案例，以及如何規劃及部署每個案例的詳細資訊連結。

>[!NOTE]
>您是否想要了解 Microsoft IT 如何使用 Intune，讓 Microsoft 在其行動裝置上存取公司資源，同時保護公司資料？ [閱讀此技術性案例研究](https://www.microsoft.com/itshowcase/Article/Content/588)，詳細查看 Microsoft IT 如何使用 Intune 與其他服務來管理身分識別、裝置、應用程式和資料。  

>[!IMPORTANT]
>我們想要確保行動裝置對於最近在 iOS 裝置上的 "Trident" 惡意程式碼攻擊，處於最新狀態。 因此我們發佈了一篇部落格文章，稱為 [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) (使用 Microsoft Intune 確定行動裝置為最新狀態)。 它提供 Intune 可協助保持您的裝置安全且最新的不同方式的相關資訊。

## <a name="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>保護內部部署電子郵件和資料，以透過行動裝置安全存取
大部分企業行動力策略計劃一開始都是讓員工，在連接網際網路的行動裝置上安全地存取電子郵件。 許多組織仍然有內部部署資料和應用程式伺服器，例如裝載在其公司網路上的 Microsoft Exchange。

Intune 和 Microsoft Enterprise Mobility + Security (EMS) 提供唯一的 Exchange Server 整合[條件式存取解決方案](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)，確保在裝置向 Intune 註冊前，沒有任何行動應用程式可以存取電子郵件。 您不必在貴公司網路邊緣部署另一部閘道電腦，就能完全做到！

Intune 支援也能存取需要安全存取內部部署資料的行動應用程式，像是商務營運應用程式伺服器。 這通常是使用 [Intune 受管理憑證](/intune/deploy-use/secure-resource-access-with-certificate-profiles)完成，適用於在周邊網路結合標準 VPN 閘道或 Proxy 的存取控制，例如 Microsoft Azure Active Directory 應用程式 Proxy。  

在這些情況下，存取公司資料的唯一方法就是註冊裝置進行管理。 註冊裝置之後，管理系統會先確保它們符合您的原則，然後才能存取公司資料。  此外，Intune 的 [App Wrapping Tool 與 App SDK](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) 可包含企業營運應用程式中的存取資料，讓它無法將公司資料傳遞至取用者應用程式或服務。

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->


## <a name="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>保護 Office 365 電子郵件和資料，以透過行動裝置安全存取
您可以更容易，您的使用者也以更順暢地在 Office 365 中保護公司資料 (電子郵件、文件、立即訊息、連絡人)。

Intune 與 Enterprise Mobility Suite + Security 解決方案特別加入了條件式存取功能，確保只有符合您公司之相容性需求 (已執行[多重要素驗證](/intune/deploy-use/protect-windows-devices-with-multi-factor-authentication)、已在 Intune 註冊，並使用受管理的 App、受支援的 OS 版本、裝置 PIN 碼、低使用者風險設定檔等等) 的使用者、應用程式或裝置，才能存取 Office 365 資料。 在其各自的應用程式存放區中的 Office 行動應用程式會準備好開始使用資料內含項目原則 (可透過 Intune 設定)，可讓您避免與未受 IT 管理的應用程式 (例如原生電子郵件應用程式) 和儲存位置 (例如 Dropbox) 共用資料。  這項功能內建於 Office 365 和 EMS。  您不需要部署額外的基礎結構即可取得此值。

各自應用程式市集裡的 Office 行動應用程式已經準備好開始使用資料內含項目原則，您可以透過 Intune 進行設定。 這可讓您避免與應用程式 (例如原生電子郵件應用程式) 及不受 IT 管理的儲存位置 (例如 Dropbox) 共用資料。  這項功能內建於 Office 365 和 EMS。  您不需要部署額外的基礎結構即可取得此值。


常見的 Office 365 部署作法是要求註冊裝置加以管理，但前題是它們需要使用公司應用程式、憑證、Wi-Fi 或 VPN 組態以完整設定，這通常是公司擁有的裝置情況。  

不過，如果使用者只需要存取公司電子郵件與文件 (通常是個人擁有的裝置情況)，則使用者也需要使用 Office 行動應用程式 ([已套用資料內含項目原則](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune))，並完全略過註冊裝置！  

無論如何，將由已定義的原則保護 Office 365 資料。

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->


## <a name="offer-a-bring-your-own-device-program-to-all-employees"></a>將攜帶您自己的裝置計劃提供給所有員工
攜帶您自己的裝置 (BYOD) 會繼續在組織間受歡迎，為員工減少硬體支出或提高行動產能選擇。 目前幾乎每個人都有手機，因此為什麼不在口袋內再放一支？ 主要的挑戰一直都是說服員工註冊其個人裝置加以管理，因為它們害怕 IT 部門會看到並使用他們的裝置做其他事。  

當裝置註冊不可行時，Intune 提供一個 BYOD 替代方法來簡單[管理包含公司資料的應用程式](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune)。  Intune 可保護公司資料，即使有問題的應用程式存取公司和個人資料也可以，此情況適用於 Office 行動應用程式。  

身為系統管理員，您可以要求使用者從 Office 行動應用程式存取 Office 365，並使用保護資料的原則來設定應用程式 (例如將它加密、使用 PIN 來保護它等等)。  這些原則會防止因為未受管理的應用程式和儲存位置而遺失資料 – 應用程式內部或外部。  例如，這些原則會防止使用者將公司電子郵件設定檔的文字複製到取用者的電子郵件設定檔，即使兩個設定檔都是在 Outlook Mobile 中設定也是如此。  可針對您的 BYOD 使用者需要的其他服務及應用程式部署類似設定。

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporate-owned-phones-to-your-information-workers"></a>向資訊工作者核發公司電話
目前的大部分資訊工作者都是機動工作，在行動裝置上創造產能是提升競爭力的必要方式。  這些員工隨時隨地都需要順暢地存取所有公司應用程式和資料。  您需要確保公司資料安全且具有低管理成本。  

Intune 提供了[大量佈建和管理解決方案](/intune/deploy-use/manage-corporate-owned-devices)，其整合目前市場上的主要企業裝置管理平台，包括 Apple 裝置註冊方案和 Samsung KNOX 行動安全性平台。  使用 Intune 集中撰寫裝置設定，有助於高度自動化佈建某些公司裝置。  

試想一下︰將未拆封的 iPhone 手機交給員工。 員工開啟手機電源，然後瀏覽他們必須自行驗證之帶有公司品牌的安裝流程。 iPhone 順暢地設定[安全性原則](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) (例如加密的硬碟、裝置 PIN)、[電子郵件、Wi-Fi/VPN、憑證設定檔](/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune)，以及一組基本[應用程式](/intune/deploy-use/add-apps)。

接著，員工啟動 Intune 公司入口網站應用程式以存取提供給他們的選擇性公司應用程式。

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limited-use-shared-tablets-to-your-task-workers"></a>將限制使用的共用平板電腦發給您的工作人員
越來越多工作人員使用行動技術。  例如，共用的平板電腦現在經常由零售商店員工使用。  不論是用來處理銷售或立即檢查庫存，平板電腦皆有助於大幅提升與客戶的互動。

在此情況下，簡單的使用者體驗很重要。  基於這個理由，通常會將有限用途模式下的平板電腦散發給員工，例如，單一特定業務應用程式是員工可進行互動的唯一工具。  Intune 可讓您大量佈建、保護和集中管理這些共用的 [iOS](/intune/deploy-use/ios-policy-settings-in-microsoft-intune#general-configuration-policy-settings) 與 [Android](/intune/deploy-use/android-policy-settings-in-microsoft-intune#general-configuration-policy) 平板電腦 (可設定在此有限用途模式下執行)。

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>讓您的員工從未受管理的公用 kiosk 中安全存取 Office 365
有時候您的員工需要使用您無法管理的裝置、應用程式或瀏覽器，例如商展和旅館的公用電腦。

您應該允許員工從中存取公司電子郵件？ 您可以利用 Intune 與 Microsoft Enterprise Mobility + Security，<!--you have choices. The-->[限制您組織所管理之裝置的電子郵件存取權](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)，告訴大家「不行」。  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).-->  這可確保經過嚴格驗證的員工不會不小心將公司資料放在不受信任的電腦上。

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->



<!--HONumber=Nov16_HO3-->

