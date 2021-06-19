---
title: Обзор Microsoft 365 Defender API
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
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029733"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>Обзор Microsoft 365 Defender API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Microsoft 365 Defender построена на платформе, готовой к интеграции.

Используйте Microsoft 365 Defender API для автоматизации рабочего процесса на основе общих таблиц инцидента и расширенных таблиц охоты.

- **[Совмещенная очередь](api-incident.md)** инцидентов . Фокус на том, что имеет решающее значение, сгруппив всю область атаки и все влияющие активы вместе в API инцидента.

- **[Межпродукционная](api-advanced-hunting.md)** охота на угрозы — использование организационных знаний группы безопасности для охоты за признаками компромисса, создав собственные пользовательские запросы для просеки необработанных данных, собранных в нескольких продуктах защиты.

Используйте [API потоковой](../defender-endpoint/raw-data-export.md) передачи для отгрузки событий и оповещений в режиме реального времени из экземпляров по мере их возникновения в одном потоке данных.

Наряду с Microsoft 365 Defender API каждый из наших других продуктов безопасности предоставляет дополнительные [API,](api-articles.md) которые помогут вам воспользоваться их уникальными возможностями.

> [!NOTE]
> Переход на единый портал не должен влиять на панели мониторинга PowerBi на основе API Microsoft Defender для конечных точек. Вы можете продолжать работать с существующими API независимо от интерактивного перехода портала.

## <a name="learn-more"></a>Подробнее

| **Понимание доступа к API** |
|-|
| [Узнайте о квотах API и лицензировании](api-terms.md) |
| [Доступ к Microsoft 365 Defender API](api-access.md) |
| **Создание приложений** |
| [Создание приложения "Hello world"](api-hello-world.md) |
| [Создание приложения для доступа Microsoft 365 Defender API от имени пользователя](api-create-app-user-context.md) |
| [Создание приложения для доступа Microsoft 365 Defender без пользователя](api-create-app-web.md) |
| [Создание приложения с несколькими партнерами-партнерами для доступа Microsoft 365 Defender API](api-partner-access.md) |
| **Устранение неполадок и обслуживание приложений** |
| [Понимание кодов ошибок API](api-error-codes.md) |
| [Управление секретами в приложениях с помощью хранилища ключей Azure](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Реализация авторизации OAuth 2.0 для входных данных пользователя](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |