---
title: Использование средства экспорта eDiscovery Office 365 в Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Для загрузки результатов поиска из поиска контента и обнаружения электронных данных в центре безопасности и соответствия требованиям необходимо включить поддержку ClickOnce, чтобы использовать последнюю версию Microsoft Edge.
ms.openlocfilehash: 80924b124521b24ffabf1e0273802265cd715500
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710348"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>Использование средства экспорта eDiscovery Office 365 в Microsoft Edge

В результате последних изменений, внесенных в последнюю версию Microsoft EDGE, поддержка ClickOnce больше не включена по умолчанию. Чтобы продолжить использование средства экспорта обнаружения электронных данных Microsoft Office 365 для загрузки результатов поиска и обнаружения электронных данных, необходимо использовать [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) или включить поддержку ClickOnce в последней версии Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Включение поддержки ClickOnce в Microsoft Edge

1. В Microsoft Edge последовательно выберите пункты **edge://flags/#edge — один раз**.

2. Если в раскрывающемся списке существующее значение установлено **по умолчанию** или **отключено** , измените его на **Enabled**.

   ![](../media/ClickOnceimage1.png)

3. Прокрутите окно вниз до конца окна браузера и выберите команду **перезапустить** , чтобы перезапустить пограничный сервер.

   ![](../media/ClickOnceimage2.png)

**Примечание:** Для отключения поддержки ClickOnce в организациях можно использовать групповую политику. Чтобы проверить, существует ли политика Организации для поддержки ClickOnce, перейдите в **Edge://Policy**. На следующем снимке экрана показано, что технология ClickOnce включена во всей Организации. Если для этого параметра политики задано значение **false**, необходимо обратиться к администратору в Организации.

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Установка и запуск средства экспорта eDiscovery

1. Нажмите кнопку **скачать результаты** на всплывающей странице экспорта в поиске контента или в случае обнаружения электронных данных.

   ![Нажмите кнопку Скачать результаты на всплывающей странице, чтобы скачать результаты поиска.](../media/ClickOnceExport1.png)

2. Появится запрос на подтверждение запуска средства, нажмите кнопку **Открыть**.

   ![Нажмите кнопку Открыть, чтобы запустить средство экспорта eDiscovery](../media/ClickOnceimage4.png)

   Если средство экспорта обнаружения электронных данных Microsoft Office 365 не установлено, появится предупреждение системы безопасности, 

   ![Нажмите кнопку установить, чтобы установить средство экспорта обнаружения электронных данных](../media/ClickOnceimage5.png)

3. Нажмите кнопку **Установить**. После установки средство экспорта будет запущено автоматически.

Дополнительную информацию см. в следующих статьях:

- [Экспорт результатов поиска контента](export-search-results.md)

- [Включение поэкспериментических флагов в Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
