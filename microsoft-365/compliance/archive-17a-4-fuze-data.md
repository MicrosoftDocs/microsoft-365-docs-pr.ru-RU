---
title: Настройка соединителю для архива данных взрывателя в Microsoft 365
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
description: Узнайте, как настроить и использовать соединителю fuze DataParser 17a-4 для импорта и архива данных взрывателя в Microsoft 365.
ms.openlocfilehash: 9f3c7590a033c2c19d9b588167d67c24f917ec5f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454509"
---
# <a name="set-up-a-connector-to-archive-fuze-data"></a>Настройка соединителю для архива данных взрывателя

Используйте [fuze DataParser](https://www.17a-4.com/fuze-dataparser/) от 17a-4 LLC для импорта и архива данных из fuze в почтовые ящики пользователей в Microsoft 365 организации. DataParser включает соединителю fuze, который настроен для захвата элементов из стороннего источника данных и импорта этих элементов в Microsoft 365. Соединиттель Fuze DataParser преобразует данные взрывателя в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.

После хранения данных взрывания в почтовых ящиках пользователей можно применить Microsoft 365, такие как хранение судебного разбирательства, электронные сведения, политики хранения и метки хранения, а также соответствие требованиям связи. Использование соединиттеля взрывателя для импорта и архива данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.

## <a name="overview-of-archiving-fuze-data"></a>Обзор архива данных взрывания

В следующем обзоре объясняется процесс использования соединителю данных для архивации данных fuze в Microsoft 365.

![Архивативная работа для данных взрывания с 17a-4](../media/FuzeDataParserConnectorWorkflow.png)

1. Ваша организация работает с 17a-4 для настройки и настройки fuze DataParser.

2. На регулярной основе элементы взрыватель собираются dataParser. DataParser также преобразует содержимое сообщения в формат сообщения электронной почты.

3. Соединителю Fuze DataParser, который вы создаете в Центр соответствия требованиям Microsoft 365, подключается к DataParser и передает сообщения в безопасное служба хранилища Azure в облаке Майкрософт.

4. В почтовых ящиках пользователей создается подмостки в папке "Входящие" с именем **Fuze DataParser,** и элементы взрыватель импортируется в эту папку. Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.* Каждый элемент fuze содержит это свойство, которое заполняется адресом электронной почты каждого участника.

## <a name="before-you-set-up-a-connector"></a>Перед настройками соединитетеля

- Создайте учетную запись DataParser для соединители Microsoft. Для этого обратитесь в [ООО "17a-4".](https://www.17a-4.com/contact/) При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.

- Пользователь, создавший соединителю Fuze DataParser в шаге 1 (и завершавший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online. Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365. По умолчанию эта роль не назначена группе ролей в Exchange Online. Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online. Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников. Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".

## <a name="step-1-set-up-a-fuze-dataparser-connector"></a>Шаг 1. Настройка соединиттеля Fuze DataParser

Первым шагом является доступ к странице соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединителя 17a-4 для данных Fuze.

1. Перейдите к соединителю данных и нажмите кнопку <https://compliance.microsoft.com>   >  **Fuze DataParser**.

2. На странице **описания продукта Fuze DataParser** нажмите **кнопку Добавить соединителю**.

3. На странице **Условия службы нажмите** кнопку **Принять**.

4. Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.

5. Вопишите в свою учетную запись 17a-4 и выполните действия в мастере подключения Fuze DataParser.

## <a name="step-2-configure-the-fuze-dataparser-connector"></a>Шаг 2. Настройка соединиттеля Fuze DataParser

Работа с поддержкой 17a-4 для настройки соединиттеля Fuze DataParser.

## <a name="step-3-map-users"></a>Шаг 3. Пользователи карт

Соединиттель Fuze DataParser автоматически соединит пользователей с Microsoft 365 адресами электронной почты перед импортом данных в Microsoft 365.

## <a name="step-4-monitor-the-fuze-dataparser-connector"></a>Шаг 4. Мониторинг соединиттеля Fuze DataParser

После создания соединиттеля Fuze DataParser можно просмотреть состояние соединителю в Центр соответствия требованиям Microsoft 365.

1. Перейдите <https://compliance.microsoft.com> и щелкните **соединители данных** в левом nav.

2. Щелкните  вкладку Соединители, а затем выберите соединителю Fuze DataParser, созданный для отображения страницы вылетов, которая содержит свойства и сведения о соединителе.

3. В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля. В этом журнале содержатся данные, импортируемые в облако Майкрософт.

## <a name="known-issues"></a>Известные проблемы

В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ. Поддержка более крупных элементов будет доступна позднее.
