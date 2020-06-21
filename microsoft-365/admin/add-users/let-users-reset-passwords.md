---
title: Предоставление пользователям прав на самостоятельный сброс пароля
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Узнайте, как можно сбросить пароли с помощью средства самостоятельного сброса пароля.
ms.openlocfilehash: 288613023ee61626bf12f7090ad0ff73139ef06d
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780593"
---
# <a name="let-users-reset-their-own-passwords"></a>Предоставление пользователям прав на самостоятельный сброс пароля

Голова идет кругом от количества запросов на сброс пароля, поступающих от пользователей? Как администратор Microsoft 365, вы можете позволить пользователям использовать [средство самостоятельного сброса пароля](https://go.microsoft.com/fwlink/p/?LinkId=522677) , чтобы не переустанавливать пароли. Работы станет гораздо меньше! 
  
Обратите внимание на некоторые важные моменты.
  
- Вы получаете возможность самостоятельного сброса паролей для облачных пользователей, которые **бесплатно** посвящены любому плану Microsoft 365 для бизнеса, образованию или некоммерческой плате. Она не работает с пробной версией Microsoft 365.

- It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.

- **Если вы используете локальную службу Active Directory**, приведенные выше две точки не применяются. Это можно сделать, но **для этого требуется платная подписка на Azure AD Premium**.

Посмотрите короткое видео о том, как позволить пользователям сбрасывать собственные пароли. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Если этот видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="let-people-reset-their-own-passwords"></a>Разрешить пользователям сбрасывать собственные пароли

Эта процедура позволяет включить функцию самостоятельного сброса пароля для всех пользователей в организации.
  
::: moniker range="o365-worldwide"

1. В <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центре администрирования</a>перейдите на страницу Параметры организации **параметров** > **Org settings** .

::: moniker-end

::: moniker range="o365-germany"

1. В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центре администрирования</a>перейдите на страницу **Параметры** \> ** &amp; конфиденциальности безопасности** .

::: moniker-end

::: moniker range="o365-21vianet"

1. В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центре администрирования</a>перейдите на **Settings** \> страницу **Параметры** \> ** &amp; конфиденциальности безопасности параметров безопасности** .

::: moniker-end

2. В верхней части страницы " **Параметры организации** " выберите вкладку **Безопасность & конфиденциальности** .
  
3. Выберите команду **самостоятельный сброс пароля**.

4. В разделе **Сброс пароля самостоятельно**выберите перейдите на **портал Azure, чтобы включить функцию самостоятельного сброса пароля**.

5. В области навигации слева выберите пункт **Пользователи**, а затем на странице **Пользователи | Все пользователи** » выберите **Сброс пароля**.
  
6. На странице " **Свойства** " выберите **все** , чтобы включить его для всех пользователей в вашей организации, а затем нажмите кнопку **сохранить**.
  
7. Когда пользователи входят в систему, им будет предложено ввести дополнительные контактные данные, которые помогут им сбросить пароль в будущем.

## <a name="related-articles"></a>Связанные статьи

[Установка политики срока действия паролей в организации](../manage/set-password-expiration-policy.md)
  
[Установка бессрочных пользовательских паролей](set-password-to-never-expire.md)

[учебные видео по Microsoft 365 бизнес](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
