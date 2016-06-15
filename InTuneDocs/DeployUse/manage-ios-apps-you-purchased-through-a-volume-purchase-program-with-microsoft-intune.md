---
# required metadata

title: 管理透過大量採購方案購買的 iOS 應用程式 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 管理透過 Microsoft Intune 大量採購方案購買的 iOS 應用程式
某些應用程式市集可讓您購買多個您想要在公司內執行的應用程式授權。 這可協助您降低追蹤多個所購買應用程式複本的管理開銷。

Microsoft Intune 透過此種程式從應用程式市集匯入授權資訊、追蹤您已經使用了多少個授權，並避免您安裝超過擁有數目的應用程式複本，來協助您管理購買的應用程式。

> [!Important]
> 目前，Intune 會指派 iOS VPP 應用程式授權給使用者，而不是裝置。 因此，使用者必須輸入其 Apple ID 密碼，才能安裝應用程式。

## 管理大量採購的 iOS 裝置應用程式
您可以透過 [Apple 商用大量採購方案 (VPP)](http://www.apple.com/business/vpp/) 大量購買 iOS 應用程式的授權。 這包括從 Apple 網站設定 Apple VPP 帳戶，並將 Apple VPP 權杖帶至 Intune。  您可以將您的大量採購資訊與 Intune 同步處理，並追蹤大量採購的應用程式使用情況。

## 開始之前
在開始之前，您必須從 Apple 取得 VPP 權杖，並將它上傳至您的 Intune 帳戶。 此外，您還應該了解下列資訊︰

* 每個組織只可以有一個 VPP 帳戶和權杖。
* 一旦您將 Apple VPP 帳戶與 Intune 建立關聯後，之後就不能與其他帳戶建立關聯。 基於這個理由，請務必讓一人以上取得您所使用帳戶的詳細資料。
* 之前如有其他產品已使用過 VPP 權杖，您必須產生新的權杖來搭配 Intune 使用。
* 每個權杖有效期限為一年。
* Intune 預設與 Apple VPP 服務一天進行兩次同步處理。 您仍可以隨時起始手動同步處理。
* 在 VPP 權杖匯入 Intune 之後，請不要將相同的權杖匯入任何其他裝置管理解決方案。 以免導致授權指派及使用者記錄遺失。
* 開始使用 iOS VPP 和 Intune 之前，請移除任何以其他 MDM 廠商建立的現有 VPP 使用者帳戶。 基於安全性考量，Intune 不會把這些使用者帳戶同步處理到 Intune。 Intune 只會同步處理 Intune 所建立的 Apple VPP 服務資料。 

## 取得並上傳 Apple VPP 權杖

1.  在 [Microsoft Intune 管理主控台](https://manage.microsoft.com)中，按一下 [管理] &gt; [iOS 和 Mac OS X] &gt;  [大量採購方案]

2.  如果還沒有這麼做，請按一下 [Apple VPP 帳戶] 連結，註冊商務大量採購方案。 註冊之後，請下載您帳戶的 Apple VPP 權杖。

3.  在 Intune 主控台的 [管理 Apple 大量採購方案 (VPP)] 頁面中，按一下 [上傳 VPP 權杖]

4.  在 [上傳 VPP 權杖] 對話方塊中，輸入或貼上 VPP 權杖名稱及您的 Apple ID，然後按一下 [上傳]

5.  在警告的對話方塊中，按一下核取方塊，表示您已了解之後您不能變更為其他 VPP 帳戶，然後按一下 [是]

您現在可以在 [大量採購方案] 頁面上檢視 Apple VPP 權杖的資訊，包括上次更新時間、到期時間，以及上次與 Intune 同步處理的時間。

您可以隨時按一下 [立即同步處理]，使用 Intune 同步處理 Apple 所儲存的資料。

## 上傳和部署大量採購的應用程式

1.  在 [Microsoft Intune 管理主控台](https://manage.microsoft.com)中，按一下 [應用程式] &gt; [受管理的軟體] &gt; [大量採購的應用程式]

2.  使用[在 Microsoft Intune 中新增行動裝置的應用程式](add-apps-for-mobile-devices-in-microsoft-intune.md)主題中的指示，完成應用程式的上傳、建立和部署。

當您將應用程式部署為 必要 安裝時，安裝應用程式的每位使用者都會使用授權。

若要回收授權，您必須變更部署動作為 [解除安裝]。 一旦應用程式解除安裝，將會回收授權。

當具有合格裝置的使用者第一次嘗試安裝 VPP 應用程式時，系統會要求他們加入 Apple 大量採購方案。 他們必須這麼做，應用程式安裝才會繼續執行。

> 查看 [VPP 條款狀態] 欄，以了解已部署應用程式之每位使用者的接受狀態。

如果沒有更多的可用授權，部署將會失敗。

## 監視 Apple VPP 應用程式
您可以監視已部署了哪些 VPP 應用程式，以及從 [應用程式] 工作區了解使用了多少授權，其位於：[受管理的軟體] &gt; [大量購買應用程式] 節點。

> 您也可以使用應用程式的 [篩選器] 來檢查每個應用程式的安裝狀態。

### 另請參閱
[在 Microsoft Intune 中新增行動裝置的應用程式](add-apps-for-mobile-devices-in-microsoft-intune.md)



<!--HONumber=May16_HO2-->

