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
description: При добавлении хранителя в дело Advanced eDiscovery все содержимое, которое было признано частично индексируемым, повторно обработать, чтобы сделать его полностью искомым.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750760"
---
# <a name="advanced-indexing-of-custodian-data"></a>Расширенная индексация данных хранителя

При добавлении хранителя в дело Advanced eDiscovery все содержимое, которое было признано частично индексируемым, повторно обработать, чтобы сделать его полностью искомым.  Этот процесс называется *"Расширенный индексация".* Контент может быть частично индексироваться по ряду причин, включая наличие изображений, неподтверченные типы файлов или ограничения на размер индексации файлов.

Дополнительные информацию о поддержке обработки и частично индексных элементов см. в:

- [Поддерживаемые типы файлов в Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Частично индексированные элементы в средстве "Поиск контента" в Office 365](partially-indexed-items-in-content-search.md)

- [Форматы файлов, индексируемые службой поиска Exchange](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Просмотр результатов расширенных индексации

После завершения процесса advanced indexing можно получить представление об эффективности обработки.  В представлении результатов "Расширенный индексация" на вкладке "Обработка" для дела на графике перечислены элементы, добавленные в *гибридный индекс.*   Гибридный индекс — это место, где Advanced eDiscovery хранит повторно обобъещенное содержимое.

Это представление также включает количество элементов, которые требуют исправлений, и еще один график ошибок по типу файла. Дополнительные сведения см. в указанных ниже статьях.

- [Исправление ошибок при обработке данных](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Исправление ошибки одного элемента](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Обновление индекса Advanced для хранителей

При добавлении хранителя в дело Advanced eDiscovery все частично индексные элементы повторно обучаются. Однако по мере того как время проходит, в почтовый ящик пользователя или учетную запись OneDrive могут добавляться частично индексные элементы.  При необходимости вы можете обновить индекс для определенного хранителя. Дополнительные сведения см. в [поддомене "Управление хранителями" в деле Advanced eDiscovery.](manage-new-custodians.md#re-index-custodian-data) Вы также можете обновить индекс для всех хранителей в случае, щелкнув индекс обновления **на** вкладке **"Обработка".**

> [!NOTE]
> Обновление индексов хранителя является длительным процессом. Рекомендуется не обновлять индексы более одного раза в день.
