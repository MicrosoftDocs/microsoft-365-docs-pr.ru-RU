---
title: REST API модели осмысления документации SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Обзор REST API модели осмысления документа SharePoint Syntex.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908093"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>REST API модели осмысления документации SharePoint Syntex

С помощью интерфейса REST в SharePoint можно создать модель осмысления документации, применить или удалить модель в одной или нескольких библиотеках, а также получить или обновить сведения о модели. 

Служба REST в SharePoint Online (а также локальной среде SharePoint 2016 или более поздней версии) поддерживает объединение нескольких запросов в один вызов службы с помощью параметра запроса OData $batch. 

Подробные сведения и ссылки на примеры кода см. в статье [Отправка пакетных запросов с помощью интерфейсов REST API](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступить к работе, убедитесь, что вы знакомы с понятиями, описанными в следующих статьях:

- [Знакомство со службой REST в SharePoint](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [Выполнение базовых операций с использованием конечных точек REST SharePoint](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a>Команды REST

Для работы с моделями осмысления документации Syntex доступны следующие команды REST.

- [Создать модель](rest-createmodel-method.md) — создает модель и связанный тип контента.
- [GetByUniqueId](rest-getbyuniqueid-method.md) — получает или обновляет сведения о модели осмысления документации SharePoint Syntex.
- [GetByTitle](rest-getbytitle-method.md) — получает или обновляет сведения о модели осмысления документации SharePoint Syntex с помощью названия модели.
- [Применить модель](rest-applymodel-method.md) — применяет (или синхронизирует) обученную модель осмысления документации к одной или нескольким библиотекам.
- [Получить сведения о модели и библиотеке](rest-getmodelandlibraryinfo.md) — получает сведения о модели и библиотеке, к которой она была применена.
- [UpdateModelSettings](rest-updatemodelsettings-method.md) — обновляет доступные параметры моделей (связанную метку хранения и описание модели) для модели осмысления документации SharePoint Syntex.
- [BatchDelete](rest-batchdelete-method.md) — удаляет примененную модель осмысления документации из одной или нескольких библиотек.
- [Создать запрос классификации](rest-createclassificationrequest.md) — создает запрос на классификацию указанного файла или файлов с помощью примененной модели.

## <a name="scenarios"></a>Сценарии

Обратите внимание, что имя метода не всегда отражает суть следующих примеров сценариев. Дополнительные сведения см. в отдельных статьях.

Метод создания модели создает только объект модели и связанный тип контента. Сначала необходимо обучить модель в центре контента, прежде чем ее можно будет применить к библиотеке.

Метод применения модели используется для настройки модели в целевой библиотеке, чтобы классифицировать документы и при желании извлекать дополнительные сведения. Этот API также поддерживает пакетное применение модели к нескольким библиотекам.

Метод удаления модели просто удаляет модель из одной или нескольких библиотек, к которым она была применена ранее. Если вы хотите удалить модель, ее необходимо сначала удалить из всех библиотек, к которым она была применена.


## <a name="see-also"></a>См. также

[Общие сведения об осмыслении документации](../document-understanding-overview.md)

