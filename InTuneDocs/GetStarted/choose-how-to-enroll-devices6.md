---
title: "選擇如何註冊行動裝置 | Microsoft Intune"
description: "回答一些簡單的問題，以決定如何在 Intune 中註冊行動裝置"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: f65bdbc7aa708b37a766275494e080436d9a5485
ms.openlocfilehash: 3e5c9ed2ba374172ea27b61a34f0746f582f0ebc


---
# 選擇如何註冊行動裝置

下列一系列問題的回答可協助您判斷所管理裝置的最佳註冊方法。

## **您會如何管理專用的 iOS 裝置？**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)   [iOS 設定輔助程式 >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [使用 IMEI 標記 >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  您可以透過下列方式，向專用的使用者註冊公司所擁有的裝置︰

  - **Apple 的裝置註冊方案 (DEP)** - 使用註冊設定檔，可以將目標設為使用 DEP 所購買或管理的 iOS 裝置。 使用者第一次開啟裝置的電源時，裝置會下載 DEP 設定檔，並向 Intune 註冊。

  - **Mac 上的 Apple Configurator** - Apple Configurator 是在 Mac 電腦上執行的 Apple 應用程式。 您可以使用 USB 纜線將 iOS 裝置連接至 Mac，以在裝置上安裝註冊設定檔。 如果您可以將裝置重設為原廠預設值來進行註冊，請使用 [設定助理] 註冊。

  - **以 IMEI 編號標記** - 匯入公司擁有之裝置的國際行動設備識別 (IMEI) 編號，以在 Intune 中將其標記為公司擁有的裝置。 使用者接著可以安裝公司入口網站，以將他們的裝置註冊為個人裝置來存取公司資源 (例如電子郵件、應用程式和資料)。

  > [!div class="button"]
  [< 返回](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO3-->

