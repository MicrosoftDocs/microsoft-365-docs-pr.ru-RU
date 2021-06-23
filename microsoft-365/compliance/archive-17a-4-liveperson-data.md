---
title: Настройка соединителя для архива данных разговорного облака LivePerson в Microsoft 365
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
description: Узнайте, как настроить и использовать соединитель 17a-4 LivePerson Conversational Cloud DataParser для импорта и архива данных разговорного облака LivePerson в Microsoft 365.
ms.openlocfilehash: 3a4156d817e1b7471f769a2365c5af9d58ade991
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097296"
---
# <a name="set-up-a-connector-to-archive-liveperson-conversational-cloud-data-preview"></a>Настройка соединителя для архива данных разговорного облака LivePerson (предварительный просмотр)

Для импорта и архива данных [из livePerson Conversational Cloud DataParser](https://www.17a-4.com/liveperson-dataparser/) от 17a-4 LLC в почтовые ящики пользователей в вашей Microsoft 365 организации. В состав DataParser входит соединитель диалогового облака LivePerson, настроенный для захвата элементов из стороннего источника данных и импорта этих элементов в Microsoft 365. Соединитель разговорного облака LivePerson DataParser преобразует данные в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.

После хранения данных в почтовых ящиках пользователей можно применить Microsoft 365, такие как хранение судебного разбирательства, открытие электронных данных, политики хранения и метки хранения, а также соответствие требованиям связи. Использование соединителя разговорного облака LivePerson для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.

## <a name="overview-of-archiving-liveperson-conversational-cloud-data"></a>Обзор архива данных livePerson Conversational Cloud

В следующем обзоре рассказывается о процессе использования соединителя данных для архивации данных livePerson Conversational Cloud в Microsoft 365.

![Архивативная работа для данных разговорного облака LivePerson с 17a-4](../media/LiveEngageDataParserConnectorWorkflow.png)

1. Ваша организация работает с 17a-4 для настройки и настройки облачного dataParser LivePerson.

2. Регулярно элементы разговорного облака LivePerson собираются в DataParser. DataParser также преобразует содержимое сообщения в формат сообщения электронной почты.

3. Соединитель беседного облака LivePerson DataParser, который вы создаете в Центр соответствия требованиям Microsoft 365, подключается к DataParser и передает сообщения в безопасное служба хранилища Azure в облаке Майкрософт.

4. В почтовых ящиках пользователей создается подмостка в папке "Входящие" с именем **LivePerson Conversational Cloud DataParser,** и элементы импортируется в эту папку. Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.* Каждый элемент содержит это свойство, которое заполняется адресом электронной почты каждого участника.

## <a name="before-you-set-up-a-connector"></a>Перед настройками соединитетеля

- Создайте учетную запись DataParser для соединители Microsoft. Для этого обратитесь в [ООО "17a-4".](https://www.17a-4.com/contact/) При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.

- Пользователь, создававший соединитель диалогового облачного облака LivePerson DataParser в шаге 1 (и завершавший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online. Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365. По умолчанию эта роль не назначена группе ролей в Exchange Online. Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online. Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников. Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".

## <a name="step-1-set-up-a-liveperson-conversational-cloud-dataparser-connector"></a>Шаг 1. Настройка соединителя беседного облака LivePerson DataParser

Первым шагом является доступ к странице соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединителя 17a-4 для данных livePerson Conversational Cloud.

1. Перейдите к соединителям данных и нажмите <https://compliance.microsoft.com>   >  **кнопку LivePerson Conversational Cloud DataParser**.

2. На странице **описания продукта LivePerson Conversational Cloud DataParser** нажмите **кнопку Добавить соединитель**.

3. На странице **Условия службы нажмите** кнопку **Принять**.

4. Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.

5. Вопишите в свою учетную запись 17a-4 и выполните действия в мастере подключения livePerson Conversational Cloud DataParser.

## <a name="step-2-configure-the-liveperson-conversational-cloud-dataparser-connector"></a>Шаг 2. Настройка соединителя livePerson Conversational Cloud DataParser

Работа с поддержкой 17a-4 для настройки соединителя облачного облачного подключения LivePerson DataParser.

## <a name="step-3-map-users"></a>Шаг 3. Пользователи карт

Соединитель беседного облачного облака LivePerson dataParser автоматически соединит пользователей с Microsoft 365 адресами электронной почты перед импортом данных в Microsoft 365.

## <a name="step-4-monitor-the-liveperson-conversational-cloud-dataparser-connector"></a>Шаг 4. Мониторинг соединителя разговорного облачного облака LivePerson DataParser

После создания соединиттеля livePerson Conversational Cloud DataParser можно просмотреть состояние соединителя в Центр соответствия требованиям Microsoft 365.

1. Перейдите <https://compliance.microsoft.com> и щелкните **соединители данных** в левом nav.

2. Щелкните  вкладку Соединители, а затем выберите соединитель livePerson Conversational Cloud DataParser, созданный для отображения страницы вылетов, которая содержит свойства и сведения о соединителе.

3. В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля. В этом журнале содержатся данные, импортируемые в облако Майкрософт.

## <a name="known-issues"></a>Известные проблемы

В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ. Поддержка более крупных элементов будет доступна позднее.
