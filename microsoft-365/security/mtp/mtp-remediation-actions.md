---
title: Действия по исправлению в автоматическом расследовании и возможностях реагирования в защите от угроз Майкрософт
description: Ознакомьтесь с возможностями автоматизированного анализа угроз и реакции на угрозы в службе защиты от угроз (Майкрософт)
keywords: автоматизированный, анализ, оповещение, триггер, действие, исправление
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225487"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Действия по исправлению в автоматическом расследовании и возможностях реагирования в защите от угроз Майкрософт

**Область применения:**
- Защита от угроз (Майкрософт)

Автоматизированные функции расследования и реагирования в защите от угроз Майкрософт включают некоторые действия по исправлению. Некоторые виды действий по исправлению выполняются на устройствах, которые также называются конечными точками. Для содержимого электронной почты применяются другие действия по исправлению.

В следующей таблице приведены действия по исправлению, которые в настоящее время поддерживаются в Microsoft Threat protection: 

|Действия по исправлению для конечных точек  |Действия по исправления для электронной почты  |
|---------|---------|
|Файл карантина<br/>Удаление раздела реестра<br/>Прекращение процесса <br/>Остановка службы <br/>Отключение драйвера <br/>Удаление запланированной задачи      |Обратимое удаление сообщений электронной почты или кластеров<br/>Блокирование URL-адреса (во время щелчка)<br/>Отключение внешней переадресации почты          |

Действия по исправлению, которые ожидают утверждения или уже завершены, можно просмотреть в [центре уведомлений](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="next-steps"></a>Дальнейшие действия:

- [Утверждение или отклонение действий, относящихся к автоматизированному анализу угроз и реакции на угрозы](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Дополнительные сведения о центре уведомлений](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
