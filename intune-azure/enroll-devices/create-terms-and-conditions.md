---
title: "設定 Microsoft Intune 中的條款和條件"
titleSuffix: Intune Azure preview
description: "Intune Azure 預覽版︰設定使用者在 Intune 公司入口網站中看到條款與條件。 "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 07a42cf8fa10d3223129fbb2932217ff90ac365b
ms.lasthandoff: 02/18/2017

---

# <a name="set-terms-and-conditions"></a>設定條款及條件 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

您可以將 Intune 條款和條件部署到使用者群組，以說明註冊、對工作資源的存取以及公司入口網站應用程式如何影響裝置和使用者。 使用者必須先接受這些條款和條件，才可使用公司入口網站來註冊及存取其工作。

您可以建立及部署多個包含不同條款和條件的原則。 您也可以產生相同條款和條件的不同語言版本，再將這些版本部署到適當的群組。

**建立條款和條件**

1. 在 Azure 入口網站中，選擇 [更多服務] > [監視 + 管理] > [Intune]。

2. 在 Intune 刀鋒視窗上選擇 [註冊裝置]，然後選擇 [條款及條件]。

3. 選取 [建立]。

4. 在 [建立條款和條件] 刀鋒視窗上指定下列資訊：

   - **顯示名稱**︰ 條款所要使用的名稱。 使用者會在公司入口網站應用程式中見到此名稱。

   - **描述**︰ 選擇是否要輸入詳細資料來協助您識別 Azure 入口網站中的原則。

5. 選取 [Define terms of use ] (定義使用規定) 旁的箭頭，以開啟 [條款及條件] 刀鋒視窗，然後輸入下列資訊︰

   - **標題**：使用者在公司入口網站中看到的標題。

   - **條款摘要**︰當使用者接受條款時說明其意義的文字。

   - **條款及條件**︰使用者看到且必須選擇接受或拒絕的法律標籤，例如「我同意條款及條件」。

6. 選取 [確定]。
