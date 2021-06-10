---
title: Расширенная индексация данных хранителя
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Когда хранитель добавляется в Advanced eDiscovery, любое содержимое, которое было сочтено частично индексируемым, будет повторно реализовано, чтобы сделать его полностью поисковым.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911213"
---
# <a name="advanced-indexing-of-custodian-data"></a>Расширенная индексация данных хранителя

Когда хранитель добавляется в Advanced eDiscovery, любое содержимое, которое было сочтено частично индексируемым, будет повторно реализовано, чтобы сделать его полностью поисковым.  Этот процесс называется *Advanced indexing*. Содержимое может быть частично индексироваться по ряду причин, включая наличие изображений, неподтверченных типов файлов или при индексации ограничений размера файла.

Дополнительные материалы о поддержке обработки и частично индексациях элементов см. в статьи:

- [Поддерживаемые типы файлов в Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Частично индексированные элементы в средстве "Поиск контента" в Office 365](partially-indexed-items-in-content-search.md)

- [Форматы файлов, индексируемые службой поиска Exchange](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Просмотр результатов предварительной индексации

После завершения процесса предварительной индексации можно получить представление об эффективности обработки.  В представлении результатов предварительной индексации на вкладке **Обработка** для случая на графике перечислены количество элементов, добавленных в *гибридный индекс.*  Гибридный индекс — это Advanced eDiscovery, где хранится повторное содержимое.

Это представление также включает количество элементов, которые требуют исправлений, и еще один график ошибок по типу файла. Дополнительные сведения см. в указанных ниже статьях.

- [Исправление ошибок при обработке данных](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Исправление ошибки одного элемента](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Обновление индекса Advanced для хранителей

При добавлении хранителя в Advanced eDiscovery случае все частично индексные элементы будут повторно проиндексироваться. Однако с течением времени в почтовый ящик или учетную запись пользователя может быть добавлено OneDrive элементов.  При необходимости можно обновить индекс для конкретного хранителя. Дополнительные сведения см. в [статью Управление хранителями в Advanced eDiscovery случае](manage-new-custodians.md#re-index-custodian-data). Вы также можете обновить индекс для всех хранителей в случае, щелкнув индекс **Обновления** на вкладке **Обработка.**

> [!NOTE]
> Обновление индексов хранителя — это длительный процесс. Рекомендуется не обновлять индексы несколько раз в день.