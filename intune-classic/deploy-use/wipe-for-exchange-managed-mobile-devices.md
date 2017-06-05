---
title: "抹除 Exchange 管理的行動裝置 | Microsoft Docs"
description: "Microsoft Intune 可讓您抹除或重設行動裝置，這些裝置搭配使用 Exchange ActiveSync (EAS) 和 Intune Exchange Connector 管理"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4b0914ab12456fd3ad5f957d68a59df9de539176
ms.contentlocale: zh-tw
ms.lasthandoff: 05/23/2017


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>抹除 Exchange 管理的行動裝置

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune 可讓您抹除或重設行動裝置，這些裝置搭配使用 Exchange ActiveSync (EAS) 和 Intune Exchange 連接器管理。 下表說明透過 Exchange ActiveSync 可用的抹除功能：

|抹除類型|Windows 8.1 和 Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|完整抹除|移除郵件帳戶及快取的郵件。|重設成 XFactory。|恢復出廠預設值。|
|選擇性抹除/電子郵件|移除電子郵件帳戶。|不支援。|不支援。|
|選擇性抹除/原則|移除原則強制執行，但不變更設定|移除原則強制執行，但不變更設定。|移除原則強制執行，但不變更設定。|
