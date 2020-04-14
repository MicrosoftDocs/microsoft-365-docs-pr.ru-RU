---
title: Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
ms.openlocfilehash: a2634a70bdbdd21efe2c59721e5532500eb4e4cc
ms.sourcegitcommit: 4c6af6530b4997055b8e60bf532e75cbc72fb6c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "43284231"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Интеграция Office 365 Advanced Threat protection с Advanced Threat Protection в защитнике Майкрософт

Если вы участвуете в группе безопасности Организации, вы можете интегрировать [Office 365 Advanced Threat protection](office-365-atp.md) и соответствующие функции расследования и ответа с помощью [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection). Это поможет быстро выяснить, подвержены ли компьютеры пользователям риску при изучении угроз в Office 365. Например, после включения интеграции вы сможете просмотреть список компьютеров, используемых получателями обнаруженного сообщения электронной почты, а также о том, сколько последних оповещений у этих компьютеров у них есть в Advanced Threat Protection в защитнике Майкрософт.
  
На следующем рисунке показана вкладка " **устройства** ", которая будет отображаться при включенной интеграции защитника Microsoft Defender:
  
![Когда включен пакет ATP для защитника, вы можете просмотреть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
В этом примере видно, что получатели сообщения электронной почты имеют четыре устройства, а одно — оповещение. Щелчок ссылки на устройство открывает его страницу в центре безопасности защитника Майкрософт.
  
## <a name="requirements"></a>Requirements

- В вашей организации должен быть Office 365 ATP (план 2) (или Office 365 в) и пакет ATP для защитника Майкрософт.
    
- Необходимо быть глобальным администратором Office 365 или иметь роль администратора безопасности (например, администратора безопасности), назначенную в [центре &amp; безопасности и соответствия требованиям](https://protection.office.com). (См. [разрешения в центре безопасности &amp; и соответствия требованиям Office 365](permissions-in-the-security-and-compliance-center.md))
    
- Необходимо иметь доступ к [проводнику (или обнаружениям в режиме реального времени)](threat-explorer.md) в центре безопасности & соответствия требованиям и центре безопасности защитника Майкрософт.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Интеграция Office 365 ATP с защитником Microsoft для пакета ATP

Интеграция Office 365 ATP с защитником Microsoft для пакета ATP настроена с помощью центра безопасности & Office 365 и центра безопасности защитника Майкрософт.
  
1. Как глобальный администратор Office 365 или администратор безопасности перейдите на [https://protection.office.com](https://protection.office.com) страницу и войдите в нее.
    
2. Выберите \> **Обозреватель** **управления угрозами** .<br>![Проводник в меню "Управление угрозами"](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. В правом верхнем углу экрана выберите **Параметры вдатп**.
    
4. В диалоговом окне Подключение к Защитнику (Майкрософт) ATP включите параметр **подключиться к Windows ATP**.<br>![Подключение к Microsoft Defender ATP](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Включите подключение в центре безопасности защитника (Майкрософт)[https://securitycenter.windows.com](https://securitycenter.windows.com)().

## <a name="related-topics"></a>Статьи по теме

[Исследование угроз и возможности реагирования в Office 365](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

