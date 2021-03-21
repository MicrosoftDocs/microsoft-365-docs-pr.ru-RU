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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922190"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Обзор API Защитника Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно изданным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender построен на платформе, готовой к интеграции.

Используйте API Защитника Microsoft 365 для автоматизации рабочего процесса на основе общих таблиц инцидента и расширенных таблиц охоты.

- **[Совмещенная очередь](api-incident.md)** инцидентов . Фокус на том, что имеет решающее значение, сгруппив всю область атаки и все влияющие активы вместе в API инцидента.

- **[Межпродукционная](api-advanced-hunting.md)** охота на угрозы — использование организационных знаний группы безопасности для охоты за признаками компромисса, создав собственные пользовательские запросы для просеки необработанных данных, собранных в нескольких продуктах защиты.

Наряду с этими API, определенными для Microsoft 365 Defender, каждый из наших других продуктов безопасности предоставляет дополнительные [API,](api-articles.md) которые помогут вам воспользоваться их уникальными возможностями.

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