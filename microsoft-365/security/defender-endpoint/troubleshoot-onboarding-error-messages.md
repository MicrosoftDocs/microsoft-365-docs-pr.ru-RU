---
title: Устранение неполадок с бортами и сообщения об ошибках
description: Устранение неполадок с учетом проблем и сообщений об ошибке при выполнении установки Microsoft Defender для конечной точки.
keywords: устранение неполадок, устранение неполадок, Azure Active Directory, onboarding, сообщение об ошибке, сообщения об ошибках, защитник Майкрософт для конечной точки
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: b8e15f27ffe4babe730870fb576980c62cb0fd59
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844041"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a>Устранение неполадок доступа к подписке и порталу.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

На этой странице подробно описаны действия по устранению неполадок, которые могут возникнуть при настройке службы Microsoft Defender для конечных точек.

Если вы получите сообщение об ошибке, Центр безопасности в Microsoft Defender подробно разъяснение о том, что такое проблема и будут предоставлены соответствующие ссылки.

## <a name="no-subscriptions-found"></a>Подписки не найдены

Если при доступе к Центр безопасности в Microsoft Defender  вы получаете найденное сообщение без подписок, это означает, что Azure Active Directory (Azure AD), используемая для входа пользователя на портал, не имеет лицензии Microsoft Defender для конечной точки.

Возможные причины:
- Лицензии Windows E5 и Office E5 — это две отдельные лицензии.
- Лицензия была приобретена, но не была предусмотрена для этого экземпляра Azure AD.
    - Это может быть проблема с подготовкаю лицензии.
    - Это может быть случайное предоставление лицензии другому Microsoft Azure AD, чем лицензия, используемая для проверки подлинности в службу.

В обоих случаях следует обратиться в службу поддержки Майкрософт в [Службу](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) поддержки конечных точек или поддержку [лицензий на объем.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)

![Изображение не найденных подписок](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a>Срок действия подписки истек

Если при доступе к Центр безопасности в Microsoft Defender  вы получаете сообщение с истекшим сроком действия подписки, срок действия подписки на онлайн-службу истек. Подписка Microsoft Defender для конечной точки, как и любая другая подписка на онлайн-службу, имеет срок действия. 

Вы можете продлить или продлить лицензию в любой момент времени. При доступе к порталу  по истечении срока действия подписки будет представлено сообщение с возможностью скачивания пакета offboarding устройства, если вы решите не продлевать лицензию.

> [!NOTE]
> По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки. Просроченные пакеты offboarding, отправленные на устройство, будут отклонены. При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.

![Срок действия подписи](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a>Доступ к порталу не разрешен

Если вы получаете средство, не уполномоченное получать доступ к порталу, следует помнить, что Microsoft Defender for Endpoint — это продукт мониторинга безопасности, расследования инцидентов и реагирования, поэтому доступ к нему ограничен и контролируется пользователем.
Дополнительные сведения см. в [**ссылке Назначение доступа пользователей к порталу.**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)

![Изображение не авторизованного портала доступа](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a>Данные в настоящее время недоступны на некоторых разделах портала
Если панель мониторинга портала и другие разделы показывают сообщение об ошибке, например "Данные в настоящее время недоступны":

![Изображение данных в настоящее время не доступно](images/atp-data-not-available.png)

Необходимо разрешить все поддомены под `securitycenter.windows.com` ней. Например, `*.securitycenter.windows.com`.


## <a name="portal-communication-issues"></a>Проблемы с связью портала
Если у вас возникнут проблемы с доступом к порталу, отсутствием данных или ограниченным доступом к частям портала, необходимо убедиться, что следующие URL-адреса разрешены и открыты для связи.

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



