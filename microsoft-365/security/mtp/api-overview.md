---
title: Обзор API Microsoft 365 Defender
description: Узнайте о доступных API в Microsoft 365 Defender
keywords: API, API, обзор, инцидент, инциденты, охота на угрозы, Защитник Microsoft 365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719194"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Обзор API Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender построен на платформе, готовой к интеграции.

Используйте API Microsoft 365 Defender для автоматизации рабочего процесса на основе общих таблиц инцидента и таблицы расширенных охоты.

- **[Объединенная очередь инцидентов](api-incident.md)** — сосредоточься на том, что важно, сгруппив всю область атаки и все активы, на которые влияет API инцидентов.

- **[Кросспроигрывная](api-advanced-hunting.md)** охота на угрозы — используйте организационные знания вашей группы безопасности, чтобы искать признаки компрометации, создавая собственные пользовательские запросы для отсев необработанных данных, собранных в нескольких продуктах защиты.

Наряду с этими API Для Защитника Microsoft 365 каждый из наших других продуктов безопасности предоставляет дополнительные [API,](api-articles.md) которые помогут вам воспользоваться их уникальными возможностями.

## <a name="learn-more"></a>Дополнительные сведения

| **Как получить доступ к API** |
|-|
| [Узнайте о квотах API и лицензировании](api-terms.md) |
| [Доступ к API Microsoft 365 Defender](api-access.md) |
| **Создание приложений** |
| [Создание приложения "Hello world"](api-hello-world.md) |
| [Создание приложения для доступа к API Microsoft 365 Defender от имени пользователя](api-create-app-user-context.md) |
| [Создание приложения для доступа к Защитнику Microsoft 365 без пользователя](api-create-app-web.md) |
| [Создание приложения с мультиязычным доступом партнеров к API Защитника Microsoft 365](api-partner-access.md) |
| **Устранение неполадок и обслуживание приложений** |
| [Коды ошибок API](api-error-codes.md) |
| [Управление секретами в приложениях с помощью Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Реализация авторизации OAuth 2.0 для входов пользователей](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
