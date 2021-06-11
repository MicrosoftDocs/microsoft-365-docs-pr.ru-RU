---
title: Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки
f1.keywords:
- NOCSH
keywords: интеграция, Microsoft Defender, Microsoft Defender для конечной точки
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
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
ms.openlocfilehash: 3f1d92d2433267b89398c7f7f582a8d1ee8cdba5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878608"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender для Office 365](defender-for-office-365.md) можно настроить для работы с [Microsoft Defender для конечной точки](/windows/security/threat-protection).

Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки может помочь группе безопасности отслеживать и быстро принимать меры, если устройства пользователей находятся под угрозой. Например, после включения интеграции группа операций безопасности сможет видеть устройства, которые потенциально затронуты обнаруженным сообщением электронной почты, а также количество последних оповещений для этих устройств в Microsoft Defender для Endpoint.

На следующем изображении изображено, как выглядит вкладка **Devices** при включенной интеграции Microsoft Defender для конечной точки:

![Когда включен Microsoft Defender для конечной точки, вы можете увидеть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

В этом примере можно увидеть, что получатели обнаруженного сообщения электронной почты имеют четыре устройства и одно имеет оповещение. Щелкнув ссылку для устройства, откроет свою страницу в Центр безопасности в Microsoft Defender ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Дополнительные дополнительные Центр безопасности в Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/use)** (также именуемой порталом Microsoft Defender для конечных точек).)

## <a name="requirements"></a>Требования

- Ваша организация должна иметь Microsoft Defender для Office 365 (или Office 365 E5) и Microsoft Defender для конечной точки.

- Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную в Центре & [безопасности.](https://protection.office.com) (См. разрешения в центре [& безопасности)](permissions-in-the-security-and-compliance-center.md)

- Необходимо иметь доступ как [к Explorer (так](threat-explorer.md) и к обнаружениям в режиме реального времени) в Центре & безопасности и Центр безопасности в Microsoft Defender.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки

Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки настроена с помощью центра & безопасности и Центр безопасности в Microsoft Defender.

1. В качестве глобального администратора или администратора безопасности <https://protection.office.com> войдите и войдите. (Это делает вас в центре Office 365 безопасности & соответствия требованиям.)

2. В области навигации выберите **Обозреватель управления** \> **угрозами.**

   ![Обозреватель в меню Управления угрозами](../../media/ThreatMgmt-Explorer-nav.png)

3. В правом верхнем углу экрана выберите **Defender for Endpoint Параметры (MDE Параметры).**

4. В диалоговом окне Microsoft Defender для подключения к конечной точке включите Подключение **в Microsoft Defender для конечной точки.**

   ![Microsoft Defender для подключения к конечной точке](../../media/Explorer-WDATPConnection-dialog.png)

5. Перейдите к Центр безопасности в Microsoft Defender ( <https://securitycenter.windows.com> ).

6. В панели навигации выберите **Параметры**. Затем в **статье General** выберите **расширенные функции**.

7. Прокрутите **Office 365 для подключения к службе сведении** об угрозах и включите подключение.

   ![Office 365 связи с данными об угрозах](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Связанные статьи

[Возможности расследования и реагирования на угрозы в Office 365](office-365-ti.md)

[Microsoft Defender для Office 365](defender-for-office-365.md)

[Microsoft Defender для конечной точки](/windows/security/threat-protection)
