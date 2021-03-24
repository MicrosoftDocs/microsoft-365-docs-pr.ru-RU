---
title: Перенаправление учетных записей из Microsoft Defender для Office 365 в новый центр безопасности Microsoft 365
description: Перенаправление из Defender для Office 365 в центр безопасности Microsoft 365.
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072678"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Перенаправление учетных записей из Microsoft Defender для Office 365 в центр безопасности Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender
- Defender для Office 365

В этой статье рассказывается о маршруте учетных записей в центр безопасности Microsoft 365, включив автоматическое перенаправление из бывшего Центра безопасности и соответствия требованиям Майкрософт (protection.office.com или securitycenter.microsoft.com) в центр безопасности Microsoft 365 (security.microsoft.com).

>[!NOTE]
> Возможность перенаправления портала доступна только для клиентов Office 365 E5 и Microsoft Defender для office P2

## <a name="what-to-expect"></a>Чего ожидать
После включения и активного автоматического перенаправления пользователи, которые получают доступ к возможностям, связанным с безопасностью в Office 365 Security and Compliance (protection.office.com), будут автоматически перенаправлены в центр безопасности Microsoft 365 ( https://security.microsoft.com) .  

Узнайте больше о том, что изменилось: [Microsoft Defender для Office 365 в центре безопасности Microsoft 365.](microsoft-365-security-center-mdo.md)

При автоматическом перенаправлении пользователи будут перенаправлены в центр безопасности Microsoft 365 при использовании возможностей безопасности в Центре безопасности и соответствия требованиям Office 365.

К ним относятся возможности в разделе Управление угрозами и панель мониторинга управления угрозами и отчеты. Элементы Центра безопасности и соответствия требованиям Office 365, не связанные с безопасностью, не перенаправляются в центр безопасности Microsoft 365.

Элементы, связанные с соответствием требованиям, можно найти в центре соответствия требованиям Microsoft 365, а элементы, связанные с потоком почты, можно найти в центре администрирования Exchange.

Перенаправление не влияет на все другие возможности, связанные с соответствием требованиям или возможности, которые служат обоим. Оповещения о безопасности Office 365 отображаются в центре безопасности Microsoft 365 и Центре безопасности и соответствия требованиям Office 365 без перенаправления.  

### <a name="set-up-portal-redirection"></a>Настройка перенаправления портала
Чтобы начать маршрутить учетные записи в центр безопасности Microsoft 365 в security.microsoft.com:

1. Убедитесь, что вы глобальный администратор или имеете разрешения администратора безопасности в каталоге Azure Active.
2. [Во входе](https://security.microsoft.com/) в центр безопасности Microsoft 365.
3. Перейдите **к настройкам**  >  **перенаправления & на**  >  **портале совместной работы.**  
4. Переключение параметра Автоматическое перенаправление **в On**.
5. Щелкните **Включить** автоматическое перенаправление на портал Центра безопасности Microsoft 365.

> [!NOTE]
> После включения перенаправления учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут перенаправлены в центр безопасности Microsoft 365 только после завершения текущего сеанса и повторного входа.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Можно ли вернуться к использованию бывшего портала?
Если что-то не работает для вас или вы не можете выполнить что-либо через портал Центра безопасности Microsoft 365, мы хотим узнать об этом с помощью варианта обратной связи портала. Если вы столкнулись с любыми вопросами с перенаправлением, мы рекомендуем вам обратиться к вашему приятелю pm непосредственно через закрытый предварительный просмотр или дайте нам знать с помощью формы отправки отзывов.

Чтобы вернуться на прежний портал:

1. [Во входе](https://security.microsoft.com/) в центр безопасности Microsoft 365 в качестве глобального администратора или использования и учетной записи с разрешениями администратора безопасности в каталоге Azure Active.

2. Перейдите **к перенаправлению** конечных  >  **точек**  >  **параметров общего**  >  **портала.**  

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