---
title: 如何監視應用程式保護原則
titleSuffix: Microsoft Intune
description: 本主題描述如何監視 Intune 中行動應用程式管理原則的合規性狀態。
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d8c34f1947a0abaa4cdf0bbcd65dcf31e4c11ff
ms.sourcegitcommit: 93286c22426dcb59191a99e3cf2af4ff6ff16522
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2019
ms.locfileid: "59566785"
---
# <a name="how-to-monitor-app-protection-policies"></a>如何監視應用程式保護原則
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

您可以從 [Azure 入口網站](https://portal.azure.com)的 Intune 應用程式保護窗格中，監視已套用到使用者的行動應用程式管理 (MAM) 原則的合規性狀態。 此外，您可以找到受 MAM 原則影響的使用者相關資訊、MAM 原則合規性狀態，以及您的使用者可能發生的任何問題。

您有三個不同的位置可以監視 MAM 原則的合規性狀態︰
-   摘要檢視
-   詳細檢視
-   報告檢視

> [!NOTE]
> 如需建立應用程式防護原則的相關詳細資訊，請參閱[如何建立及指派應用程式防護原則](app-protection-policies.md)。

## <a name="summary-view"></a>摘要檢視

1. 登入 [Azure 入口網站](https://portal.azure.com)。
2. 選擇 [All services] (所有服務) > [Intune]。 Intune 位於 [Monitoring + Management] (監視 + 管理) 區段。
3. 在 [Intune] 窗格上，選擇 [用戶端應用程式]。
4. 在 [用戶端應用程式] 工作負載中，從 [監視] 區段選擇 [應用程式防護狀態]，以查看摘要檢視：

![[Intune 行動應用程式管理] 窗格上的 [摘要] 磚](./media/app-protection-user-status-summary.png)

- **指派的使用者**：您公司中使用與工作內容原則建立關聯之應用程式的指派使用者當中，受到保護且授權的總數，以及未受保護且未授權的總數。
- **已標幟的使用者**：遇到問題的使用者數目。 [已標幟的使用者] 下會報告已進行 JB (iOS) 或 Root (Android) 破解的裝置。 這裡將會報告具有透過 Google SafetyNet 裝置證明檢查 (如果 IT 系統管理員有開啟) 標幟之裝置的使用者。 
- **iOS 使用者狀態**和 **Android 使用者狀態**：已使用應用程式並在相關平台工作內容中獲派原則的使用者數目。 此資訊顯示由原則管理的使用者數目，以及使用工作內容中任何原則未設為目標之應用程式的使用者數目。 您可以考慮將這些使用者新增至原則。
- **最受保護的 iOS 應用程式**：根據最常使用的 iOS 應用程式，這項資訊會顯示受保護與未受保護之 iOS 應用程式的數目。
- **最受保護的 Android 應用程式**：根據最常使用的 Android 應用程式，這項資訊會顯示受保護與未受保護之 Android 應用程式的數目。
- **經過頂級設定的未註冊 iOS 應用程式**：根據未註冊裝置最常使用的 iOS 應用程式，這項資訊會顯示已設定之 iOS 應用程式的數目。
- **經過頂級設定的未註冊 Android 應用程式**：根據未註冊裝置最常使用的 Android 應用程式，這項資訊會顯示已設定之 Android 應用程式的數目。

    > [!NOTE]
    > 如果一個平台有多個原則，當至少指派一個原則給使用者時，會將使用者視為由原則管理。

## <a name="detailed-view"></a>詳細檢視
選擇 [使用者狀態] 磚 (依裝置作業系統平台而定) 和 [已標記的使用者] 磚，即可進入摘要的 [詳細檢視]。

### <a name="user-status"></a>使用者狀態
您可以搜尋單一使用者，並查看該使用者的相容性狀態。 [應用程式報告] 窗格會顯示所選使用者的下列資訊：
- **圖示**：顯示應用程式狀態是否是最新的。
- **應用程式名稱**：應用程式的名稱。
- **裝置名稱**：與使用者帳戶相關聯的裝置。
- **裝置類型**：裝置或裝置所執行之作業系統的類型。
- **原則**：與應用程式相關聯的原則。
- **狀態**：
  - **已簽入**：此原則已部署至使用者，而且在工作內容中至少使用一次應用程式。
  - **未簽入**：此原則已部署至使用者，但從那時起並未在工作內容中使用應用程式。
- **上次同步處理**：裝置上次同步處理的時間。

>[!NOTE]
> 如果您搜尋的使用者沒有部署 MAM 原則，則會看見一則訊息，通知您該使用者不針對任何 MAM 原則。

若要查看使用者的報告，請遵循下列步驟︰

1.  若要選取使用者，請選擇 [使用者狀態] 摘要磚。

    ![[Intune 行動應用程式管理] 的 [摘要] 磚螢幕擷取畫面](./media/MAM-reporting-6.png)

2. 在開啟的 [應用程式報告] 窗格上，選擇 [選取使用者] 來搜尋 Azure Active Directory 使用者。

    ![[應用程式報告] 窗格上的 [選取使用者] 選項螢幕擷取畫面](./media/MAM-reporting-2.png)

3. 從清單中選取一個使用者。 您可以看到該使用者之合規性狀態的詳細資料。

### <a name="flagged-users"></a>標有旗標的使用者
[詳細檢視] 會顯示錯誤訊息、發生錯誤時存取的應用程式、受影響的裝置作業系統平台和時間戳記。 這裡將會報告具有透過 Google SafetyNet 裝置證明檢查標幟之裝置的使用者，其中包含 Google 報告的原因。

## <a name="reporting-view"></a>報告檢視

您可以在 [應用程式保護狀態] 刀鋒視窗頂端找到相同的報表。

> [!NOTE]
> Intune 提供其他裝置報告欄位，包括應用程式註冊識別碼、Android 製造商、型號和安全性修補程式版本，以及 iOS 型號。 在 Intune 中，您可以藉由選取 [用戶端應用程式] > [應用程式防護狀態]，然後選擇 [應用程式防護報表：iOS、Android] 來使用這些欄位。 此外，這些參數將協助您設定適用於裝置製造商 (Android) 的 [允許] 清單、適用於裝置型號 (Android 和 iOS) 的 [允許] 清單，以及最低的 Android 安全性修補程式版本設定。 

還提供其他報表以協助您處理 MAM 原則合規性狀態。 若要檢視這些報表，請選取 [用戶端應用程式] > [應用程式防護狀態] > [報表]。 

[報表] 刀鋒視窗提供數個以使用者和應用程式為基礎的報表，包括：


- **使用者報表**：此報表列出的資訊與您在上述 [詳細檢視](app-protection-policies-monitor.md#detailed-view) 區段下 [使用者狀態] 報表中所找到的資訊相同。

- **應用程式報表**：除了選取平台和應用程式之外，此報表提供兩種不同的應用程式保護狀態，供您在產生報表之前選取。 狀態可以是 [受保護] 或 [不受保護]。

    -   受控 MAM 活動的使用者狀態 ([受保護])：這份報表會依每個使用者列出每個受控 MAM 應用程式的活動。 它會顯示每個使用者的所有 MAM 原則目標應用程式，並將每個應用程式的狀態細分為使用 MAM 原則簽入，或由 MAM 原則鎖定但永遠不會簽入應用程式。
    -   非受控 MAM 活動的使用者狀態 ([不受保護])：這份報表會依每個使用者列出目前非受控之啟用 MAM 的應用程式活動。 可能的發生原因如下︰
        -   使用者或目前不是由 MAM 原則鎖定的應用程式正在使用這些應用程式。
        -   所有的應用程式都已簽入，但未收到任何 MAM 原則。

        ![使用者的 [應用程式報告] 刀鋒視窗螢幕擷取畫面，其中包含 3 個應用程式的詳細資料](./media/MAM-reporting-4.png)

- **使用者設定報告**：根據選取的使用者，此報表會提供使用者已收到的任何應用程式設定的相關詳細資料。
- **應用程式設定報告**：根據選取的平台和應用程式，此報表會提供使用者已收到所選應用程式設定的相關詳細資料。
- **Windows 資訊保護的應用程式學習報表**：此報表會顯示哪些應用程式嘗試跨越原則界限。
- **Windows 資訊保護的網站學習報表**：此報表會顯示哪些網站嘗試跨越原則界限。

## <a name="table-grouping"></a>資料表群組

當**應用程式保護使用者報表**資料顯示時，您可以依據下列項目彙總資料︰

- **驗證結果：** 顯示的資料會依應用程式防護狀態分組，可能是失敗、警告或成功。
- **應用程式名稱：** 顯示的資料會依應用程式 (實際應用程式名稱) 分組，可能是失敗、警告或成功。

## <a name="export-app-protection-activities-to-csv"></a>將應用程式保護活動匯出到 CSV

您可以將您所有的應用程式保護原則活動匯出到單一的 *.csv* 檔案。 當您分析使用者回報的所有應用程式保護狀態時，可以加以使用。

若要產生應用程式保護報表，請執行下列步驟︰

1. 在 Intune [行動應用程式管理] 窗格上，選擇 [應用程式保護報表]。

    ![應用程式防護下載連結的螢幕擷取畫面](./media/app-protection-report-csv-2.png)

2. 選擇 [是] 儲存報表，然後選擇 [另存新檔]，再選取要儲存報表的資料夾。

    ![[儲存報表] 確認方塊的螢幕擷取畫面](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>請參閱
- [管理 iOS 應用程式之間的資料傳輸](data-transfer-between-apps-manage-ios.md)
- [當 Android 應用程式交由應用程式防護原則管理時的行為](app-protection-enabled-apps-android.md)
- [當 iOS 應用程式交由應用程式防護原則管理時的行為](app-protection-enabled-apps-ios.md)
