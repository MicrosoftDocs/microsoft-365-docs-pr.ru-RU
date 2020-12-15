---
title: Переход в центр уведомлений для просмотра и утверждения автоматического исследования и задач по исправлению
description: Используйте центр уведомлений для просмотра сведений об автоматическом исследовании и утверждения ожидающих действий
keywords: Центр уведомлений, защита от угроз, исследование, оповещение, ожидание, автоматически, обнаружение
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
ms.date: 12/09/2020
ms.openlocfilehash: aa9f433bc60949aa625d9346421b025121347a2c
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683323"
---
# <a name="the-action-center"></a>Центр уведомлений

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Используйте центр действий () для проверки результатов текущих и прошлых расследований на устройствах и почтовых [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ящиках организации. В зависимости от типа угрозы и [](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) итоговых результатов решения действия по исправлению могут происходить автоматически или после утверждения командой операций безопасности вашей организации. Все действия по исправлению (как ожидающие утверждения, так и утвержденные) объединяются в центре уведомлений. 

![Центр уведомлений](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Интерфейс "единой области представления"

В центре уведомлений доступен интерфейс "единой области представления" для задач, таких как:
- утверждение ожидающих действий по исправлению;
- просмотр журнала аудита утвержденных действий по исправлению; и
- проверка выполненных действий по исправлению.

Ваша группа операций безопасности может работать эффективнее и эффективнее, так как Центр действий предоставляет комплексное представление о Защитнике Microsoft 365 в работе.

## <a name="go-to-the-action-center"></a>Переход в центр уведомлений

1. Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите. 

2. В панели навигации щелкните **Центр уведомлений**. 

3. В центре действий вы увидите две  вкладки: "Ожидание" и **"История".**

    - На вкладке **Ожидание** перечислены исследования, требующие проверки и утверждения участником группы операций по безопасности для продолжения процесса. Обязательно просмотрите ожидающие элементы, представленные здесь, и выполните соответствующие действия.

    - На вкладке **Журнал** перечислены прошлые исследования и действия по исправлению, выполненные автоматически. Вы можете просматривать данные за последний день, неделю, месяц или шесть месяцев.

4. Чтобы отобразить только нужные столбцы, выберите команду **Настроить столбцы**.<br/>![Центр действий в Защитнике Microsoft 365](../../media/mtp-action-center.png)

5. Выберите элемент в списке, чтобы просмотреть дополнительные сведения об исследовании. Откроется представление со сведениями об исследовании.<br/>![Сведения об исследовании](../../media/mtp-air-investdetails.png)

    - Если исследование относится к содержимому электронной почты (например, объектом является почтовый ящик), сведения об исследованиях открываются в Центре безопасности & соответствия требованиям ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Если исследование затрагивает устройство, сведения об исследовании откроются в Центре безопасности ([https://security.microsoft.com](https://security.microsoft.com)). 

> [!TIP]
> Если вы считаете, что функции автоматического исследования и реагирования в Защитнике Microsoft 365 что-то было пропущено или неправильно обнаружено, дайте нам знать! Узнайте, как сообщать о ложных срабатываах и отрицательных результатах в автоматизированных исследованиях и [ответах (AIR) в Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

## <a name="available-actions"></a>Доступные действия

По мере принятия мер по исправлению они перечислены на вкладке **"История"** в центре действий. К таким действиям относятся следующие:

- Сбор пакета исследования 
- Изолировать устройство (это действие можно отменить) 
- Отключение компьютера 
- Освобождение выполнения кода 
- Освобождение из карантина 
- Пример запроса 
- Ограничение выполнения кода (это действие можно отменить) 
- Запуск антивирусной проверки 
- Остановка и карантин 

> [!NOTE]
> Помимо действий по исправлению, которые принимаются автоматически, группа по работе с безопасностью может вручную устранять обнаруженные угрозы. Дополнительные сведения об автоматических и ручных действиях по исправлению см. [в действиях по исправлению.](mtp-remediation-actions.md)

## <a name="action-source"></a>Источник действия

(**NEW!**) Как вы знаете, Microsoft 365 Defender объединяет автоматизированные возможности исследования и реагирования на них в нескольких службах, таких как [Microsoft Defender для endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) и [Microsoft Defender для Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Новый и улучшенный центр действий  теперь содержит столбец источника действий, который сообщает, откуда поступило каждое действие по исправлению. 

В следующей таблице описываются возможные **значения источника** действий:

| Значение источника действия | Описание |
|:-----|:---|
| **Действие устройства вручную** | Ручное действие на устройстве. Примеры: [изоляция устройства](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) [или карантин файлов.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **Действие по электронной почте вручную** | Ручное действие с электронной почтой. Пример включает в себя удаление электронных сообщений с возможностью восстановления или исправление сообщения [электронной почты.](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365) |
| **Автоматическое действие устройства** | Автоматическое действие с объектом, например файл или процесс. Примеры автоматизированных действий: отправка файла в карантин, остановка процесса и удаление ключа реестра. [(См. действия по исправлению в Microsoft Defender для конечной точки.)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions) |
| **Автоматическое действие электронной почты** | Автоматическое действие с содержимым электронной почты, например сообщением электронной почты, вложением или URL-адресом. Примеры автоматизированных действий включают обратимые удаления сообщений электронной почты, блокировку URL-адресов и отключение внешней пересылки почты. [(См. действия по исправлению в Microsoft Defender для Office 365.)](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions) |
| **Действие "Расширенный поиск"** | Действия, предпринятые на устройствах или в электронной почте с [расширенным поиском.](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview) |
| **Действие проводника** | Действия, предпринятые с содержимым электронной почты с [помощью проводника.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) |
| **Действие ответа вручную в режиме онлайн** | Действия, предпринятые на устройстве с [ответом в прямом отклике.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) Примеры: удаление файла, остановка процесса и удаление запланированной задачи. |
| **Действие live response** | Действия, предпринятые на устройстве с [API конечных точек в Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) К примерам действий относятся изоляция устройства, запуск антивирусной проверки и получение сведений о файле. |

## <a name="required-permissions-for-action-center-tasks"></a>Обязательные разрешения для задач центра уведомлений

Чтобы утвердить или отклонить ожидающие действия в центре уведомлений, вам должны быть назначены разрешения, указанные в следующей таблице.

|Действие по исправлению |Обязательные роли и разрешения |
|--|----|
|Microsoft Defender для исправлений конечных точек (устройства) |Роль администратора безопасности, назначенная в Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) или Центре администрирования Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- или ---<br/>Роль активных действий по исправлению, назначенная в Microsoft Defender для конечной точки <br/> <br/> Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами. <br/>- [Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Создание ролей для управления доступом на основе ролей (Microsoft Defender для конечной точки) и управление ими](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Исправление в Microsoft Defender для Office 365 (содержимое и электронная почта Office)  |Роль администратора безопасности, назначенная в Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) или Центре администрирования Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- и --- <br/>Роль поиска и очистки, назначенная Центру безопасности & соответствия требованиям ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**ВАЖНО!** Если вам назначена роль администратора безопасности только в Центре безопасности & соответствия требованиям, вы не сможете получить доступ к центру поддержки или возможностям Защитника Microsoft 365. У вас должна быть роль администратора безопасности, назначенная в Azure Active Directory или Центре администрирования Microsoft 365. <br/><br/>Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами. <br/>- [Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Разрешения в Центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Пользователи, которым назначена роль Глобальный администратор в Azure Active Directory, могут утвердить или отклонить любые ожидающие действия в центре уведомлений. Однако рекомендуется ограничить в организации число пользователей, которым назначена роль глобального администратора. Рекомендуем использовать роли Администратор безопасности, Активные действия по исправлению, и Поиск и очистка, указанные выше, в качестве разрешений центра уведомлений.

## <a name="next-steps"></a>Дальнейшие действия 

- [Утверждение или отклонение ожидающих действий после автоматического исследования](mtp-autoir-actions.md)
- [Просмотр результатов автоматического исследования](mtp-autoir-results.md)

