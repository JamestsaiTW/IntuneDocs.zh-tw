---
# required metadata

title: 透過 Microsoft Intune 使用受管理的瀏覽器原則管理網際網路存取 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 透過 Microsoft Intune 使用受管理的瀏覽器原則管理網際網路存取
受管理的瀏覽器是一個 Web 瀏覽應用程式，您可以在組織中使用 Microsoft Intune 來部署此應用程式。 受管理的瀏覽器原則會設定允許清單或封鎖清單，以限制受管理瀏覽器的使用者可瀏覽的網站。

由於此應用程式是受管理的應用程式，因此，您也可以將行動應用程式管理原則套用到此應用程式，例如，控制剪下、複製和貼上等功能的使用、防止螢幕擷取，同時也可確保使用者按一下內容的連結時，只會在其他受管理的應用程式中開啟。 如需詳細資訊，請參閱[在 Microsoft Intune 主控台中設定及部署行動應用程式管理原則](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)

> [!IMPORTANT]
>如果使用者從應用程式市集安裝受管理瀏覽器，而它不受 Intune 的管理，則會適用下列行為︰
iOS - 受管理瀏覽器應用程式可以當做基本 Web 瀏覽器，但某些功能將無法使用，且它不能存取來自其他 Intune 受管理應用程式的資料。
Android - 無法使用受管理瀏覽器應用程式。 如果使用者自行在版本早於 iOS 9 的 iOS 裝置上安裝受管理瀏覽器，它將不受您所建立的任何原則管理。 若要確保瀏覽器會受到 Intune 所管理，在您可將應用程式部署為受管理的應用程式以供其使用之前，使用者必須先解除安裝該應用程式。

在 iOS 9 及更新版本，如果使用者自行安裝受管理瀏覽器，將會提示他們允許它受到原則管理。

-   您可以針對下列裝置類型建立受管理的瀏覽器原則：

-   執行 Android 4 和更新版本的裝置

執行 iOS 7.1 及更新版本的裝置

## Intune Managed Browser 支援從 [Microsoft Intune 應用程式合作夥伴](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)開啟 Web 內容

1.  建立受管理的瀏覽器原則

2.  在 [Microsoft Intune 管理主控台](https://manage.microsoft.com)中，按一下 [原則] &gt; [新增原則]

    -   **設定下列其中一種 [軟體]  原則類型：**

    -   **受管理瀏覽器原則 (Android 4 及更新版本)**

    受管理的瀏覽器原則 (iOS 7.1 及更新版本)

3.  如需如何建立和部署原則的詳細資訊，請參閱[透過 Microsoft Intune 原則管理裝置上的設定和功能](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)主題。

|使用下表協助您設定受管理的瀏覽器原則設定：|設定名稱|
    |----------------|--------------------|
    |**詳細資料**|Name|
    |**輸入受管理瀏覽器原則的專用名稱，有助於您在 Intune 主控台中識別該原則。**|說明|
    |**提供可給予受管理瀏覽器原則概觀的說明，以及可協助您找到該說明的其他相關資訊。**|啟用允許清單或封鎖清單來限制受管理瀏覽器可開啟的 URL<br /><br />選取下列其中一個選項：<br /><br />允許受管理的瀏覽器只開啟下列 URL - 指定受管理的瀏覽器可開啟的 URL 清單。 禁止受管理的瀏覽器開啟下列 URL - 指定要禁止受管理的瀏覽器開啟的 URL 清單。<br />注意：您不能在同一個受管理的瀏覽器原則中同時包含允許和封鎖的 URL。|

4.  如需您可指定的 URL 格式詳細資訊，請參閱本主題中的適用於允許和封鎖 URL 的 URL 格式。

完成之後，請按一下 [儲存原則]

## 新的原則會顯示在 [原則]  工作區的 [設定原則]  節點中。
針對受管理的瀏覽器應用程式建立部署

> [!IMPORTANT]
> 建立受管理的瀏覽器原則之後，您接著可針對受管理的瀏覽器應用程式建立軟體部署，然後將它與您建立的受管理瀏覽器原則產生關聯。 受管理的瀏覽器原則不會使用與其他 Intune 原則相同的方式來進行部署。

此類型的原則必須與受管理的瀏覽器軟體套件相關聯。

部署應用程式，確定您在 [行動應用程式管理]  頁面上選取了受管理的瀏覽器原則，並將該原則與應用程式產生關聯。

## 如需如何部署應用程式的詳細資訊，請參閱[在 Microsoft Intune 中部署應用程式](deploy-apps-in-microsoft-intune.md)。

-   受管理瀏覽器的安全性與隱私權

-   在 iOS 裝置上，無法開啟使用者利用過期或未受信任的憑證瀏覽的網站。 受管理的瀏覽器不會使用使用者在其裝置上針對內建瀏覽器所做的設定。

-   這是因為受管理的瀏覽器沒有這些設定的存取權。

-   如果您在與受管理瀏覽器相關聯的行動應用程式管理原則中設定了 [需要簡單的 PIN 以進行存取]  或 [需要公司認證以進行存取]  選項，而且使用者按下驗證頁面上的說明連結，則他們可以瀏覽任何的網際網路網站，而無論是否已將其加入受管理瀏覽器原則的封鎖清單中。 受管理的瀏覽器可以在直接存取網站時，只封鎖網站的存取。

-   使用中繼服務 (例如翻譯服務) 存取網站時，它無法封鎖存取。

### 若要允許驗證，以及確定可以存取 Intune 文件，請從允許或封鎖清單設定中排除 &#42;.microsoft.com (一律會允許)。
關閉使用量資料 Microsoft 會自動收集有關受管理瀏覽器效能和使用的匿名資料，以改善 Microsoft 產品和服務，但是使用者可以使用裝置上的 [使用量資料] 設定，來關閉資料收集。

## 您無法控制這項資料的收集。

### 參考資訊
適用於允許和封鎖 URL 的 URL 格式

-   使用下列資訊，來了解您在允許和封鎖清單中指定 URL 時可使用的允許格式與萬用字元。

-   您可以根據下列許可模式清單中的規則，來使用萬用字元符號 '&#42;'。

-   確定您在清單中輸入 UTL 時，已在所有 URL 中加上 http 或 https 的前置詞。 您可以在位址中指定連接埠號碼。

    -   如果未指定連接埠號碼，將使用下列值：

    -   針對 http 使用連接埠 80

    針對 https 使用連接埠 443

-   不支援針對連接埠號碼使用萬用字元，例如 http://www.contoso.com:; 和 http://www.contoso.com: /

|使用下表來了解您在指定 URL 時可使用的允許模式：|URL|詳細資料|相符項|
    |-------|---------------|-----------|------------------|
    |不符合|http://www.contoso.com|比對單一頁面|www.contoso.com<br /><br />host.contoso.com<br /><br />www.contoso.com/images|
    |contoso.com/|http://contoso.com|比對單一頁面|contoso.com/<br /><br />host.contoso.com<br /><br />www.contoso.com/images|
    |www.contoso.com|http://www.contoso.com/&#42;|比對所有以 www.contoso.com 開始的 URL<br /><br />www.contoso.com<br /><br />www.contoso.com/images|www.contoso.com/videos/tvshows<br /><br />host.contoso.com|
    |host.contoso.com/images|http://&#42;.contoso.com/&#42;|比對 contoso.com 下方的所有子網域<br /><br />developer.contoso.com/resources<br /><br />news.contoso.com/images|news.contoso.com/videos|
    |contoso.host.com|http://www.contoso.com/images|比對單一資料夾|www.contoso.com/images|
    |www.contoso.com/images/dogs|http://www.contoso.com:80|使用連接埠號碼來比對單一頁面||
    |http://www.contoso.com:80|https://www.contoso.com|比對單一且安全的頁面|https://www.contoso.com|
    |http://www.contoso.com|http://www.contoso.com/images/&#42;|符合單一資料夾及所有子資料夾<br /><br />www.contoso.com/images/dogs|www.contoso.com/images/cats|

-   www.contoso.com/videos

    -   以下是一些您無法指定的輸入範例：

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP 位址

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

### http://www.contoso.com: /&#42;
如何解決允許和封鎖清單間的衝突 如果將多個受管理的瀏覽器原則部署到裝置且設定發生衝突，則會針對衝突評估這兩種模式 (允許或封鎖) 和 URL 清單。

-   一旦發生衝突，會採用下列行為：

-   如果每個原則中的模式都一樣，但 URL 清單不同，則不會在裝置上強制執行 URL。

-   如果每個原則中的模式都不同，但 URL 清單一樣，則不會在裝置上強制執行 URL。 如果裝置是第一次接收受管理的瀏覽器原則且有兩個原則發生衝突，則不會在裝置上強制執行 URL。

-   請使用 [原則]  工作區的 [原則衝突]  節點來檢視衝突。 如果裝置已經接收受管理的瀏覽器原則且部署的第二個原則含有發生衝突的設定，則會在裝置上保留原始的設定。


<!--HONumber=May16_HO2-->

