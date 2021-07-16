---
title: Управление правилами подавления конечных точек в Microsoft Defender
description: Возможно, вам потребуется предотвратить появляние оповещений на портале с помощью правил подавления. Узнайте, как управлять правилами подавления в Microsoft Defender для конечной точки.
keywords: управление подавлением, правилами, именем правила, областью, действием, оповещениями, включите, отключите
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 74b89d86b770cb47a0855b45d457ea8ce5fb9802
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454761"
---
# <a name="manage-suppression-rules"></a>Управление правилами подавления

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Возможны сценарии, в которых необходимо подавить появляющиеся на портале оповещения. Можно создать правила подавления для определенных оповещений, которые, как известно, являются безобидными, например известных инструментов или процессов в вашей организации. Дополнительные сведения о подавлении оповещений см. в [рублях Suppress alerts.](manage-alerts.md)

Вы можете просмотреть список всех правил подавления и управлять ими в одном месте. Вы также можете включить или отключить правило подавления оповещений.


1. В области навигации выберите подавление **Параметры**  >  **endpoints**  >  **Rules**  >  **Alert.** Отображается список правил подавления, созданных пользователями в организации.

2. Выберите правило, щелкнув на чек-окне рядом с именем правила.

3. Нажмите **кнопку Включите правило**, **изменить правило** или  **удалить правило**. При внесении изменений в правило можно выбрать выпуск оповещений, которые он уже подавил, независимо от того, соответствуют ли эти оповещения новым критериям. 


## <a name="view-details-of-a-suppression-rule"></a>Просмотр сведений о правиле подавления

1. В области навигации выберите подавление **Параметры**  >  **endpoints**  >  **Rules**  >  **Alert.** Отображается список правил подавления, созданных пользователями в организации.

2. Щелкните имя правила. Отображаются сведения о правиле. Вы увидите сведения о правилах, таких как состояние, область, действие, количество совпадающих оповещений, созданных по и дате создания правила. Вы также можете просматривать связанные оповещения и условия правил.

## <a name="related-topics"></a>Связанные статьи

- [Управление оповещениями](manage-alerts.md)
