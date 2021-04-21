---
title: Обзор API Защитника Microsoft 365
description: Узнайте о доступных API в Microsoft 365 Defender
keywords: api, apis, обзор, инциденты, инциденты, охота на угрозы, защитник Microsoft 365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904192"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Обзор API Защитника Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Microsoft 365 Defender построен на платформе, готовой к интеграции.

Используйте API Защитника Microsoft 365 для автоматизации рабочего процесса на основе общих таблиц инцидента и расширенных таблиц охоты.

- **[Совмещенная очередь](api-incident.md)** инцидентов . Фокус на том, что имеет решающее значение, сгруппив всю область атаки и все влияющие активы вместе в API инцидента.

- **[Межпродукционная](api-advanced-hunting.md)** охота на угрозы — использование организационных знаний группы безопасности для охоты за признаками компромисса, создав собственные пользовательские запросы для просеки необработанных данных, собранных в нескольких продуктах защиты.

Наряду с этими API, определенными для Microsoft 365 Defender, каждый из наших других продуктов безопасности предоставляет дополнительные [API,](api-articles.md) которые помогут вам воспользоваться их уникальными возможностями.


> [!NOTE]
> Переход на единый портал не должен влиять на панели мониторинга PowerBi на основе API Microsoft Defender для конечных точек. Вы можете продолжать работать с существующими API независимо от интерактивного перехода портала.


## <a name="learn-more"></a>Подробнее

| **Понимание доступа к API** |
|-|
| [Узнайте о квотах API и лицензировании](api-terms.md) |
| [Доступ к API защитника Microsoft 365](api-access.md) |
| **Создание приложений** |
| [Создание приложения "Hello world"](api-hello-world.md) |
| [Создание приложения для доступа к API Защитника Microsoft 365 от имени пользователя](api-create-app-user-context.md) |
| [Создание приложения для доступа к Microsoft 365 Defender без пользователя](api-create-app-web.md) |
| [Создание приложения с несколькими партнерами-партнерами для API Защитника Microsoft 365](api-partner-access.md) |
| **Устранение неполадок и обслуживание приложений** |
| [Понимание кодов ошибок API](api-error-codes.md) |
| [Управление секретами в приложениях с помощью хранилища ключей Azure](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Реализация авторизации OAuth 2.0 для входных данных пользователя](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |