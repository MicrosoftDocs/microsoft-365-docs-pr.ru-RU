---
title: Использование Microsoft Defender для Office 365 вместе с Microsoft Defender для конечной точки
f1.keywords:
- NOCSH
keywords: интеграция, Microsoft Defender, ATP
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
description: Используйте Microsoft Defender для Office 365 вместе с Microsoft Defender for Endpoint, чтобы получить более подробные сведения об угрозах для устройств и содержимого электронной почты.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166091"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Использование Microsoft Defender для Office 365 вместе с Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender для Office 365](office-365-atp.md) можно настроить для работы с [Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection)

Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки может помочь группе безопасности отслеживать и быстро действовать, если устройства пользователей находятся под угрозой. Например, после включения интеграции группа операций безопасности сможет увидеть устройства, на которые может повлиять обнаруженное сообщение электронной почты, а также количество последних оповещений для этих устройств в Microsoft Defender для конечной точки.

На следующем рисунке по изображена вкладка **"Устройства"** при включенной интеграции с Microsoft Defender для конечных точек:

![Когда Microsoft Defender для конечной точки включен, вы можете увидеть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

В этом примере видно, что у получателей обнаруженного сообщения электронной почты четыре устройства, а на одном из них есть оповещение. Щелкнув ссылку для устройства, вы откроете свою страницу в Центре безопасности Microsoft Defender ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Узнайте больше о Центре](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** безопасности Microsoft Defender (также называется порталом Microsoft Defender для конечных точек).)

## <a name="requirements"></a>Требования

- Ваша организация должна иметь Microsoft Defender для Office 365 (или Office 365 E5) и Microsoft Defender для конечной точки.

- Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную в Центре безопасности [& соответствия требованиям.](https://protection.office.com) [(См. "Разрешения" в Центре безопасности & соответствия требованиям)](permissions-in-the-security-and-compliance-center.md)

- У вас должен быть доступ к [проводнику (или](threat-explorer.md) обнаружению в режиме реального времени) в Центре безопасности & соответствия требованиям и Центре безопасности Microsoft Defender.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки

Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки настроена с помощью Центра безопасности & соответствия требованиям и Центра безопасности Microsoft Defender.

1. В качестве глобального администратора или администратора безопасности войдите <https://protection.office.com> и войдите в нее. (Вы можете ться в Центре безопасности и соответствия & Office 365.)

2. В области навигации выберите **обозреватель управления** \> **угрозами.**

   ![Проводник в меню "Управление угрозами"](../../media/ThreatMgmt-Explorer-nav.png)

3. В правом верхнем углу экрана выберите "Защитник для параметров конечных точек **(параметры MDE)**".

4. В диалоговом окне подключения Microsoft Defender для конечной точки включите подключение к **Microsoft Defender для конечной точки.**

   ![Microsoft Defender для подключения к конечной точке](../../media/Explorer-WDATPConnection-dialog.png)

5. Перейдите в Центр безопасности Microsoft Defender ( <https://securitycenter.windows.com> ).

6. На панели навигации выберите **"Параметры".** Затем в области **"Общие"** выберите **дополнительные функции.**

7. Прокрутите вниз до **подключения Office 365 Threat Intelligence** и включите подключение.

   ![Подключение аналитики угроз Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Статьи по теме

[Возможности исследования угроз и реагирования на них в Office 365](office-365-ti.md)

[Microsoft Defender для Office 365](office-365-atp.md)

[Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection)
