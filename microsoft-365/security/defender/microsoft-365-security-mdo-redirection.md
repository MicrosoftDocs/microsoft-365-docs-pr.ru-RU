---
title: Перенаправление учетных записей из центра Office 365 безопасности и соответствия требованиям в новый центр Microsoft 365 безопасности
description: Перенаправление с центра Office 365 defender для Microsoft 365 безопасности.
keywords: Microsoft 365 центра безопасности, начало работы с центром Microsoft 365, перенаправление центра безопасности
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
ms.openlocfilehash: 703d3c3c9086aa2bdfada560c009e8738dffbb18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768973"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-security-center"></a>Перенаправление учетных записей из центра Office 365 безопасности и соответствия требованиям в центр Microsoft 365 безопасности

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender
- Defender для Office 365

В этой статье рассказывается о маршруте учетных записей в центр безопасности Microsoft 365, включив автоматическое перенаправление из бывшего центра Office 365 безопасности и соответствия требованиям (protection.office.com) в центр безопасности Microsoft 365 (security.microsoft.com).

## <a name="what-to-expect"></a>Чего ожидать
После включения и активного автоматического перенаправления пользователи, которые получают доступ к возможностям, связанным с безопасностью в Office 365 безопасности и соответствия требованиям (protection.office.com), будут автоматически перенаправляться в центр безопасности Microsoft 365 ( https://security.microsoft.com) . .  

Узнайте больше о том, что изменилось: [Microsoft Defender для Office 365 в центре Microsoft 365 безопасности.](microsoft-365-security-center-mdo.md)

При автоматическом перенаправлении пользователи будут перенаправлены в центр Microsoft 365 безопасности при использовании возможностей безопасности в центре Office 365 безопасности и соответствия требованиям.

К ним относятся возможности в разделе Управление угрозами и панель мониторинга управления угрозами и отчеты. Элементы центра Office 365 безопасности и соответствия требованиям, не связанные с безопасностью, не перенаправляются в центр Microsoft 365 безопасности.

Элементы, связанные с соответствием требованиям, можно найти в центре Microsoft 365, а связанные с потоком почты элементы можно найти в центре администрирования Exchange.

Перенаправление не влияет на все другие возможности, связанные с соответствием требованиям или возможности, которые служат обоим. Office 365 оповещения о безопасности отображаются как в центре Microsoft 365, так и в центре Office 365 безопасности и соответствия требованиям без перенаправления.  

### <a name="set-up-portal-redirection"></a>Настройка перенаправления портала
Чтобы начать маршрутизать учетные записи в центр Microsoft 365 безопасности в security.microsoft.com:

1. Убедитесь, что вы глобальный администратор или имеете разрешения администратора безопасности в каталоге Azure Active.
2. [Вход в](https://security.microsoft.com/) центр Microsoft 365 безопасности.
3. Перейдите **к Параметры**  >  **электронной почты & перенаправление**  >  **портала совместной работы.**  
4. Переключение параметра Автоматическое перенаправление **в On**.
5. Щелкните **Включить** автоматическое перенаправление на портал центра Microsoft 365 безопасности.

> [!NOTE]
> После включения перенаправления учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут перенаправлены в центр безопасности Microsoft 365 после завершения текущего сеанса и повторного входа.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Можно ли вернуться к использованию бывшего портала?
Если что-то не работает для вас или не удается выполнить что-либо через портал центра Microsoft 365 безопасности, мы хотим узнать об этом с помощью параметра обратной связи портала. Если у вас были проблемы с перенаправлением, сообщите нам об этом.

Чтобы вернуться на прежний портал:

1. [Вход в](https://security.microsoft.com/) центр Microsoft 365 в качестве глобального администратора или использование и учетная запись с разрешениями администратора безопасности в каталоге Azure Active.

2. Перейдите **к Параметры**  >  **электронной почты & перенаправление**  >  **портала совместной работы.**   

3. Переключение параметра Автоматическое перенаправление в **Off**.

4. Нажмите **кнопку Отключение** & отзывов о совместной работе при запросе.

Этот параметр можно включить снова в любое время.

После отключения учетные записи больше не будут security.microsoft.com, и вы снова будете иметь доступ к бывшему порталу securitycenter.windows.com или securitycenter.microsoft.com.

## <a name="related-information"></a>Статьи по теме
- [Обзор Центра безопасности Microsoft 365](overview-security-center.md)
- [Microsoft Defender для конечной точки в центре Microsoft 365 безопасности](microsoft-365-security-center-mde.md)
- [Корпорация Майкрософт предоставляет унифицированные SIEM и XDR для модернизации операций безопасности](https://www.microsoft.com/security/blog/?p=91813) 
- [Инфографика XDR и SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Новый защитник](https://afrait.com/blog/the-new-defender/) 
- [О Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Порталы безопасности Майкрософт и центры администрирования](portals.md)
