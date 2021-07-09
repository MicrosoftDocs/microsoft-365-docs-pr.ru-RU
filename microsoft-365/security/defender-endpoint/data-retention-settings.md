---
title: Проверка расположения хранилища данных и обновление параметров хранения данных
description: Проверка расположения хранилища данных и обновление параметров хранения данных для Microsoft Defender для конечной точки
keywords: данные, хранение, параметры, хранение, обновление
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: eb9e4b905112d3d144b10d68418695df3cda29cb
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339254"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a>Проверка расположения хранилища данных и обновление параметров хранения данных для Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-gensettings-abovefoldlink)

Во время процесса работы с бортовой установкой мастер проводит вас через параметры хранения и хранения данных Defender для конечной точки. 

После завершения бортовой установки можно проверить выбор на странице параметры хранения данных.

## <a name="verify-data-storage-location"></a>Проверка расположения хранилища данных
На [этапе Настройка](production-deployment.md)выбрано расположение для хранения данных. 

Вы можете проверить расположение данных, переназначив Параметры  >  **конечных**  >  **точек хранения данных.**

## <a name="update-data-retention-settings"></a>Обновление параметров хранения данных

Вы можете обновить параметры хранения данных. По умолчанию период хранения составляет 180 дней. 

1. В области навигации выберите **Параметры**  >  **конечных точек**  >  **хранения данных.**

2. Выберите продолжительность хранения данных из выпадаемого списка.

    > [!NOTE]
    > Другие параметры не могут быть изменены.

3. Нажмите **кнопку Сохранить предпочтения**.


## <a name="related-topics"></a>Статьи по теме
- [Обновление параметров хранения данных](data-retention-settings.md)
- [Настройка оповещений в Defender для конечной точки](configure-email-notifications.md)
- [Настройка дополнительных функций](advanced-features.md)
