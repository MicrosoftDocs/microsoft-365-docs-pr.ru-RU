---
title: Доступ к API защиты от угроз Майкрософт
description: Узнайте, как получить доступ к API защиты от угроз Майкрософт
keywords: доступ, API, контекст приложения, контекст пользователя, приложение AAD, маркер доступа
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
ms.openlocfilehash: bccf36f46121caceeb6dc6d97c126f48149d9426
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197885"
---
# <a name="access-the-microsoft-threat-protection-apis"></a>Доступ к API защиты от угроз Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

>[!IMPORTANT] 
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.


 Защита от угроз Майкрософт предоставляет множество своих данных и действий через набор программных интерфейсов API. Эти API позволяют автоматизировать рабочие процессы и внедрять их на основе возможностей защиты от угроз Майкрософт. Для доступа к API требуется проверка подлинности OAuth 2.0. Для получения дополнительных сведений см [код авторизации OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


В общем случае необходимо выполнить следующие действия, чтобы использовать API:
- Создание приложения AAD
- Получение маркера доступа с помощью этого приложения
- Использование маркера для доступа к API защиты от угроз Майкрософт


Доступ к API Microsoft Threat Protection можно получить с помощью **контекста приложения** или **контекста пользователя**.

- **Контекст приложения: (рекомендуется)** <br>
    Используется приложениями, которые запускаются без наличия вошедшего пользователя. Например, приложения, запускаемые как фоновые службы или управляющие программы.

    Действия, которые необходимо предпринять для доступа к API Microsoft Threat protection с контекстом приложения:

  1. Создайте веб-приложение AAD.
  2. Назначьте нужное разрешение для примера Аппликатионфор, " **инцидент. Read. ALL**", **адванцедхунтинг. Read. ALL**. 
  3. Создайте ключ для этого приложения.
  4. Получение маркера с помощью приложения с ключом.
  5. Использование маркера для доступа к API защиты от угроз Майкрософт

     Дополнительные сведения приведены в разделе [Get Access with context](api-create-app-web.md).


- **Контекст пользователя:** <br>
    Используется для выполнения действий в API от имени пользователя.

    Действия, которые необходимо предпринять для доступа к API Microsoft Threat protection с контекстом приложения:
  1. Создание собственного приложения AAD.
  2. Назначьте нужное разрешение приложению. Например, " **происшествия. чтение**", " **адванцедхунтинг. Read**".
  3. Получение маркера с помощью приложения с учетными данными пользователя.
  4. Использование маркера для доступа к API защиты от угроз Майкрософт

     Дополнительные сведения можно найти [в разделе Получение доступа с помощью контекста пользователя](api-create-app-user-context.md).


## <a name="related-topics"></a>Связанные статьи
- [API защиты от угроз Майкрософт](api-supported.md)
- [Доступ к защите от угроз Майкрософт с помощью контекста приложения](api-create-app-web.md)
- [Доступ к защите от угроз Майкрософт с помощью контекста пользователя](api-create-app-user-context.md)
