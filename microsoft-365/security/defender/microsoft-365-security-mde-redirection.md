---
title: Перенаправление учетных записей из Microsoft Defender для конечной точки в центр безопасности Microsoft 365
description: Перенаправление учетных записей и сеансов из Центра безопасности Defender для конечной точки в центр безопасности Microsoft 365.
keywords: Центр безопасности Microsoft 365, начало работы с центром безопасности Microsoft 365, перенаправление центра безопасности
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c993977e0f052a7dc2e7827ff5bdefacee19ac2d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072685"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a>Перенаправление учетных записей из Microsoft Defender для конечной точки в центр безопасности Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Область применения:**
- Microsoft 365 Defender
- Defender для конечной точки

В соответствии с меж доменным подходом Корпорации Майкрософт к защите от угроз с помощью SIEM и расширенного обнаружения и реагирования (XDR) мы ребрендинг microsoft Defender Advanced Threat Protection в microsoft Defender для конечной точки и унифицированы в единый интегрированный портал — центр безопасности Microsoft 365.

В этом руководстве рассказывается, как перенаправлять учетные записи в центр безопасности Microsoft 365 путем автоматического перенаправления с бывшего портала Microsoft Defender для конечных точек (securitycenter.windows.com или securitycenter.microsoft.com) на портал Центра безопасности Microsoft 365 (security.microsoft.com).

> [!NOTE]
> Microsoft Defender для конечной точки в центре безопасности Microsoft 365 поддерживает предоставление доступа к управляемым поставщикам служб безопасности [(MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) таким же образом, как доступ предоставляется в центре безопасности [Microsoft Defender.](./mssp-access.md)

## <a name="what-to-expect"></a>Чего ожидать
После включения автоматического перенаправления учетные записи, которые получают доступ к бывшему порталу Microsoft Defender для конечных точек в securitycenter.windows.com или securitycenter.microsoft.com, будут автоматически перенаправлены на портал Центра безопасности Microsoft 365 в security.microsoft.com.
 
Узнайте больше о том, что изменилось: Microsoft Defender для конечной точки в центре безопасности [Microsoft 365.](microsoft-365-security-center-mde.md)

Это включает перенаправление для прямого доступа к бывшему порталу через браузер, включая ссылки, указывающие на прежний портал securitycenter.windows.com , такие как ссылки в уведомлениях электронной почты и ссылки, возвращаемые вызовами API SIEM.  

 Внешние ссылки из уведомлений электронной почты или API SIEM в настоящее время содержат ссылки на оба портала. После включения перенаправления обе ссылки будут указать на центр безопасности Microsoft 365, пока старая ссылка не будет удалена. Мы рекомендуем вам принять новую ссылку, указав на центр безопасности Microsoft 365.

Дополнительные ссылки на ссылки и маршруты см. в таблице ниже.
## <a name="siem-api-routing"></a>Маршрутия API SIEM

|**Property**  |**Назначение, когда перенаправление отключено**  |**Назначение при перенаправлении** | 
|---------|---------|---------|
| LinkToWDATP | Страница оповещения в securitycenter.windows.com | Страница оповещения в security.microsoft.com  |
| IncidentLinkToWDATP | Страница инцидента в securitycenter.windows.com  | Страница инцидента в security.microsoft.com  |
| LinkToMTP | Страница оповещения в security.microsoft.com | Страница оповещения в security.microsoft.com  |
| IncidentLinkToMTP | Страница инцидента в security.microsoft.com  | Страница инцидента в security.microsoft.com  

## <a name="email-alert-notifications"></a>Уведомления об оповещении по электронной почте

|**Property**  |**Назначение, когда перенаправление отключено**  |**Назначение при перенаправлении** |
|---------|---------|---------|
| Страница Оповещение  | Страница оповещения в securitycenter.windows.com  | Страница оповещения в security.microsoft.com  |
| Страница инцидентов  |Страница инцидента в securitycenter.windows.com  | Страница инцидента в security.microsoft.com  
| Страница оповещения на портале Центра безопасности | Страница оповещения в security.microsoft.com | Страница оповещения в security.microsoft.com | 
| Страница инцидента на портале Центра безопасности | Страница инцидента в security.microsoft.com  | Страница инцидента в security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>Когда это вступает в силу? 
После включения это обновление может вступает в силу практически сразу для некоторых учетных записей. Но перенаправление может занять больше времени для распространения на каждую учетную запись в вашей организации. Учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут перенаходить в центр безопасности Microsoft 365 только после завершения текущего сеанса и повторной регистрации.  

### <a name="set-up-portal-redirection"></a>Настройка перенаправления портала
Чтобы начать маршрутить учетные записи в центр безопасности Microsoft 365:
1. Убедитесь, что вы глобальный администратор или у вас есть разрешения администратора безопасности в каталоге Azure Active 

2. [Во входе](https://security.microsoft.com/) в центр безопасности Microsoft 365.

3. Перейдите **по ссылке**  >  **Параметры Конечные точки**  >  **Общего**  >  **портала перенаправления** или [нажмите здесь](https://security.microsoft.com/preferences2/portal_redirection).  

4. Переключение параметра Автоматическое перенаправление **в On**.

5. Щелкните **Включить** автоматическое перенаправление на портал Центра безопасности Microsoft 365.

>[!IMPORTANT]
>Включение этого параметра не прекращает активные сеансы пользователей. Учетные записи, которые находятся в активном сеансе при применении этого параметра, будут направлены в центр безопасности Microsoft 365 только после завершения текущего сеанса и повторной регистрации.

>[!NOTE]
>Вы должны быть глобальным администратором или иметь разрешения администратора безопасности в Azure Active Directory, чтобы включить или отключить этот параметр.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Можно ли вернуться к использованию бывшего портала?
Если что-то не работает для вас или если вы не можете выполнить что-либо через портал Центра безопасности Microsoft 365, мы хотим узнать об этом. Если у вас были проблемы с перенаправлением, мы рекомендуем вам предоставить нам информацию с помощью формы отправки отзывов.

Чтобы вернуться к бывшему порталу Microsoft Defender для конечных точек:

1. [Во входе](https://security.microsoft.com/) в центр безопасности Microsoft 365 в качестве глобального администратора или использования и учетной записи с разрешениями администратора безопасности в каталоге Azure Active.

2. Перейдите **к перенаправлению** параметров  >  конечных **точек**  >  **общего**  >  **портала** или [откройте страницу здесь.](https://security.microsoft.com/preferences2/portal_redirection)  

3. Переключение параметра Автоматическое перенаправление в **Off**.

4. Нажмите **кнопку Отключение** & отзывов о совместной работе при запросе.

Этот параметр можно включить снова в любое время. 

После отключения учетные записи больше не будут security.microsoft.com, и вы снова будете иметь доступ к бывшему порталу — securitycenter.windows.com или securitycenter.microsoft.com. 

## <a name="related-information"></a>Статьи по теме
- [Обзор Центра безопасности Microsoft 365](overview-security-center.md)
- [Защитник Microsoft для конечной точки в центре безопасности Microsoft 365](microsoft-365-security-center-mde.md)
- [Корпорация Майкрософт предоставляет унифицированные SIEM и XDR для модернизации операций безопасности](https://www.microsoft.com/security/blog/?p=91813) 
- [Инфографика XDR и SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Новый защитник](https://afrait.com/blog/the-new-defender/) 
- [О Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Порталы безопасности Майкрософт и центры администрирования](portals.md)