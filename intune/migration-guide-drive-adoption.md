---
title: "使用條件式存取引導使用者採用"
description: "本文旨在提供如何使用條件式存取引導使用者註冊 Intune 的見解。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>使用條件式存取引導使用者採用

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

使用 Intune 啟用條件式存取功能 (例如封鎖來自未註冊裝置的電子郵件) 有助於推動註冊與合規性，但不是移轉成功的要件。 您的移轉採用目標和安全性需求才是決定成功的關鍵。

## <a name="migration-campaign-with-conditional-access"></a>使用條件式存取的移轉活動

以下是使用條件式存取增強移轉活動的典型方法︰

1.  設定針對所有使用者強制的條件式存取規則，但特別排除需要從舊的 MDM 提供者移轉的使用者。 您可以建立一個 Azure AD 使用者群組，其中包含所有條件式存取排除的使用者。

2.  當使用者移轉時，從條件式存取排除群組中移除他們。

3.  在移轉完成後，將所有條件式存取原則設為除非 Intune 允許否則預設為封鎖。

### <a name="advantages"></a>優點

-   為新的使用者帳戶或不受先前的解決方案管理的使用者帳戶提供存取控制。

-   為先前的解決方案使用者提供移轉寬限期。

-   將生產力的損失降至最低

### <a name="disadvantages"></a>缺點

-   先前的解決方案使用者可能會使用未受管理的裝置存取資源，直到針對這些使用者啟用條件式存取為止。

> [!TIP]
> 這是眾多方法之一。 您可以選擇較簡單的程序，以延遲所有條件式存取直到使用者已收到每個階段的註冊指示後為止，或是選擇較嚴格的程序，從一開始就強制條件式存取，而且要求所有存取的完整合規性。

-   深入了解[使用 Microsoft Intune 限制電子郵件、Office 365 和其他服務的存取](/intune/conditional-access)。

## <a name="task-list-for-conditional-access"></a>條件式存取的工作清單

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>工作 1：決定實作條件式存取的方式

[使用條件式存取的常見方式](/intune/conditional-access-intune-common-ways-use)。

### <a name="task-2-set-up-intune-conditional-access"></a>工作 2︰設定 Intune 條件式存取

選擇下列其中一個選項：

-   [在 Azure Active Directory 中設定條件式存取](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [使用 Intune 安裝內部部署 Exchange Connector](/intune/exchange-connector-install)

-   [為 Exchange Online 設定以應用程式為基礎的條件式存取原則](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [為 SharePoint Online 設定以應用程式為基礎的條件式存取原則](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [封鎖未使用新式驗證 (ADAL) 的應用程式](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>後續步驟

[典型移轉週期](migration-guide-cycle.md)