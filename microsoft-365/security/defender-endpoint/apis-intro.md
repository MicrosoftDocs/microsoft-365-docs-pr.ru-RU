---
title: Доступ к API Microsoft Defender для конечной точки
ms.reviewer: ''
description: Узнайте, как можно использовать API для автоматизации рабочих процессов и инноваций на основе возможностей Microsoft Defender for Endpoint
keywords: apis, api, wdatp, открытый api, Microsoft Defender для endpoint api, Microsoft Defender atp, public api, поддерживаемый apis, оповещения, устройство, пользователь, домен, ip, файл, продвинутая охота, запрос
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571833"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Доступ к API Microsoft Defender для конечной точки 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Область применения:** 
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Microsoft Defender для конечной точки? [Подпишитесь на бесплатную пробную версию.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API позволят автоматизировать рабочие процессы и внедрять инновации на основе возможностей Defender for Endpoint. Доступ к API требует проверки подлинности OAuth2.0. Для получения дополнительной информации [см Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

Посмотрите это видео для краткого обзора API Defender for Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Как правило, необходимо предпринять следующие шаги для использования API:
- Создание [приложения AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Получить токен доступа с помощью этого приложения
- Используйте токен для доступа к Defender для API конечной точки


Вы можете получить доступ к API Defender for Endpoint с **контекстом приложения или** **контекстом пользователя.**

- **Контекст приложения: (Рекомендуемый)** <br>
    Используется приложениями, которые работают без ва-во всех пользователей. например, приложения, которые работают в качестве фоновых служб или daemons.

    Шаги, которые необходимо предпринять для доступа к API Defender for Endpoint с контекстом приложения:

  1. Создание веб-приложения AAD.
  2. Назначьте желаемое разрешение приложению, например, 'Read Alerts', 'Isolate Machines'. 
  3. Создайте ключ для этого приложения.
  4. Получите токен с помощью приложения с его ключом.
  5. Используйте токен для доступа к Microsoft Defender для API конечной точки

     Для получения дополнительной информации [см.](exposed-apis-create-app-webapp.md)


- **Контекст пользователя:** <br>
    Используется для выполнения действий в API от имени пользователя.

    Шаги, которые необходимо предпринять для доступа к API Defender for Endpoint с контекстом приложения:

  1. Создайте родное приложение AAD.
  2. Назначьте желаемое разрешение приложению, например,:« Читать оповещения», «Изолировать машины» и т.д. 
  3. Получите токен с помощью приложения с учетными данными пользователя.
  4. Используйте токен для доступа к Microsoft Defender для API конечной точки

     Для получения дополнительной информации [см.](exposed-apis-create-app-nativeapp.md)


## <a name="related-topics"></a>Связанные статьи
- [Microsoft Defender для API конечных точек](exposed-apis-list.md)
- [Доступ к Microsoft Defender для конечной точки с контекстом приложения](exposed-apis-create-app-webapp.md)
- [Доступ к Microsoft Defender для конечной точки с контекстом пользователя](exposed-apis-create-app-nativeapp.md)
