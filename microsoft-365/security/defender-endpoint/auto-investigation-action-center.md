---
title: Посетите центр действий, чтобы увидеть действия по исправлению
description: Используйте центр действий для просмотра сведений и результатов после автоматического расследования
keywords: action, center, autoir, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: af9e9315088a8dd5da9740b33135551d28664ed7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186117"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Посетите центр действий, чтобы увидеть действия по исправлению

Во время и после автоматического расследования выявляются действия по устранению угроз. В зависимости от конкретной угрозы и настройки [Microsoft Defender для конечной](https://docs.microsoft.com/windows/security/threat-protection) точки для вашей организации некоторые действия по исправлению принимаются автоматически, а другие требуют утверждения. Если вы входите в команду операций безопасности организации, вы [](manage-auto-investigation.md#remediation-actions) можете просмотреть ожидающих и завершенных действий по исправлению в **Центре действий.** 


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEW!) Единый центр действий


Мы рады объявить о новом едином центре действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ()!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Центр действий в центре безопасности Microsoft 365":::

В следующей таблице сравнивает новый единый центр действий с предыдущим центром действий.

|Новый единый центр действий  |Предыдущий центр действий  |
|---------|---------|
|Списки ожидающих и завершенных действий для устройств и электронной почты в одном расположении <br/>([Microsoft Defender для конечной точки](microsoft-defender-endpoint.md) плюс Microsoft Defender для Office [365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))|Списки ожидающих и завершенных действий для устройств <br/> ([Только для Защитника Майкрософт для конечной](microsoft-defender-endpoint.md) точки)   |
|Расположен по адресу:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Расположен по адресу:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| В центре безопасности Microsoft 365 выберите **Центр действий.** <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Перемещение в Центр действий в центре безопасности Microsoft 365"::: | В Центре безопасности защитника Майкрософт выберите **центр действий**  >  **автоматизированных расследований.** <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Перемещение в центр действий из Центра безопасности защитника Майкрософт":::  |

Единый центр действий объединяет действия по исправлению в Defender для конечной точки и Defender для Office 365. Он определяет общий язык для всех действий по исправлению и предоставляет унифицированный опыт исследования. 

Вы можете использовать единый центр действий, если у вас есть соответствующие разрешения и одна или несколько следующих подписок:
- [Defender для конечной точки](microsoft-defender-endpoint.md)
- [Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Дополнительные дополнительные новости см. [в см. в руб. Требования.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)

## <a name="using-the-action-center"></a>Использование центра действий

Чтобы добраться до единого центра действий в улучшенном центре безопасности Microsoft 365:
1. Перейдите в центр безопасности Microsoft 365 () и [https://security.microsoft.com](https://security.microsoft.com) войдите.
2. В области навигации выберите **Центр действий.** 

При посещении центра действий вы увидите две вкладки: **"Ожидающих действий"** и **"История".** В следующей таблице кратко излагается то, что вы увидите на каждой вкладке:

|Вкладка  |Описание  |
|---------|---------|
|**Pending**     | Отображает список действий, которые требуют внимания. Вы можете одобрить или отклонить действия по одному или выбрать несколько действий, если они имеют один и тот же тип действия (например, файл **карантина).** <br/>**СОВЕТ.** Убедитесь в том, что необходимо как можно скорее просмотреть и утвердить [(или](manage-auto-investigation.md) отклонить) ожидающих действий, чтобы автоматические расследования могли быть завершены своевременно. |
|**Журнал**     | Служит журналом аудита для принятых действий, таких как: <br/>- Действия по исправлению, принятые в результате автоматизированных расследований <br>- Действия по исправлению, утвержденные вашей командой операций безопасности  <br/>- Команды, которые были запускаются и исправление действий, которые были применены во время сеансов Live Response  <br/>- Действия по исправлению, предпринятые функциями защиты от угроз в антивирусе Microsoft Defender  <p>Предоставляет способ отмены определенных действий (см. [в статьях Отмена завершенных действий).](manage-auto-investigation.md#undo-completed-actions)       |

Можно настроить, сортировать, фильтровать и экспортировать данные в Центре действий.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Столбцы и фильтры в центре действий":::

- Выберите столбец, заголовок для сортировки элементов в порядке по возрастанию или убыванию.
- Используйте фильтр периода времени для просмотра данных за прошедший день, неделю, 30 дней или 6 месяцев.
- Выберите столбцы, которые необходимо просмотреть.
- Укажите, сколько элементов необходимо включить на каждой странице данных.
- Используйте фильтры для просмотра только элементов, которые необходимо просмотреть.
- Выберите **экспорт** для экспорта результатов в файл csv. 

## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр и утверждение действий по исправлению](manage-auto-investigation.md)
- [См. интерактивное руководство: изучение и устранение угроз с помощью Microsoft Defender для конечной точки](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>См. также

- [Устранение ложных срабатыва-минусов в Microsoft Defender для конечной точки](defender-endpoint-false-positives-negatives.md)
