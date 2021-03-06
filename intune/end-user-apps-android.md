---
title: Android 使用者如何取得其應用程式
description: 讓終端使用者可以使用 Android 應用程式的方法
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/21/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f4169f5625965ebc7d2bbbf9153cb4183fcd22b3
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/14/2019
ms.locfileid: "57388096"
---
# <a name="how-your-android-users-get-their-apps"></a>Android 使用者如何取得其應用程式

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

使用這項資訊，了解您的 Android 使用者取得您透過 Microsoft Intune 散發之應用程式的方式和位置。 該資訊可能會因裝置類型 (原生 Android 裝置或 Samsung Knox Standard 裝置) 而有所不同。

## <a name="native-non-samsung-knox-standard-android-devices"></a>原生 (非 Samsung Knox Standard) Android 裝置

| 應用程式類型 | 企業營運 (LOB) 應用程式 | Play Store 應用程式  |
| ------------- |-------------| -----|
| 可用的應用程式      | 使用者在公司入口網站中點選 [安裝]。 隨即會出現通知，而使用者將點選該通知以開始安裝。 安裝成功之後，通知將會消失。 | 使用者點選公司網站中的應用程式，並被移至 Play Store 中的應用程式頁面，使用者可以在該處開始安裝。|
| Required apps      | 使用者會看見一個無法關閉的通知，指出他們必須安裝應用程式。 使用者點選通知以開始安裝。 安裝成功之後，通知將會消失。    | 使用者會看見一個無法關閉的通知，指出他們必須安裝應用程式。 使用者點選通知，並被移至 Play Store 中的應用程式頁面，使用者可以在該處開始安裝。 安裝成功之後，通知將會消失。 |

您的終端使用者必須允許來自未知來源的安裝，才能安裝 [LOB 應用程式](lob-apps-android.md)。 這些通常可以在兩個不同的位置找到：

* **Android 7.1.2 和更舊版本**：[設定] > [安全性] > [未知來源]
* **Android 8.0 和更新版本**：[設定] > [應用程式與通知] > [特殊應用程式存取] > [安裝未知的應用程式] > [公司入口網站] > [允許從這個來源]

如果發生這種情況，公司入口網站應用程式將會通知，並直接引導終端使用者進行適當的設定。 


## <a name="samsung-knox-standard-android-devices"></a>Samsung Knox Standard Android 裝置

| 應用程式類型 | 企業營運 (LOB) 應用程式 | Play Store 應用程式  |
| ------------- |-------------| -----|
| 可用的應用程式      | 使用者在公司入口網站中點選 [安裝]。 應用程式將在使用者無須介入下完成安裝。 | 使用者點選公司網站中的應用程式，並被移至 Play Store 中的應用程式頁面，使用者可以在該處開始安裝。|
| Required apps      | 應用程式將在使用者無須介入下完成安裝。    | 使用者會看見一個無法關閉的通知，指出他們必須安裝應用程式。 使用者點選通知，並被移至 Play Store 中的應用程式頁面，使用者可以在該處開始安裝。 安裝成功之後，通知將會消失。 |

應用程式可為受管理或不受管理，如下所述。 讓應用程式受管理的程序，針對所有類型的 Android 裝置都是相同的。

**受管理的應用程式** - 可透過原則進行管理的應用程式。 它們已由 Intune「包裝」或已透過 Intune App SDK 建置。 這些應用程式可由 Intune 管理，並套用應用程式原則。

**未受管理的應用程式** - 無法透過原則進行管理的應用程式。 它們未受 Intune 包裝或不包含 Intune App SDK。 應用程式原則不適用於這些應用程式。

### <a name="see-also"></a>請參閱
[使用 Microsoft Intune 新增應用程式](apps-add.md)

[iOS 使用者如何取得其應用程式](end-user-apps-ios.md)

[Windows 使用者如何取得其應用程式](end-user-apps-windows.md)
