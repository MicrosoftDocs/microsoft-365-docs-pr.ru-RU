---
title: Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки
f1.keywords:
- NOCSH
keywords: интеграция, Microsoft Defender, Microsoft Defender для конечной точки
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки, чтобы получить более подробные сведения об угрозах в отношении устройств и контента электронной почты.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028885"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender для Office 365](defender-for-office-365.md) можно настроить для работы с [Microsoft Defender для конечной точки](/windows/security/threat-protection).

Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки может помочь группе безопасности отслеживать и быстро принимать меры, если устройства пользователей находятся под угрозой. Например, после включения интеграции группа операций безопасности сможет видеть устройства, которые потенциально затронуты обнаруженным сообщением электронной почты, а также количество последних оповещений для этих устройств в Microsoft Defender для Endpoint.

На следующем изображении изображено, как выглядит вкладка **Devices** при включенной интеграции Microsoft Defender для конечной точки:

![Когда включен Microsoft Defender для конечной точки, вы можете увидеть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

В этом примере можно увидеть, что получатели обнаруженного сообщения электронной почты имеют четыре устройства и одно имеет оповещение. Щелкнув ссылку для устройства, откроет свою страницу [в Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (ранее Центр безопасности в Microsoft Defender).

> [!TIP]
> Портал Microsoft 365 Defender заменяет Центр безопасности в Microsoft Defender. См. [в Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requirements

- Ваша организация должна иметь Microsoft Defender для Office 365 (или Office 365 E5) и Microsoft Defender для конечной точки.

- Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную в Microsoft 365. [(См. разрешения в Microsoft 365 Defender)](permissions-in-the-security-and-compliance-center.md)

- Вы должны иметь доступ к Explorer (или обнаружения [в режиме реального времени).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки

Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки настроена как в Defender для конечной точки, так и в Defender для Office 365.

1. В качестве глобального администратора или администратора безопасности [https://security.microsoft.com](https://security.microsoft.com) войдите и войдите. (Это передает вас на Microsoft 365 Defender портала.)

2. В области навигации выберите **обозреватель &** \> **электронной почты.**

3. В правом верхнем углу экрана нажмите **кнопку MDE Параметры**.

4. В диалоговом окне Microsoft Defender для подключения к конечной точке включите Подключение **в Microsoft Defender для конечной точки.**

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Подключение к MDE":::

5. Перейдите на Microsoft 365 Defender портал ( [https://security.microsoft.com](https://security.microsoft.com) .

6. В панели навигации выберите **Параметры**. Затем в **статье General** выберите **расширенные функции**.

7. Прокрутите **Office 365 для подключения к службе сведении** об угрозах и включите подключение.

   ![Office 365 связи с данными об угрозах](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Статьи по теме

[Возможности расследования и реагирования на угрозы в Office 365](office-365-ti.md)

[Microsoft Defender для Office 365](defender-for-office-365.md)

[Microsoft Defender для конечной точки](/windows/security/threat-protection)
