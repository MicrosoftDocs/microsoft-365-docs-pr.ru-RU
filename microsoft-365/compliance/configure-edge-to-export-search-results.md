---
title: Использование средства экспорта eDiscovery Office 365 в Microsoft Edge
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Необходимо включить поддержку ClickOnce, чтобы использовать Microsoft Edge для экспорта результатов поиска из поиска контента и обнаружения электронных данных в центре безопасности и соответствия требованиям.
ms.openlocfilehash: 75595f45a1369eb732c2249258af21edced86890
ms.sourcegitcommit: 062be618f0b18611001552273bb175020420e463
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "39676892"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>Использование средства экспорта eDiscovery Office 365 в Microsoft Edge

В результате последних изменений в Microsoft EDGE поддержка ClickOnce больше не включена по умолчанию. Чтобы продолжить использование средства экспорта обнаружения электронных данных Microsoft Office 365 для загрузки результатов поиска и обнаружения электронных данных, необходимо использовать [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) или включить поддержку ClickOnce в Microsoft Edge.

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a>Включение поддержки ClickOnce в Microsoft Edge

1. В Microsoft Edge перейдите в **раздел edge://flags/#edge — один раз**.

2. Если в раскрывающемся списке существующее значение установлено **по умолчанию** или **отключено** , измените его на **Enabled**.
    
   ![](media/ClickOnceimage1.png)

3. Прокрутите окно вниз до конца окна браузера и выберите команду **перезапустить** , чтобы перезапустить пограничный сервер.

   ![](media/ClickOnceimage2.png)

**Примечание:** Для отключения поддержки ClickOnce в организациях можно использовать групповую политику. Чтобы проверить, существует ли политика Организации для поддержки ClickOnce, перейдите в раздел **Edge://Policy**. На следующем снимке экрана показано, что технология ClickOnce включена во всей Организации. Если для этого параметра политики задано значение **false**, необходимо обратиться к администратору в Организации.

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a>Установка и запуск средства экспорта eDiscovery для Office 365

1. Нажмите кнопку **скачать результаты** на всплывающей странице экспорта в поиске контента или в случае обнаружения электронных данных.

   ![Нажмите кнопку Скачать результаты на всплывающей странице, чтобы скачать результаты поиска.](media/ClickOnceExport1.png)

2. Появится запрос на подтверждение запуска средства, нажмите кнопку **Открыть**.

   ![Нажмите кнопку Открыть, чтобы запустить средство экспорта eDiscovery](media/ClickOnceimage4.png)

   Если средство экспорта обнаружения электронных данных Microsoft Office 365 не установлено, появится предупреждение системы безопасности, 

   ![Нажмите кнопку установить, чтобы установить средство экспорта обнаружения электронных данных](media/ClickOnceimage5.png)

3. Нажмите кнопку **Установить**. После установки средство экспорта будет запущено автоматически.

Дополнительную информацию см. в следующих статьях:

- [Экспорт результатов поиска контента](export-search-results.md)

- [Включение поэкспериментических флагов в Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
