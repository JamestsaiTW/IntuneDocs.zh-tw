---
title: Microsoft Intune 的網路需求與頻寬詳細資料
titleSuffix: ''
description: 檢閱 Intune 的網路設定需求與頻寬詳細資料。
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40f9ada715570de7b5b2f95292b7ed0d238242d2
ms.sourcegitcommit: 04d29d47b61486b3586a0e0e5e8e48762351f2a3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2019
ms.locfileid: "59570789"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Intune 網路設定需求與頻寬

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

本指南可協助 Intune 系統管理員了解 Intune 服務的網路需求。 您可以使用這項資訊來了解頻寬需求，以及 Proxy 設定所需的 IP 位址和連接埠設定。

## <a name="average-network-traffic"></a>平均網路流量
此表格列出每個用戶端透過網路傳輸的一般內容的估計大小和頻率。

> [!NOTE]
> 為確保裝置從 Intune 接收更新與內容，它們必須定期連線到網際網路。 接收更新或內容所需要的時間不定，但應保持每天至少 1 小時持續連線到網際網路。

|內容類型|大小近似值|頻率和詳細資料|
|----------------|--------------------|-------------------------|
|Intune 用戶端安裝<br /><br />**以下是除了安裝 Intune 用戶端以外的需求**|125 MB|**一次**<br /><br />用戶端下載的大小會因用戶端電腦的作業系統而不同。|
|用戶端註冊套件|15 MB|**一次**<br /><br />當此內容類型有更新時，可能會進行其他下載。|
|Endpoint Protection 代理程式|65 MB|**一次**<br /><br />當此內容類型有更新時，可能會進行其他下載。|
|Operations Manager 代理程式|11 MB|**一次**<br /><br />當此內容類型有更新時，可能會進行其他下載。|
|原則代理程式|3 MB|**一次**<br /><br />當此內容類型有更新時，可能會進行其他下載。|
|Remote Assistance via Microsoft Easy Assist 代理程式|6 MB|**一次**<br /><br />當此內容類型有更新時，可能會進行其他下載。|
|日常用戶端作業|6 MB|**每日**<br /><br />Intune 用戶端會定期與 Intune 服務通訊，以檢查是否有更新和原則，並將用戶端的狀態回報給服務。|
|Endpoint Protection 惡意程式碼定義更新|不定<br /><br />通常為 40 KB 到 2 MB|**每日**<br /><br />最多一天 3 次。|
|Endpoint Protection 引擎更新|5 MB|**每月**|
|軟體更新|不定<br /><br />大小依您部署的更新而定。|**每月**<br /><br />一般情況下，軟體更新會在每個月的第二個星期二發佈。<br /><br />剛完成註冊或部署的電腦在下載先前發行的整組更新時，可能也會佔用較大的網路頻寬。|
|Service Pack|不定<br /><br />大小會因您部署的每個 Service Pack 而不同。|**不定**<br /><br />視您何時部署 Service Pack 而定。|
|軟體發佈|不定<br /><br />大小依您部署的軟體而定。|**不定**<br /><br />視您何時部署軟體而定。|

## <a name="ways-to-reduce-network-bandwidth-use"></a>減少網路頻寬用量的方式
您可以使用下列其中一或多種方法，減少 Intune 用戶端佔用的網路頻寬。

### <a name="use-a-proxy-server-to-cache-content-requests"></a>使用 Proxy 伺服器快取內容要求
Proxy 伺服器可以快取內容來減少重複的下載，並減少網際網路內容佔用的網路頻寬。

接收用戶端內容要求的快取 Proxy 伺服器可以擷取該內容，並快取網頁回應和下載。 伺服器會使用快取的資料回應用戶端的後續要求。

下列一般設定適用於快取 Intune 用戶端內容的 Proxy 伺服器。


|          設定           |           建議值           |                                                                                                  詳細資料                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         快取大小         |             5 GB 至 30 GB             | 這個值會根據網路中的用戶端電腦數目以及您使用的設定而不同。 為了避免系統太快刪除檔案，請根據您的環境調整快取的大小。 |
| 個別快取檔案大小 |                950 MB                 |                                                                     某些快取 Proxy 伺服器可能沒有提供這項設定。                                                                     |
|   要快取的物件類型    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Intune 封裝是背景智慧型傳送服務 (BITS) 下載作業透過 HTTP 擷取的 CAB 檔。                                               |
> [!NOTE]
> 如果您使用 Proxy 伺服器快取內容要求，此時只會將用戶端到 Proxy 和 Proxy 到 Intune 之間的通訊加密。 用戶端至 Intune 的端至端連線不會加密。

如需有關如何使用 Proxy 伺服器快取內容的詳細資訊，請參閱您的 Proxy 伺服器解決方案的文件。

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>在電腦上使用背景智慧型傳送服務 (BITS)
您可以在自己設定的小時時間內，於 Windows 電腦上使用 BITS 以減少網路頻寬。 您可以在 Intune 代理程式原則的 [網路頻寬] 頁面中設定 BITS 原則。

> [!NOTE]
> 對於 Windows 上的 MDM 管理，只有 MobileMSI 應用程式類型的作業系統管理介面會使用 BITS 進行下載。 AppX/MsiX 會使用自己的非 BITS 下載堆疊，而且 Win32 應用程式會透過 Intune 代理程式使用傳遞最佳化，而非 BITS。

若要深入了解 BITS 和 Windows 電腦，請參閱 TechNet Library 中的[背景智慧型傳送服務](http://technet.microsoft.com/library/bb968799.aspx)。

### <a name="use-branchcache-on-computers"></a>在電腦上使用 BranchCache
Intune 用戶端可以使用 BranchCache 來減少廣域網路 (WAN) 流量。 下列作業系統支援 BranchCache：

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

若要使用 BranchCache，用戶端電腦必須已啟用 BranchCache，接著再完成**分散式快取模式**的設定。

在電腦上安裝 Intune 用戶端時，預設會啟用 BranchCache 和分散式快取模式。 但如果群組原則已停用 BranchCache，Intune 不會覆寫該原則，因此 BranchCache 會保持停用。

如果使用 BranchCache，請與組織中其他系統管理員合作管理群組原則和 Intune 防火牆原則。 請確定他們沒有部署停用 BranchCache 或防火牆例外的原則。 如需 BranchCache 的詳細資訊，請參閱 [BranchCache 概觀](http://technet.microsoft.com/library/hh831696.aspx)。

## <a name="network-communication-requirements"></a>網路通訊需求

可讓您管理的裝置與雲端式服務所需的端點之間進行網路通訊。

Intune 屬於僅限雲端的服務，因此不需要內部部署基礎結構，例如伺服器或閘道。

若要管理位於防火牆和 Proxy 伺服器後方的裝置，您必須啟用 Intune 的通訊功能。

- Proxy 伺服器必須同時支援 **HTTP (80)** 和 **HTTPS (443)**，因為 Intune 用戶端會使用這兩種通訊協定
- 針對某些工作 (例如下載軟體更新)，Intune 會需要未驗證的 Proxy 伺服器存取 manage.microsoft.com

您可以修改個別用戶端電腦上的 Proxy 伺服器設定。 也可以使用群組原則設定，針對位於指定 Proxy 伺服器後方的所有用戶端電腦變更設定。


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

受管理裝置需要進行可讓 [所有使用者] 穿過防火牆存取服務的設定。

下表列出 Intune 用戶端存取的連接埠和服務：

|**網域**|**IP 位址**|
|---------------------|-----------|
|login.microsoftonline.com | 更多資訊請參閱 [Office 365 URL 與 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212|
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|52.169.82.238|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|fef.amsua0202.manage.microsoft.com|52.165.165.17|
|fef.amsua0402.manage.microsoft.com|40.69.157.122|
|fef.amsua0502.manage.microsoft.com|13.85.68.142|
|fef.amsua0602.manage.microsoft.com|52.161.28.64|
|fef.amsub0102.manage.microsoft.com|40.118.98.207|
|fef.amsub0202.manage.microsoft.com|40.69.208.122|
|fef.amsub0302.manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|






### <a name="apple-device-network-information"></a>Apple 裝置網路資訊


|用途|主機名稱 (IP 位址/子網路)|通訊協定|Port|
|-----|--------|------|-------|
|透過 Apple Push Notification Service (APNS) 從 Intune 服務接收推播通知。 請參閱 [Apple 文件](https://support.apple.com/en-us/HT203609) \(英文\)|                                    gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |
|透過 Apple Push Notification Service (APNS) 將意見反應傳送至 Intune 服務|                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |
|擷取並顯示來自 Apple 伺服器的內容|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|與 APNS 伺服器通訊|#-courier.push.apple.com (17.0.0.0/8)<br>'#' 是從 0 至 50 的隨機數字。|    TCP     |  5223 和 443  |
|各種功能，包括存取全球資訊網、iTunes store、macOS app store、iCloud、Messaging 等等。 |phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 或 443   |

如需詳細資訊，請參閱 Apple 提供的 [Apple 軟體產品使用的 TCP 和 UDP 連接埠](https://support.apple.com/en-us/HT202944) \(英文\)、[關於 macOS、iOS 和 iTunes 伺服器主機連線與 iTunes 背景處理序](https://support.apple.com/en-us/HT201999) \(英文\)，以及[如果您的 macOS 和 iOS 用戶端未取得 Apple 推播通知](https://support.apple.com/en-us/HT203609) \(英文\)。
