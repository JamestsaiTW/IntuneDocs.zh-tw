---
title: 將 iOS 市集應用程式新增至 Microsoft Intune
titleSuffix: ''
description: 了解如何將 iOS 市集應用程式新增至 Microsoft Intune。 如果應用程式在 App Store 中是免費的，您可以使用此方法來指派應用程式。
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 454000ccc7ac2d6f531b5ab43bb7652541559992
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2019
ms.locfileid: "59568540"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>將 iOS 市集應用程式新增至 Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

使用本文中的資訊，協助您將 iOS 市集應用程式新增至 Microsoft Intune。 iOS 市集應用程式就是 Intune 安裝於使用者裝置的應用程式。 使用者是您公司的員工。 會自動更新 iOS 市集應用程式。

>[!NOTE]
>雖然 iOS 裝置的使用者可以移除部分內建的 iOS 應用程式 (例如股票和地圖)，但您無法使用 Intune 來重新部署這些應用程式。 如果您的使用者刪除這些應用程式，則必須移至應用程式商店，並手動重新安裝。

## <a name="before-you-start"></a>開始之前

如果應用程式在應用程式市集中是免費的，您只能使用這個方法指派應用程式。 如果您想要使用 Intune 指派付費應用程式，請考慮使用 [iOS 大量採購方案](vpp-apps-ios.md)。

>[!NOTE]
>當您使用 Microsoft Intune 時，建議使用 Microsoft Edge 或 Google Chrome 瀏覽器。

1. 登入 [Azure 入口網站](https://portal.azure.com)。
2. 選取 [所有服務] > [Intune]。  
    Intune 位於 [Monitoring + Management] (監視 + 管理) 區段。
3. 在 [Intune] 窗格中，選取 [用戶端應用程式]。
4. 在 [用戶端應用程式] 工作負載窗格中的 [管理] 下，選取 [應用程式]。
5. 在 [應用程式] 窗格中，選取 [新增]。
6. 在 [應用程式類型] 清單中的 [市集應用程式] 類型下，選取 [iOS]。
7. 選取 [Search the App Store] \(搜尋應用程式市集\)。
8. 在 [Search the App Store] \(搜尋應用程式市集\) 窗格中，選取 App Store 國家地區設定。
9. 在 [搜尋] 方塊中輸入應用程式的名稱 (或部分名稱)。  
    Intune 會搜尋市集，並傳回一份相關的結果清單。
10. 在結果清單中，選取您想要的應用程式，然後再選取 [選取]。
11. 在 [新增應用程式] 窗格中，選擇 [應用程式資訊] 來設定應用程式。
12. 在 [應用程式資訊] 窗格中，新增應用程式資訊。 窗格中某些值會隨所選的應用程式自動填入︰
    - **名稱**：輸入要在公司入口網站中顯示的應用程式名稱。 您使用的任何應用程式名稱都必須是唯一的。 如果應用程式名稱重複，則使用者只會在公司入口網站看到一個名稱。
    - **描述**：輸入應用程式的描述。 使用者會在公司入口網站上看到這項描述。
    - **發行者**：輸入應用程式發行者的名稱。
    - **AppStore URL**：輸入您想要建立之應用程式的 App Store URL。
    - **最基本的作業系統**：從清單中，選取能夠安裝應用程式的最早作業系統版本。 若將應用程式指派給安裝舊版作業系統的裝置，就不會進行安裝。
    - **適用的裝置類型**：從清單中，選取應用程式所使用的裝置。
    - **類別**：(選擇性) 選取一或多個內建的應用程式類別，或選取您建立的類別。 這麼做的話，當使用者在瀏覽公司入口網站時，可以更輕鬆地找到應用程式。
    - **將此顯示為公司入口網站中的精選應用程式**：若要在使用者瀏覽應用程式時，於公司入口網站的主頁面上以醒目方式顯示應用程式套件，請選取此選項。
    - **資訊 URL**：(選用) 輸入包含此應用程式相關資訊的網站 URL。 使用者會在公司入口網站中看到這個 URL。
    - **隱私權 URL**：(選擇性) 輸入包含這個應用程式之隱私權資訊的網站 URL。 使用者會在公司入口網站中看到這個 URL。
    - **開發人員**：(選擇性) 輸入應用程式開發人員的姓名。 此欄位只有系統管理員可以看到，並不會對您的使用者顯示。
    - **擁有者**：(選擇性) 輸入此應用程式的擁有者名稱，例如「人力資源部門」。 此欄位只有系統管理員可以看到，並不會對您的使用者顯示。
    - **附註**：(選擇性) 輸入要與此應用程式建立關聯的任何附註。 這個欄位只有系統管理員看得到，使用者看不到。
    - **標誌**：(選擇性) 上傳將與應用程式建立關聯的圖示。 這是使用者瀏覽公司入口網站時，會隨應用程式一起顯示的圖示。
13. 選取 [確定]。
14. 選取 [新增]。

您建立的應用程式即會顯示在應用程式清單中，而您可從中將該應用程式指派給所選的群組。

## <a name="next-steps"></a>後續步驟

- [將應用程式指派給群組](apps-deploy.md)
