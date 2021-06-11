---
title: Просмотр и управление действиями по исправлению в Microsoft Defender для Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
description: Узнайте о действиях по исправлению в автоматизированных возможностях расследования и ответа в Microsoft Defender для Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 525f6cf922f80067219f6c33a2c11559e9e58a39
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878776"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Просмотр и управление действиями по исправлению в Office 365

**Область применения**
- [Microsoft Defender для Office 365 (план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

По мере автоматического расследования & контента совместной работы создаются определенные действия по исправлению, например вредоносные или подозрительные.  В Microsoft Defender для Office 365 действий по исправлению можно включить следующие действия:

- Блокировка URL-адреса (время щелчка мыши)
- Мягкое удаление сообщений электронной почты или кластеров
- Карантин вложения электронной почты или электронной почты
- Отключение внешней пересылаемой почты

Эти действия по исправлению не принимаются до тех пор, пока их не утвердит группа операций безопасности. Мы рекомендуем как можно скорее просмотреть и утвердить все ожидающие действия, чтобы автоматические расследования были завершены своевременно. В некоторых случаях можно отменить действие по исправлению.

## <a name="approve-or-reject-pending-actions"></a>Утверждение (или отклонение) ожидающих действий

1. Перейдите на портал Microsoft 365 Defender <https://security.microsoft.com> () и войдите.
2. В области навигации выберите **Центр действий.**
3. На **вкладке Ожидание** просмотрите список действий, ожидающих утверждения.
4. Выберите элемент в списке. Откроется его поле для вылетов. 
5. Просмотрите сведения в области вылетов и примите один из следующих действий:
   - Выберите **страницу Open investigation,** чтобы просмотреть дополнительные сведения о расследовании.
   - Выберите **Утверждение,** чтобы инициировать ожидающих действий.
   - Выберите **Отклонение,** чтобы предотвратить ожидающих действий.

## <a name="undo-one-remediation-action"></a>Отмена одного действия по исправлению

1. Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.
2. На **вкладке История** выберите действие, которое необходимо отменить.
3. В области справа от экрана выберите **Отмена**.

## <a name="undo-multiple-remediation-actions"></a>Отмена нескольких действий по исправлению

1. Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.
2. На **вкладке История** выберите действия, которые необходимо отменить. Убедитесь, что выберите элементы с одинаковым типом действия. Открывается поле для вылетов.
3. В области вылетов выберите Отмена.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Удаление файла из карантина на нескольких устройствах

1. Перейдите в центр действий <https://security.microsoft.com/action-center> () и войдите.
2. На **вкладке История** выберите файл с карантиным файлом типа **Action.**
3. В области справа от экрана выберите **Применить** к X дополнительные экземпляры этого файла, а затем **отменить**.

## <a name="next-steps"></a>Дальнейшие действия

- [Использование обозревателя угроз](threat-explorer.md)
- [Как сообщать о ложных срабатывах и отрицательных результатах в возможностях автоматического расследования и ответа](air-report-false-positives-negatives.md)

## <a name="see-also"></a>См. также

- [Просмотр сведений и результатов автоматического расследования в Office 365](air-view-investigation-results.md)
