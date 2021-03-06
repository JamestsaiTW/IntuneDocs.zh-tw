---
title: Microsoft Intune 中 Windows 10 裝置的保護設定 - Azure | Microsoft Docs
description: 在 Microsoft Intune 中，於 Windows 10 裝置上，使用或設定 Endpoint Protection 設定以啟用 Windows Defender 功能，包括「應用程式防護」、「防火牆」、SmartScreen、加密和 Bitlocker、「惡意探索防護」、「應用程式控制」、「資訊安全中心」，以及本機裝置上的安全性。
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4c2df888e146a7f240530e5cbc6628dbce34cb61
ms.sourcegitcommit: b0b1030017e741d92c508130447a8242d9ad7a51
ms.translationtype: MTE75
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2019
ms.locfileid: "58342992"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>使用 Intune 保護裝置的 Windows 10 (及更新版本) 設定

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune 包含許多設定，可協助保護您的裝置。 本文描述您可以在 Windows 10 及更新版本裝置中啟用及設定的所有設定。 這些設定是為了控制安全性而在 Intune 的 Endpoint Protection 組態設定檔中建立，包括 BitLocker 和 Windows Defender。

若要設定 Windows Defender 防毒軟體，請參閱 [Windows 10 裝置限制](device-restrictions-windows-10.md#windows-defender-antivirus)。

## <a name="before-you-begin"></a>開始之前

[建立 Endpoint Protection 裝置組態設定檔](endpoint-protection-configure.md)。

## <a name="windows-defender-application-guard"></a>Windows Defender 應用程式防護

支援下列 Windows 10 版本：

- 企業
- Professional

使用 Microsoft Edge 時，Windows Defender 應用程式防護可保護您的環境免受組織不信任之網站的影響。 當使用者瀏覽未列在隔離之網路界限中的網站時，這些網站將在 Hyper-V 虛擬瀏覽工作階段中開啟。 信任的網站是由網路界限定義，並在 [裝置設定] 中進行設定。

應用程式防護只適用於 Windows 10 (64 位元) 裝置。 使用此設定檔會安裝 Win32 元件，以啟動應用程式防護。

- **應用程式防護**：[為 Edge 啟用] 表示開啟此功能，這會在 Hyper-V 虛擬化的瀏覽容器中開啟不受信任的網站。 **未設定**（預設值） 表示在裝置上開啟任何網站 （受信任和未受信任的）。
- **剪貼簿行為**：選擇本機電腦和應用程式防護虛擬瀏覽器之間允許的複製/貼上動作。
- **企業網站上的外部內容**：[封鎖] 自未經核准的網站載入內容。 [未設定] (預設) 表示非企業網站可在裝置上開啟。
- **從虛擬瀏覽器列印**：選擇 [允許] 可讓 PDF、XPS、本機及或網路印表機列印虛擬瀏覽器的內容。 [未設定] (預設) 會停用所有列印功能。
- **收集記錄檔**：[允許] 表示收集應用程式防護瀏覽工作階段內發生的事件記錄檔。 [未設定] (預設) 不會收集瀏覽工作階段內的任何記錄檔。
- **保留使用者產生的瀏覽器資料**：[允許] 儲存於應用程式防護虛擬瀏覽工作階段期間建立的使用者資料 (例如密碼、我的最愛和 Cookie)。 [未設定] (預設) 會在裝置重新啟動或使用者登出時，捨棄使用者下載的檔案和資料。
- **圖形加速**：選擇 [啟用] 以透過取得對虛擬圖形處理器的存取權，加快載入高圖形效能需求網站和視訊的速度。 [未設定] (預設) 會使用裝置的 CPU 來處理圖形，而不使用虛擬圖形處理器。
- **將檔案下載到主機檔案系統**：[啟用] 會讓使用者將檔案從虛擬化瀏覽器下載到主機作業系統。 [未設定] (預設) 會將檔案保留在本機裝置上，而不將檔案下載到主機檔案系統。

## <a name="windows-defender-firewall"></a>Windows Defender 防火牆

支援下列 Windows 10 版本：
- 首頁
- Professional
- 商務
- 企業
- 教育
- 行動電話
- 行動裝置企業版

### <a name="global-settings"></a>全域設定

這些設定適用於所有網路類型。

- **檔案傳輸通訊協定**：[封鎖] 表示停用可設定狀態的 FTP。 [未設定] (預設) 時，防火牆會執行可設定狀態的 FTP 篩選來允許次要連線。
- **刪除前的安全性關聯閒置時間**：*n* 秒偵測不到任何網路流量之後，即刪除安全性關聯。 輸入閒置時間 (以秒為單位)。
- **預先共用金鑰編碼**：選擇 [啟用] 以使用採用 UTF-8 的預先共用金鑰編碼。 [未設定] (預設) 會使用本機存放區值。
- **IPsec 豁免**：設定自 IPsec 豁免的特定流量，包括：
  - **芳鄰探索 IPv6 的 ICMP 類型代碼**
  - **ICMP**
  - **路由器探索 IPv6 的 ICMP 類型代碼**
  - **IPv4 和 IPv6 的 DHCP 網路流量**
- **憑證撤銷清單驗證**： 選擇 裝置如何驗證憑證撤銷清單。 選項包括 [停用 CRL 驗證]、[僅撤銷憑證上的 CRL 驗證會失敗]，以及 [發生任何錯誤 CRL 驗證都會失敗]。
- **每個金鑰處理模組都伺機比對驗證組**：[啟用] 會讓金鑰處理模組「只能」忽略不支援的驗證套件。 [未設定] 時，如果金鑰處理模組不支援驗證組中指定的所有驗證套件，則「必須」忽略整個驗證組。
- **封包佇列**：指定如何啟用接收端軟體的縮放比例，處理 IPsec 通道閘道案例中轉接接收和清除的加密文字。 此設定會確認保留封包順序。

### <a name="network-settings"></a>網路設定

這些設定適用於特定的網路類型，包括**網域 (工作場所) 網路**、**私人 (可探索) 網路**和**公用 (非可探索) 網路**。

#### <a name="general-settings"></a>一般設定  
- **Windows Defender 防火牆**：選擇 [啟用] 以開啟防火牆和進階安全性。 [未設定] (預設) 會允許所有網路流量，而不論任何其他原則設定為何。
- **隱形模式**：[封鎖] 防火牆在隱形模式下運作。 封鎖隱形模式可讓您也封鎖 **IPsec 安全封包豁免**。 [未設定] (預設) 會在隱形模式下執行防火牆，這有助於避免回應探查要求。
- **受防護**：[封鎖] 會關閉此功能。 [未設定] (預設) 會啟用此設定。 開啟此設定和 Windows Defender 防火牆時，則會封鎖所有連入流量，而不論任何其他原則設定為何。
- **多點傳送廣播的單點傳播回應**：當設定為 [封鎖] 時，則會停用多點傳送廣播的單點傳播回應。 一般而言，您不希望接收對多點傳送或廣播訊息的單點傳播回應。 這些回應可能表示拒絕服務 (DOS) 的攻擊，或者攻擊者嘗試探查已知的即時電腦。 [未設定] (預設) 會啟用此設定。
- **輸入通知**：當設定為 [封鎖] 時，則會在封鎖應用程式接聽連接埠期間向使用者隱藏通知。 [未設定] (預設) 會啟用此設定，並可在封鎖應用程式接聽連接埠期間向使用者顯示通知。
- **輸入連線的預設動作**：當設定為 [封鎖] 時，不會對輸入連線執行預設防火牆動作。 當設定為 [未設定] (預設) 時，則會對輸入連線執行預設防火牆動作。

#### <a name="rule-merging"></a>規則合併

- **來自本機存放區的已授權應用程式 Windows Defender 防火牆規則**：選擇 [啟用] 套用本機存放區中的防火牆規則，以便其受辨識並施行。 [未設定] (預設) 時，則會忽略且不會強制執行本機存放區中的已授權應用程式防火牆規則。
- **來自本機存放區的全域連接埠 Windows Defender 防火牆規則**：選擇 [啟用] 以套用本機存放區中要辨識並施行的全域連接埠防火牆規則。 [未設定] (預設) 時，則會忽略且不會強制執行本機存放區中的全域連接埠防火牆規則。
- **來自本機存放區的 Windows Defender 防火牆規則**：選擇 [啟用] 以套用本機存放區中要辨識並施行的防火牆規則。 [未設定] (預設) 時，則會忽略且不會強制執行來自本機存放區的防火牆規則。
- **來自本機存放區的 IPsec 規則**：選擇 [啟用] 以套用來自本機存放區的連線安全性規則，而不論結構描述或連線安全性規則版本為何。 [未設定] (預設) 時，則會忽略且不會強制執行來自本機存放區的連線安全性規則，而不論結構描述版本和連線安全性規則版本為何。

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen 設定

支援下列已安裝 Microsoft Edge 的 Windows 10 版本：
- 首頁
- Professional
- 商務
- 企業
- 教育
- 行動電話
- 行動裝置企業版

**設定**：

- **應用程式及檔案適用的 SmartScreen**：[啟用] Windows SmartScreen 執行檔案，以及執行應用程式。 SmartScreen 是雲端式防網路釣魚和反惡意程式碼元件。 [未設定] (預設) 會停用 SmartScreen。
- **未經驗證檔案的執行**：[封鎖] 終端使用者執行 Windows SmartScreen 尚未驗證的檔案。 [未設定] (預設) 會停用此功能，並讓終端使用者執行尚未驗證的檔案。

## <a name="windows-encryption"></a>Windows 加密

### <a name="windows-settings"></a>Windows 設定

支援下列 Windows 10 版本：

- Professional
- 商務
- 企業
- 教育
- 行動電話
- 行動裝置企業版

**設定**：

- **加密裝置**：[需要] 表示提示使用者啟用裝置加密。 根據 Windows 版本和系統設定，可能會要求使用者：  
  - 確認未啟用來自其他提供者的加密
  - 必須關閉 BitLocker 磁碟機加密，然後重新開啟 BitLocker
    
    如果已在另一種加密方法為使用中時開啟 Windows 加密，裝置可能會變得不穩定。 
- **加密儲存卡 (僅限行動裝置版)**：[需要] 表示加密裝置使用的任何抽取式儲存卡。 [未設定] (預設) 不需要儲存卡加密，而且不會提示使用者將它開啟。 這項設定只適用於 Windows 10 行動裝置版裝置。

### <a name="bitlocker-base-settings"></a>BitLocker 基本設定

支援下列 Windows 10 版本：

- 企業
- 教育
- 行動電話
- 行動裝置企業版
- Professional

基底設定是適用於所有資料磁碟機類型的通用 BitLocker 設定。 這些設定會管理終端使用者在所有資料磁碟機類型上可以修改的磁碟機加密工作或設定選項。

- **其他磁碟加密警告**：選取 [封鎖] 可在裝置上有其他磁碟加密服務時，停用警告提示。 [未設定] (預設) 允許顯示警告。
    - **允許標準使用者，若要啟用加密在 Azure AD Join**： 當您選擇**允許**，標準使用者/非系統管理員可以啟用 BitLocker 加密，當使用者登入。 此設定僅適用於已加入 Azure Active Directory (Azure ADJ) 的裝置。 [未設定] 會只允許系統管理員在裝置上啟用 BitLocker 加密。
      
      此設定僅適用於已加入 Azure Active Directory (Azure ADJ) 的裝置。 它也會要求將 [其他磁碟加密的警告] 設定設為 [封鎖]。
- **設定加密方法**：[啟用] 此設定可設定作業系統、資料和抽取式磁碟機的加密演算法。 [未設定] (預設) 時，BitLocker 會使用 XTS-AES 128 位元作為預設加密方法，或使用任何安裝指令碼指定的加密方法。
  - **作業系統磁碟機的加密**：選擇作業系統磁碟機的加密方法。 建議您使用 XTS-AES 演算法。
  - **固定式資料磁碟機的加密**：選擇固定式 (內建) 資料磁碟機的加密方法。 建議您使用 XTS-AES 演算法。
  - **抽取式資料磁碟機的加密**：選擇抽取式資料磁碟機的加密方法。 如果抽取式磁碟機與不是執行 Windows 10 的裝置搭配使用，則建議您使用 AES-CBC 演算法。

### <a name="bitlocker-os-drive-settings"></a>BitLocker 作業系統磁碟機設定
支援下列 Windows 10 版本：

- 企業
- 教育
- 行動電話
- 行動裝置企業版
- Professional

這些設定只套用在作業系統資料磁碟機。

- **啟動時的其他驗證**：選取 [需要] 可設定電腦啟動時的驗證需求，包括使用信賴平台模組 (TPM)。 選取 [未設定] (預設) 可在具有 TPM 的裝置上只設定基本選項。
  - **具有不相容 TPM 晶片的 BitLocker**：當裝置沒有相容 TPM 晶片時，[封鎖] (停用) 使用 BitLocker。 [未設定] 時，使用者可在不含相容 TPM 晶片的情形下使用 BitLocker。 BitLocker 可能需要密碼或啟動金鑰。
  - **相容的 TPM 啟動**：選擇允許、不允許，或需要 TPM 晶片。
  - **相容的 TPM 啟動 PIN**：選擇允許、不允許，或需要搭配 TPM 晶片使用啟動 PIN。 啟用啟動 PIN 需要與終端使用者互動。 
  - **相容的 TPM 啟動金鑰**：選擇允許、不允許，或需要搭配 TPM 晶片使用啟動金鑰。 啟用啟動金鑰需要與終端使用者互動。 
  - **相容的 TPM 啟動金鑰及 PIN**：選擇允許、不允許，或需要搭配 TPM 晶片使用啟動金鑰及 PIN。 啟用啟動金鑰及 PIN 需要與終端使用者互動。
- **最小 PIN 長度**：[啟用] 此設定可設定 TPM 啟動 PIN 的最小長度。 [未設定] (預設) 時，使用者可以設定介於 6 到 20 位數之任意長度的啟動 PIN。
  - **字元數下限**：輸入啟動 PIN 所需的字元數 (**4**-**20**)。
- **OS 磁碟機修復**：[啟用] 此設定可控制在未提供必要的啟動資訊時，如何復原受 BitLocker 保護的作業系統磁碟機。 [未設定] (預設) 時，BitLocker 修復支援預設修復選項。 預設允許 DRA，這是使用者選擇的修復選項，包括修復密碼和修復金鑰，以及未備份到 AD DS 的修復資訊。
  - **憑證式資料修復代理**：當設定為 [封鎖] 時，資料修復代理無法與受 BitLocker 保護的 OS 磁碟機搭配使用。 設定為 [未設定] (預設) 可啟用此設定，這可讓資料修復代理與受 BitLocker 保護的作業系統磁碟機搭配使用。
  - **使用者的修復密碼建立**：選擇是否允許、需要還是不允許使用者產生 48 位數的修復密碼。
  - **使用者的修復金鑰建立**：選擇是否允許、需要還是不允許使用者產生 256 位元的修復金鑰。
  - **BitLocker 安裝精靈中的修復選項**：設定為 [封鎖] 會讓使用者無法看到及變更修復選項。 當設定為 [未設定] (預設) 時，使用者可在開啟 BitLocker 時看到及變更修復選項。
  - **將 BitLocker 修復資訊儲存到 AD DS**：選擇 [啟用] 以將 BitLocker 修復資訊儲存到 Azure Active Directory (AAD)。 當設定為 [未設定] (預設) 時，不會將修復資訊儲存在 AAD 中。
  - **儲存在 AD DS 的 BitLocker 修復資訊**：設定 BitLocker 修復資訊的哪些部分會儲存在 Azure AD 中。 從下列選項進行選擇：
    - **備份修復密碼和金鑰封裝**
    - **只備份修復密碼**
  - **先將修復資訊儲存在 AD DS 再啟用 BitLocker**：**需要**此設定來阻止使用者開啟 BitLocker，除非 BitLocker 修復資訊成功儲存在 Azure Active Directory (AD) 中。 [未設定] (預設) 可讓使用者開啟 BitLocker，即使修復資訊未成功儲存在 Azure AD 中也一樣。
- **開機前修復訊息及 URL**：[啟用] 此設定可設定開機前金鑰修復畫面顯示的訊息及 URL。 [未設定] (預設) 會停用此功能。
  - **開機前修復訊息**：設定開機前修復訊息會向使用者顯示。 從下列選項進行選擇：
    - **使用預設修復訊息及 URL**
    - **使用空白修復訊息及 URL**
    - **使用自訂修復訊息**
    - **使用自訂修復 URL**

### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker 固定式資料磁碟機設定

支援下列 Windows 10 版本：

- 企業
- 教育
- 行動電話
- 行動裝置企業版
- Professional

**設定**：

- **不受 BitLocker 保護之固定式資料磁碟機的寫入權限**：設定為 [封鎖] 可提供不受 BitLocker 保護之資料磁碟機的唯讀權限。 [未設定] (預設) 時，則會有不受 BitLocker 保護之資料磁碟機的讀取和寫入權限。
- **固定式磁碟機修復**：[啟用] 此設定可控制在未提供必要的啟動資訊時，如何復原受 BitLocker 保護的固定式磁碟機。 [未設定] (預設) 會停用此功能。
  - **資料修復代理**：[封鎖] 資料修復代理與受 BitLocker 保護的固定式磁碟機原則編輯器搭配使用。 [未設定] (預設) 可讓資料修復代理與受 BitLocker 保護的固定式磁碟機搭配使用。
  - **使用者的修復密碼建立**：設定使用者是允許、需要還是不允許產生 48 位數的修復密碼。  
  - **使用者的修復金鑰建立**：設定使用者是允許、需要還是不允許產生 256 位元的修復金鑰。
  - **BitLocker 安裝精靈中的修復選項**：設定為 [封鎖] 會讓使用者無法看到及變更修復選項。 當設定為 [未設定] (預設) 時，使用者可在開啟 BitLocker 時看到及變更修復選項。
  - **將 BitLocker 修復資訊儲存到 Azure Active Directory**：選擇 [啟用] 以將 BitLocker 修復資訊儲存到 Azure Active Directory (Azure AD)。 [未設定] (預設) 時，不會將修復資訊儲存在 Azure AD 中。
  - **儲存在 Azure Active Directory 的 BitLocker 修復資訊**：設定 BitLocker 修復資訊的哪些部分會儲存在Azure AD 中。 選項包括：
    - **備份修復密碼和金鑰封裝**
    - **只備份修復密碼**
  - **先將修復資訊儲存在 Azure Active Directory 再啟用 BitLocker**：**需要**此設定以阻止使用者開啟 BitLocker，除非 BitLocker 修復資訊成功儲存在 Azure AD 中。 [未設定] (預設) 可讓使用者開啟 BitLocker，即使修復資訊未成功儲存在 Azure AD 中也一樣。

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker 抽取式資料磁碟機設定

支援下列 Windows 10 版本：

- 企業
- 教育
- 行動電話
- 行動裝置企業版
- Professional

**設定**：

- **不受 BitLocker 保護的抽取式資料磁碟機的寫入權限**：設定為 [封鎖] 可提供不受 BitLocker 保護之資料磁碟機的唯讀權限。 [未設定] (預設) 時，則會有不受 BitLocker 保護之資料磁碟機的讀取和寫入權限。
  - **在其他組織中設定的裝置的寫入權限**：[封鎖] 允許在其他組織中設定之裝置的寫入權限。 [未設定] (預設) 會拒絕寫入權限。

## <a name="windows-defender-exploit-guard"></a>Windows Defender 惡意探索防護

支援下列 Windows 10 版本：

- 首頁
- Professional
- 商務
- 企業
- 教育
- 行動電話
- 行動裝置企業版

使用 [Windows Defender 惡意探索防護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)來管理員工所用應用程式並減少受攻擊面。

### <a name="attack-surface-reduction"></a>攻擊表面縮減

- **標記對 Windows 本機安全性授權子系統進行的認證竊取**

  [協助預防搜尋惡意探索程式碼一般感染電腦所使用的動作和應用程式](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)。

#### <a name="rules-to-prevent-office-macro-threats"></a>預防 Office 巨集威脅的規則

禁止 Office 應用程式採取下列動作：

- **Office 應用程式插入其他處理序 (沒有例外狀況)**
- **Office 應用程式/巨集建立可執行檔內容**
- **Office 應用程式啟動子處理序**
- **Win32 從 Office 巨集程式碼匯入**

#### <a name="rules-to-prevent-script-threats"></a>預防指令碼威脅的規則

請封鎖下列項目以協助防止指令碼威脅：

- **混淆的 js/vbs/ps/巨集程式碼**
- **js/vbs 從網際網路執行裝載下載 (無例外狀況)**
- **從 PSExec 與 WMI 命令建立的程序**
- **從 USB 執行的未受信任及未簽署程序**
- **未符合普遍性、年齡或受信任清單準則的可執行檔**

#### <a name="rules-to-prevent-email-threats"></a>預防電子郵件威脅的規則

請封鎖下列項目以協助防止電子郵件威脅：

- **執行自電子郵件 (webmail/郵件用戶端) 卸除的可執行檔內容 (exe、dll、ps、js、vbs 等) (沒有例外狀況)**

#### <a name="rules-to-protect-against-ransomware"></a>可預防勒索軟體的規則
- **進階勒索軟體保護**

> [!TIP]
> [使用 Windows Defender 惡意探索防護來減少受攻擊面](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) \(英文\) 提供有關這些規則的更多詳細資料。

#### <a name="attack-surface-reduction-exceptions"></a>攻擊表面縮減例外狀況

- **從攻擊介面降低規則中排除的檔案和資料夾**：匯入/新增要從設定規則中排除的位置清單。

> [!IMPORTANT]
> 若要允許適當的安裝和執行 LOB 的 Win32 應用程式，反惡意程式碼設定應該從正在掃描排除下列目錄：<p>
> **在 X64 上用戶端機器**:<br>
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **在 X86 上的用戶端機器**:<br>
> *C:\Program Files\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*

### <a name="controlled-folder-access"></a>受控資料夾存取權

協助保護寶貴的資料不受惡意應用程式和威脅侵害，例如勒索軟體。

- **資料夾防護**：保護檔案和資料夾不受惡意應用程式進行不想要的變更。 您可以匯入**可存取受保護資料夾的應用程式清單**或手動新增它們。 您也可以上傳來新增**其他需要保護的資料夾清單**或手動新增它們。

### <a name="network-filtering"></a>網路篩選

- **網路保護**： 保護從任何應用程式的輸出連線到低信譽的 IP 位址或網域。 目的是為了防止具有存取權的應用程式中的使用者，網路釣魚詐騙、 惡意探索裝載站台，並在網際網路上的惡意內容。 它也會防止協力廠商瀏覽器連接到危險的網站。

  選項包括：

  - [未設定] (預設) 會停用此功能。 使用者和應用程式不被封鎖危險的網域連線。 系統管理員無法看到此 Windows Defender 資訊安全中心中的活動。
  - **啟用**開啟網路保護，並封鎖使用者和應用程式無法連線到危險的網域。 系統管理員可以看到此 Windows Defender 資訊安全中心中的活動。
  - **僅稽核**： 使用者和應用程式未遭到封鎖無法連線到危險的網域。 系統管理員可以看到此 Windows Defender 資訊安全中心中的活動。

  [Defender EnableNetworkProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)

### <a name="exploit-protection"></a>惡意探索保護

若要使用惡意探索保護，請建立包含所需系統和應用程式風險降低設定的 XML 檔案。 有兩種方法可供使用：

 1. PowerShell：使用一或多個 Get-ProcessMitigation、Set-ProcessMitigation 和 ConvertTo-ProcessMitigationPolicy PowerShell Cmdlet。 Cmdlet 會設定安全防護功能設定，並匯出它們的 XML 表示法。

 2. Windows Defender 資訊安全中心 UI：Windows Defender 資訊安全中心，按一下 [App 與瀏覽器控制]，然後捲動至結果畫面的底部，找到 [惡意探索保護]。 首先，使用 [系統設定] 與 [程式設定] 索引標籤來進行低風險的設定。 然後，在畫面底部找到 [匯出設定] 連結，匯出它們的 XML 表示。

上載 XML 檔案，讓您設定記憶體、控制流程以及原則限制，以封鎖**使用者編輯的惡意探索保護介面**。 XML 檔案中的設定可用來封鎖惡意探索應用程式。 [未設定] (預設) 不會推送自訂設定。 

## <a name="windows-defender-application-control"></a>Windows Defender 應用程式控制

支援下列 Windows 10 版本：

**行動裝置管理 (MDM)**： 
- Professional
- 商務
- 企業
- 教育
- 行動電話
- 行動裝置企業版

**群組原則管理**： 
- 企業

使用**應用程式控制程式碼完整性原則**，選擇其他由 Windows Defender 應用程式控制稽核或信任執行的應用程式。 Windows 元件和所有 Windows 市集的應用程式都自動受信任執行。

在**僅稽核**模式中執行時，不會封鎖應用程式。 **僅稽核**模式會在本機用戶端記錄檔中記錄所有事件。

應用程式控制一經啟用，就只能透過從**強制**變更為**僅稽核**模式來停用。 從**強制**變更為**未設定**模式的結果會是在指派的裝置上繼續強制使用應用程式控制。

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard

支援下列 Windows 10 版本：

- 企業

Windows Defender Credential Guard 可防止認證遭竊的攻擊。 它會隔離機密資料，因此只有特殊權限的系統軟體可以存取它們。

**Credential Guard** 設定包括：

- **停用**：如果先前是以 [在不含 UEFI 鎖定情況下啟用] 選項開啟 Credential Guard，此選項就會從遠端關閉它。

- **在包含 UEFI 鎖定的情況下啟用**：此選項無法使用登錄機碼或群組原則從遠端停用 Credential Guard。

    > [!NOTE]
    > 如果您使用此設定，而稍後想要停用 Credential Guard，則必須將群組原則設定為 [停用]。 此外，從每一部電腦實際清除 UEFI 設定資訊。 只要 UEFI 設定持續存在，就會啟用 Credential Guard。

- **在不含 UEFI 鎖定情況下啟用**：此選項可使用群組原則從遠端停用 Credential Guard。 使用此設定的裝置必須執行 Windows 10 1511 版及更新版本。

當您啟用 Credential Guard 時，也會啟用下列必要的功能：

- **虛擬化型安全性** (VBS)：在下次重新開機期間開啟。 虛擬化型安全性會使用 Windows Hypervisor 來提供安全性服務的支援。
- **安全開機與直接記憶體存取**：使用安全開機和直接記憶體存取 (DMA) 保護開啟 VBS。 DMA 保護需要硬體支援，而且只能在正確設定的裝置上啟用。

## <a name="windows-defender-security-center"></a>Windows Defender 資訊安全中心

支援下列 Windows 10 版本：

- 首頁
- Professional
- 商務
- 企業
- 教育
- 行動電話
- 行動裝置企業版

Windows Defender 資訊安全中心是以個別的應用程式或各個功能的處理序運行。 它會透過重要訊息中心顯示通知。 它充當收集器，或查看狀態及執行每項功能一些設定的單一位置。 詳細資訊請參閱 [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) 文件。

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender 資訊安全中心應用程式和通知

封鎖使用者對「Windows Defender 資訊安全中心」應用程式之各種區域的存取。 隱藏區段也會封鎖相關通知。

- **病毒與威脅防護**
- **裝置效能與健全狀況**
- **防火牆與網路保護**
- **應用程式與瀏覽器控制**
- **家長監護選項**
- **應用程式顯示區中的通知**：選擇要向使用者顯示的通知。 非重大通知包括 Windows Defender 防毒軟體活動摘要，包括掃描完成時的通知。 所有其他通知都被視為重大通知。

#### <a name="it-contact-information"></a>IT 連絡人資訊

提供要顯示在「Windows Defender 資訊安全中心」應用程式和應用程式通知中的 IT 連絡人資訊。 您可以選擇 [Display in app and in notifications] \(在應用程式和通知中顯示)、[Display only in app] \(只在應用程式中顯示)、[Display only in notifications] \(只在通知中顯示) 或 [Don't display] \(不顯示)。 輸入 **IT 組織名稱**，以及至少下列其中一個連絡選項：

- **IT 部門電話號碼或 Skype 識別碼**
- **IT 部門電子郵件地址**
- **IT 支援網站 URL**

## <a name="local-device-security-options"></a>本機裝置安全性選項

支援下列 Windows 10 版本：
 
- 首頁
- Professional
- 商務
- 企業
- 教育

您可以使用這些選項來設定 Windows 10 裝置上的本機安全性設定。

### <a name="accounts"></a>帳戶

- **新增 Microsoft 帳戶**：設定為 [封鎖] 可防止使用者在裝置上新增 Microsoft 帳戶。 當設定為 [未設定] (預設) 時，使用者可在裝置上使用 Microsoft 帳戶。
- **不使用密碼進行遠端登入**：[封鎖] 僅允許具有空白密碼之本機帳戶使用裝置的鍵盤登入。 [未設定] (預設) 可讓具有空白密碼的本機帳戶從實體裝置以外的位置登入。

#### <a name="admin"></a>系統管理員

- **本機系統管理員帳戶**：設定為 [啟用] 可允許本機系統管理員帳戶。 設定為 [未設定] (預設) 可停用本機系統管理員帳戶。
- **重新命名系統管理員帳戶**：定義與系統管理員帳戶的安全性識別碼 (SID) 相關聯的其他帳戶名稱。

#### <a name="guest"></a>Guest

- **來賓帳戶**：設定為 [啟用] 可允許本機來賓帳戶。 設定為 [未設定] (預設) 可停用本機來賓帳戶。
- **重新命名來賓帳戶**：定義與來賓帳戶的安全性識別碼 (SID) 相關聯的其他帳戶名稱。

### <a name="devices"></a>裝置

- **卸除未登入的裝置**：設定為 [封鎖] 可讓使用者按停駐可攜式裝置的實體退出按鈕，安全地卸除裝置。 [未設定] (預設) 需要使用者登入裝置並收到權限，才能卸除裝置。
- **安裝共用印表機的印表機驅動程式**：[啟用] 時，任何使用者都可以安裝印表機驅動程式作為連線到共用印表機的一部分。 [未設定] (預設) 時，只有系統管理員可以安裝印表機驅動程式作為連線到共用印表機的一部分。
- **限制本機作用中使用者的 CD-ROM 存取**：[啟用] 時，只有以互動方式登入的使用者可以使用 CD-ROM 媒體。 如果啟用此原則，而且沒有任何人以互動方式登入，則會透過網路存取 CD-ROM。 [未設定] (預設) 時，任何人都可以存取 CD-ROM。
- **格式化及退出卸除式媒體**：定義可以格式化並退出卸除式 NTFS 媒體的人員：
  - **未設定**
  - **系統管理員**
  - **系統管理員與進階使用者**
  - **系統管理員和互動式使用者**

### <a name="interactive-logon"></a>互動式登入

- **鎖定畫面閒置，直到螢幕保護裝置啟動的分鐘數**：輸入互動式桌面登入畫面閒置，直到螢幕保護裝置啟動的最長分鐘數。
- **需要 CTRL+ALT+DEL 才能登入**：設定為 [啟用] 可讓使用者不需要按 CTRL+ALT+DEL 就能登入。 設定為 [未設定] (預設) 則需要使用者按 CTRL+ALT+DEL 才能登入 Windows。
- **智慧卡移除行為**：判斷從智慧卡讀卡機中移除登入使用者的智慧卡時會發生的情況。 選項包括：

  - **鎖定工作站**：移除智慧卡時鎖定工作站。 此選項可讓使用者離開該區域、攜帶智慧卡，並且仍然維持受保護的工作階段。
  - **強制登出**：移除智慧卡時，使用者會自動登出。
  - **在遠端桌面服務工作階段時中斷連線**：移除智慧卡會中斷工作階段的連線，但無需登出使用者。 此選項可讓使用者插入智慧卡並在稍後繼續工作階段，或在另一部配備智慧卡讀取器的電腦上，而不需要再次登入。 如果工作階段是本機，則此原則的功能與鎖定工作站相同。

    [LocalPoliciesSecurity 選項](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior)提供更多詳細資料。

#### <a name="display"></a>顯示

- **鎖定螢幕上的使用者資訊**：設定在工作階段鎖定時顯示的使用者資訊。 如果未設定，則會顯示使用者顯示名稱、網域及使用者名稱。
  - **未設定**  
  - **使用者顯示名稱、網域及使用者名稱**
  - **僅使用者顯示名稱**
  - **不顯示使用者資訊**
- **隱藏上次登入的使用者**：[啟用] 會隱藏使用者名稱。 [未設定] (預設) 會顯示使用者名稱。
- **在登入時隱藏使用者名稱**：[啟用] 會隱藏使用者名稱。 [未設定] (預設) 會顯示使用者名稱。
- **登入訊息標題**：設定給登入之使用者的訊息標題。
- **登入訊息文字**：設定給登入之使用者的訊息文字。

### <a name="network-access-and-security"></a>網路存取與安全性

- **具名管道和共用的匿名存取**：[未設定] (預設) 會限制共用和具名管道設定的匿名存取。 適用於可以匿名存取的設定。
- **SAM 帳戶的匿名列舉**：[允許] 匿名使用者列舉 SAM 帳戶。 Windows 允許匿名使用者列舉網域帳戶和網路共用的名稱。
- **SAM 帳戶和共用的匿名列舉**：[未設定] (預設) 表示匿名使用者可以列舉網域帳戶和網路共用的名稱。 若要防止 SAM 帳戶和共用的匿名列舉，請設定為 [封鎖]。
- **密碼變更時儲存的 LAN Manager 雜湊值**：在下次密碼變更時，選擇 [允許] LAN Manager (LM) 儲存新密碼的雜湊值。 當設定為 [未設定] (預設) 時，不會儲存雜湊值。
- **PKU2U 驗證要求**：[封鎖] 此裝置的 PKU2U 驗證要求以使用線上身分識別。 [未設定] (預設) 可允許這些要求。
- **限制 SAM 的遠端 RPC 連線**： 設為**允許**拒絕從遠端 RPC 呼叫到安全性帳戶管理員 (SAM)，它會儲存使用者帳戶和密碼的使用者和群組。 **允許**也可讓您變更預設安全性描述元定義語言 (SDDL) 字串，以明確允許或拒絕使用者和群組來進行這些遠端呼叫。 **未設定**（預設值） 會使用預設安全性描述元，並可讓使用者和群組來進行 sam 的遠端 RPC 呼叫。
  - **安全性描述元**

### <a name="recovery-console-and-shutdown"></a>修復主控台和關閉

- **關閉時清除虛擬記憶體分頁檔**：設定為 [啟用] 可在裝置關機時清除虛擬記憶體分頁檔。 [未設定] 不會清除虛擬記憶體。
- **未登入關閉**：[封鎖] 會隱藏 Windows 登入畫面上的關機選項。 使用者必須登入裝置，再關機。 [未設定] (預設) 可讓使用者從 Windows 登入畫面關閉裝置。

### <a name="user-account-control"></a>使用者帳戶控制

- **不安全位置的 UIA 完整性**：當設定為 [封鎖] 時，只有檔案系統安全位置中的應用程式才能以 UIAccess 完整性執行。 [未設定] (預設) 可讓應用程式以 UIAccess 完整性執行，即使應用程式不在檔案系統的安全位置中也一樣。
- **將每個使用者位置的檔案及登錄寫入失敗虛擬化**： 當設定為**已啟用**，應用程式將資料寫入受保護的位置失敗。 當設定為 [未設定] (預設) 時，應用程式寫入失敗會在執行階段重新導向至檔案系統和登入的已定義使用者位置。
- **僅針對已簽署與驗證過的可執行檔，提升其權限**：設定為 [啟用] 會對可執行檔強制執行 PKI 憑證路徑驗證，之後其才能執行。 設定為 [未設定] (預設) 不會強制執行 PKI 憑證路徑驗證，可執行檔就能執行。

#### <a name="uia-elevation-prompt-behavior-settings"></a>UIA 提高權限提示的行為設定

- **針對系統管理員的提高權限提示**：在管理員核准模式中定義系統管理員提高權限提示的行為：
  - **提高權限而不提示**
  - **在安全桌面提示輸入認證**
  - **在安全桌面提示要求同意**
  - **提示輸入認證**
  - **提示決定是否同意**
  - **未設定**：提示要求同意非 Windows 二進位檔案
- **針對標準使用者的提高權限提示**：定義標準使用者提高權限提示的行為：
  - **自動拒絕提高權限要求**
  - **在安全桌面提示輸入認證**
  - **未設定**：認證的提示
- **將提高權限提示路由傳送至使用者的互動式桌面**：[啟用] 可讓所有的提高權限要求前往互動式使用者的桌面，而不是安全桌面。 系統會使用系統管理員和標準使用者的任何提示行為原則設定。 [未設定] (預設) 會強制所有提高權限要求前往安全桌面，而不論系統管理員和標準使用者的任何提示行為原則設定為何。
- **針對應用程式安裝的提高權限提示**：當設定為 [啟用] 時，不會偵測應用程式安裝套件，也不會提示提高權限。 當設定為 [未設定] (預設) 時，若應用程式安裝套件需要較高的權限，則會提示使用者輸入系統管理使用者名稱和密碼。
- **UIA 提高權限提示不使用安全桌面**：[啟用] 表示允許 UIAccess 應用程式不使用安全桌面來提示提高權限。 [未設定] (預設) 時，提高權限提示會使用安全桌面。

#### <a name="admin-approval-mode-settings"></a>管理員核准模式設定

- **內建系統管理員的管理員核准模式**：[啟用] 可讓內建系統管理員帳戶使用「管理員核准模式」。 任何需要提高權限的作業會提示使用者核准該作業。 [未設定] (預設) 會以完整管理員權限執行所有應用程式。
- **以管理員核准模式執行所有管理**：設定為 [啟用] 可停用「管理員核准模式」及所有相關 UAC 原則設定。 [未設定] (預設) 會啟用「管理員核准模式」。

### <a name="microsoft-network-client"></a>Microsoft 網路用戶端

- **數位簽章通訊 (如果伺服器同意)**：判斷 SMB 用戶端是否會交涉 SMB 封包簽署。 [未設定] 或啟用 (預設) 時，Microsoft 網路用戶端會要求伺服器在工作階段設定期間執行 SMB 封包簽署。 如果在伺服器上啟用封包簽署，則會交涉封包簽署。 若設定為 [停用]，SMB 用戶端永遠不會交涉 SMB 封包簽署。
- **將未加密的密碼傳送到協力廠商 SMB 伺服器**：當設定為 [啟用] 時，伺服器訊息區 (SMB) 重新導向程式可將純文字密碼傳送給驗證期間不支援密碼加密的非 Microsoft SMB 伺服器。 [未設定] (預設) 時，則會加密密碼。

### <a name="microsoft-network-server"></a>Microsoft 網路伺服器

- **數位簽章通訊 (如果用戶端同意)**：判斷 SMB 伺服器是否會與要求 SMB 封包簽署的用戶端協商 SMB 封包簽署。 當設定為 [啟用] 時，Microsoft 網路伺服器會根據用戶端要求交涉 SMB 封包簽署。 就是說，如果用戶端已啟用封包簽署，則會交涉封包簽署。 [未設定] 或停用 (預設) 時，SMB 用戶端永遠不會交涉 SMB 封包簽署。
- **數位簽章通訊 (自動)**：判斷 SMB 伺服器元件是否需要封包簽署。 當設定為 [啟用] 時，Microsoft 網路伺服器不會與 Microsoft 網路用戶端通訊，除非該用戶端同意 SMB 封包簽署。 [未設定] 或停用 (預設) 時，用戶端和伺服器之間會交涉 SMB 封包簽署。

## <a name="next-steps"></a>後續步驟

設定檔已建立，但還不會執行任何動作。 接下來，[指派設定檔](device-profile-assign.md)並[監視其狀態](device-profile-monitor.md)。

設定 [macOS](endpoint-protection-macos.md) 裝置上的 Endpoint Protection 設定。
