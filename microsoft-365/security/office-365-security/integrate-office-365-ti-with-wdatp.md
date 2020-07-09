---
title: Интеграция ATP Office 365 с ATP в Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт для просмотра подробных сведений об управлении угрозами.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086712"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт

[Office 365 Advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) можно настроить для работы с [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection) (Майкрософт Defender ATP).

Интеграция Office 365 ATP с помощью защитника Microsoft Defender может помочь вам в обеспечении безопасности групп и быстро предпринимать действия в случае, если устройства пользователей подвержены риску. Например, если интеграция включена, Группа операций безопасности сможет просматривать устройства, на которые потенциально влияет обнаруженное сообщение электронной почты, а также количество последних оповещений, которые эти устройства имеют в пакет ATP для защитника Майкрософт. 

На следующем рисунке показано, как выглядит вкладка " **устройства** " с включенной интеграцией Microsoft Defender ATP:
  
![Когда включен пакет ATP для защитника, вы можете просмотреть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
В этом примере видно, что получатели обнаруженного сообщения электронной почты имеют четыре устройства, а одно — оповещение. Щелчок ссылки на устройство открывает его страницу в центре безопасности защитника (Майкрософт) ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Узнайте больше о центре безопасности защитника](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (Майкрософт), также называемом порталом ATP для защитника Майкрософт.
  
## <a name="requirements"></a>Requirements

- В вашей организации должен быть Office 365 ATP (план 2) (или Office 365 в) и пакет ATP для защитника Майкрософт.
    
- Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную [в &amp; центре безопасности и соответствия требованиям](https://protection.office.com). (См. [разрешения в центре безопасности и &amp; соответствия требованиям](permissions-in-the-security-and-compliance-center.md))
    
- Необходимо иметь доступ к [проводнику (или обнаружениям в режиме реального времени)](threat-explorer.md) в центре безопасности & соответствия требованиям и центре безопасности защитника Майкрософт.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Интеграция Office 365 ATP с защитником Microsoft для пакета ATP

Интеграция Office 365 ATP с защитником Microsoft для пакета ATP настроена с помощью центра безопасности & соответствия требованиям и центра безопасности защитника Майкрософт.
  
1. Как глобальный администратор или администратор безопасности перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите в нее. (Откроется центр соответствия требованиям & безопасности Office 365.)
    
2. В области навигации выберите Обозреватель **управления угрозами**  >  **Explorer**.<br>![Проводник в меню "Управление угрозами"](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. В правом верхнем углу экрана выберите **Параметры вдатп**.
    
4. В диалоговом окне Подключение к Защитнику (Майкрософт) ATP включите параметр **подключиться к Windows ATP**.<br>![Подключение к Microsoft Defender ATP](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Перейдите в центр безопасности защитника (Майкрософт [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ().

6. В панели навигации выберите **Параметры**. Затем в разделе **Общие**выберите **Дополнительные функции**.

7. Прокрутите список вниз до раздела **Office 365 Threat Intelligence Connection**и включите подключение.<br/>![Подключение к бизнес-аналитике Office 365](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Статьи по теме

[Исследование угроз и возможности реагирования в Office 365](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)
