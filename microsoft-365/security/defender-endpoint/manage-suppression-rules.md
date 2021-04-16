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
ms.openlocfilehash: f1549512a02fe3af71d32c6b33c69cc705de99a8
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862131"
---
# <a name="manage-suppression-rules"></a>Управление правилами подавления

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Возможны сценарии, в которых необходимо подавить появляющиеся на портале оповещения. Можно создать правила подавления для определенных оповещений, которые, как известно, являются безобидными, например известных инструментов или процессов в вашей организации. Дополнительные сведения о подавлении оповещений см. в [рублях Suppress alerts.](manage-alerts.md)

Вы можете просмотреть список всех правил подавления и управлять ими в одном месте. Вы также можете включить или отключить правило подавления оповещений.


1. В области навигации выберите подавление **параметров**  >  **оповещения.** Отображается список правил подавления, созданных пользователями в организации.

2. Выберите правило, щелкнув на чек-окне рядом с именем правила.

3. Нажмите **кнопку Включите правило**, **изменить правило** или  **удалить правило**. При внесении изменений в правило можно выбрать выпуск оповещений, которые он уже подавил, независимо от того, соответствуют ли эти оповещения новым критериям. 


## <a name="view-details-of-a-suppression-rule"></a>Просмотр сведений о правиле подавления

1. В области навигации выберите подавление **параметров**  >  **оповещения.** Отображается список правил подавления, созданных пользователями в организации.

2. Щелкните имя правила. Отображаются сведения о правиле. Вы увидите сведения о правилах, таких как состояние, область, действие, количество совпадающих оповещений, созданных по и дате создания правила. Вы также можете просматривать связанные оповещения и условия правил.

## <a name="related-topics"></a>Похожие темы

- [Управление оповещениями](manage-alerts.md)
