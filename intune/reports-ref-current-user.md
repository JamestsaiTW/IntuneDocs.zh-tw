---
title: "使用者 - Intune 資料倉儲 | Microsoft Docs"
description: "Intune 資料倉儲 API 中 [使用者] 類別實體集合的參考主題。"
keywords: "Intune 資料倉儲"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6f321a3a9ac09c004639a3db15df280fbdb5be3c
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2017
---
# <a name="reference-for-current-user-entity"></a>目前使用者實體的參考

**Current User** 類別包含資料模型中的使用者和代理程式屬性。 **Current User** 實體集合只限於目前作用中的使用者。 該實體包含目前已指派授權的所有 Azure Active Directory 使用者。 該授權可以是 Intune 授權、混合式授權或 Microsoft Office 365 授權。 如果使用者已經被移除，則他們不會在資料收集的期間出現。 如需包含使用者狀態變更歷程記錄的集合，請參閱 [User 實體的參考](reports-ref-user.md)。


## <a name="user"></a>使用者

**User** 實體列出企業中具有所指派授權的所有 Azure Active Directory (Azure AD) 使用者。

| 屬性  | 描述 | 範例 |
|---------|------------|--------|
| UserKey |資料倉儲中使用者的唯一識別碼 - Surrogate 索引鍵。 |123 |
| UserId |使用者的唯一識別碼 - 與 UserKey 類似，但為自然索引鍵。 |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |使用者的電子郵件地址。 |John@constoso.com |
| UPN | 使用者的使用者主體名稱。 | John@constoso.com |
| DisplayName |使用者的顯示名稱。 |John |
| IntuneLicensed |指定這位使用者是否獲授權使用 Intune。 |True/False |
| StartDateInclusiveUTC |在資料倉儲中建立此使用者的 UTC 日期和時間。 |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |前次在資料倉儲中修改此使用者的 UTC 日期和時間。 |11/23/2016 12:00:00 AM |

## <a name="next-steps"></a>後續步驟
 - 您可以使用 **User** 實體集合來將使用者資料擴展到目前非作用中的使用者。 如需詳細資訊，請參閱 [User 實體的參考](reports-ref-user.md)。 
 - 若要深入了解資料倉儲如何在 Intune 中追蹤使用者的存留期，請參閱 [Intune 資料倉儲中的使用者存留期表示法](reports-ref-user-timeline.md)。