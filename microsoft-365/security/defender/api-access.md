---
title: Доступ к API защитника Microsoft 365
description: Узнайте, как получить доступ к API защитника Microsoft 365
keywords: доступ, apis, контекст приложений, пользовательский контекст, aad-приложение, маркер доступа
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
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072758"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Доступ к API защитника Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API помогают автоматизировать рабочий процесс и полностью использовать возможности Microsoft 365 Defender.

В общем, для использования API необходимо предпринять следующие действия:

- Создание приложения Azure Active Directory
- Получение маркера доступа с помощью этого приложения
- Используйте маркер для доступа к API Защитника Microsoft 365

> [!NOTE]
> Доступ к API требует проверки подлинности OAuth2.0. Дополнительные сведения см. в [тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

После выполнения этих действий вы будете готовы получить доступ к API защитника Microsoft 365 с помощью определенного контекста.

## <a name="application-context-recommended"></a>Контекст приложения (рекомендуется)

Используйте этот контекст для приложений, которые работают без участия пользователя, например фоновых служб или daemons.

1. Создание веб-приложения Azure Active Directory.
2. Назначение нужных разрешений приложению.
3. Создайте ключ для приложения.
4. Получение маркера безопасности с помощью приложения и его ключа.
5. Используйте маркер для доступа к API Защитника Microsoft 365.

Дополнительные сведения см. в **[статью Создание приложения для доступа к Microsoft 365 Defender без пользователя.](api-create-app-web.md)**

## <a name="user-context"></a>Контекст пользователя

Используйте этот контекст для выполнения действий от имени одного пользователя.

1. Создание родного приложения Azure Active Directory.
2. Назначьте нужное разрешение приложению.
3. Получение маркера безопасности с помощью учетных данных пользователя для приложения.
4. Используйте маркер для доступа к API Защитника Microsoft 365.

Дополнительные сведения см. в приложении **[Create to access Microsoft 365 Defender API от имени пользователя.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Контекст партнеров

Используйте этот контекст, когда необходимо предоставить приложение многим пользователям во [многих клиентах.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Создание мульти-клиентского приложения Azure Active Directory.
2. Назначьте нужное разрешение приложению.
3. Получите [согласие администратора](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) для приложения от каждого клиента.
4. Получите маркер безопасности с помощью учетных данных пользователей на основе удостоверения клиента клиента.
5. Используйте маркер для доступа к API Защитника Microsoft 365.

Дополнительные сведения см. в приложении **[Create with partner access to Microsoft 365 Defender API.](api-partner-access.md)**

## <a name="related-articles"></a>Связанные статьи

- [Обзор API защитника Microsoft 365](api-overview.md)
- [Авторизация OAuth 2.0 для входов пользователей и доступа к API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Управление секретами в приложениях сервера с помощью хранилища ключей Azure](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Создание приложения "Hello world", которое имеет доступ к API Microsoft 365](api-hello-world.md)