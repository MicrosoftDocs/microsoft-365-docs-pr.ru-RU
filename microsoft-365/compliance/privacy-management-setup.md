---
title: Начало работы с управлением конфиденциальностью Майкрософт (предварительный просмотр)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Узнайте, как настроить управление конфиденциальностью для организации, установить роли и разрешения и настроить важные параметры.
ms.openlocfilehash: 5199cf96e9ede3287dc9ac33e26388c065189748
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378549"
---
# <a name="get-started-with-privacy-management-preview"></a>Начало работы с управлением конфиденциальностью (предварительный просмотр)

В этой статье: узнайте,  как настроить доступ к управлению конфиденциальностью для организации, как начать работу с оценкой данных и как обрабатывать **важные параметры.** 

## <a name="sign-up"></a>Регистрация

Управление конфиденциальностью будет доступно в Центр соответствия требованиям Microsoft 365. Общедоступный предварительный просмотр управления конфиденциальностью доступен организациям с корпоративными лицензиями E1, E3 и E5 Office 365 и Microsoft 365 конфиденциальности. При общей доступности управления конфиденциальностью организациям потребуется получить новую лицензию.

Обратите внимание, что общедоступный предварительный просмотр управления конфиденциальностью не будет доступен для клиентов Community (GCC) умеренных, GCC high или Department of Defense (DoD).

Чтобы начать работу с общедоступным предварительным просмотром, получите предварительную подписку в центре администрирования. Если у вас еще нет лицензии при первом выборе управления конфиденциальностью в центре соответствия требованиям, вы будете направлены в центр администрирования, чтобы начать работу. Рекомендуется, чтобы глобальный администратор входил и устанавливал разрешения пользователей, как описано ниже, при первом посещении управления конфиденциальностью. Если у вас не будет необходимой роли для получения подписки или согласия на условия использования управления конфиденциальностью, вам будет предложено обратиться за помощью к глобальному администратору.

Подтверждение того, что вы хотите начать использовать сигналы управления конфиденциальностью, которые согласуются с условиями и процессом оценки персональных данных. Вы можете просмотреть предоставленные ссылки в полном объеме перед началом разбирательства.

## <a name="set-user-permissions-and-assign-roles"></a>Настройка разрешений пользователей и назначение ролей

Управление конфиденциальностью использует модель разрешений для управления доступом на основе ролей (RBAC). Только пользователи, которым назначена роль, могут получать доступ к управлению конфиденциальностью, а действия, разрешенные каждым пользователем, ограничены типом ролей.

Разрешения и назначения ролей для управления конфиденциальностью можно обрабатывать в Центр соответствия требованиям Microsoft 365, как следует. Обратите внимание, что роли, определенные управлению конфиденциальностью, не отображаются в Azure Active Directory.

### <a name="in-the-microsoft-365-compliance-center"></a>В Центр соответствия требованиям Microsoft 365

- Выберите Разрешения в левой навигации.
- Расширь центр соответствия требованиям и выберите роли. Появится полный список групп ролей. 
- Прокрутите, чтобы найти группы управления конфиденциальностью или поиск по ключевому слову, например "конфиденциальность".
- Выберите соответствующую группу ролей, чтобы увидеть описание, назначенную роль и список участников.
- Используйте ссылку Изменить рядом с этими разделами, чтобы добавить или изменить пользователей или изменить параметры.

### <a name="learn-about-role-groups-and-roles"></a>Узнайте о группах ролей и ролях

В этом разделе описаны группы ролей и роли, которые имеют отношение к управлению конфиденциальностью. Члены должны быть назначены группам ролей администратором верхнего уровня в зависимости от того, какие задачи им необходимо выполнить и какой уровень доступа к файлам является подходящим. Каждая группа ролей включает одну или несколько ролей. Эти роли могут соответствовать определенным задачам управления конфиденциальностью или соответствовать ключевым функциям, которые включены или ограничены для членов этой группы.

Группы ролей можно настроить при необходимости. Чтобы избежать случайной потери доступа, рекомендуется создать копию существующей группы ролей, которую вы хотите настроить, давая копию идентифицируемого имени, делая и проверяя изменения в новой группе и назначая ей людей по мере необходимости.

**Управление конфиденциальностью.** Эта группа содержит все роли разрешений на управление конфиденциальностью в одной группе. Это самый простой способ быстрого начала работы с управлением конфиденциальностью и управления управлением доступом для других групп, которые будут использовать управление конфиденциальностью. Это также подходит для организаций, которые не нуждаются в отдельных разрешениях, определенных для отдельных групп пользователей.

Администраторы управления конфиденциальностью. Члены этой группы ролей фокусируется на задачах конфигурации и администрирования и имеют широкий доступ к функциям управления конфиденциальностью, включая создание, чтение, обновление и удаление политик управления конфиденциальностью, запросов на права субъектов, разрешений на управление конфиденциальностью и параметров управления конфиденциальностью.

**Аналитики управления конфиденциальностью.** Члены этой группы ролей выступают в качестве аналитиков по управлению конфиденциальностью. Они могут исследовать совпадения политик, просматривать метаданные файлов и принимать меры по исправлению. Эта группа не может получить доступ к полным файлам через обозреватель контента.

**Исследователи управления конфиденциальностью.** Члены этой группы выступают в качестве исследователей данных по управлению конфиденциальностью. Они могут исследовать совпадения политик, просматривать связанное содержимое файла и принимать меры по исправлению. Эта группа может получать доступ к файлам через обозреватель контента.

**Просмотра конфиденциальности.** Члены этой группы могут просматривать аналитические сведения в управлении конфиденциальностью, такие как обзор, профиль данных и отчеты о запросах субъектов.

**Администраторы запросов на права** субъектов. Члены этой группы имеют полный доступ к администрированию и созданию запросов на права субъекта.

**Вкладчики управления конфиденциальностью.** Члены этой группы имеют доступ к запросам на права субъекта.

Чтобы увидеть конкретные роли, включенные в каждую группу ролей, см. в следующей таблице.

| **Группа ролей**      | **Роли, включенные**                        |
|:-- |:--|
| Управление конфиденциальностью  | Управление случаем                           |
|                     | Просмотр контента классификации данных        |
|                     | Просмотр списка классификации данных           |
|                     | Администратор управления конфиденциальностью                  |
|                     | Анализ управления конфиденциальностью               |
|                     | Исследование управления конфиденциальностью          |
|                     | Постоянный вклад управления конфиденциальностью |
|                     | Временный вклад управления конфиденциальностью |
|                     | Просмотр конфиденциальности                 |
|                     | Администратор запроса на права субъекта              |
|                     | View-Only Case                            |
| Администратор управления конфиденциальностью | Управление случаем                      |
|                          | Администратор управления конфиденциальностью             |
|                          | View-Only Case                       |
| Аналитики управления конфиденциальностью | Управление случаем                   |
|                             | Просмотр списка классификации данных   |
|                             | Анализ управления конфиденциальностью       |
|                             | View-Only Case                    |
| Исследователи управления конфиденциальностью | Управление случаем              |
|                                  | Просмотр контента классификации данных |
|                                  | Просмотр списка классификации данных    |
|                                  | Исследование управления конфиденциальностью   |
|                                  | View-Only Case                     |
| Просмотр конфиденциальности        | Просмотр конфиденциальности          |
| Администратор запроса на права субъекта | Администратор запроса на права субъекта   |
|Вкладчики управления конфиденциальностью       | Временный вклад управления конфиденциальностью |
|                                      | Постоянный вклад управления конфиденциальностью |

## <a name="configure-settings"></a>Настройка параметров

Страница Параметры доступна через колесо передач в правом верхнем углу главных страниц управления конфиденциальностью. Это позволяет администраторам управления конфиденциальностью настраивать основные свойства в рамках управления конфиденциальностью. Параметры включают в себя следующее.

### <a name="anonymization"></a>Обезличивание

Эта функция позволяет показывать анонимные версии имен пользователей в функциях управления конфиденциальностью пользователям в определенных ролях. Это заменит идентифицируемые имена отображения, такие как "Grace Taylor" с общими меткой, как "AnonyIS8-988", чтобы помочь скрыть удостоверения пользователей при просмотре конфиденциальных данных. Этот параметр не применяется к модуле запроса прав субъекта.

### <a name="user-notification-emails"></a>Сообщения электронной почты уведомлений пользователей

При обнаружении совпадения политик обработки данных управление конфиденциальностью может отправить пострадавшим пользователям письмо с исправлением действий и ссылку на обучение конфиденциальности. В Параметры вы можете включить или отключить возможность уведомления электронной почты управления конфиденциальностью в целом. Вы можете активировать отдельные уведомления, задать частоту электронной почты и указать URL-адрес обучения при создании или редактировании политики. Если возможность уведомления отключена в Параметры, любая конфигурация на уровне политики для определенных почтовых уведомлений будет отключена. Дополнительные новости о политиках см. в см. в ["Создание и управление политиками".](privacy-management-policies.md)

### <a name="teams-collaboration"></a>Совместная работа в Teams

Интеграция Microsoft Teams с управлением конфиденциальностью для расширения взаимодействия с заинтересованными сторонами. Каждый раз, когда создается запрос на права субъекта, создается связанная группа. Пользователи могут быть добавлены в команду со вкладки Соавторы запроса. Дополнительные новости о запросах на права субъекта см. в руб. Управление запросами [на права субъекта.](privacy-management-subject-rights-requests.md)

### <a name="power-automate-flows"></a>Power Automate потоков

Использование Power Automate потоков для автоматического управления процессами и задачами, связанными с конфиденциальностью. Вы можете создавать потоки в разделе Параметры с помощью встроенных шаблонов управления конфиденциальностью или использовать консоль Power Automate для создания настраиваемого потока. Дополнительные дополнительные Power Automate см. [в](/power-automate/) Power Automate документации.

### <a name="data-matching"></a>Соответствие данным

Используйте этот раздел для отправки схем данных, описываемых атрибутами субъектов данных, которые помогут определить правильный субъект данных при поиске личных данных в Microsoft 365 среде. Схемы и пакеты правил создаются и загружаются в формате XML. При отправке персональных данных можно также отправлять персональные данные, которые совпадают с предоставленной схемой. Вы можете создавать и загружать собственный файл или загружать личные данные из Azure. Дополнительные новости о запросах на права субъекта см. в руб. Управление запросами [на права субъекта.](privacy-management-subject-rights-requests.md)

### <a name="data-retention-periods"></a>Периоды хранения данных

Для запросов на права субъекта выберите, сколько времени необходимо сохранить окончательные данные, собранные, и сообщить об этом после закрытия запроса. Вы можете выбрать от 30 до 90 дней. Дополнительные новости о запросах на права субъекта см. в руб. Управление запросами [на права субъекта.](privacy-management-subject-rights-requests.md)

### <a name="data-review-tags"></a>Теги проверки данных

Управление тегами, которые будут использовать для маркировки файлов, извлеченных в запросе на права субъекта. В этом разделе можно изменить имена и описания пользовательских тегов. Кроме того, можно изменить описания тегов для встроенных тегов, предоставляемых системой. Имена системных тегов не могут быть изменены. Дополнительные новости о запросах на права субъекта см. в руб. Управление запросами [на права субъекта.](privacy-management-subject-rights-requests.md)

## <a name="get-initial-data-insights"></a>Получить начальные сведения о данных

После регистрации в управлении конфиденциальностью вы прибудете на страницу **Обзор.** Эта страница предоставляет динамические сведения о персональных данных, хранимых в Microsoft 365 среде, чтобы помочь вам быстро выявлять проблемы, определять индикаторы риска и принимать меры для устранения проблем. Обзор должен заполняться начальными сведениями в течение первых 24 часов после регистрации. По мере использования управления конфиденциальностью страница обзоров обновляется, чтобы продолжать предоставлять текущую информацию.

Чтобы получить дополнительные сведения о  ваших данных со временем, на странице профилей данных будет предоставляться больше визуализаций и аналитики, а также предоставляется представление данных организации на высоком уровне по географическому расположению и Microsoft 365 службе.

Дополнительные сведения об этих страницах см. в странице [Find and visualize your data.](privacy-management-data-profile.md)
