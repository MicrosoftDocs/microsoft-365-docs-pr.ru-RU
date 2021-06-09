---
title: Посетите центр действий, чтобы увидеть действия по исправлению
description: Используйте центр действий для просмотра сведений и результатов после автоматического расследования
keywords: action, center, autoir, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844914"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Посетите центр действий, чтобы увидеть действия по исправлению

Во время и после автоматического расследования выявляются действия по устранению угроз. В зависимости от конкретной угрозы и настройки [Microsoft Defender для конечной](/windows/security/threat-protection) точки для вашей организации некоторые действия по исправлению принимаются автоматически, а другие требуют утверждения. Если вы входите в команду операций безопасности организации, вы [](manage-auto-investigation.md#remediation-actions) можете просмотреть ожидающих и завершенных действий по исправлению в **Центре действий.** 


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEW!) Единый центр действий


Мы рады объявить о новом едином центре действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ()!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Центр действий в центре Microsoft 365 безопасности":::

В следующей таблице сравнивает новый единый центр действий с предыдущим центром действий.

|Новый единый центр действий  |Предыдущий центр действий  |
|---------|---------|
|Списки ожидающих и завершенных действий для устройств и электронной почты в одном расположении <br/>([Microsoft Defender для конечной точки](microsoft-defender-endpoint.md) плюс Microsoft Defender для [Office 365](/microsoft-365/security/office-365-security/office-365-atp))|Списки ожидающих и завершенных действий для устройств <br/> ([Только для Защитника Майкрософт для конечной](microsoft-defender-endpoint.md) точки)   |
|Расположен по адресу:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Расположен по адресу:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| В центре Microsoft 365 выберите центр **действий.** <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Перемещение в Центр действий в центре Microsoft 365 безопасности"::: | В центре Центр безопасности в Microsoft Defender выберите **центр действий**  >  **автоматизированных расследований**. <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Перемещение в центр действий из Центр безопасности в Microsoft Defender":::  |

Единый центр действий объединяет действия по исправлению в Defender for Endpoint и Defender для Office 365. Он определяет общий язык для всех действий по исправлению и предоставляет унифицированный опыт исследования. 

Вы можете использовать единый центр действий, если у вас есть соответствующие разрешения и одна или несколько следующих подписок:
- [Защитник для конечной точки](microsoft-defender-endpoint.md)
- [Defender для Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Дополнительные дополнительные новости см. [в см. в руб. Требования.](/microsoft-365/security/mtp/prerequisites)

## <a name="using-the-action-center"></a>Использование центра действий

Чтобы добраться до единого центра действий в центре Microsoft 365 безопасности:
1. Перейдите в центр Microsoft 365 безопасности [https://security.microsoft.com](https://security.microsoft.com) () и войдите.
2. В области навигации выберите **Центр действий.** 

При посещении центра действий вы увидите две вкладки: **"Ожидающих действий"** и **"История".** В следующей таблице кратко излагается то, что вы увидите на каждой вкладке:

|Вкладка  |Описание  |
|---------|---------|
|**Pending**     | Отображает список действий, которые требуют внимания. Вы можете одобрить или отклонить действия по одному или выбрать несколько действий, если они имеют один и тот же тип действия (например, файл **карантина).** <br/>**СОВЕТ.** Убедитесь в том, что необходимо как можно скорее просмотреть и утвердить [(или](manage-auto-investigation.md) отклонить) ожидающих действий, чтобы автоматические расследования могли быть завершены своевременно. |
|**Журнал**     | Служит журналом аудита для принятых действий, таких как: <br/>- Действия по исправлению, принятые в результате автоматизированных расследований <br>- Действия по исправлению, утвержденные вашей командой операций безопасности  <br/>- Команды, которые были запускаются и исправление действий, которые были применены во время сеансов Live Response  <br/>- Действия по исправлению, принятые функциями защиты от угроз в антивирусная программа в Microsoft Defender  <p>Предоставляет способ отмены определенных действий (см. [в статьях Отмена завершенных действий).](manage-auto-investigation.md#undo-completed-actions)       |

Можно настроить, сортировать, фильтровать и экспортировать данные в Центре действий.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Столбцы и фильтры в центре действий":::

- Выберите столбец, заголовок для сортировки элементов в порядке по возрастанию или убыванию.
- Используйте фильтр периода времени для просмотра данных за прошедший день, неделю, 30 дней или 6 месяцев.
- Выберите столбцы, которые необходимо просмотреть.
- Укажите, сколько элементов необходимо включить на каждой странице данных.
- Используйте фильтры для просмотра только элементов, которые необходимо просмотреть.
- Выберите **Экспорт** для экспорта результатов в .csv файл. 

## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр и утверждение действий по исправлению](manage-auto-investigation.md)
- [См. интерактивное руководство: изучение и устранение угроз с помощью Microsoft Defender для конечной точки](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>См. также

- [Устранение ложных положительных/отрицательных срабатываний в Microsoft Defender для конечной точки](defender-endpoint-false-positives-negatives.md)
