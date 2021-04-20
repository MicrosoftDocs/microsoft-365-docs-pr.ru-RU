---
title: Станьте партнером Microsoft Defender для конечной точки
ms.reviewer: ''
description: Узнайте о действиях и требованиях для интеграции решения с Microsoft Defender для конечной точки и стать партнером
keywords: партнер, интеграция, проверка решений, сертификация, требования, член, misa, портал приложений
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 35ba1fe85fa9b62770142636d46303b37534b976
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893321"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Станьте партнером Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Чтобы стать партнером решения Defender для конечной точки, необходимо выполнить следующие действия.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>Шаг 1. Подписка на лицензию Microsoft Defender для разработчика конечных точек
Подпишитесь на [лицензию Microsoft Defender для разработчика конечных точек.](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9) Подписка позволяет использовать клиента Microsoft Defender для конечных точек с до 10 устройствами для разработки решений, которые интегрируются с Microsoft Defender для конечной точки. 

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Шаг 2. Выполнение требований проверки и сертификации решений
Лучший способ для партнеров по технологиям сертифицировать, что их интеграция работает, — это чтобы совместный [](https://securitycenter.microsoft.com/interoperability/partners) клиент одобрил предложенный проект интеграции (клиент может использовать параметр **Recommend** a partner на странице партнерского приложения в Центре безопасности Microsoft Defender) и протестировать и демолизировать его в команде Microsoft Defender для endpoint.

После проверки и утверждения интеграции командой Защитника Майкрософт для конечных точек мы направим вас в качестве партнера в Ассоциацию безопасности Microsoft Intelligent Security.

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>Шаг 3. Стать членом Microsoft Intelligent Security Association
[Microsoft Intelligent Security Association](https://www.microsoft.com/security/partnerships/intelligent-security-association) — это программа, предназначенная специально для партнеров по безопасности Майкрософт, которая помогает обогатить продукты безопасности и повысить доступность интеграции с продуктами безопасности Майкрософт.

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Шаг 4. Получение списка на портале приложений-партнеров Microsoft Defender для конечных точек
Microsoft Defender for Endpoint поддерживает обнаружение и интеграцию сторонних [](partner-applications.md) приложений с помощью страницы партнеров продукта, встроенной в портал управления Microsoft Defender для конечных точек. 

Чтобы ваша компания была указана в качестве партнера на странице партнера в продукте, необходимо предоставить следующие сведения:

1. Квадратный логотип (SVG).
2. Имя продукта, который будет представлен.
3. Предописай описание продукта из 15 слов.
4. Ссылка на посадочную страницу для клиента, чтобы завершить интеграцию или сообщение в блоге, которое будет включать достаточную информацию для клиентов. Любой пресс-релиз, включая имя продукта Microsoft Defender для конечной точки, должен быть рассмотрен маркетинговыми и инженерными группами. Подождите не менее 10 дней, пока будет сделан процесс проверки.
5.  Если вы используете многоканальный подход Azure AD, нам потребуется имя приложения Azure AD для отслеживания использования приложения.
6. Включай User-Agent поля в каждый вызов API, сделанный в Microsoft Defender для общедоступных API конечных точек или API безопасности Graph. Это будет использоваться для статистических целей, устранения неполадок и распознавания партнеров. Кроме того, этот шаг является требованием для членства в Microsoft Intelligent Security Association (MISA).

    Выполните приведенные ниже действия.
    
    - Установите поле User-Agent в каждом заглавном заготке http-запроса в нижеформатном формате.

    - `MdePartner-{CompanyName}-{ProductName}/{Version}`
    
    - Например, User-Agent: `MdePartner-Contoso-ContosoCognito/1.0.0`
    
    - Дополнительные сведения см. в [разделе RFC 2616-14.43](https://tools.ietf.org/html/rfc2616#section-14.43).

Партнерские отношения с Microsoft Defender для конечной точки помогают нашим взаимным клиентам дополнительно упорядочить, интегрировать и организовать защиту. Мы рады, что вы решили стать партнером Microsoft Defender для конечных точек и добиться нашей общей цели эффективной защиты клиентов и их активов путем предотвращения и совместного реагирования на современные угрозы.

## <a name="related-topics"></a>Похожие темы
- [Возможности для технических партнеров](partner-integration.md)
