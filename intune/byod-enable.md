---
title: "使用 Microsoft Intune 來啟用 BYOD"
description: 
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 880b83a63eefe13a96ab8838c7092c185aa32cd0
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2017
---
# <a name="enable-byod-with-intune"></a>使用 Intune 來啟用 BYOD

本主題提供設定 Intune 來為您的組織啟用「攜帶您自己的裝置」(BYOD) 解決方案的高階工作流程。 它會將工作組織成三個程序，並連結至支援的使用說明主題。

工作流程分成下列三個程序。 您可以調整每個程序的層面，以符合您組織的需求。

-   **[註冊裝置及檢查合規性](#enroll-devices-and-check-for-compliance)**說明如何讓使用者利用 Intune 註冊其個人裝置以納入管理。 Intune 可管理 iOS、macOS、Android 和 Windows 裝置。 本節也說明如何將原則部署到裝置，以及確保它們符合基本的安全性需求。

- **[提供公司資源存取](#provide-access-to-company-resources)**為您示範 IT 如何讓使用者輕鬆且安全地存取公司資源。 您可以將存取設定檔部署到受管理的裝置來完成這項操作。 本節也說明如何使用 Intune 管理大量採購的應用程式部署。

-   **[保護公司資料](#protect-company-data)**可協助您了解如何提供公司資源的條件式存取、避免資料遺失，以及當工作不再需要裝置、裝置遺失或遭竊時，如何移除裝置上的公司應用程式與資料。

[![使用 Microsoft Intune 來啟用 BYOD 的高階工作流程圖表](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>開始之前
在使用者註冊裝置之前，您必須先準備 Intune 服務本身。 若要這樣做，請[指派授權給使用者](licenses-assign.md)並[設定行動裝置管理授權單位](mdm-authority-set.md)。

當您進行這項操作時，也應該[自訂公司入口網站](company-portal-customize.md)。 新增公司品牌並向使用者提供支援資訊。 這會為您的使用者建立可信任的註冊和支援體驗。

## <a name="enroll-devices-and-check-for-compliance"></a>註冊裝置及檢查合規性

準備好 Intune 服務之後，您必須符合想要管理之不同裝置類型的各種註冊需求。 註冊裝置以納入管理的程序很簡單，但根據裝置類型會略有不同。

-   **iOS 和 Mac 裝置** 您必須[取得 Apple Push Notification Service (APN) 憑證](apple-mdm-push-certificate-get.md)，才能註冊 iPad、iPhone 或 MacOS 裝置。 將 APN 憑證上傳至 Intune 之後，使用者可以使用公司入口網站應用程式[註冊 iOS 裝置](/intune-user-help/enroll-your-device-in-intune-ios)，並使用公司入口網站[註冊 MacOS 裝置](/intune-user-help/enroll-your-device-in-intune-macos)。

-   **Android 裝置** 您不需要準備 Intune 服務即可註冊 Android 裝置。 使用者只要使用 Google Play 提供的公司入口網站應用程式即可[註冊 Android 裝置](/intune-user-help/enroll-your-device-in-intune-android.md)。

-   **Windows Phone 和電腦** 您應該[設定註冊伺服器的 DNS 別名](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium) 以利註冊 Windows 裝置。 使用者也可以藉由新增工作或學校帳戶[註冊 Windows 裝置](/intune-user-help/enroll-your-w10-phone-or-w10-pc-windows)。

  - 如果您具有 Azure AD Premium，則可以[啟用自動註冊](windows-enroll.md)功能，讓使用者更方便註冊 Windows 裝置。 當使用者新增工作或學校帳戶來註冊其個人裝置時，此功能會將裝置自動註冊到 Intune 中。 這也適用於加入貴組織之 Azure AD 的屬公司擁有的裝置。


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>請確定受管理的裝置符合基本安全性需求

在使用者註冊其裝置以納入管理之後，IT 必須確定用來存取公司應用程式和資料的裝置必須符合基本安全性需求。 這些規則可能包括使用 PIN 來存取裝置，以及為裝置中儲存的資料加密。 這組規則稱為[合規性政策](device-compliance.md)。

當您為使用者[部署合規性原則](device-compliance-get-started.md)時，Intune 會檢查 Intune 管理的所有使用者裝置，以確認這些裝置符合您 BYOD 原則中定義的基本安全性需求。 裝置經過原則合規性評估之後，會向 Intune 回報其狀態。 在某些情況下，可能會要求使用者修正設定，例如其 PIN 或裝置加密。 其他時候，公司入口網站應用程式只會通知使用者有關任何不符合原則的設定。

## <a name="provide-access-to-company-resources"></a>提供公司資源存取

大部分員工在其行動裝置上要做的第一件事，就是存取公司電子郵件和文件。 他們希望不經複雜的步驟或呼叫技術支援中心，就能完成設定。 Intune 可讓您為預先安裝在行動裝置上的原生電子郵件應用程式，輕鬆[建立及部署電子郵件設定](conditional-access-intune-common-ways-use.md)。
<!--- this was old link: (https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune). check with Andre--->

> [!NOTE]
> Intune 支援 Google Play 商店中 Gmail 和 Nine Work 電子郵件應用程式的 Android for Work 電子郵件設定檔設定。

Intune 也可在您於異地工作時，協助您控制及保護對內部部署公司資料的存取。 Intune [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)、[VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) 和電子郵件設定檔一起運作，允許使用者隨時隨地存取完成其工作所需的檔案及資源。 貴公司內部部署裝載的 Web 應用程式和服務，也可以使用 Azure Active Directory 應用程式 Proxy 和條件式存取進行安全存取和保護。

### <a name="manage-volume-purchased-apps"></a>管理大量購買的應用程式
利用 Intune，輕鬆地：
* 從任一應用程式市集匯入大量授權資訊
* 檢視您有多少份可用的授權
* 避免您的使用者安裝超過擁有數目的應用程式複本
* [將市集應用程式傳遞給受管理的裝置](apps-deploy.md)
* 使用公司入口網站，將應用程式目標設為未受管理的裝置

Intune 也可讓管理及部署您從 iOS 應用程式市集和商務用 Windows 市集所大量購買的應用程式。 這可協助您降低追蹤大量採購應用程式的管理負荷。

> [!TIP]
> 您可以[使用 Azure AD Connect 設定單一登入 (SSO) ](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。 SSO 可讓使用者利用內部部署所使用的網域使用者名稱和密碼來登入應用程式。 此外，您還可以使用 Azure Active Directory 應用程式 Proxy，[為內部部署裝載的 Web 應用程式提供網際網路存取](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)。

-   [管理大量採購的 iOS 裝置應用程式](vpp-apps-ios.md)。 您可以透過 [Apple 商務適用的大量採購方案](http://www.apple.com/business/vpp/)購買多個 iOS 應用程式的授權。 您需要從 Apple 網站設定 Apple VPP 帳戶，並將 Apple VPP 權杖上傳到 Intune。 您可以將您的大量採購資訊與 Intune 同步處理，並追蹤大量採購的應用程式使用情況。

-   [管理您從商務用 Windows 市集購買的應用程式](windows-store-for-business.md)。 [商務用 Windows 市集](https://www.microsoft.com/business-store)可讓您為組織個別或大量尋找及購買應用程式。 透過連接市集與 Intune，可讓您從 Intune 入口網站管理大量採購的應用程式。

## <a name="protect-company-data"></a>保護公司資料

Intune 透過多個技術層級保護公司資料。 在身分識別層中，條件式存取可保護服務存取。 條件式存取僅允許受管理及符合標準的裝置存取公司資源。 在用戶端應用程式層中，行動應用程式管理 (MAM) 可保護避免資料遺失。  應用程式保護原則可防止資料移至未受保護的應用程式或儲存位置。 這些原則也可讓您在裝置遺失或遭竊時抹除公司資料。

### <a name="enforce-conditional-access-to-company-resources"></a>強制執行公司資源的條件式存取

您可以合併合規性原則與[條件式存取原則](device-compliance.md)，以檢查裝置是否符合 BYOD 原則所要求的基本安全性需求。 如果裝置不符合需求，則會強制執行規則並拒絕存取，直到該裝置符合原則需求為止。 如此可確保只有受管理和符合標準的裝置可以從 Exchange ([Exchange 內部部署](exchange-connector-install.md)或 [Exchange Online](conditional-access-exchange-create.md))、SharePoint Online、商務用 Skype Online 等服務來存取公司資料。
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> 如果沒有可驗證相容性的相容性原則，條件式存取原則即無法運作。

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>使用應用程式保護原則來避免公司資料遺失

利用 Intune 的應用程式保護原則，不論裝置是否已註冊，您都可以選擇存取資料方式。 這項彈性可讓您保護公司資料，即使使用者未在 Intune 中註冊其裝置，他們仍然可以安全地存取公司資料。

您可以使用 [Intune 應用程式保護原則](app-protection-policies.md)，協助保護由使用者的 iOS 和 Android 裝置存取的公司資料。 使用這些應用程式層級原則時，即使裝置本身不是由 Intune 所管理，您也可以控制員工使用與共用公司資料的方式

使用 [Windows 資訊保護 (WIP) 原則](app-protection-policies-configure-windows-10.md)，可為受管理的 Windows 10 裝置執行相同動作。 這些原則的運作不會干擾員工的體驗。 它們不需要變更您的網路環境或其他應用程式。

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>抹除公司資料，但是完整保留個人資料

當裝置不再用於工作、要重新決定用途或只是遺失時，您需要能夠從中移除公司的應用程式和資料。 若要這樣做，您可以使用 Intune 的選擇性抹除和完整抹除功能。 如果已在 Intune 中註冊使用者的個人自有裝置，您的使用者也可以從 Intune 公司入口網站遠端抹除這些裝置。

[完整抹除](devices-wipe.md)會將裝置還原為其原廠預設值，並移除使用者資料和設定。 [選擇性抹除](devices-wipe.md#selective-wipe)只會從裝置移除公司資料，而保留使用者的個人資料。

只要一啟動，裝置就會立即開始要從管理移除的選擇性抹除程序。 當程序完成時，會刪除所有的公司資料，並從 Intune 系統管理員主控台中移除裝置名稱。 這會結束裝置管理生命週期。