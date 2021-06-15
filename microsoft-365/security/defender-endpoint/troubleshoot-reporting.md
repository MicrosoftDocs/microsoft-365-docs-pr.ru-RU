---
title: Устранение неполадок с средствами отчетности для microsoft Defender AV
description: Определение и решение распространенных проблем при попытке сообщить в microsoft Defender av protection status in Update Compliance
keywords: устранение неполадок, ошибка, исправление, обновление соответствия требованиям, oms, монитор, отчет, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 405955de63de9f84a783ca1b8c0348c3935440cd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926179"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Устранение неполадок с отчетами антивирусной программы в Microsoft Defender в соответствии с требованиями обновлений

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> 31 марта 2020 г. функция антивирусная программа в Microsoft Defender отчетов о соответствии требованиям к обновлению будет удалена. Вы можете продолжать определять и пересматривать политики соответствия требованиям безопасности с [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)что позволяет более точно контролировать функции безопасности и обновления.

Вы можете использовать антивирусная программа в Microsoft Defender с обновлением соответствия требованиям. Вы увидите состояние лицензий E3, B, F1, VL и Pro. Однако для лицензий E5 необходимо использовать портал [Microsoft Defender для конечных точек.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) Дополнительные возможности лицензирования см. в Windows 10 [вариантов лицензирования продуктов.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

При использовании Windows обновления [аналитики](/windows/deployment/update/update-compliance-using#wdav-assessment) для получения отчетов о состоянии защиты устройств или конечных точек в сети, использующих антивирусная программа в Microsoft Defender, могут возникнуть проблемы или проблемы.

Как правило, наиболее распространенными показателями проблемы являются:
- Вы видите только небольшое число или подмножество всех устройств, которые вы ожидали увидеть
- Вы не видите никаких устройств вообще
- Отчеты и сведения, которые вы видите, устарели (старше нескольких дней)

Общие коды ошибок и коды событий, относящиеся к службе антивирусная программа в Microsoft Defender, не связанные с обновлением соответствия требованиям, см. в антивирусная программа в Microsoft Defender [событиях.](troubleshoot-microsoft-defender-antivirus.md) 

Устранение этих проблем можно решить тремя шагами.

1. Подтверждение того, что вы выполнили все необходимые условия
2. Проверка подключения к облачной Защитник Windows службе
3. Отправка журналов поддержки

>[!IMPORTANT]
>Обычно для начала появления устройств в обновлении требуется 3 дня.


## <a name="confirm-prerequisites"></a>Подтверждение необходимых условий

Для правильного показа устройств в соответствии с обновлениями необходимо выполнить определенные требования как для службы соответствия требованиям обновления, так и для антивирусная программа в Microsoft Defender:

>[!div class="checklist"]
>- Конечные точки используют антивирусная программа в Microsoft Defender в качестве единственного приложения для защиты от антивирусов. [Использование любого другого антивирусного приложения](microsoft-defender-antivirus-compatibility.md) приведет к отключению microsoft Defender AV, а конечная точка не будет отчитаться в обновлении.
> - [Включена облачная защита.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Конечные точки могут [подключаться к облаку AV Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Если конечная точка запущена Windows 10 версии 1607 или более ранней версии, Windows 10 диагностические данные должны быть задарены на [расширенном уровне.](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)
> - Прошло 3 дня с тех пор, как все требования были выполнены

"Вы можете использовать антивирусная программа в Microsoft Defender с обновлением соответствия требованиям. Вы увидите состояние лицензий E3, B, F1, VL и Pro. Однако для лицензий E5 необходимо использовать портал Microsoft Defender для конечных точек (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Дополнительные возможности лицензирования см. в Windows 10 параметры лицензирования продуктов"

Если все вышеперечисленные условия выполнены, может потребоваться перейти к следующему шагу для сбора диагностических сведений и отправки их нам.

> [!div class="nextstepaction"]
> [Сбор диагностических данных для устранения неполадок в соответствии с соответствием требованиям.](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Статьи по теме

- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Развертывание антивирусная программа в Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)