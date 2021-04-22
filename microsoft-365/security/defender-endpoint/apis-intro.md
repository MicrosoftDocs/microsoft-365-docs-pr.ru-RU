---
title: Доступ к API Microsoft Defender для конечной точки
ms.reviewer: ''
description: Узнайте, как можно использовать API для автоматизации рабочего процесса и инновация на основе возможностей Microsoft Defender для конечных точек
keywords: apis, api, Microsoft Defender for Endpoint, open api, Microsoft Defender for Endpoint api, public api, supported apis, alerts, device, user, domain, ip, file, advanced hunting, query
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
ms.openlocfilehash: 87dce8ff4fde505eb8d4e458c8d9fb56556f4d78
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935111"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Доступ к API Microsoft Defender для конечной точки 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Область применения:** 
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint предоставляет большую часть своих данных и действий с помощью набора программных API. Эти API позволят автоматизировать рабочий процесс и инновациям на основе возможностей Defender для конечных точек. Доступ к API требует проверки подлинности OAuth2.0. Дополнительные сведения см. в [тексте OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

Просмотрите это видео для краткого обзора API Defender для API endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

В общем, для использования API необходимо предпринять следующие действия:
- Создание приложения AAD
- Получение маркера доступа с помощью этого приложения
- Использование маркера для доступа к API Defender для endpoint


Вы можете получить доступ к API Defender для конечной точки с **помощью контекста приложений** или **пользовательского контекста.**

- **Контекст приложения: (Рекомендуется)** <br>
    Используется приложениями, которые работают без участия пользователя. например, приложения, которые работают в качестве фоновых служб или daemons.

    Действия, которые необходимо предпринять для доступа к API Defender для конечной точки с контекстом приложения:

  1. Создание веб-приложения AAD.
  2. Назначьте нужное разрешение приложению, например, "Read Alerts", "Isolate Machines". 
  3. Создайте ключ для этого приложения.
  4. Получение маркера с помощью приложения с его ключом.
  5. С помощью маркера можно получить доступ к API Endpoint Defender для Microsoft Defender

     Дополнительные сведения см. в [приложении Get access with application context.](exposed-apis-create-app-webapp.md)


- **Контекст пользователя:** <br>
    Используется для выполнения действий в API от имени пользователя.

    Действия, которые необходимо предпринять для доступа к API Defender для конечной точки с контекстом приложения:

  1. Создание приложения AAD.
  2. Назначьте нужное разрешение приложению, например"Read Alerts", "Isolate Machines" и т.д. 
  3. Получение маркера с помощью приложения с учетными данными пользователей.
  4. С помощью маркера можно получить доступ к API Endpoint Defender для Microsoft Defender

     Дополнительные сведения см. в [ссылке Получить доступ к пользовательскому контексту.](exposed-apis-create-app-nativeapp.md)


## <a name="related-topics"></a>Похожие темы
- [Microsoft Defender для API конечных точек](exposed-apis-list.md)
- [Доступ к Microsoft Defender для конечной точки с контекстом приложений](exposed-apis-create-app-webapp.md)
- [Доступ к Microsoft Defender для конечной точки с пользовательским контекстом](exposed-apis-create-app-nativeapp.md)
