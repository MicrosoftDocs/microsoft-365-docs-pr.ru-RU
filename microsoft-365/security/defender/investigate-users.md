---
title: Исследование пользователей в Центре безопасности Microsoft 365
description: Исследование пользователей в центре Microsoft 365 безопасности
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, удостоверения, данные, устройства, приложения, инциденты, анализ, ответ
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
ms.openlocfilehash: c03e4d5bd94eb6105ffab91c6dad2b74d7159dde
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300065"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a>Исследование пользователей в Центре безопасности Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

Часть расследования инцидента может включать учетные записи пользователей. Начните со вкладки **"Пользователи"** об инциденте из & оповещений о > *>* **пользователи**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Пример страницы &quot;Пользователи&quot; для инцидента":::

Чтобы получить краткое описание учетной записи пользователя для инцидента, выберите контрольный знак рядом с именем учетной записи пользователя. Ниже приведен пример.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Пример сводки учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::

> [!NOTE]
> На странице Пользователя Azure Active Directory организации и группы, помогающие понять группы и разрешения, связанные с пользователем.

На этой странице вылетов вы можете просмотреть сведения об угрозах пользователей, включая текущие инциденты, активные оповещения и уровень риска, а также экспозицию пользователей, учетные записи, устройства и т. д.

Кроме того, вы можете принять меры непосредственно в центре Microsoft 365 безопасности, чтобы обратиться к скомпрометированного пользователя, подтвердив, что пользователь скомпрометирован или требует от него снова войти.

Здесь вы можете выбрать **страницу Перейти на страницу пользователя,** чтобы узнать подробности учетной записи пользователя. Ниже приведен пример.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Пример страницы учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::

Вы также можете увидеть эту страницу, выбрав имя учетной записи пользователя из списка на странице **Пользователи.**

Страница Microsoft 365 центра безопасности объединяет сведения из Microsoft Defender for Endpoint, Microsoft Defender for Identity и Microsoft Cloud App Security (в зависимости от лицензий). 

На этой странице показаны сведения, определенные для риска безопасности учетной записи пользователя. Это включает оценку, которая помогает оценить риски и недавние события и оповещения, которые способствовали общему риску пользователя.

На этой странице можно сделать дополнительные действия: 

- Пометить учетную запись пользователя как скомпрометированную
- Требовать от пользователя снова войти
- Приостановка учетной записи пользователя
- См. Azure Active Directory параметров учетной записи пользователя Azure AD
- Просмотр файлов, которые принадлежат учетной записи пользователя
- Просмотр файлов, общих этому пользователю. 

Ниже приведен пример.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Пример действий учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Следующие шаги

По мере необходимости для инцидентов в процессе продолжайте [расследование.](investigate-incidents.md)

## <a name="see-also"></a>См. также

- [Обзор инцидентов](incidents-overview.md)
- [Управление приоритетом инцидентов](incident-queue.md)
- [Управление инцидентами](manage-incidents.md)