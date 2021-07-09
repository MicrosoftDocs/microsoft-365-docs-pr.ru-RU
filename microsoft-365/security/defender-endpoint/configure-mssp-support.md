---
title: Настройка поддержки поставщика управляемых служб безопасности
description: Примите необходимые меры для настройки интеграции MSSP с Microsoft Defender для конечной точки
keywords: поставщик управляемых служб безопасности, mssp, настройка, интеграция
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d82bffd6eea54256f2c6773f843030a19e27275d
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339362"
---
# <a name="configure-managed-security-service-provider-integration"></a>Настройка интеграции управляемого поставщика службы безопасности

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

Чтобы включить интеграцию поставщика управляемых служб безопасности (MSSP), необходимо предпринять следующие действия по настройке.

>[!NOTE]
>В этой статье используются следующие термины для различия между поставщиком услуг и потребителем услуг:
> - MSSPs. Организации безопасности, которые предлагают отслеживать и управлять устройствами безопасности для организации.
> - Клиенты MSSP. Организации, которые занимаются службами MSSPs.

Интеграция позволит MSSP принять следующие действия:

- Получить доступ к порталу Microsoft 365 Defender msSP
- Получать уведомления электронной почты и 
- Извлечение оповещений с помощью средств управления безопасностью и событий (SIEM)

Прежде чем msSPs смогут принять эти действия, клиент MSSP должен предоставить доступ к своему клиенту Defender для конечной точки, чтобы MSSP получил доступ к порталу. 
 

Как правило, клиенты MSSP принимают начальные шаги по настройке, чтобы предоставить msSPs доступ к Защитник Windows центральному Защитник Windows безопасности. После предоставления доступа клиент MSSP или MSSP могут предпринять другие действия по настройке.


В общем, необходимо предпринять следующие действия по настройке:


- **Предоставление доступа msSP к Microsoft 365 Defender** <br>
Это действие должно быть сделано клиентом MSSP. Предоставляет доступ msSP к клиенту клиента MSSP Defender для конечной точки.
 

- **Настройка уведомлений оповещений, отправленных в MSSP** <br>
Это действие может быть принято либо клиентом MSSP, либо MSSP. Это позволяет msSPs знать, какие оповещения необходимо адресовать для клиента MSSP.

- **Извлечение оповещений клиента MSSP в систему SIEM** <br> Это действие будет принимать msSP. Она позволяет MSSP получать оповещения в средствах SIEM.

- **Извлечение оповещений клиента MSSP с помощью API** <br>
Это действие будет принимать msSP. Она позволяет MSSP получать оповещения с помощью API.

## <a name="multi-tenant-access-for-mssps"></a>Multi-tenant access for MSSPs
Сведения о реализации делегированного доступа с несколькими клиентами см. в нескольких клиентах для поставщиков управляемых [служб безопасности.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)



## <a name="related-topics"></a>Статьи по теме
- [Предоставление MSSP доступа к порталу](grant-mssp-access.md)
- [Получение доступа к порталу клиентов MSSP](access-mssp-portal.md)
- [Настройка уведомлений оповещений](configure-mssp-notifications.md)
- [Получение оповещений от владельца клиента](fetch-alerts-mssp.md)

