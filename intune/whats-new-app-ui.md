---
title: "Intune 終端使用者應用程式的 UI 更新"
description: "了解在與 Intune 搭配使用之終端使用者裝置上運作的應用程式 UI 變更。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1e2e1eb6da9114c689aae5eb06f7d7c780f35817
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2017
---
# <a name="ui-updates-for-intune-end-user-apps"></a>Intune 終端使用者應用程式的 UI 更新
了解我們針對您的使用者在這版 Microsoft Intune 中看到的應用程式 UI 做了哪些更新。 這可協助您進行使用者通訊以及您已建立來支援您部署的任何更新中自訂文件。 它也可協助您了解如何進一步對下列問題進行疑難排解：他們尋求有關公司入口網站使用支援的技術服務時所面臨的問題。

## <a name="week-of-june-12-2017"></a>2017 年 6 月 12 日一週

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Android 公司入口網站應用程式的應用程式保護原則現在有了新的使用者體驗<!--1305217-->
根據客戶的意見反應，我們已修改 Android 公司入口網站應用程式，以顯示 [存取公司內容] 按鈕。 目的是為了防止使用者在他們只需要存取支援應用程式保護原則 (Intune 行動應用程式管理的一項功能) 的應用程式時，不必要地進行註冊程序。

使用者將點選 [存取公司內容] 按鈕，而非開始註冊裝置。

![Android 公司入口網站應用程式的影像，這會在中間顯示「存取公司內容」大型文字，而不是如同標準案例提供立即註冊選項](./media/and_access_company_content_after_1706.png)

接著，使用者會進入公司入口網站來授權應用程式在其裝置上使用，公司入口網站會在其中確認他們的認證。

![公司入口網站的影像，正在確認登入。](./media/and_iwp_sign_in_auth_page_after_1706.png)

透過點選 [動作] 功能表，裝置仍可註冊以接受完整管理。

![Android 公司入口網站應用程式的影像 ，其中顯示畫面右上角的功能表含有仍可註冊裝置的選項。](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>透過 Windows 10 Creators Update 改進應用程式同步<!--676505-->

Windows 10 版公司入口網站應用程式現在會針對具有 Windows 10 Creators Update (版本 1703) 之裝置的應用程式安裝要求，自動初始化同步處理。 這會減少應用程式安裝在「待同步」狀態期間出現拖延的問題。 此外，使用者將能夠從應用程式內手動起始同步。

![Windows 10 公司入口網站應用程式的影像，在其中從公司入口網站應用程式市集下載 Microsoft Word 的作業處於擱置狀態。](./media/w10_download_pending_after_1706.png)

![Windows 10 公司入口網站應用程式的影像，其中顯示新的自動同步處理狀態與一則狀態訊息，該訊息指出裝置正在同步處理，並嘗試下載應用程式。](./media/w10_download_pending_syncing_after_1706.png)

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 公司入口網站新型引導式體驗 <!---1058938--->
Windows 10 的公司入口網站應用程式將包含之前尚未確定或註冊之裝置的引導式 Intune 逐步解說體驗。 此全新體驗提供逐步指示，引導使用者向 Azure Active Directory 註冊 (條件式存取功能所需)，以及 MDM 註冊 (裝置管理功能所需)。 此引導式體驗將可從公司入口網站首頁上存取。 如果使用者無法完成註冊，他們可以繼續使用該應用程式，但將經歷有限的功能。

此更新只會顯示在執行 Windows 10 年度更新版 (組建 1607) 或更高版本的裝置上。

![Windows 10 公司入口網站應用程式登陸頁面的影像，其中 [裝置] 清單中間的狀態訊息會告知使用者，他們所在的裝置尚未設定為公司用，以及使用者應選取該訊息來開始設定。](./media/win10_guided_enroll_select_setup_after_1706.png)

![Windows 10 公司入口網站應用程式設定頁面的影像，警告使用者他們需要將公司帳戶新增到此裝置，然後可以註冊它以接受管理。](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![Windows 10 公司入口網站應用程式已將公司帳戶新增到此裝置頁面的影像，告知使用者他們需要移至設定應用程式，然後選取 [連接] 以完成註冊。 這麼做之後，畫面會告知使用者他們必須返回公司入口網站應用程式，以完成註冊。](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![Windows 10 公司入口網站應用程式註冊以接受管理畫面的影像，其中顯示完成的狀態訊息，指出使用者的裝置現在已註冊，以及他們應點選 [下一步] 按鈕以繼續。](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![Windows 10 公司入口網站應用程式完成畫面的影像，可讓使用者知道它們已完整設定，以及裝置已在正確加入公司帳戶的情況下註冊。](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>新的功能表動作，可輕鬆地移除公司入口網站<!--1164569-->
根據使用者意見反應，Android 版公司入口網站應用程式已新增功能表動作，可從裝置起始公司入口網站的移除。 這個動作會從 Intune 管理移除裝置，讓使用者可以從裝置移除應用程式。

![Android 版公司入口網站應用程式的影像，右上角是開啟的動作功能表。 新的 [移除公司入口網站] 選項是第三個選項，位於 [我的設定檔] 和 [設定] 底下，在 [條款及條件]、[說明與意見反應] 和 [關於] 之上。](./media/android_remove_cp_menu_action_after_1705.png)

![確認對話方塊的影像，從動作功能表選取新的 [移除公司入口網站] 選項後就會顯示。 此對話方塊會告知使用者「若移除公司入口網站，您的裝置將不再受 IT 管理員管理，並可能移除對公司資料、公司應用程式及公司電子郵件的存取權。」 然後，它會要求使用者選取 [是] 以確認要移除公司入口網站應用程式。](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="week-of-june-5-2017"></a>2017 年 6 月 5 日一週

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS 版公司入口網站應用程式中應用程式磚的增強功能
我們已更新首頁上應用程式磚的設計，以反映您為公司入口網站設定的商標色彩。

**更新前**

![更新前的 iOS 版公司入口網站應用程式影像，顯示預先設定之 [所有 App]、[精選 App] 和 [類別] 的篩選影像。](./media/cp_ios_homepage_before_1705.png)

**更新後**

![更新後的 iOS 版公司入口網站應用程式影像，現在反映出可自由選取與組織相關的任何色彩。](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>iOS 版公司入口網站應用程式現在有帳戶選擇器可供使用
若使用者已使用工作或學校帳戶登入他們的 iOS 裝置上的其他 Microsoft 應用程式，第一次登入公司入口網站時，他們會看到新的帳戶選擇器。

![帳戶選擇器的影像，顯示一個名為 Robin Swanson 的測試使用者在兩個電子郵件地址之間選擇。 這兩個地址下方有一個按鈕，可讓使用者以其他的帳戶登入。](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a>2017 年 4 月

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Managed Browser 和公司入口網站的新圖示 <!--918433, 918431-->

Managed Browser 會同時收到 Android 和 iOS 版應用程式的更新圖示。 此新圖示會包含更新的 Intune 徽章，以使它與 Enterprise Mobility + Security (EM+S) 中的其他應用程式更一致。

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

公司入口網站也會收到 Android、iOS 和 Windows 版應用程式的更新圖示，以改進與 EM+S 中其他應用程式的一致性。 從四月起到五月底，這些圖示會逐漸在各平台發行。

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android 公司入口網站中的登入進度列指示器 <!--953374-->

Android 公司入口網站應用程式的更新會在使用者啟動或繼續執行應用程式時，顯示登入進度指示器。 該指示器會顯示新的狀態進度，一開始為「正在連線...」，接著依序為「正在登入...」和「正在檢查安全性需求...」，之後才允許使用者存取應用程式。

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>改進 Windows 10 公司入口網站應用程式的應用程式安裝狀態 <!--676495-->
Windows 10 公司入口網站應用程式現在於應用程式詳細資料頁面提供安裝進度列。 在執行 Windows 10 年度更新版與更新版本裝置上的新式應用程式可支援此功能。

__改進前__ ![舊版載入畫面的影像，其中狀態僅簡單地表示「安裝中」。](./media/cp_win10_install_status_before_1704.png)

__改進後__ ![更新版本的載入畫面影像，現在會顯示安裝進度列。](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>2017 年 2 月

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Android 版公司入口網站應用程式的新使用者體驗 <!--621622, announced 1702-->
從 3 月起，Android 版公司入口網站應用程式會遵循[素材設計方針](https://material.io/guidelines/material-design/introduction.html)建立更現代化的外觀與風格。 此改善的使用者體驗包括︰

* __色彩__︰索引標籤標頭可根據您的自訂調色盤上色。

![左側是更新前的 Android 版公司入口網站應用程式影像。 右側是更新後的 Android 版公司入口網站應用程式影像。 兩張影像顯示從 [應用程式]、[裝置] 以及 [連絡 IT] 三個可用索引標籤選取的 [裝置] 索引標籤。](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __介面__︰[應用程式] 索引標籤中已更新 [精選 App] 和 [所有 App] 按鈕。 [搜尋] 按鈕現在是浮動的動作按鈕。

![左側是更新前的 Android 版公司入口網站應用程式影像。 右側是更新後的 Android 版公司入口網站應用程式影像。 兩張影像顯示從 [應用程式]、[裝置] 以及 [連絡 IT] 三個可用索引標籤選取的 [應用程式] 索引標籤。](./media/CP_Android_AppsTab_BeforeAfter.png)

* __瀏覽__︰所有應用程式都會以索引標籤式的檢視顯示 [精選]、[所有] 與 [類別] 以方便瀏覽。 [連絡 IT] 已簡化以改善可讀性。

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>2017 年 1 月

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>現代化公司入口網站 <!--753980, announced 1701-->
從 2 月開始，公司入口網站將支援以沒有受管理裝置的使用者為目標的應用程式。 網站會使用新的對比色彩配置、動態圖例及「漢堡功能表」，與其他 Microsoft 產品和服務達成一致， ![公司入口網站左上角新增的漢堡功能表小型影像](./media/CP_hamburger_menu.png) 其包含技術服務連絡人詳細資料以及現有受管理裝置的相關資訊。 登陸頁面將會予以重新排列，以透過 [精選和最近更新] 應用程式的浮動切換來強調使用者可用的應用程式。

![在左側，影像會顯示具有其舊版 [應用程式]、[我的裝置] 以及 [精選] 和 [類別] 檢視的最新版公司入口網站。 在右側，影像會顯示具有重新整理之應用程式浮動切換、最近發佈的應用程式清單和更新過的 [類別] 檢視的公司入口網站更新版。](./media/CP_Website_BeforeAfter_Feb2016.png)

## <a name="coming-soon-in-the-ui"></a>即將在 UI 登場
我們計劃將更新使用者介面，以改進使用者的體驗。

> [!Note]
> 請注意，下列影像為預覽，宣告的產品可能與展示版本不同。

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>改善適用於所有平台的公司入口網站應用程式登入體驗 <!--User Story 1132123-->

我們宣布將在幾個月內推出變更，以改進 Android、iOS 和 Windows 版 Intune 公司入口網站應用程式的登入體驗。 當 Azure AD 進行此變更時，新的使用者體驗會自動顯示在所有平台的公司入口網站應用程式上。 此外，使用者現在可以使用產生的一次性驗證碼，從另一部裝置登入公司入口網站。 在使用者需要不使用認證登入的情況下，這特別有用。  

以下您可以看到舊版的登入體驗、使用認證的新登入體驗，以及從另一部裝置登入的新登入體驗。

__舊版登入體驗__

![公司入口網站登入頁面，具有一個人員位於代表網站的圖形前方的圖示。 下方是 [登入] 按鈕。 底部的連結會指向 Microsoft 隱私權與 Cookie 資訊。](./media/cp_ios_aad_signin_before_1704_001.png)

![點選 [登入] 之後，使用者會在此頁面上輸入其認證，此頁面會要求輸入使用者的電子郵件和密碼，以及提供解決密碼失敗的方法。](./media/cp_ios_aad_signin_before_1704_002.png)

![使用者提供密碼之後，公司入口網站應用程式會登入，並以載入列指出進度。](./media/cp_ios_aad_signin_before_1704_003.png)

__新的登入體驗__

![公司入口網站登入頁面，具有一個人員位於代表網站的圖形前方的圖示。 下方是 [登入] 按鈕。 底部的連結會指向 Microsoft 隱私權與 Cookie 資訊。](./media/cp_ios_aad_signin_after_1704_001.png)

![系統會在畫面上單獨提示使用者輸入電子郵件地址，而不是同時提示輸入電子郵件與密碼。](./media/cp_ios_aad_signin_after_1704_002.png)

![接受使用者的電子郵件地址後，系統會提示使用者輸入密碼。](./media/cp_ios_aad_signin_after_1704_003.png)

![經過驗證程序之後，公司入口網站應用程式會登入，並以載入列指出進度。](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__從另一部裝置登入時的新登入體驗__

![公司入口網站登入頁面，具有一個人員位於代表網站的圖形前方的圖示。 下方是 [登入] 按鈕。 底部的連結會指向 Microsoft 隱私權與 Cookie 資訊。](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

點選 [從另一部裝置登入] 連結。

![系統會顯示使用唯一密碼從工作電腦移至 aka.ms/devicelogin 頁面，並使用驗證碼進行登入的指示。](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

啟動瀏覽器並移至 [https://aka.ms/devicelogin](https://aka.ms/devicelogin)。

![使用者工作電腦上的瀏覽器 (而非公司入口網站應用程式) 的影像。 顯示的 [裝置登入] 頁面提示使用者輸入在公司入口網站應用程式中收到的驗證碼。](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

輸入您在公司入口網站應用程式中看到的驗證碼。 當您選取 [繼續] 時，您可以使用貴公司所支援的任何方法 (例如智慧卡) 進行驗證。

![使用者已將唯一驗證碼輸入至欄位，且 [裝置登入] 網站已要求確認 Intune 公司入口網站是接收驗證以登入的正確應用程式。](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![確認頁面指出使用者現已在其裝置上登入公司入口網站應用程式，並且可以關閉此頁面。](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

公司入口網站應用程式將會開始登入。

![經過驗證程序之後，公司入口網站應用程式會登入，並以載入列指出進度。](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)
### <a name="see-also"></a>請參閱
* [Microsoft Intune 部落格](http://go.microsoft.com/fwlink/?LinkID=273882)
* [雲端平台藍圖](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Intune 的新功能](https://docs.microsoft.com/intune/whats-new)