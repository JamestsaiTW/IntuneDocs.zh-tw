---
title: 搭配 Intune 使用應用程式型條件式存取
titleSuffix: Microsoft Intune
description: 了解應用程式型條件式存取如何搭配 Intune 運作。
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/11/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b4c39a1d95a10c96b8f34703f99c4d8414efbbf0
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567370"
---
# <a name="app-based-conditional-access-with-intune"></a>搭配 Intune 使用應用程式型條件式存取

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

[Intune 應用程式保護原則](app-protection-policy.md)可協助保護您已在 Intune 中註冊之裝置上的公司資料。 您也可以在未向 Intune 註冊管理之員工擁有的裝置上，使用應用程式保護原則。 在此情況下，即使您的公司未管理裝置，仍然需要確定公司資料和資源受到保護。

應用程式型條件式存取和用戶端應用程式管理會新增一個安全性層級，方法是確定只有支援 Intune 應用程式保護原則的用戶端應用程式才能存取 Exchange Online 和其他 Office 365 服務。

> [!NOTE]
> 受管理應用程式是已套用應用程式保護原則的應用程式，而且可由 Intune 管理。

當您只允許 Microsoft Outlook 應用程式存取 Exchange Online 時，可以封鎖 iOS 和 Android 上內建的郵件應用程式。 此外，您可以封鎖沒有套用 Intune 應用程式保護原則的應用程式，阻擋它們存取 SharePoint Online。

## <a name="prerequisites"></a>必要條件
在您建立以應用程式為基礎的條件式存取原則之前，必須擁有：

- **Enterprise Mobility + Security (EMS)** 或 **Azure Active Directory (AD) Premium 訂用帳戶**
- 使用者必須獲得 EMS 或 Azure AD 的授權

如需詳細資訊，請參閱 [Enterprise Mobility 定價](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing)或 [Azure Active Directory 定價](https://azure.microsoft.com/pricing/details/active-directory/)。

## <a name="supported-apps"></a>支援的應用程式

您可以在 [Azure Active Directory 條件式存取的技術參考文件](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)中找到支援應用程式型條件式存取的應用程式清單。

以應用程式為基礎的條件式存取[也支援企業營運 (LOB) 應用程式](app-modern-authentication-block.md)，但這些應用程式需使用 [Office 365 新式驗證](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a)。 

## <a name="how-app-based-conditional-access-works"></a>以應用程式為基礎的條件式存取如何運作

在這個範例中，系統管理員已經將應用程式保護原則套用至 Outlook 應用程式，接著套用條件式存取規則，將 Outlook 應用程式新增到可在存取公司電子郵件時使用之應用程式的核准清單中。

> [!NOTE]
> 下方的流程圖結構可以用於其他受管理的應用程式。

![流程圖所示之應用程式型條件式存取程序](./media/ca-intune-common-ways-3.png)

1. 使用者嘗試從 Outlook 應用程式向 Azure AD 驗證。

2. 在第一次嘗試驗證時，系統會將使用者重新導向至應用程式市集，以安裝訊息代理程式應用程式。 訊息代理程式應用程式可以是適用於 iOS 的 Microsoft 驗證器，或適用於 Android 裝置的 Microsoft 公司入口網站。

   如果使用者嘗試使用原生電子郵件應用程式，系統會將他們重新導向至應用程式市集，然後安裝 Outlook 應用程式。

3. 會在裝置上安裝訊息代理程式應用程式。

4. 訊息代理程式應用程式會啟動 Azure AD 註冊程序，這會在 Azure AD 中建立裝置記錄。 這和行動裝置管理 (MDM) 註冊程序不同，但必須有此記錄，才能在裝置上強制實行條件式存取原則。

5. 訊息代理程式應用程式會確認應用程式的身分。 系統中有一個安全性層級，所以訊息代理程式應用程式才能驗證應用程式是否已獲使用者授權使用。

6. 訊息代理程式應用程式會在使用者驗證程序中，將應用程式用戶端識別碼傳送至 Azure AD，以檢查該應用程式是否在原則核准的清單中。

7. Azure AD 可允許使用者依據原則核准的清單驗證及使用應用程式。 如果應用程式不在清單中，Azure AD 會拒絕對應用程式的存取。

8. Outlook 應用程式會與 Outlook 雲端服務通訊，以起始和 Exchange Online 的通訊。

9. Outlook 雲端服務會與 Azure AD 通訊，為使用者擷取 Exchange Online 服務存取權杖。

10. Outlook 應用程式會與 Exchange Online 通訊，以擷取使用者的公司電子郵件。

11. 公司電子郵件就會傳遞到使用者的信箱。

## <a name="next-steps"></a>後續步驟
[建立以應用程式為基礎的條件式存取原則](app-based-conditional-access-intune-create.md)

[封鎖沒有新式驗證的應用程式](app-modern-authentication-block.md)
