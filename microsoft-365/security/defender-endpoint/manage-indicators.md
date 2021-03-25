---
title: Создание индикаторов
ms.reviewer: ''
description: Создание индикаторов для хеш-файлов, IP-адресов, URL-адресов или доменов, определяющих обнаружение, предотвращение и исключение сущностями.
keywords: управление, разрешено, заблокировано, блокируется, очищается, вредоносный, файл, IP-адрес, URL-адреса, домен
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
ms.openlocfilehash: a04f3be1f13fb57cd76cda7115d014f2ba3aa8d6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198841"
---
# <a name="create-indicators"></a>Создание индикаторов

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Индикатор компрометации (IoCs) является важной функцией в каждом решении по защите конечной точки. Эта возможность позволяет SecOps устанавливать список индикаторов для обнаружения и блокировки (предотвращение и реагирование).

Создание индикаторов, определяющих обнаружение, предотвращение и исключение сущностями. Можно определить действие, которое необходимо принять, а также продолжительность применения действия, а также область действия группы устройств для его применения.

В настоящее время поддерживаемые источники — это двигатель обнаружения облаков Defender для конечной точки, автоматизированный механизм исследования и устранения последствий, а также двигатель предотвращения конечных точек (антивирус Microsoft Defender).

**Движок обнаружения облаков**<br>
Механизм обнаружения облаков Defender для конечной точки регулярно сканирует собранные данные и пытается соответствовать установленным индикаторам. При совпадении действие будет приниматься в соответствии с настройками, указанными для IoC.

**Двигатель предотвращения конечных точек**<br>
Тот же список показателей почитается агентом по профилактике. Это означает, что если microsoft Defender AV является основной конфигурацией AV, то соответствующими индикаторами будут обработаны в соответствии с настройками. Например, если действие "Оповещение и блок", microsoft Defender AV предотвратит выполнение файлов (блок и исправление), и будет поднято соответствующее оповещение. С другой стороны, если действие настроено на "Разрешить", microsoft Defender AV не обнаруживает и не блокирует запуск файла.

**Автоматизированный механизм расследования и восстановления**<BR>
Автоматическое расследование и исправление ведут себя одинаково. Если индикатор задат "Разрешить", автоматизированное расследование и исправление будут игнорировать "плохой" вердикт для него. Если установлено "Block", автоматизированное расследование и исправление будут относиться к нему как к "плохому".


Текущие поддерживаемые действия:
- Разрешить
- Только оповещение
- Оповещение и блокировка


Можно создать индикатор для:
- [Files](indicator-file.md)
- [IP-адреса, URL-адреса/домены](indicator-ip-domain.md)
- [Сертификаты](indicator-certificates.md)


> [!NOTE]
> Существует ограничение в 15 000 показателей на одного клиента. Индикаторы файлов и сертификатов не блокируют [исключения, определенные для антивируса Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) Индикаторы не поддерживаются в антивирусе Microsoft Defender в пассивном режиме. 


## <a name="related-topics"></a>Статьи по теме

- [Создание контекстного IoC](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Используйте API индикаторов Endpoint в Microsoft Defender для](ti-indicator.md)
- [Использование интегрированных решений партнеров](partner-applications.md)
