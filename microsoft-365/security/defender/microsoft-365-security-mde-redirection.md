---
title: Перенаправление учетных записей из Microsoft Defender для конечной точки в Microsoft 365 Defender
description: Перенаправление учетных записей и сеансов из защитника для конечной точки в Microsoft 365 Defender.
keywords: Microsoft 365 Defender, начало работы с Microsoft 365 Defender, перенаправление центра безопасности
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
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842570"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Перенаправление учетных записей из Microsoft Defender для конечной точки в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender
- Defender для конечной точки

В соответствии с меж доменным подходом Корпорации Майкрософт к защите от угроз с помощью SIEM и расширенного обнаружения и ответа (XDR), мы ребрендинг Расширенная защита от угроз в Microsoft Defender в качестве Защитника Microsoft для конечной точки и унифицированы в единый интегрированный портал — Microsoft 365 Defender.

В этом руководстве объясняется, как перенаправлять учетные записи в Microsoft 365 Defender, включив автоматическое перенаправление с бывшего портала Microsoft Defender для конечных точек (securitycenter.windows.com или securitycenter.microsoft.com), на портал Microsoft 365 Defender (security.microsoft.com).

> [!NOTE]
> Microsoft Defender для конечной точки в Microsoft 365 Defender поддерживает предоставление доступа к управляемым поставщикам служб безопасности [(MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) таким же образом, как доступ предоставляется в центре безопасности [Microsoft Defender.](./mssp-access.md)

## <a name="what-to-expect"></a>Чего ожидать
После включения автоматического перенаправления учетные записи, которые получают доступ к бывшему порталу Microsoft Defender для конечных точек в securitycenter.windows.com или securitycenter.microsoft.com, будут автоматически перенаправлены на портал Microsoft 365 Defender в security.microsoft.com.
 
Узнайте больше о том, что изменилось: [Microsoft Defender для конечной точки в Microsoft 365 Defender](microsoft-365-security-center-mde.md).

Это включает перенаправление для прямого доступа к бывшему порталу через браузер, включая ссылки, указывающие на прежний портал securitycenter.windows.com , такие как ссылки в уведомлениях электронной почты и ссылки, возвращаемые вызовами API SIEM.  

 Внешние ссылки из уведомлений электронной почты или API SIEM в настоящее время содержат ссылки на оба портала. После включения перенаправления обе ссылки будут Microsoft 365 Defender до удаления старой ссылки. Мы рекомендуем вам принять новую ссылку, указывав на Microsoft 365 Defender.

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
После включения это обновление может вступает в силу практически сразу для некоторых учетных записей. Но перенаправление может занять больше времени для распространения на каждую учетную запись в вашей организации. Учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут переналожены в Microsoft 365 Defender после завершения текущего сеанса и повторной регистрации.  

### <a name="set-up-portal-redirection"></a>Настройка перенаправления портала
Чтобы приступить к маршрутике учетных записей Microsoft 365 Defender:
1. Убедитесь, что вы глобальный администратор или у вас есть разрешения администратора безопасности в каталоге Azure Active 

2. [Вопишите в](https://security.microsoft.com/) Microsoft 365 Defender.

3. Перейдите **Параметры**  >  **конечных точек**  >  **общего**  >  **перенаправления портала** или [нажмите здесь](https://security.microsoft.com/preferences2/portal_redirection).  

4. Переключение параметра Автоматическое перенаправление **в On**.

5. Щелкните **Включить** автоматическое перенаправление Microsoft 365 Defender.

>[!IMPORTANT]
>Включение этого параметра не прекращает активные сеансы пользователей. Учетные записи, которые находятся в активном сеансе при применении этого параметра, будут направлены в Microsoft 365 Defender после завершения текущего сеанса и повторной регистрации.

>[!NOTE]
>Вы должны быть глобальным администратором или иметь разрешения администратора безопасности в Azure Active Directory, чтобы включить или отключить этот параметр.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Можно ли вернуться к использованию бывшего портала?
Если что-то не работает для вас или если вы не можете выполнить что-либо через Microsoft 365 Defender, мы хотим узнать об этом. Если у вас были проблемы с перенаправлением, мы рекомендуем вам предоставить нам информацию с помощью формы отправки отзывов.

Чтобы вернуться к бывшему порталу Microsoft Defender для конечных точек:

1. [Ворегистрируйся](https://security.microsoft.com/) Microsoft 365 защитника в качестве глобального администратора или используя и учетную запись с разрешениями администратора безопасности в каталоге Azure Active.

2. Перейдите **Параметры**  >  **конечных точек**  >  **общего**  >  **портала перенаправления** или [откройте страницу здесь](https://security.microsoft.com/preferences2/portal_redirection).  

3. Переключение параметра Автоматическое перенаправление в **Off**.

4. Нажмите **кнопку Отключение** & отзывов о совместной работе при запросе.

Этот параметр можно включить снова в любое время. 

После отключения учетные записи больше не будут security.microsoft.com, и вы снова будете иметь доступ к бывшему порталу — securitycenter.windows.com или securitycenter.microsoft.com. 

## <a name="related-information"></a>Статьи по теме
- [Microsoft 365 Обзор defender](overview-security-center.md)
- [Microsoft Defender для конечной точки в Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Корпорация Майкрософт предоставляет унифицированные SIEM и XDR для модернизации операций безопасности](https://www.microsoft.com/security/blog/?p=91813) 
- [Инфографика XDR и SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Новый защитник](https://afrait.com/blog/the-new-defender/) 
- [О Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Порталы безопасности Майкрософт и центры администрирования](portals.md)