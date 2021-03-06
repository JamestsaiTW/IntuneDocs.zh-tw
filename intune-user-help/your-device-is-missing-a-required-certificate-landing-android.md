---
title: 您的裝置遺失必要的憑證 | Microsoft Docs
titlesuffix: Microsoft Intune
description: 您的裝置遺失公司支援人員所要求的憑證。
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cc86a53dd790059297430fd6b08f1a699aafbc84
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: zh-TW
ms.lasthandoff: 03/14/2019
ms.locfileid: "55850653"
---
# <a name="your-device-is-missing-a-required-certificate"></a>您的裝置遺漏必要的憑證

## <a name="whats-a-certificate"></a>何謂憑證？

[密碼編譯](https://technet.microsoft.com/library/cc962030.aspx)是提供資訊安全的科學。 密碼編譯在傳統上是用於傳遞加密訊息，以[確保通訊保持機密](https://technet.microsoft.com/library/cc962019.aspx)。 最簡單的密碼編譯形式是，它會取代或調換字母以建立加密訊息，使其變成無意義、無規則，或隱藏的訊息。 只有擁有解密金鑰 (或「憑證」) 的人才能將加密訊息轉換回可閱讀的原始格式。 Android 裝置會搭配使用憑證與 Intune，以確保裝置和組織資源之間在空中傳送的通訊 (如電子郵件與文件) 能夠保持安全。

## <a name="fixing-certificate-issues"></a>修正憑證問題

如果您的 Android 裝置未在 Intune 註冊，且遺失公司支援人員所要求的特定憑證，您就無法登入公司入口網站應用程式。 當您嘗試登入時，您會看到下列訊息：

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

您應該先查看裝置是否[遺失通常已預先安裝的憑證](your-device-is-missing-a-preinstalled-certificate-android.md)。

如果仍然無法解決憑證問題，您公司的支援人員可能會[要求您安裝第二個憑證以獲得額外的安全性](your-device-is-missing-an-IT-required-certificate-android.md)。

是否仍需要協助？ 請連絡您公司的支援人員。 如需連絡資訊，請查看[公司入口網站](https://go.microsoft.com/fwlink/?linkid=2010980)。
