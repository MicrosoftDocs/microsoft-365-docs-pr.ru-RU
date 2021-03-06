---
title: Планирование соответствия требованиям к обмену данными
description: Узнайте о планировании использования соответствия требованиям связи в организации.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: d64edc9d80722080db18c45127bfc82110d1ea9e
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131541"
---
# <a name="plan-for-communication-compliance"></a>Планирование соответствия требованиям к обмену данными

Перед [началом](communication-compliance.md) работы с соблюдением требований к общению в организации необходимо учитывать важные действия и соображения планирования, которые должны быть рассмотрены группами по управлению информационными технологиями и соответствием требованиям. Тщательное понимание и планирование развертывания в следующих областях помогут обеспечить бесперебойную реализацию и использование функций соответствия требованиям связи и соответствие с лучшими практиками решения.

## <a name="work-with-stakeholders-in-your-organization"></a>Работа с заинтересованными сторонами в организации

Определите соответствующих заинтересованных лиц в организации для совместной работы по принятию мер по оповещениям о соответствии требованиям связи. Некоторые заинтересованные стороны, рекомендуемые для рассмотрения в том [](communication-compliance.md#workflow) числе в начальном планировании и конечной работе по обеспечению соответствия требованиям связи, — это люди из следующих областей организации:

- Информационные технологии
- Соответствие требованиям
- Конфиденциальность
- Безопасность
- Управление персоналом
- Юридические аспекты

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Планирование рабочего процесса по расследованию и исправлению

Выберите выделенных заинтересованных лиц для мониторинга и проверки оповещений и случаев на регулярной основе в центре Microsoft 365 [соответствия](https://compliance.microsoft.com/)требованиям . Убедитесь в том, что вы назначите пользователям и заинтересованным лицам различные группы ролей соответствия требованиям связи в вашей организации.

В зависимости от того, как управлять политиками и оповещениями в области связи, необходимо назначить пользователей одной или несколько групп ролей администраторам, рецензентам и следователям. У вас есть возможность назначать пользователей определенным группам ролей для управления различными наборами функций соответствия требованиям. Или вы можете назначить всех пользователей соответствия требованиям связи в группу ролей соответствия требованиям связи. Используйте одну группу ролей или несколько групп, чтобы наилучшим образом соответствовать вашим требованиям по управлению соответствием требованиям.

Планирование выбора из этих параметров группы ролей при настройке соответствия требованиям к коммуникации:

|**Role**|**Разрешения роли**|
|:-----|:-----|
| **Соответствие требованиям связи** | Используйте эту группу ролей для управления соответствием требованиям к общению для организации в одной группе. Добавляя все учетные записи пользователей для назначенных администраторов, аналитиков, следователей и зрителей, можно настроить разрешения на соответствие требованиям связи в одной группе. Эта группа ролей содержит все роли разрешений на связь. Эта конфигурация является самым простым способом быстрого начала работы с соответствием требованиям к связи и подходит для организаций, которые не нуждаются в отдельных разрешениях, определенных для отдельных групп пользователей. |
| **Администратор соответствия требованиям к обмену данными** | Используйте эту группу ролей для первоначальной настройки соответствия требованиям к коммуникациям, а затем для разделения администраторов соответствия требованиям связи в определенную группу. Пользователи, назначенные этой группе ролей, могут создавать, читать, обновлять и удалять политики соответствия требованиям к связи, глобальные параметры и назначения групп ролей. Пользователи, назначенные этой группе ролей, не могут просматривать оповещения о сообщениях. |
| **Аналитик соответствия требованиям связи** | Используйте эту группу для назначения разрешений пользователям, которые будут выступать в качестве аналитиков соответствия требованиям связи. Пользователи, назначенные этой группе ролей, могут просматривать политики, в которых они назначены в качестве рецензентов, просматривать метаданные сообщений (а не содержимое сообщений), переадрастать в дополнительные рецензенты или отправлять уведомления пользователям. Аналитики не могут разрешить ожидающих оповещений. |
| **Следователь соответствия требованиям связи** | Используйте эту группу для назначения разрешений пользователям, которые будут выступать в качестве исследователей соответствия требованиям связи. Пользователи, назначенные этой группе ролей, могут просматривать метаданные и содержимое сообщений, перенаправляться в дополнительные рецензенты, перерастать в Advanced eDiscovery, отправлять уведомления пользователям и устранять предупреждение. |
| **Зритель соответствия требованиям к обмену данными** | Используйте эту группу для назначения разрешений пользователям, которые будут управлять отчетами о связи. Пользователи, заметив эту группу ролей, могут получать доступ ко всем виджетам отчетности на домашней странице соответствия требованиям связи и просматривать все отчеты о соответствии требованиям связи. |

## <a name="plan-for-policies"></a>Планирование политик

Создание политик соответствия требованиям к коммуникациям легко и быстро с помощью заранее определенных шаблонов для оскорбительных языков, конфиденциальной информации и соответствия нормативным требованиям. [](communication-compliance-feature-reference.md#policy-templates) Настраиваемые политики соответствия требованиям к коммуникациям позволяют гибко обнаруживать и выявлять проблемы, специфические для организации и требований.

При планировании политик соответствия требованиям к коммуникациям рассмотрите следующие области:

- Рассмотрите возможность добавления всех пользователей в организации в качестве дополнительных для политик соответствия требованиям к коммуникациям. Определение конкретных пользователей в качестве потенциальных для отдельных политик полезно в некоторых случаях, однако большинство организаций должны включать всех пользователей в политики соответствия требованиям связи, оптимизированные для обнаружения домогательств или дискриминации.
- Чтобы упростить настройку, рассмотрите возможность создания групп для людей, которые нуждаются в просмотре их сообщений. Если вы используете группы; может потребоваться несколько. Например, если вы хотите контролировать общение двух разных групп пользователей или указать группу, которую не нужно контролировать.
- Настройте процент сообщений для проверки на уровне 100%, чтобы политики ловили все проблемы, волнуемые в коммуникациях для организации.
- Вы можете сканировать сообщения из [сторонних](communication-compliance-feature-reference.md#supported-communication-types) источников для данных, импортируемых в почтовые ящики в Microsoft 365 организации. Чтобы включить обзор сообщений на этих платформах, необходимо настроить соединители для этих служб, прежде чем условия политики собраний сообщений будут отслеживаться политикой связи.
- Политики могут поддерживать мониторинг языков, помимо английского, в пользовательских политиках соответствия требованиям. Создайте [настраиваемый](communication-compliance-feature-reference.md#custom-keyword-dictionaries) словарь слов оскорбительных слов на языке вашего выбора или создайте собственную модель машинного обучения с помощью обучаемых [классификаторов](classifier-get-started-with.md) в Microsoft 365.
- Все организации имеют различные стандарты связи и потребности в политике. Отслеживайте конкретные ключевые слова с использованием условий политики соответствия требованиям к коммуникации [или](communication-compliance-feature-reference.md#conditional-settings) отслеживайте для определенных типов информации с [настраиваемыми типами конфиденциальной информации.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>Готовы приступить к работе?

Чтобы настроить соответствие требованиям связи для Microsoft 365 организации, см. в примере Настройка соответствия требованиям связи для [Microsoft 365](communication-compliance-configure.md) или ознакомьтесь с тематией для [Contoso](communication-compliance-case-study.md) и тем, как они быстро настроили политику соответствия требованиям связи для мониторинга оскорбительных языков в Microsoft Teams, Exchange Online и Yammer коммуникациях.
