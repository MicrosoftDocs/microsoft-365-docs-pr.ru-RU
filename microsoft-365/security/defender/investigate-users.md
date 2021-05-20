---
title: Расследование пользователей в Microsoft 365 Defender
description: Расследование пользователей инцидента в центре Microsoft 365 безопасности.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, удостоверения личности, данные, устройства, приложения, инциденты, анализ, ответ
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572805"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Расследование пользователей в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

Часть расследования инцидентов может включать учетные записи пользователей. Начните с **вкладки** Пользователи для инцидента из **инцидентов & оповещения >** *инциденте* **> пользователей.** 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Пример страницы пользователей для инцидента":::

Чтобы получить краткое резюме учетной записи пользователя для инцидента, выберите контрольную отметку рядом с именем учетной записи пользователя. Ниже приведен пример.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Пример сводки учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::

> [!NOTE]
> На странице пользователя показана Azure Active Directory (Azure AD), а также группы, помогающие вам понять группы и разрешения, связанные с пользователем.

На этой странице можно просмотреть информацию об угрозах пользователей, включая любые текущие инциденты, активные оповещения и уровень риска, а также экспозицию пользователей, учетные записи, устройства и многое другое.

Кроме того, вы можете принять меры непосредственно в центре безопасности Microsoft 365 для решения проблемы скомпрометированного пользователя, подтвердив, что пользователь скомпрометирован, или требуя от них снова войти в систему.

Здесь вы можете выбрать Перейти на **страницу пользователя, чтобы** увидеть детали учетной записи пользователя. Ниже приведен пример.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Пример страницы учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::

Вы также можете увидеть эту страницу, выбрав имя учетной записи пользователя из списка на странице **пользователей.**

Страница Microsoft 365 безопасности объединяет информацию от Microsoft Defender for Endpoint, Microsoft Defender for Identity и Microsoft Cloud App Security (в зависимости от того, какие лицензии у вас есть). 

На этой странице показана информация, специфичная для безопасности учетной записи пользователя. Это включает в себя оценку, которая помогает оценить риск и последние события и оповещения, которые способствовали общему риску пользователя.

На этой странице вы можете вы сделать эти дополнительные действия: 

- Отметь учетную запись пользователя как скомпрометированную
- Требовать от пользователя снова войти в
- Приостановить учетную запись пользователя
- Посмотреть Azure Active Directory учетной записи пользователя (Azure AD)
- Просмотр файлов, принадлежащих учетной записи пользователя
- Просмотр файлов, совместно с этим пользователем. 

Ниже приведен пример.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Пример действий в учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Дальнейшие действия

По мере необходимости для инцидентов в процессе, продолжить [расследование](investigate-incidents.md).

## <a name="see-also"></a>См. также

- [Обзор инцидентов](incidents-overview.md)
- [Управление приоритетом инцидентов](incident-queue.md)
- [Управление инцидентами](manage-incidents.md)