---
title: Повторное поиск контента для устранения ошибки расположения контента
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Во время расследования можно использовать кнопку Retry для разрешения поиска контента с ошибками расположения контента.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311824"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Повторное поиск контента для устранения ошибки расположения контента

При использовании поиска контента в центре безопасности и соответствия требованиям для поиска большого количества почтовых ящиков могут возникнуть ошибки поиска, аналогичные ошибке:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Эти ошибки (с кодами ошибок CS001-002, CS003-002, CS008-009, CS012-002 и другими ошибками формы CS0XX-0XX) указывают на то, что поиск контента не удалось найти определенные расположения контента; В этом примере два почтовых ящика не были отправлены в поиск. Эти ошибки отображаются на странице сведений о состоянии на странице поиска контента.

## <a name="cause-of-content-location-errors"></a>Причина ошибок расположения контента

При поиске большого количества почтовых ящиков поиск распространяется на тысячи серверов центра обработки данных Майкрософт. В любое время определенные серверы могут быть в состоянии перезагрузки или в процессе отказа от избыточных копий. В любом из этих случаев запрос поиска контента на извлечение данных будет отстает. В предыдущем примере ошибки для сбоя почтовых ящиков были результатом времени поиска.

## <a name="resolving-content-location-errors"></a>Устранение ошибок расположения контента

Перезапуск поиска часто приводит к аналогичным ошибкам на разных серверах. Вместо перезапуска поиска нажмите кнопку **Retry,** отображаемую в верхней части страницы результатов поиска.

![Нажмите кнопку Retry для устранения ошибок расположения контента](../media/retrycontentsearch3.png)

Это приведет к повторному поиску только для сбоя почтовых ящиков. При повторном поиске сохраняются другие успешно возвращенные результаты.

## <a name="tips-to-avoid-content-location-errors"></a>Советы, чтобы избежать ошибок расположения контента

Вот некоторые дополнительные причины ошибок расположения контента и советы, которые помогут избежать их при поиске большого количества почтовых ящиков.

- Поиск почтового ящика может быть занят из-за активности пользователя. В этом случае служба поиска может затормошать себя, чтобы не допустить недоступности почтового ящика. Чтобы избежать этого, попробуйте запускать поиск в не-бизнес-часы.

- Запрос поиска может быть поиск слишком содержимого из почтового ящика. По возможности попробуйте сузить область поиска с помощью ключевых слов, диапазонов дат и условий поиска.

- Слишком много ключевых слов или фраз ключевых слов при создании поискового запроса с помощью списка [ключевых слов](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches). При запуске поискового запроса, использующего список ключевых слов, служба по сути выполняет отдельный поиск для каждой строки в списке ключевых слов, чтобы можно было получить статистику. Если вы используете список ключевых слов в поисковых запросах, свести к минимуму количество строк в списке ключевых слов или разделить число ключевых слов на более мелкие списки и создать другой поиск для каждого списка ключевых слов.

  > [!NOTE]
  > Чтобы уменьшить проблемы, вызванные большими списками ключевых слов, теперь в списке ключевых слов поискового запроса ограничено не более 20 строк.

- В одном почтовом ящике одновременно выполняется слишком много поисков. По возможности попробуйте выполнить один поиск одновременно на любом почтовом ящике.

- Поиск слишком много почтовых ящиков в одном поиске. Вероятность ошибок расположения контента увеличивается при поиске большого количества почтовых ящиков. По возможности попробуйте выполнить несколько поисков, чтобы каждый поиск включал подмножество почтовых ящиков в организации.

- В почтовом ящике выполняется обязательное обслуживание. Хотя эта причина, вероятно, происходит нечасто, подождите некоторое время после получения ошибки расположения контента, а затем повторного поиска.
