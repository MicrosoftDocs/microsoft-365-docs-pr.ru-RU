---
title: Настройка соединитетеля для архивирования данных Zoom в Microsoft 365
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
description: Узнайте, как настроить и использовать соединиттель Zoom DataParser 17a-4 для импорта и архивирования данных Zoom в Microsoft 365.
ms.openlocfilehash: 1c70099efa17b5ff6c1c4dfcd71c6bf6790535c8
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453949"
---
# <a name="set-up-a-connector-to-archive-zoom-data"></a>Настройка соединитетеля для архивирования данных Zoom

Используйте [zoom DataParser](https://www.17a-4.com/dataparser/) от 17a-4 LLC для импорта и архивирования данных с платформы Zoom в почтовые ящики пользователей в Microsoft 365 организации. В dataParser включен соединиттель Zoom, настроенный для захвата элементов из стороннего источника данных и импорта этих элементов в Microsoft 365. Соединиттель Zoom DataParser преобразует масштабирование данных в формат сообщений электронной почты, а затем импортирует эти элементы в почтовые ящики пользователей в Microsoft 365.

После хранения данных Zoom в почтовых ящиках пользователей можно применить Microsoft 365, такие как хранение судебных разбирательств, открытие электронных данных, политики хранения и метки хранения, а также соответствие требованиям к связи. Использование соединиттеля Zoom для импорта и архивирования данных в Microsoft 365 может помочь вашей организации соблюдать государственные и нормативные политики.

## <a name="overview-of-archiving-zoom-data"></a>Обзор архивирования данных Zoom

В следующем обзоре объясняется процесс использования соединиттеля данных для архивации данных Zoom в Microsoft 365.

![Архивирование рабочего процесса для масштабирования данных с 17a-4](../media/ZoomDataParserConnectorWorkflow.png)

1. Ваша организация работает с 17a-4 для настройки и настройки масштабирования dataParser.

2. Регулярно элементы Zoom собираются в DataParser. DataParser также преобразует содержимое сообщения в формат сообщения электронной почты.

3. Соединиттель Zoom DataParser, который создается в Центр соответствия требованиям Microsoft 365 подключается к DataParser и передает сообщения в безопасное служба хранилища Azure в облаке Майкрософт.

4. В почтовых ящиках пользователя создается подмостка в папке "Входящие" с именем **Zoom DataParser,** и элементы Zoom импортируется в эту папку. Соединитатель определяет, в какой почтовый ящик импортировать элементы, используя значение свойства *Email.* Каждый элемент Zoom содержит это свойство, которое заполняется адресом электронной почты каждого участника.

## <a name="before-you-set-up-a-connector"></a>Перед настройками соединитетеля

- Создайте учетную запись DataParser для соединители Microsoft. Для этого обратитесь в [ООО "17a-4".](https://www.17a-4.com/contact/) При создании соединитетеля в шаге 1 необходимо войти в эту учетную запись.

- Пользователь, создававший соединиттель Zoom DataParser в шаге 1 (и завершавший его в шаге 3), должен быть назначен роли экспорта импорта почтовых ящиков в Exchange Online. Эта роль требуется для добавления соединители на странице **соединители** данных в Центр соответствия требованиям Microsoft 365. По умолчанию эта роль не назначена группе ролей в Exchange Online. Вы можете добавить роль экспорта импорта почтовых ящиков в группу ролей управления организацией в Exchange Online. Или вы можете создать группу ролей, назначить роль экспортировать импорт почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников. Дополнительные сведения см. в разделах [Создание](/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение](/Exchange/permissions-exo/role-groups#modify-role-groups) групп ролей в статье "Управление группами ролей в Exchange Online".

## <a name="step-1-set-up-a-zoom-dataparser-connector"></a>Шаг 1. Настройка соединиттеля Zoom DataParser

Первым шагом является доступ к странице соединители данных в Центр соответствия требованиям Microsoft 365 и создание соединителя 17a-4 для масштабирования данных.

1. Перейдите к соединитетелям данных и нажмите кнопку <https://compliance.microsoft.com>   >  **Масштабирование dataParser**.

2. На странице **Описание продукта Zoom DataParser** нажмите **кнопку Добавить соединителю**.

3. На странице **Условия службы нажмите** кнопку **Принять**.

4. Введите уникальное имя, которое идентифицирует соединителен, а затем нажмите **кнопку Далее**.

5. Вопишите в свою учетную запись 17a-4 и выполните действия мастера подключения Zoom DataParser.

## <a name="step-2-configure-the-zoom-dataparser-connector"></a>Шаг 2. Настройка соединиттеля Zoom DataParser

Работа с поддержкой 17a-4 для настройки соединиттеля Zoom DataParser.

## <a name="step-3-map-users"></a>Шаг 3. Пользователи карт

Соединиттель Zoom DataParser автоматически соединит пользователей с Microsoft 365 адресами электронной почты перед импортом данных Microsoft 365.

## <a name="step-4-monitor-the-zoom-dataparser-connector"></a>Шаг 4. Мониторинг соединиттеля Zoom DataParser

После создания соединиттеля Zoom DataParser можно просмотреть состояние соединитетеля в Центр соответствия требованиям Microsoft 365.

1. Перейдите <https://compliance.microsoft.com> и щелкните **соединители данных** в левом nav.

2. Щелкните  вкладку Соединители, а затем выберите разъем Zoom DataParser, созданный для отображения страницы вылетов, которая содержит свойства и сведения о соединителе.

3. В **состоянии Соединитель с исходным кодом** щелкните ссылку **Журнал** загрузки, чтобы открыть (или сохранить) журнал состояния соединитетеля. В этом журнале содержатся данные, импортируемые в облако Майкрософт.

## <a name="known-issues"></a>Известные проблемы

В настоящее время мы не поддерживаем импорт вложений или элементов размером более 10 МБ. Поддержка более крупных элементов будет доступна позднее.
