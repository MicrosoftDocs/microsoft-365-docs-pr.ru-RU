---
title: Настройка соединитетеля для архива данных Pivot в Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Администраторы могут настроить соединитель для импорта и архива данных Pivot из Veritas в Microsoft 365. Этот соединитатель позволяет архивировать данные из сторонних источников данных в Microsoft 365, чтобы можно было использовать функции соответствия требованиям, такие как политики хранения, поиска контента и хранения для управления сторонними данными организации.
ms.openlocfilehash: 8e88f5166ebcc4d1285a81e041b6d97be46786e3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164196"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Настройка соединитетеля для архива данных Pivot

Используйте соединитель Veritas в центре Microsoft 365 для импорта и архива данных с платформы Pivot в почтовые ящики пользователей в Microsoft 365 организации. Veritas предоставляет вам соединитель [Pivot,](https://globanet.com/pivot/) который настроен для захвата элементов из стороннего источника данных (на регулярной основе), а затем импортировать эти элементы в Microsoft 365. Pivot — это платформа обмена мгновенными сообщениями, которая позволяет сотрудничать с участниками финансового рынка. Соединитатель преобразует элементы, такие как сообщения чата, из учетных записей pivot пользователей в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.

После хранения данных Pivot в почтовых ящиках пользователей можно применять Microsoft 365, такие как хранение судебного разбирательства, электронные сведения, политики хранения и метки хранения, а также соответствие требованиям к связи. Использование соединиттеля Pivot для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.

## <a name="overview-of-archiving-pivot-data"></a>Обзор архива данных свода

В следующем обзоре объясняется процесс использования соединитетеля для архивации данных Pivot в Microsoft 365.

![Архивавка рабочего процесса для данных Pivot](../media/PivotConnectorWorkflow.png)

1. Организация работает с Pivot, чтобы настроить и настроить исходный сайт Pivot.

2. Каждые 24 часа элементы Pivot копируется на сайте Veritas Merge1. Соединитело также преобразует элементы Pivot в формат сообщений электронной почты.

3. Соединитель Pivot, который создается в центре Microsoft 365 соответствия требованиям, подключается к сайту Veritas Merge1 каждый день и передает элементы Pivot в безопасное расположение служба хранилища Azure в облаке Microsoft.

4. Соединитатель импортирует элементы Pivot в почтовые ящики определенных пользователей, используя значение свойства *Email* автоматического сопоставления пользователей, как описано в [шаге 3](#step-3-map-users-and-complete-the-connector-setup). Подмостки в папке "Входящие" с именем **Pivot** создаются в почтовых ящиках пользователей, и элементы импортируется в эту папку. Соединитатель делает это, используя значение свойства *Email.* Каждый элемент Pivot содержит это свойство, которое заполняется адресом электронной почты каждого участника элемента.

## <a name="before-you-begin"></a>Прежде чем начать

- Создайте учетную запись Veritas Merge1 для соединители Microsoft. Чтобы создать эту учетную запись, обратитесь в службу поддержки [клиентов Veritas.](https://www.veritas.com/content/support/) При создании соединитетеля в шаге 1 вы вопишитесь в эту учетную запись.

- Пользователь, создававший соединитатель Pivot в шаге 1 (и завершавший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online. Эта роль требуется для добавления соединители на странице соединители данных в центре Microsoft 365 соответствия требованиям. По умолчанию эта роль не назначена группе ролей в Exchange Online. Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online. Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников. Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".

## <a name="step-1-set-up-the-pivot-connector"></a>Шаг 1. Настройка соединиттеля Pivot

Первым шагом является доступ к странице **Соединители** данных в центре соответствия требованиям Майкрософт и создание соединитетеля для данных Pivot.

1. Перейдите [https://compliance.microsoft.com](https://compliance.microsoft.com/) к и нажмите **кнопку Соединители данные**  >  **Pivot**.

2. На странице **описание продукта Pivot** нажмите кнопку **Добавить соединителю**.

3. На странице **Условия службы нажмите** кнопку **Принять**.

4. Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.

5. Впишитесь в свою учетную запись Merge1, чтобы настроить соединители.

## <a name="step-2-configure-the-pivot-connector-on-the-veritas-merge1-site"></a>Шаг 2. Настройка соединителя pivot на сайте Veritas Merge1

На втором этапе необходимо настроить соединители Pivot на сайте Merge1. Сведения о настройке соединиттеля Pivot на сайте Veritas Merge1 см. в руководстве по пользователю [Merge1 сторонних соединителях.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)

После нажатия **кнопки Сохранить &**  finish отображается страница сопоставления пользователей в мастере соединители в центре Microsoft 365 соответствия требованиям.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Шаг 3. Карта пользователей и завершение установки соединитетеля

Чтобы составить карту пользователей и завершить установку соединитетеля в центре соответствия требованиям Microsoft 356, выполните следующие действия:

1. На странице **Pivot map пользователи Microsoft 365 страницу,** включив автоматическое сопоставление пользователей. Элементы Pivot включают свойство *Email,* которое содержит адреса электронной почты для пользователей в вашей организации. Если соединитатель может связать этот адрес с Microsoft 365 пользователем, элементы импортируется в почтовый ящик этого пользователя.

2. Нажмите **кнопку Далее,** просмотрите  параметры и перейдите на страницу соединители данных, чтобы просмотреть ход процесса импорта нового соединитетеля.

## <a name="step-4-monitor-the-pivot-connector"></a>Шаг 4. Мониторинг соединиттеля pivot

После создания соединиттеля Pivot можно просмотреть состояние соединитетеля в центре Microsoft 365 соответствия требованиям.

1. Перейдите [https://compliance.microsoft.com](https://compliance.microsoft.com) и щелкните **соединители данных** в левом nav.

2. Щелкните **вкладку** Соединители, а затем выберите **соединителет Pivot,** чтобы отобразить страницу вылетов. На этой странице содержатся свойства и сведения о соединители.

3. В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля. В этом журнале содержатся данные, импортируемые в облако Майкрософт.

## <a name="known-issues"></a>Известные проблемы

- В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ. Поддержка более крупных элементов будет доступна позднее.