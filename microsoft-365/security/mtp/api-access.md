---
title: Доступ к API Microsoft 365 Defender
description: Узнайте, как получить доступ к API Microsoft 365 Defender
keywords: доступ, API, контекст приложения, контекст пользователя, приложение aad, маркер доступа
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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719242"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Доступ к API Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Защитник Microsoft 365 предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API помогают автоматизировать процессы и в полной мере использовать возможности Защитника Microsoft 365.

В общем, для использования API необходимо сделать следующее:

- Создание приложения Azure Active Directory
- Получение маркера доступа с помощью этого приложения
- Использование маркера для доступа к API Защитника Microsoft 365

> [!NOTE]
> Для доступа к API требуется проверка подлинности OAuth2.0. Дополнительные сведения см. в потоке кода авторизации [OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

После выполнения этих действий вы можете получить доступ к API Защитника Microsoft 365 с использованием определенного контекста.

## <a name="application-context-recommended"></a>Контекст приложения (рекомендуется)

Используйте этот контекст для приложений, которые работают без выписаного пользователя, например фоновых служб или мям.

1. Создайте веб-приложение Azure Active Directory.
2. Назначьте приложению нужные разрешения.
3. Создайте ключ для приложения.
4. Получение маркера безопасности с помощью приложения и его ключа.
5. Используйте маркер для доступа к API Защитника Microsoft 365.

Дополнительные сведения см. в **[теме "Создание приложения для доступа к Защитнику Microsoft 365 без пользователя".](api-create-app-web.md)**

## <a name="user-context"></a>Контекст пользователя

Используйте этот контекст для выполнения действий от имени одного пользователя.

1. Создание нативного приложения Azure Active Directory.
2. Назначьте приложению нужное разрешение.
3. Получение маркера безопасности с использованием учетных данных пользователя для приложения.
4. Используйте маркер для доступа к API Защитника Microsoft 365.

Дополнительные сведения см. в записи "Создание приложения для доступа к API Защитника **[Microsoft 365 от имени пользователя".](api-create-app-user-context.md)**

## <a name="partner-context"></a>Контекст партнера

Используйте этот контекст, если вам нужно предоставить приложение множеству пользователей в [нескольких клиентах.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Создайте мультиантивное приложение Azure Active Directory.
2. Назначьте приложению нужное разрешение.
3. Получите [согласие администратора](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) для приложения от каждого клиента.
4. Получите маркер безопасности, используя учетные данные пользователя на основе ИД клиента.
5. Используйте маркер для доступа к API Защитника Microsoft 365.

Дополнительные сведения см. в записи "Создание приложения с партнерским **[доступом к API Защитника Microsoft 365".](api-partner-access.md)**

## <a name="related-articles"></a>Статьи по теме

- [Обзор API Microsoft 365 Defender](api-overview.md)
- [Авторизация OAuth 2.0 для доступа пользователя к API и входу в нее](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Управление секретами в серверных приложениях с помощью Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Создание приложения "Hello world", которое имеет доступ к API Microsoft 365](api-hello-world.md)
