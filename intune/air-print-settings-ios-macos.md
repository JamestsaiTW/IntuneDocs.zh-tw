---
title: "適用於 iOS 和 macOS 裝置的 Intune AirPrint 設定"
titleSuffix: Intune Azure preview
description: "Intune Azure 預覽版：了解如何使用 Intune，以協助將 iOS 和 macOS 裝置自動連線到相容 AirPrint 的印表機。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55486693e2f5678ceeb20dd3a0ef3c52553871d2
ms.contentlocale: zh-tw
ms.lasthandoff: 05/23/2017


---

# <a name="airprint-settings-for-ios-and-macos-devices"></a>適用於 iOS 和 macOS 裝置的 AirPrint 設定

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

使用這些設定來設定 iOS 或 macOS 裝置，以自動連線到網路中相容 AirPrint 的印表機。 您將需要印表機的 IP 位址和資源路徑才能繼續。

## <a name="find-airprint-printer-information"></a>尋找 AirPrint 印表機資訊

使用此程序將 AirPrint 資訊新增到 AirPrint 承載，如此 iOS 裝置使用者就可以列印至已知的 AirPrint 印表機。

1. 首先，Mac 連線的區域網路 (子網路) 必須與 AirPrint 印表機連線的區域網路相同。然後在 Mac 上，開啟「終端機」 (從 **/Applications/Utilities**)
2. 在終端機中，輸入 **ippfind**，然後按 Enter。
3. 記下命令傳回的任何印表機資訊，例如：**ipp://myprinter.local.:631/ipp/port1**。 此項資訊的第一個部分是印表機的名稱，最後一個部分是資源路徑。
4. 在終端機中，輸入 **ping myprinter.local**，然後按 Enter。
5. 記下命令傳回的 IP 位址資訊，例如 **PING myprinter.local (10.50.25.21)**。
6. 最後，在 AirPrint 承載設定中使用 IP 位址和資源路徑。 舉例而言，IP 位址可能是 **10.50.25.21**，而資源路徑可能是 **/ipp/port1**。

## <a name="configure-an-airprint-profile"></a>設定 AirPrint 設定檔

1. 在 [裝置功能] 刀鋒視窗上選擇 [AirPrint]。
2. 在 [AirPrint] 刀鋒視窗上，輸入 AirPrint 目的地的 **IP 位址**和**資源路徑**以新增 AirPrint 目的地，然後按一下 [新增]。
3. 繼續新增您所需的目的地。 完成之後，請選擇 [確定]。

您也可以從逗號分隔值 (.csv) 檔案匯入印表機清單，或是將清單匯出。
