---
title: Утверждение или отклонение ожидающих действий за автоматическим исследованием
description: Используйте центр уведомлений для управления действиями, связанными с автоматизированным анализом угроз и реакцией на угрозы
keywords: действие, центр, автоматизированный анализ угроз и реакция на угрозы, автоматизированный, анализ угроз, реакция на угрозы, исправление
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 22a40e3c0c804800f2de02e705d1dfec6e296db0
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429615"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Утверждение или отклонение ожидающих действий за автоматическим исследованием

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

При выполнении автоматического анализа угроз может возникать одно или несколько [действий по исправлению](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions), для которых требуется утверждение. Например, может потребоваться удалить кластер сообщений электронной почты или файл из карантина. Необходимо как можно скорее утвердить (или отклонить) ожидающие выполнения действия, чтобы автоматизированный анализ угроз мог продолжить работу и своевременно завершить ее. 

> [!TIP]
> Если вы считаете, что что-то пошло не так или неправильно, с помощью автоматизированного расследования и функции ответа в Microsoft Threat Protection, сообщите нам о! Сведения о [том, как сообщить о ложных положительных и отрицательных значениях при автоматическом расследовании и возможностях реагирования (AIR) в защите от угроз Майкрософт](mtp-autoir-report-false-positives-negatives.md).

Ожидающие действия могут быть просмотрены и утверждены с помощью [центра уведомлений](#review-a-pending-action-in-the-action-center) или [представления сведений об исследовании](#review-a-pending-action-in-the-investigation-details-view).

> [!NOTE]
> Чтобы утвердить или отклонить действия по исправлению, необходимы [соответствующие разрешения](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="review-a-pending-action-in-the-action-center"></a>Просмотр ожидающего действия в центре уведомлений

1. Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите. 

2. В панели навигации щелкните **Центр уведомлений**. 

3. В центре уведомлений на вкладке **Ожидание** выберите элемент в списке. 

    - При выборе элемента в столбце **Номер анализа** откроется страница сведений об анализе угроз. На ней вы можете просмотреть результаты анализа угроз и утвердить или отклонить рекомендуемое действие.
 
    - При выборе строки в списке откроется всплывающее окно, в котором можно просмотреть сведения об этом элементе. <br/>![Утверждение или отклонение действия](../../media/air-actioncenter-itemselected.png)<br/>Используйте ссылки для просмотра связанного предупреждения или анализа, а также для утверждения или отклонения действия.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Просмотр ожидающего действия в представлении со сведениями об анализе угроз

![Сведения об анализе](../../media/mtp-air-investdetails.png)

1. На странице [сведений анализа](mtp-autoir-results.md) выберите вкладку **Ожидающие действия** (или **Действия**). Здесь перечислены элементы, ожидающие утверждения.

2. Выберите элемент в списке, а затем выберите **утвердить** или **отклонить**.

## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр сведений и результатов автоматического исследования](mtp-autoir-results.md)
- [Обработка ложных срабатываний/отрицательных результатов в автоматизированном расследовании и возможностях реагирования](mtp-autoir-report-false-positives-negatives.md)
