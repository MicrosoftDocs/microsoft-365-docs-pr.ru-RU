---
title: Использование защитника Microsoft для Office 365 вместе с защитником Майкрософт для конечной точки
f1.keywords:
- NOCSH
keywords: интеграция, защитник Майкрософт, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Используйте защитник Майкрософт для Office 365 вместе с Advanced Threat Protection в защитнике Майкрософт, чтобы получить более подробные сведения об угрозах для ваших устройств и содержимого электронной почты.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c95e15c3cf16547843f9d2976dbf9df0d5747c0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48309241"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-advanced-threat-protection"></a>Использование защитника Microsoft для Office 365 вместе с Advanced Threat Protection в защитнике Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Защитник Майкрософт для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) можно настроить для работы с [защитником Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection).

Интеграция защитника Microsoft для Office 365 с помощью защитника Майкрософт для конечной точки может помочь вашей группе управления операциями безопасности и быстро выполнить действия в случае риска на устройствах пользователей. Например, если интеграция включена, Группа операций безопасности сможет видеть устройства, на которые потенциально влияет обнаруженное сообщение электронной почты, а также количество последних оповещений, созданных для этих устройств в Microsoft Defender для конечной точки. 

На следующем рисунке показано, как выглядит эта вкладка " **устройства** " с включенным защитником Майкрософт для интеграции конечных точек:
  
![Если защитник Майкрософт для конечной точки включен, вы можете просмотреть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
В этом примере видно, что получатели обнаруженного сообщения электронной почты имеют четыре устройства, а одно — оповещение. Щелчок ссылки на устройство открывает его страницу в центре безопасности защитника (Майкрософт) ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Узнайте больше о центре безопасности защитника](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (Майкрософт), также называемом порталом ATP для защитника Майкрософт.
  
## <a name="requirements"></a>Требования

- У вашей организации должен быть защитник Майкрософт для Office 365 (или Office 365 в ~) и защитник Майкрософт для конечной точки.
    
- Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную [в &amp; центре безопасности и соответствия требованиям](https://protection.office.com). (См. [разрешения в центре безопасности и &amp; соответствия требованиям](permissions-in-the-security-and-compliance-center.md))
    
- Необходимо иметь доступ к [проводнику (или обнаружениям в режиме реального времени)](threat-explorer.md) в центре безопасности & соответствия требованиям и центре безопасности защитника Майкрософт.
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Интеграция защитника Microsoft для Office 365 с защитником Майкрософт для конечной точки

Интеграция защитника Microsoft для Office 365 с защитником Майкрософт для конечной точки настраивается с помощью центра безопасности & соответствия требованиям и центра безопасности защитника Майкрософт.
  
1. Как глобальный администратор или администратор безопасности перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите в нее. (Откроется центр соответствия требованиям & безопасности Office 365.)
    
2. В области навигации выберите Обозреватель **управления угрозами**  >  **Explorer**.<br>![Проводник в меню "Управление угрозами"](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. В правом верхнем углу экрана выберите **Параметры вдатп**.
    
4. В диалоговом окне защитник (Майкрософт) для подключения к конечной точке включите параметр **подключиться к Windows ATP**.<br>![Защитник Майкрософт для подключения к конечной точке](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Перейдите в центр безопасности защитника (Майкрософт [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ().

6. В панели навигации выберите **Параметры**. Затем в разделе **Общие**выберите **Дополнительные функции**.

7. Прокрутите список вниз до раздела **Office 365 Threat Intelligence Connection**и включите подключение.<br/>![Подключение к бизнес-аналитике Office 365](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Статьи по теме

[Исследование угроз и возможности реагирования в Office 365](office-365-ti.md)
  
[Защитник Майкрософт для Office 365](office-365-atp.md)
  
[Защитник Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection)
