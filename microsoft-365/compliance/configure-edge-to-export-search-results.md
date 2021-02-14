---
title: Использование средства экспорта для eDiscovery в Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Необходимо включить поддержку ClickOnce использовать новую версию Microsoft Edge для скачивания результатов поиска контента и eDiscovery в Центре безопасности и соответствия требованиям.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546823"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Использование средства экспорта для eDiscovery в Microsoft Edge

В результате последних изменений последней версии Microsoft Edge поддержка ClickOnce больше не включена по умолчанию. Чтобы продолжить использование средства экспорта eDiscovery для скачивания результатов поиска контента или eDiscovery, необходимо либо использовать [Microsoft Internet Explorer,](https://support.microsoft.com/help/17621/internet-explorer-downloads) либо включить поддержку ClickOnce в самой новой версии Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Включить поддержку ClickOnce в Microsoft Edge

1. В Microsoft Edge перейдите **к edge://flags/#edge-click-once.**

2. Если в списке **выпаданий** установлено значение Default или **Disabled,** измените его на **"Включено".**

   ![Выберите "Включено" в выпадаемом списке](../media/ClickOnceimage1.png)

3. Прокрутите страницу вниз до нижней части окна браузера и нажмите кнопку **"Перезапустить",** чтобы перезапустить Edge.

   ![Нажмите кнопку "Перезапустить"](../media/ClickOnceimage2.png)

**Примечание.** Организации могут использовать групповую политику для отключения ClickOnce поддержки. Чтобы проверить, существует ли политика организации для поддержки ClickOnce, перейдите **по edge://policy.** На следующем снимке экрана показано ClickOnce включено во всей организации. Если для этого значения политики установлено **значение false,** вам потребуется связаться с администратором в вашей организации.

![Список политик организации edge](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Установка и запуск средства экспорта для eDiscovery

1. Нажмите **кнопку "Скачать** результаты" на странице "Экспорт" в запросе "Поиск контента" или в деле eDiscovery.

   ![Щелкните "Скачать результаты" на странице "Скачать" для скачивания результатов поиска](../media/ClickOnceExport1.png)

2. Вам будет предложено подтвердить запуск средства, нажмите кнопку **"Открыть".**

   ![Нажмите кнопку "Открыть", чтобы запустить средство экспорта eDiscovery](../media/ClickOnceimage4.png)

   Если средство экспорта для eDiscovery не установлено, вам будет предложено предупреждение системы безопасности. 

   ![Click Install to install the eDiscovery Export Tool](../media/ClickOnceimage5.png)

3. Нажмите **Установить**. После установки средство экспорта запустится автоматически.

Дополнительную информацию см. в следующих статьях:

- [Экспорт результатов поиска контента](export-search-results.md)

- [Как включить флаги экспериментов в Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
