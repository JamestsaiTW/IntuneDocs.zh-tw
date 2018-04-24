---
title: 在 Microsoft Intune 中設定 Endpoint Protection 設定 - Azure | Microsoft Docs
description: 您可以在於 Microsoft Intune 中建立 macOS 或 Windows 10 裝置設定檔時，建立 Endpoint Protection 設定。
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b960b837cef5941fac829eeb878eb520b0274fba
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="add-endpoint-protection-settings-in-intune"></a>在 Intune 中新增 Endpoint Protection 設定

Endpoint Protection 可讓您控制裝置上的各種不同安全性功能，包括防火牆、Bitlocker、允許和封鎖應用程式、Windows Defender 和加密等。 您可以在 Microsoft Intune 中使用裝置設定檔來進行這些設定。

例如，您可以建立一個只允許 macOS 使用者從 Mac App Store 安裝應用程式的 Endpoint Protection 設定檔。 或者，在於 Windows 10 裝置上執行應用程式時，啟用 Windows SmartScreen。

本文將說明如何建立設定檔。 接著，請選取裝置平台，以取得有關可用設定的更多詳細資料。

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>建立包含 Endpoint Protection 設定的裝置設定檔

1. 登入 [Azure 入口網站](https://portal.azure.com)。
2. 選取 [All services] (所有服務)，篩選 [Intune]，然後選取 [Microsoft Intune]。
3. 選取 [裝置設定] > [設定檔] > [建立設定檔]。
4. 輸入 Endpoint Protection 設定檔的 [名稱] 和 [描述]。
5. 從 [平台] 下拉式清單中，選取要套用自訂設定的裝置平台。 您目前可選擇下列平台之一，進行裝置限制設定︰
   - **macOS**
   - **Windows 10 及更新版本**
6. 從 [設定檔類型] 下拉式清單中，選擇 [Endpoint Protection]。 
7. 您可設定的設定會視您選擇的平台而不同。 前往下列主題之一，即可取得每個平台的詳細設定︰
   - [macOS 設定](endpoint-protection-macos.md)
   - [Windows 10 設定](endpoint-protection-windows-10.md)
8. 當您完成時，請返回 [建立設定檔] 頁面，然後按一下 [建立]。

設定檔隨即建立，並出現在 [設定檔清單] 頁面上。 若要將此設定檔指派給群組，請參閱[指派裝置設定檔](device-profile-assign.md)。

## <a name="next-steps"></a>接下來的步驟
若要將設定檔指派給群組，請參閱[指派裝置設定檔](device-profile-assign.md)。