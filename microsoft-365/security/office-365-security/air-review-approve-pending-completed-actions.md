---
title: Просмотр действий по исправлению и управление ими в Microsoft Defender для Office 365
keywords: AIR, autoIR, ATP, автоматизированный, исследование, ответ, исправление, угрозы, расширенные, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Узнайте о действиях по исправлению в автоматизированном расследовании и реагировании на них в Microsoft Defender для Office 365 (план 2).
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 3fb77fa41ff3e9af995cf80b9f4024aa92a51212
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176019"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Просмотр действий по исправлению и управление ими в Office 365

Так как автоматизированные исследования электронной почты & совместной  работы выдают решения, такие как вредоносные или подозрительные, создаются определенные действия по исправлению. В Microsoft Defender для Office 365 действия по исправлению могут включать:
- Блокировка URL-адреса (время щелчка)
- Мягкое удаление сообщений электронной почты или кластеров
- Карантин электронной почты или вложений электронной почты
- Отключение внешней пересылки почты

Эти действия по исправлению не будут предприняты до тех пор, пока группа безопасности не утвердит их. Мы рекомендуем как можно скорее просмотреть и утвердить все ожидающие действия, чтобы автоматические расследования были завершены своевременно. В некоторых случаях можно отменить действие по исправлению.

**Область применения**
- [Microsoft Defender для Office 365 (план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="approve-or-reject-pending-actions"></a>Утверждение (или отклонение) ожидающих действий

1. Перейдите в Центр безопасности Microsoft 365) [https://security.microsoft.com](https://security.microsoft.com) и войдите.
2. В области навигации выберите **"Центр действий".**
3. На **вкладке** "Ожидание" просмотрите список действий, ожидающих утверждения.
4. Выберите элемент в списке. Откроется его вылетная области. 
5. Просмотрите сведения во flyout pane и с последующим одним из следующих действий:
   - Выберите **страницу "Открыть исследование",** чтобы просмотреть дополнительные сведения об этом расследовании.
   - Выберите **"Утвердить",** чтобы инициировать ожидающих действий.
   - Выберите  "Отклонить", чтобы предотвратить ожидающих действий.

## <a name="undo-one-remediation-action"></a>Отмена одного действия по исправлению

1. Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите в нее.
2. На **вкладке "История"** выберите действие, которое нужно отменить.
3. В области в правой части экрана выберите **"Отменить".**

## <a name="undo-multiple-remediation-actions"></a>Отмена нескольких действий по исправлению

1. Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите в нее.
2. На **вкладке "История"** выберите действия, которые нужно отменить. Убедитесь, что выбраны элементы с одинаковым типом действия. Откроется открываемая окно.
3. На flyout pane, select Undo.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Удаление файла из карантина на нескольких устройствах

1. Перейдите в центр действий [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () и войдите в нее.
2. На **вкладке "История"** выберите файл с типом действия **"Карантин".**
3. В области в правой части экрана выберите "Применить к **X"** дополнительных экземпляров этого файла, а затем выберите **"Отменить".**

## <a name="next-steps"></a>Дальнейшие действия

- [Использование обозревателя угроз](threat-explorer.md)
- [Как сообщать о ложных срабатываах и отрицательных результатах в автоматизированном расследовании и реагировании на них](air-report-false-positives-negatives.md)

## <a name="see-also"></a>См. также

- [Просмотр сведений и результатов автоматического исследования в Office 365](air-view-investigation-results.md)
