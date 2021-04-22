---
title: Устранение неполадок в Microsoft Defender для конечной точки на Android
description: Устранение неполадок для Microsoft Defender для конечной точки на Android
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mde, android, cloud, connectivity, communication
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5f57d14427ef68280a065489e068955db9e5045a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934805"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Устранение неполадок в Microsoft Defender для конечной точки на Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

При входе на устройство после установки приложения могут возникнуть проблемы с входом.

Во время входной платы после установки приложения на вашем устройстве могут возникнуть проблемы с входом.

В этой статье данная статья предоставляет решения, которые помогут решить проблемы с входом.  

## <a name="sign-in-failed---unexpected-error"></a>Вход не удалось - неожиданная ошибка
**Вход не удалось:** *непредвиденное ошибка, попробуйте позже*

![Изображение знака в ошибке с ошибкой Непредвиденное ошибка](images/f9c3bad127d636c1f150d79814f35d4c.png)

**Сообщение:**

Неожиданная ошибка, попробуйте позже

**Причина:**

На вашем устройстве установлена более старая версия приложения "Microsoft Authenticator".

**Решение:**

Установите последнюю версию и [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) из магазина Google Play и попробуйте еще раз

## <a name="sign-in-failed---invalid-license"></a>Вход в сбой - недействительные лицензии

**Вход сбой:** *недействительные лицензии, обратитесь к администратору*

![Изображение знака в сбой, пожалуйста, свяжитесь с администратором](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Сообщение.** *Недействительные лицензии, обратитесь к администратору*

**Причина:**

Вам не назначена лицензия Microsoft 365 или у организации нет лицензии на подписку microsoft 365 Enterprise.

**Решение:**

Обратитесь к системному администратору.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Фишинговые страницы не заблокированы на некоторых устройствах OEM

**Применяется к:** Только конкретные OEMs

-   **Xiaomi**

Фишинговые и вредоносные веб-угрозы, обнаруженные Defender для конечной точки для Android, не блокируются на некоторых устройствах Xiaomi. Следующие функции не работают на этих устройствах.

![Изображение сайта, сообщаемого небезопасно](images/0c04975c74746a5cdb085e1d9386e713.png)


**Причина:**

Устройства Xiaomi включают новую модель разрешений. Это не позволяет Защитнику для конечной точки для Android отобразить всплывающее окно во время его работы в фоновом режиме.

Разрешение устройств Xiaomi: "Отображение всплывающих окон во время работы в фоновом режиме".

![Изображение всплывающее параметра](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**Решение:**

Включить необходимое разрешение на устройствах Xiaomi.

- Отображение всплывающих окон во время работы в фоновом режиме.
