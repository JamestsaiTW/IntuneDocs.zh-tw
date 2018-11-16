---
title: 快速入門 - 建立 Android 裝置的密碼合規性政策
titlesuffix: Microsoft Intune
description: 您將在本快速入門中，使用 Microsoft Intune 設定 Android 裝置所需的密碼長度。
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 438121e0375559455547f4cc5453d272576681ca
ms.sourcegitcommit: 4c4e87cb0d8906085fcb7cdd170bd6b0cfeb23ff
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2018
ms.locfileid: "51510800"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>快速入門：建立 Android 裝置的密碼合規性政策

您將在本快速入門中，使用 Microsoft Intune 要求您使用 Android 裝置的員工必須先輸入特定長度的密碼，才會在其 Android 裝置上授與資訊存取權。 

Intune 裝置合規性政策指定裝置必須符合的規則和設定，才能視為相容。 您可以將合規性政策與條件式存取搭配使用，來允許或封鎖公司資源的存取。 您也可以取得裝置報表，並針對不相容採取動作。

> [!IMPORTANT]
> 除了密碼設定之外，也應該考量運用其他系統安全性設定保護您的員工。 如需詳細資訊，請參閱[系統安全性設定](compliance-policy-create-android-for-work.md#system-security-settings)。

如果您沒有 Intune 訂用帳戶，請[註冊免費試用帳戶](free-trial-sign-up.md)。

## <a name="sign-in-to-intune"></a>登入 Intune

請以全域管理員或 Intune 服務管理員身分登入 [Intune](https://aka.ms/intuneportal)。 

## <a name="create-a-device-compliance-policy"></a>建立裝置合規性政策

您將在本快速入門中，使用 Intune 要求您使用 Android 裝置的員工必須先輸入特定長度的密碼，才能在其 Android 裝置上授與資訊存取權。

1. 在 Intune 中選取 [裝置合規性] > [原則] > [建立原則]。
2. 新增 [Android 合規性] 作為 [名稱]。 也請新增 [描述]。
3. 針對 [平台]，選取 [Android]。 
4. 選取 [設定] > [系統安全性] 以顯示 Android [系統安全性] 刀鋒視窗。
5. 按一下 [需要密碼才可解除鎖定行動裝置] 旁的 [必要]。
6. 在 [最小密碼長度] 旁邊，輸入 **6**。 

    ![在 Microsoft Intune 中建立群組的螢幕擷取畫面](media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. 完成後，請按一下 [確定] > [確定] > [建立] 來建立政策。

成功建立政策時，它會顯示在裝置合規性政策的清單中。 

## <a name="clean-up-resources"></a>清除資源

不再需要時，請刪除原則。 若要這樣做，請選取合規性政策，然後按一下 [刪除]。

## <a name="next-steps"></a>接下來的步驟

您可以在本快速入門中，使用 Intune 為員工的 Android 裝置建立合規性政策，以要求長度至少為六個字元的密碼。 如需建立合規性政策的詳細資訊，請參閱[開始使用 Intune 中的裝置合規性政策](device-compliance-get-started.md)。

若要遵循此 Intune 快速入門系列，請繼續前往下一個快速入門。

> [!div class="nextstepaction"]
> [快速入門：傳送通知到不符合規範的裝置](quickstart-send-notification.md)