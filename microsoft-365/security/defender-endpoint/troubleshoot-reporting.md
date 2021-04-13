---
title: Устранение неполадок с средствами отчетности для microsoft Defender AV
description: Определение и решение распространенных проблем при попытке сообщить в microsoft Defender av protection status in Update Compliance
keywords: устранение неполадок, ошибка, исправление, обновление соответствия требованиям, oms, монитор, отчет, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1a1c807c86aa95148300298484319001b59963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691590"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Устранение неполадок в антивирусной отчетности Microsoft Defender в обновлении соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> 31 марта 2020 г. функция антивирусной отчетности Microsoft Defender в соответствии с обновлениями будет удалена. Вы можете продолжать определять и пересматривать политики соответствия требованиям безопасности с помощью [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)что позволяет более точно контролировать функции безопасности и обновления.

Антивирус Microsoft Defender можно использовать с соблюдением требований к обновлению. Вы увидите состояние лицензий E3, B, F1, VL и Pro. Однако для лицензий E5 необходимо использовать портал [Microsoft Defender для конечных точек.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) Дополнительные информацию о вариантах лицензирования см. в [меню Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

При использовании соответствия требованиям обновления [Windows Analytics](/windows/deployment/update/update-compliance-using#wdav-assessment) для получения отчетов о состоянии защиты устройств или конечных точек в сети, использующих антивирус Microsoft Defender, могут возникнуть проблемы или проблемы.

Как правило, наиболее распространенными показателями проблемы являются:
- Вы видите только небольшое число или подмножество всех устройств, которые вы ожидали увидеть
- Вы не видите никаких устройств вообще
- Отчеты и сведения, которые вы видите, устарели (старше нескольких дней)

Общие коды ошибок и коды событий, относящиеся к антивирусной службе Microsoft Defender, не связанные с соответствием требованиям к обновлению, см. в [веб-сайте События](troubleshoot-microsoft-defender-antivirus.md)антивируса Microsoft Defender. 

Устранение этих проблем можно решить тремя шагами.

1. Подтверждение того, что вы выполнили все необходимые условия
2. Проверка подключения к облачной Защитник Windows службе
3. Отправка журналов поддержки

>[!IMPORTANT]
>Обычно для начала появления устройств в обновлении требуется 3 дня.


## <a name="confirm-prerequisites"></a>Подтверждение необходимых условий

Для правильного показа устройств в обновлении необходимо выполнить определенные требования как для службы соответствия требованиям обновления, так и для антивируса Microsoft Defender:

>[!div class="checklist"]
>- Конечные точки используют антивирус Microsoft Defender в качестве единственного приложения для защиты от антивирусов. [Использование любого другого антивирусного приложения](microsoft-defender-antivirus-compatibility.md) приведет к отключению microsoft Defender AV, а конечная точка не будет отчитаться в обновлении.
> - [Включена облачная защита.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Конечные точки могут [подключаться к облаку AV Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Если конечная точка работает под управлением Windows 10 версии 1607 или более ранней версии, диагностические данные Windows 10 должны быть задарены на [расширенном уровне.](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)
> - Прошло 3 дня с тех пор, как все требования были выполнены

"Вы можете использовать антивирус Microsoft Defender с обновлением соответствия требованиям. Вы увидите состояние лицензий E3, B, F1, VL и Pro. Однако для лицензий E5 необходимо использовать портал Microsoft Defender для конечных точек https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) (. Дополнительные информацию о вариантах лицензирования см. в дополнительных версиях лицензирования продуктов Windows 10"

Если все вышеперечисленные условия выполнены, может потребоваться перейти к следующему шагу для сбора диагностических сведений и отправки их нам.

> [!div class="nextstepaction"]
> [Сбор диагностических данных для устранения неполадок в соответствии с соответствием требованиям.](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Статьи по теме

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Развертывание антивируса Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)