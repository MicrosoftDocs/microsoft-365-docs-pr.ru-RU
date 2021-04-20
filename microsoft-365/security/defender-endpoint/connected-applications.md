---
title: Подключенные приложения в Microsoft Defender для конечной точки
ms.reviewer: ''
description: Просмотр подключенных партнерских приложений, которые используют стандартный протокол OAuth 2.0 для проверки подлинности и предоставления маркеров для использования в API конечных токенов Microsoft Defender.
keywords: партнеры, приложения, сторонние подключения, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26c531c0544f92d664bfa0f1a21e4f33a0765d24
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893501"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Подключенные приложения в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Подключенные приложения интегрируются с платформой Defender для конечных точек с помощью API. 

Приложения используют стандартный протокол OAuth 2.0 для проверки подлинности и предоставления маркеров для использования в API конечных токенов Microsoft Defender.  Кроме того, приложения Azure Active Directory (Azure AD) позволяют администраторам клиентов устанавливать явный контроль над доступом к API с помощью соответствующего приложения.
 
Чтобы использовать API [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) с подключенным приложением, необходимо следовать этим шагам.
 
## <a name="access-the-connected-application-page"></a>Доступ к подключенной странице приложения
Из левого меню навигации выберите **приложения &**  >  **AAD.**

 
## <a name="view-connected-application-details"></a>Просмотр сведений о подключенных приложениях
На странице Подключенные приложения содержится информация о приложениях Azure AD, подключенных к Microsoft Defender для конечной точки в вашей организации. Вы можете просмотреть использование подключенных приложений: последнее просмотрение, количество запросов за последние 24 часа и тенденции запроса за последние 30 дней.

![Изображение подключенных приложений](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Изменение, перенастройка или удаление подключенного приложения
Ссылка **"Параметры открытого приложения"** открывает соответствующую страницу управления приложениями Azure AD на портале Azure. На портале Azure можно управлять разрешениями, перенастройка или удаление подключенных приложений.
