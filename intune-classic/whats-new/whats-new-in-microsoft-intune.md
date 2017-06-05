---
title: "新增功能 | Microsoft Docs"
description: "了解 Microsoft Intune 本月及過去版本中的新增功能"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2e6452a066aa7eaeb295a3b531d83dc3b632bcf5
ms.contentlocale: zh-tw
ms.lasthandoff: 05/23/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Microsoft Intune 的新增功能 - 2017 年 4 月
了解此 Microsoft Intune 版本中的新增功能。 您也可以了解即將推出且您應該加以規劃的變更，以及過去版本的相關資訊。

> [!Note]
> 混合式客戶部署於未來將會支援這些功能 (具備 Intune 的 Configuration Manager)。 如需新混合式功能的詳細資訊，請查看我們的[混合式新增功能](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)頁面。

## <a name="new-capabilities"></a>新功能

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps 可供 Managed Browser 使用 <!--822308, 822303-->

Microsoft MyApps 現在於 Managed Browser 中提供更佳支援。 非管理目標的 Managed Browser 使用者將會直接進入 MyApps 服務，以在其中存取其系統管理員佈建的 SaaS 應用程式。 Intune 管理目標的使用者將能夠繼續從內建 Managed Browser 書籤存取 MyApps。

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Managed Browser 和公司入口網站的新圖示 <!--918433, 918431, 971473-->

Managed Browser 會同時收到 Android 和 iOS 版應用程式的更新圖示。 此新圖示會包含更新的 Intune 徽章，因此與 Enterprise Mobility + Security (EM+S) 中的其他應用程式更一致。 您可以在 [Intune App UI 中的新增功能頁面](whats-new-in-intune-app-ui.md)中看到 Managed Browser 的新圖示。

公司入口網站也會收到 Android、iOS 和 Windows 版應用程式的更新圖示，以改進與 EM+S 中其他應用程式的一致性。 從四月起到五月底，這些圖示會逐漸在各平台發行。

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android 公司入口網站中的登入進度列指示器 <!--953374-->

Android 公司入口網站應用程式的更新會在使用者啟動或繼續執行應用程式時，顯示登入進度指示器。 該指示器會顯示新的狀態進度，一開始為「正在連線...」，接著依序為「正在登入...」和「正在檢查安全性需求...」，之後才允許使用者存取應用程式。 您可以在 [Intune 應用程式 UI 中的新增功能頁面](whats-new-in-intune-app-ui.md)中看到 Android 版公司入口網站應用程式的新畫面。

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>禁止應用程式存取 SharePoint Online <!-- 679339 -->

您現在可以建立以應用程式為基礎的條件式存取原則，來禁止沒有套用應用程式保護原則的應用程式存取 [SharePoint Online](/intune-classic/deploy-use/mam-ca-for-sharepoint-online)。 在以應用程式為基礎的條件式存取案例中，您可以使用 Azure 入口網站指定能存取 SharePoint Online 的應用程式。

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>從 iOS 版入口網站到 iOS 版 Outlook 的單一登入 <!--834012-->
如果使用者在同一部裝置上使用相同的帳戶登入 iOS 公司入口網站應用程式，則不必再登入 Outlook 應用程式。 當使用者啟動 Outlook 應用程式時，將能夠選取其帳戶並自動登入。 我們也將努力為其他 Microsoft 應用程式新增這項功能。

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>改進 iOS 公司入口網站應用程式中的狀態訊息 <!--744866-->
iOS 公司入口網站應用程式中現在會顯示更具體的新錯誤訊息，以提供有關裝置狀況之更容易存取的資訊。 這些錯誤狀況之前包含在標題為「公司入口網站暫時無法使用」的一般錯誤訊息中。 此外，如果使用者在沒有網際網路連線時啟動 iOS 上的公司入口網站，則會在首頁上看到持續性狀態列，指出「沒有網際網路連線」。

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>改進 Windows 10 公司入口網站應用程式的應用程式安裝狀態 <!--676495-->

針對在 Windows 10 公司入口網站應用程式中啟動的應用程式安裝，包括下列新的改進項目：
-    更快速地報告 MSI 套件的安裝進度
-    針對在執行 Windows 10 年度更新版及更新版本裝置上的新式應用程式，可以更快速地報告安裝進度
-    針對在執行 Windows 10 年度更新版及更新版本裝置上的新式應用程式安裝，有新的進度列

您可以在 [Intune 應用程式 UI 的新增功能頁面](whats-new-in-intune-app-ui.md)中看到新的進度列。

### <a name="bulk-enroll-windows-10-devices----747607---"></a>大量註冊 Windows 10 裝置 <!-- 747607 -->

您現在可以使用 Windows 設定設計工具 (WCD) 將執行 Windows 10 Creators Update 的大量裝置加入到 Azure Active Directory 和 Intune。若要為您的 Azure AD 租用戶啟用大量 MDM 註冊，請使用 Windows 設定設計工具建立會將裝置加入到 Azure AD 租用戶的佈建套件，然後將套件套用至您要大量註冊及管理的公司擁有的裝置。 將套件套用至裝置之後，裝置會加入 Azure AD、在 Intune 中註冊，並準備好供 Azure AD 使用者登入。  Azure AD 使用者是這些裝置上的標準使用者，並且會接收指派的原則和必要應用程式。 目前不支援自助式和公司入口網站案例。

## <a name="notices"></a>通知

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>直接存取 Apple 註冊案例 <!--951869-->

對於在 2017 年 1 月之後建立的 Intune 帳戶，Intune 已經啟用使用 Azure Preview 入口網站中的「註冊裝置」工作負載直接存取 Apple 註冊案例。 Apple 註冊預覽原本只能從傳統 Intune 入口網站中的連結存取。 在 2017 年 1 月之前建立的 Intune 帳戶，將需要進行一次性移轉，才能在 Azure 中使用這些功能。 移轉的排程尚未宣布，但將會盡快提供詳細資料。 如果您現有的帳戶無法存取預覽，我們強烈建議您建立試用帳戶來測試新的體驗。

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Appx 在 Azure 上的 Intune 中的未來動態 <!-- 1000270 -->

在移轉到 Azure 上的 Intune 的過程中，我們將進行三個 appx 變更：

1. 在傳統 Intune 主控台中，新增只能部署到 MDM 註冊裝置的 appx 應用程式類型。
2. 重新規劃現有的 appx 應用程式類型，將目標僅限於透過 Intune PC 代理程式管理的電腦。
3. 透過移轉，將所有現有的 appxs 轉換成 MDM appxs。

#### <a name="how-does-this-affect-me"></a>此變更對我造成什麼影響？

這不會影響透過 Intune PC 代理程式管理之裝置上的任何現有部署。 不過移轉之後，您無法將這些移轉的 appxs 部署到透過 Intune PC 代理程式管理但先前未設為目標的任何新裝置。

#### <a name="what-action-do-i-need-to-take"></a>我需要採取什麼動作

移轉之後，如果您想要執行新的 PC 部署，您將必須再次重新上傳 appx 作為 PC 的 appx。 若要深入了解，請參閱 Intune 支援小組部落格上的 [Azure 上的 Intune 中的 Appx 變更 (英文)](https://aka.ms/appxchange)。  

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure 的 Intune 系統管理體驗公開預覽新增功能 <!--736542-->

在 2017 年初，我們會將完整系統管理體驗移轉到 Azure，以便在可透過圖形 API 擴充的新式服務平台上，對核心 EMS 工作流程進行強大的整合式管理。

新的試用租用戶將於本月開始看到 Azure 入口網站中新系統管理體驗的公開預覽。 在預覽狀態期間，將提供與現有 Intune 主控台相同與相當的功能。

Azure 入口網站中的系統管理體驗將使用已宣佈的新分組和目標設定功能；當您現有的租用戶移轉至新的分組體驗時，也會同時將您移轉，以預覽您租用戶的新系統管理體驗。 同時，如果您想要在移轉租用戶之前測試或查看任何新功能，請註冊新的 Intune 試用帳戶或查看[新文件](/intune/whats-new)。

> [!Note]
> 針對 Azure 入口網站預覽版，我們將在本月首度發行變更。 不過，基於 Intune 服務發行的方式不同，變更可能無法立即生效。  數個服務元件必須依序更新，才能使用新的入口網站功能。 Azure 入口網站預覽版的變更將於近日首度發行，屆時請務必試試看。 如需變更的完整清單，請參閱 [Microsoft Intune 預覽版中的新增功能](/intune/whats-new)。

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Azure 入口網站中將被取代的系統管理角色

在 Intune 傳統入口網站 (Silverlight) 中使用的現有行動應用程式管理 (MAM) 系統管理角色 (參與者、擁有者或唯讀) 在 Intune Azure 入口網站中會被取代為一組新的、完整的角色型系統管理控制 (RBAC)。 當您移轉至 Azure 入口網站之後，您必須將系統管理員重新指派至這些新的系統管理角色。 如需 RBAC 和新角色的詳細資訊，請參閱 [Microsoft Intune 的角色型存取控制](/intune/role-based-access-control)。

## <a name="whats-coming"></a>未來動態

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>改善適用於所有平台的公司入口網站應用程式登入體驗 <!--User Story 1132123-->

我們宣布將在幾個月內推出變更，以改進 Android、iOS 和 Windows 版 Intune 公司入口網站應用程式的登入體驗。 當 Azure AD 進行此變更時，新的使用者體驗會自動顯示在所有平台的公司入口網站應用程式上。 此外，使用者現在可以使用產生的一次性驗證碼，從另一部裝置登入公司入口網站。 在使用者需要不使用認證登入的情況下，這特別有用。

您可以在[應用程式 UI 的新增功能](whats-new-in-intune-app-ui.md)頁面上找到舊版登入體驗、使用認證的新登入體驗，以及從另一部裝置登入的新登入體驗的螢幕擷取畫面。

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>變更計畫：Intune 正在變更 Intune 合作夥伴入口網站體驗 <!-- 1050016 -->

我們會在 2017 年 5 月中旬的服務更新將 Intune 合作夥伴頁面從 manage.microsoft.com 移除。  

如果您是合作夥伴系統管理員，將無法再從 Intune 合作夥伴頁面代表客戶檢視或採取動作，但會需要登入在 Microsoft 的另外兩個合作夥伴入口網站的其中一個。

[Microsoft 合作夥伴中心](https://partnercenter.microsoft.com/)和 [Microsoft Office 365 合作夥伴系統管理中心](https://portal.office.com/)都能讓您登入所管理客戶的帳戶。 合作夥伴在此後請使用這兩個網站來管理客戶。


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple 要求必須更新 Application Transport Security <!--748318-->

Apple 宣布將會強制執行 Application Transport Security (ATS) 的特定需求。 ATS 可用來對透過 HTTPS 進行的所有應用程式通訊，強制執行更嚴格的安全性。 此變更會影響使用 iOS 公司入口網站應用程式的 Intune 客戶。

我們已透過 Apple TestFlight 方案，提供符合新 ATS 需求的 iOS 版公司入口網站應用程式。 如果您想試用該版本以便測試 ATS 合規性，請傳送電子郵件到 <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a>，並附上您的姓氏、名字、電子郵件地址和公司名稱。 如需詳細資訊，請檢閱我們的 [Intune 支援部落格](https://aka.ms/compportalats)。

### <a name="see-also"></a>另請參閱
* [Microsoft Intune 部落格](http://go.microsoft.com/fwlink/?LinkID=273882)
* [雲端平台藍圖](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure 預覽中的新增功能](https://docs.microsoft.com/intune/whats-new)
* [公司入口網站 UI 中的新增功能](/intune-classic/whats-new/whats-new-in-company-portal-ui)
* [新增功能封存](whats-new-archive.md)
