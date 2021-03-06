---
title: Настройка соединителю для архивации данных CellTrust в Microsoft 365
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
description: Администраторы могут настроить соединитель для импорта и архивации данных CellTrust из Veritas в Microsoft 365. Этот соединитатель позволяет архивировать данные из сторонних источников данных в Microsoft 365. После архива эти данные можно использовать такие функции соответствия требованиям, как юридические удержания, политики поиска контента и хранения для управления сторонними данными.
ms.openlocfilehash: 855d48303c7c35c32951105799aa117675820420
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164393"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a>Настройка соединителю для архивации данных CellTrust

Используйте соединитель Veritas в центре Microsoft 365 для импорта и архивации данных с платформы CellTrust в почтовые ящики пользователей в Microsoft 365 организации. Veritas предоставляет соединитель [CellTrust,](https://globanet.com/celltrust/) который захватывает элементы из стороннего источника данных и импортирует эти элементы в Microsoft 365. Соединитель преобразует содержимое SMS из учетных записей CellTrust в формат сообщений электронной почты, а затем импортирует эти элементы в почтовый ящик пользователя в Microsoft 365.

После хранения данных CellTrust в почтовых ящиках пользователей можно применить Microsoft 365, такие как хранение судебных разбирательств, электронные сведения, политики хранения и метки хранения, а также соответствие требованиям к связи. Использование соединиттеля CellTrust для импорта и архивации данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.

## <a name="overview-of-archiving-celltrust-data"></a>Обзор архивации данных CellTrust

В следующем обзоре объясняется процесс использования соединителю для архивации данных CellTrust в Microsoft 365.

![Архивация рабочего процесса для данных CellTrust](../media/CellTrustConnectorWorkflow.png)

1. Ваша организация работает с CellTrust для настройки и настройки сайта CellTrust.

2. Каждые 24 часа элементы CellTrust копируется на сайте Veritas Merge1. Соединителет также преобразует содержимое сообщения в формат сообщения электронной почты.

3. Соединитель CellTrust, который вы создаете в центре Microsoft 365 соответствия требованиям, подключается к сайту Veritas Merge1 каждый день и передает сообщения в безопасное расположение служба хранилища Azure в облаке Майкрософт.

4. Автоматическое сопоставление пользователей в качестве соединиттеля импортирует элементы в почтовые ящики определенных пользователей, используя значение свойства *Email,* описанного в [шаге 3.](#step-3-map-users-and-complete-the-connector-setup) В почтовых ящиках пользователей создается подмостки в папке "Входящие" с именем **CellTrust,** и элементы сообщений импортируются в эту папку. Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.* Каждый элемент CellTrust содержит это свойство, которое заполняется адресом электронной почты каждого участника.

## <a name="before-you-begin"></a>Прежде чем начать

- Создание учетной записи Merge1 для соединители Microsoft. Чтобы создать учетную запись, обратитесь [в службу поддержки клиентов Veritas.](https://www.veritas.com/content/support/) При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.

- Пользователь, создавший соединитель CellTrust в шаге 1 (и завершивший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online. Эта роль необходима для добавления соединители на **странице** соединители данных в центре Microsoft 365 соответствия требованиям. По умолчанию эта роль не назначена ни одной группе ролей в Exchange Online. Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online. Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников. Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".

## <a name="step-1-set-up-the-celltrust-connector"></a>Шаг 1. Настройка соединиттеля CellTrust

На первом этапе необходимо  получить доступ к соединителю данных в центре Microsoft 365 и создать соединитель для данных CellTrust.

1. Перейдите [https://compliance.microsoft.com](https://compliance.microsoft.com/) к и нажмите **кнопку Соединители данных** \> **CellTrust**.

2. На странице **описания продукта CellTrust** нажмите кнопку **Добавить соединитель**.

3. На странице **Условия службы нажмите** кнопку **Принять**.

4. Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.

5. Впишитесь в свою учетную запись Merge1, чтобы настроить соединители.

## <a name="step-2-configure-the-celltrust-connector-on-the-veritas-merge1-site"></a>Шаг 2. Настройка соединителя CellTrust на сайте Veritas Merge1

Второй шаг — настройка соединителя CellTrust на сайте Veritas Merge1. Сведения о настройке соединиттеля CellTrust см. в руководстве по пользователю [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)

После нажатия **кнопки Сохранить &**  finish отображается страница сопоставления пользователей в мастере соединители в центре Microsoft 365 соответствия требованиям.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Шаг 3. Карта пользователей и завершение установки соединитетеля

Чтобы соединять пользователей и выполнить подключение, настроенное в центре Microsoft 365 соответствия требованиям, выполните следующие действия:

1. На странице **Map CellTrust пользователи, Microsoft 365 пользователи,** включат автоматическое сопоставление пользователей. Элементы CellTrust включают свойство *Email,* которое содержит адреса электронной почты для пользователей в организации. Если соединитатель может связать этот адрес с Microsoft 365 пользователем, элементы импортируется в почтовый ящик этого пользователя.

2. Нажмите **кнопку Далее,** просмотрите  параметры и перейдите на страницу соединители данных, чтобы просмотреть ход процесса импорта нового соединитетеля.

## <a name="step-4-monitor-the-celltrust-connector"></a>Шаг 4. Мониторинг соединителю CellTrust

После создания соединиттеля CellTrust можно просмотреть состояние соединителю в центре Microsoft 365 соответствия требованиям.

1. Перейдите [https://compliance.microsoft.com](https://compliance.microsoft.com/) и щелкните **соединители данных** в левом nav.

2. Щелкните **вкладку** Соединители, а затем выберите соединитель **CellTrust,** чтобы отобразить страницу вылетов, которая содержит свойства и сведения о соединителе.

3. В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля. В этом журнале содержатся данные, импортируемые в облако Майкрософт.

## <a name="known-issues"></a>Известные проблемы

- В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ. Поддержка более крупных элементов будет доступна позднее.