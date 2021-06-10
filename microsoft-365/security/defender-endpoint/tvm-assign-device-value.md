---
title: Назначение значения устройства — контроль угроз и уязвимостей
description: Узнайте, как назначить устройству низкое, нормальное или высокое значение, чтобы помочь вам различать приоритеты активов.
keywords: Значение Microsoft Defender для конечных устройств, контроль угроз и уязвимостей устройства, устройства с высоким значением, оценка экспозиции значения устройства
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935201"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a>Назначение значения устройства — контроль угроз и уязвимостей

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Угроза и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Определение значения устройства позволяет различать приоритеты активов. Значение устройства используется для включения аппетита к риску отдельного актива в контроль угроз и уязвимостей оценки экспозиции. Устройства, назначенные как "высокое значение", будут получать больше веса.

Вы также можете использовать API значения [за установленного устройства.](set-device-value.md)

Параметры значения устройства:

- Низкие
- С обычными интервалами (по умолчанию)
- Фишинговое сообщение с

Примеры устройств, которые должны быть назначены с высоким значением:

- Контроллеры домена, Active Directory
- Устройства с подключением к Интернету
- VIP-устройства
- Устройства, на которые размещены внутренние и внешние производственные службы

## <a name="choose-device-value"></a>Выбор значения устройства

1. Перейдите на любую страницу устройства, самое простое место из инвентаризации устройства.

2. Выберите **значение Device** из трех точек рядом со стойкой действий в верхней части страницы.

    ![Пример отсев значения устройства.](images/tvm-device-value-dropdown.png)

3. Вылет появится с текущим значением устройства и его значением. Просмотрите значение устройства и выберите устройство, которое лучше всего подходит вашему устройству.
![Пример вылета значения устройства.](images/tvm-device-value-flyout.png)

## <a name="how-device-value-impacts-your-exposure-score"></a>Влияние значения устройства на оценку экспозиции

Оценка экспозиции — это средневзвешение для всех устройств. Если у вас есть группы устройств, вы также можете фильтровать оценку по группе устройств.

- Вес обычных устройств составляет 1
- Устройства с низким значением имеют вес 0,75
- Устройства с высоким значением имеют вес NumberOfAssets / 10.
    - Если у вас 100 устройств, каждое устройство с высоким значением будет иметь вес 10 (100/10)

## <a name="related-topics"></a>Статьи по теме

- [Обзор угроз и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Оценка экспозиции](tvm-exposure-score.md)
- [Интерфейсы API](next-gen-threat-and-vuln-mgt.md#apis)