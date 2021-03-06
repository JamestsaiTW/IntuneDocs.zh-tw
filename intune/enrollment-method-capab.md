---
title: 適用於 Windows 裝置的 Intune 註冊方法的功能
titleSuffix: Microsoft Intune
description: 適用於 Windows 裝置的每個註冊方法的功能。
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd1dbb3280fbbb93423796b18f6dd85a50a41f11
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567539"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>適用於 Windows 裝置的 Intune 註冊方法的功能
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

有數種方法可以在 Intune 中註冊員工裝置。 每種方法都有不同的最佳做法和功能，如下表所示。

## <a name="best-practices-by-enrollment-method"></a>最佳做法 (依註冊方法列出)
| **最佳做法** | **[Azure AD 加入](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD 加入 (使用 Autopilot) (使用者驅動模式)](enrollment-autopilot.md)** |**[Azure AD 加入 (使用 Autopilot) (自我部署模式)](enrollment-autopilot.md)** |**[大量](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[共同管理](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|常用於教育目的|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|裝置可用作共用裝置|![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|個人裝置必須存取公司資源|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|應用程式自助服務|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>功能 (依註冊方法列出)

| **功能** | **[Azure AD 加入](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD 加入 (使用 Autopilot) (使用者驅動模式)](enrollment-autopilot.md)** |**[Azure AD 加入 (使用 Autopilot) (自我部署模式)](enrollment-autopilot.md)** |**[大量](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[共同管理](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|條件式存取                                      |![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|
|使用者與裝置建立關聯                    |![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|
|需要 Azure AD Premium                               |![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|
|裝置可以評估 CA 所保護的資源             |![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|
|使用者不得為其裝置的系統管理員               |![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|能夠設定裝置設定體驗        |![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|能夠在不需要使用者互動的情況下註冊裝置      |![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|
|能夠執行 PowerShell 指令碼                       |![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|支援在 AD 網域加入之後自動註冊      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|
|支援在混合式 Azure AD 加入之後自動註冊|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|
|支援在 Azure AD 加入之後自動註冊       |![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![核取記號](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>後續步驟

[設定 Windows 的註冊](windows-enroll.md)

