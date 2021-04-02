---
title: Использование общих запросов в расширенной охоте
description: Быстро начинайте охоту на угрозы с помощью готовых и общих запросов. Делитесь своими запросами с людьми или со своей организацией.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, mdatp, microsoft defender atp, поиск wdatp, запрос, телеметрия, пользовательские обнаружения, схема, kusto, github repo, мои запросы, общие запросы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 78a532167e4256e3453803f1a0b4a9e4875771cf
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499426"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Использование общих запросов в расширенной охоте

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Запросами [расширенной охоты](advanced-hunting-overview.md) можно делиться с пользователями одной организации. Вы также можете найти общедоступные запросы в GitHub. Эти запросы позволяют быстро реализовывать сценарии охоты на угрозы, не создавая запросы с нуля.

![Изображение общих запросов](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Сохранение и изменение запроса и предоставление к нему общего доступа
Вы можете сохранить новый или существующий запрос, чтобы он был доступен только вам, или поделиться им с пользователями своей организации.

1. Введите новый запрос или загрузим существующий из **разделов Общие запросы** или **Мои запросы.**

2. Выберите **сохранить** **или сохранить как** из параметров сохранения. Чтобы не переписать существующий запрос, выберите **Сохранить как**.

3. Введите имя запроса.

   ![Изображение сохранения запроса](images/advanced-hunting-save-query.png)

4. Выберите папку, в которую нужно сохранить запрос.
    - **Общие запросы** — общие для всех пользователей в вашей организации
    - **Мои запросы** — доступны только для вас
    
5. Нажмите кнопку **Сохранить**.

## <a name="delete-or-rename-a-query"></a>Удаление или переименование запроса
1. Щелкните правой кнопкой мыши запрос, который нужно переименовать или удалить.

    ![Изображение удаления запроса](images/atp_advanced_hunting_delete_rename.png)

2. Нажмите кнопку **Удалить** и подтвердите удаление. Или нажмите кнопку **Переименовать** и введите новое имя запроса.

## <a name="create-a-direct-link-to-a-query"></a>Создание прямой ссылки на запрос
Чтобы создать ссылку, открываемую запрос непосредственно в редакторе предварительного запроса охоты, завершите запрос и выберите **ссылку Share.**

## <a name="access-queries-in-the-github-repository"></a>Доступ к запросам в репозитории GitHub  
Исследователи безопасности Майкрософт часто делятся запросами расширенной охоты в [специальном общедоступном репозитории в GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries). Этот репозиторий открыт для участия. Чтобы внести свой вклад, [бесплатно присоединяйтесь к GitHub](https://github.com/). 

>[!TIP]
>Исследователи безопасности Майкрософт также предоставляют запросы расширенной охоты, которые можно использовать для обнаружения действий и индикаторов, связанных с возникающими угрозами. Эти запросы предоставляются в рамках отчетов [аналитики угроз](threat-analytics.md) в Центре безопасности в Microsoft Defender.

## <a name="related-topics"></a>См. также
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
- [Обзор настраиваемых обнаружений](overview-custom-detections.md)
