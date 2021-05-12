---
title: Этап 2. Исправление первого инцидента
description: Начало работы по исправлению первого инцидента в Microsoft 365 Defender.
keywords: инциденты, оповещения, расследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверения, почтовый ящик, электронная почта, 365, Microsoft, m365, реагирование на инциденты, кибератака
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ed597c55a646eb00d6e6d256c287b22c119f8148
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297348"
---
# <a name="step-2-remediate-your-first-incident"></a>Этап 2. Исправление первого инцидента

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

Microsoft 365 Defender не только предоставляет возможности обнаружения и анализа, но и обеспечивает сдерживание и ликвидацию вредоносных программ. Сдерживание включает шаги по снижению воздействия атаки, а ликвидация обеспечивает удаление всех следов действий злоумышленников из сети.  Microsoft 365 Defender предлагает несколько действий по исправлению, которые можно настроить на автоматическое исправление в зависимости от операционной системы и типа атаки. [](m365d-autoir.md)

Microsoft 365 Defender предлагает несколько действий по исправлению, которые аналитики могут инициировать вручную. Действия разделены на две категории: Действия на устройствах и Действия в файлах. Некоторые действия можно использовать для немедленной остановки угрозы, а другие действия помогают в дальнейшем судебно-медицинском анализе.

## <a name="actions-on-devices"></a>Действия на устройствах

- **Изолировать** устройство . Эта активность немедленно блокирует весь сетевой трафик (интернет и внутренний), чтобы свести к минимуму распространение вредоносных программ и позволить аналитикам продолжить анализ без возможности злоумышленника продолжить атаку. Разрешено только подключение к облаку службы Microsoft Defender для удостоверений, чтобы Microsoft Defender for Identity продолжила следить за устройством. 
- **Ограничение выполнения** приложения . Чтобы ограничить запуск приложения, применяется политика целостности кода, которая позволяет запускать файлы только в том случае, если они подписаны сертификатом, выданным Корпорацией Майкрософт. Этот метод ограничения может помочь злоумышленнику контролировать скомпрометированную устройства и выполнять дальнейшие вредоносные действия.
- **Запуск антивирусного** сканирования — антивирусная программа в Microsoft Defender может работать вместе с другими антивирусными решениями, независимо от того, является ли антивирус Defender активным антивирусным решением или нет. Если основным решением защиты конечной точки является другой антивирусный продукт, можно запустить антивирус Defender в пассивном режиме.
- **Инициировать автоматическое** расследование . Вы можете начать новое общее автоматическое расследование на устройстве. В ходе расследования любое другое оповещение, сгенерированное с устройства, будет добавлено в текущее автоматическое расследование до завершения этого расследования. Кроме того, если такая же угроза видна на других устройствах, эти устройства добавляются в исследование.
- **Инициировать** живой ответ . Live response — это возможность мгновенного доступа к устройству с помощью удаленного подключения к оболочке. Это дает возможность выполнять углубленные следственные действия и принимать срочные меры реагирования для оперативного сдерживания выявленных угроз в режиме реального времени. Live response предназначен для повышения эффективности расследований, позволяя собирать судебно-медицинские данные, запускать сценарии, отправлять подозрительные объекты для анализа, устранения угроз и активной охоты на возникающие угрозы.
- **Сбор пакета расследований** . В рамках расследования или процесса реагирования можно собрать пакет исследований с устройства. Собирая пакет исследований, вы можете определить текущее состояние устройства и дополнительно понять инструменты и методы, используемые злоумышленником. 
- **Обратитесь к** эксперту по угрозам (доступно как в действиях на устройствах, так и в файлах) - Вы можете проконсультироваться с экспертом по угрозам Майкрософт, чтобы получить дополнительные сведения о потенциально скомпрометированных устройствах или устройствах, которые уже скомпрометированы. Эксперты по угрозам Майкрософт могут быть вовлечены непосредственно из Центр безопасности в Microsoft Defender для быстрого и точного ответа. 

## <a name="actions-on-files"></a>Действия в файлах

- **Стоп-файл** и файл карантина . Это действие включает остановку запущенных процессов, карантиновую обработку файлов и удаление сохраняющихся данных, например любых ключей реестра. Это действие действует на устройствах Windows 10 версии 1703 или более поздней версии, где файл был замечен в течение последних 30 дней. 
- **Добавление индикаторов для** блокировки или допуска файла . Предотвращение дальнейшего распространения атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы. Эта операция предотвратит чтение, написание или выполнение файла на устройствах в организации.
- **Скачивание или** сбор файла — это действие позволяет аналитикам скачивать файл в защищенном .zip архивном файле для дальнейшего анализа организацией.
- **Глубокий анализ** . Это действие выполняет файл в безопасной, полностью оборудованной облачной среде. Результаты глубокого анализа показывают действия файла, наблюдаемое поведение и связанные артефакты, такие как отброшенные файлы, изменения реестра и связь с IP-адресами. 

Продолжая пример в [detect, triage и analyse incidents,](first-incident-analyze.md#analyze-your-first-incident)аналитик может исправление этого инцидента с помощью этих действий:

1. Немедленно сброс пароля учетной записи пользователя
2. Изолировать устройство в Microsoft 365 Defender до завершения глубокого анализа
3. Убедитесь, что вредоносный файл был карантин из SharePoint
4. Проверьте, какие конечные точки были затронуты вредоносными программами
5. Восстановление систем
6. Проверьте, есть ли аналогичные Microsoft Cloud App Security оповещения для других пользователей
7. Создание пользовательского индикатора в Microsoft Defender для конечной точки для блокировки IP-адреса Tor
8. Создайте действие управления в Microsoft Cloud App Security для этого типа оповещений, таких как те, которые показаны на следующем изображении:

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Пример действий управления на Microsoft Cloud App Security портале"::: 
 
Большинство действий по исправлению можно применять и отслеживать в Microsoft 365 Defender. 

## <a name="using-playbooks"></a>Использование playbooks

Кроме того, автоматизированное исправление можно создать с помощью книг воспроизведения. В настоящее время в Microsoft есть шаблоны playbook в [GitHub,](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) которые предоставляют книги для следующих сценариев:

- Удаление деликатного общего доступа к файлам после запроса проверки пользователя
- Автоматические оповещения о нечастойной стране
- Запрос на действие диспетчера перед отключением учетной записи
- Отключение вредоносных правил почтовых ящиков

В playbooks Power Automate для создания пользовательских потоков автоматизации роботизированных процессов для автоматизации определенных действий после запуска определенных критериев. Организации могут создавать книги воспроизведения либо из существующих шаблонов, либо с нуля. 

Ниже приведен пример.
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Пример пользовательского потока автоматизации Power Automate роботизированных процессов"::: 
 
Во время проверки после [](first-incident-post.md) инцидента также можно создавать книги для создания действий по исправлению последствий инцидентов для более быстрых действий по исправлению. 

## <a name="next-step"></a>Следующий шаг

[![Шаг 3. Узнайте, как выполнить проверку инцидента после инцидента](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)

Узнайте, [как выполнить проверку инцидента после инцидента.](first-incident-post.md)

## <a name="see-also"></a>См. также

- [Обзор инцидентов](incidents-overview.md)
- [Исследование инцидентов](investigate-incidents.md)
- [Управление инцидентами](manage-incidents.md)