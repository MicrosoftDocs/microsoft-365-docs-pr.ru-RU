---
title: Используйте средство экспорта электронных открытий в Microsoft Edge
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
description: Вы должны включить ClickOnce для использования самой новой версии Microsoft Edge для загрузки результатов поиска из центра поиска контента и поиска электронных данных в центре безопасности и соответствия требованиям.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546823"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Используйте средство экспорта электронных открытий в Microsoft Edge

В результате недавних изменений в новейшей версии Microsoft Edge поддержка ClickOnce больше не включена по умолчанию. Чтобы продолжить использование экспортного средства eDiscovery для загрузки результатов поиска контента или поиска по электронной информации, необходимо либо использовать [Microsoft Internet Explorer,](https://support.microsoft.com/help/17621/internet-explorer-downloads) либо включить ClickOnce поддержку в самой новой версии Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Включить ClickOnce в Microsoft Edge

1. В Microsoft Edge перейдите **в edge://flags/#edge-click-once**.

2. Если существующее значение за установлено по **умолчанию** или **отключено** в списке выпаданий, измените его на **Включено.**

   ![Выберите Включено из списка выпаданий](../media/ClickOnceimage1.png)

3. Прокрутите вниз в нижней части окна браузера и нажмите **кнопку Перезапустить,** чтобы перезапустить Edge.

   ![Щелкните Перезапуск](../media/ClickOnceimage2.png)

**Примечание:** Организации могут использовать групповую политику для отключения ClickOnce поддержки. Чтобы проверить, существует ли организационной политики ClickOnce поддержки, перейдите в **edge://policy**. На следующем скриншоте показано ClickOnce включена вся организация. Если это значение политики установлено как **ложное,** необходимо обратиться к администратору в организации.

![Список организационных политик Edge](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Установка и запуск экспортного средства eDiscovery

1. Нажмите **кнопку Скачать** результаты на странице вылет экспорта в поиске контента или случае поиска электронной информации.

   ![Нажмите кнопку Скачать результаты на странице вылет, чтобы скачать результаты поиска](../media/ClickOnceExport1.png)

2. Вам будет предложено подтверждение о запуске средства Нажмите кнопку **Открыть**.

   ![Нажмите кнопку Открыть, чтобы запустить средство экспорта электронных обнаружений](../media/ClickOnceimage4.png)

   Если средство экспорта электронных данных не установлено, вам будет предложено предупреждение о безопасности, 

   ![Щелкните Установите, чтобы установить средство экспорта электронных обнаружений](../media/ClickOnceimage5.png)

3. Нажать кнопку **Установить**. После установки средство экспорта запускается автоматически.

Дополнительную информацию см. в следующих статьях:

- [Экспорт результатов поиска контента](export-search-results.md)

- [Как включить флаги эксперимента в Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
