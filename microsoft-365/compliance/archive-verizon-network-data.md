---
title: Настройка соединителя для архивации данных сети Веризон в Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Администраторы могут настроить соединитель сообщений для импорта и сохранения данных SMS и MMS из сети Веризон в Microsoft 365. Это позволяет архивировать данные из сторонних источников данных в Microsoft 365, чтобы можно было использовать такие функции обеспечения соответствия, как юридическая служба, поиск контента и политики хранения для управления сторонними данными Организации.
ms.openlocfilehash: 1acc6f7c189d1ce48999e033b744e538a1e20275
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "46601940"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data-preview"></a>Настройка соединителя для архивации данных сети Веризон (Предварительная версия)

Используйте соединитель для обмена сообщениями в центре соответствия требованиям Microsoft 365, чтобы импортировать и архивировать данные службы обмена мгновенными сообщениями (SMS) и службы обмена мультимедийными сообщениями (MMS) из сети Веризон. После настройки и настройки соединителя он подключается к сети Веризон в организации каждый день и импортирует SMS и MMS данные в почтовые ящики в Microsoft 365.

После хранения данных сетевого соединителя Веризон в почтовых ящиках пользователей можно применить такие функции обеспечения соответствия требованиям Microsoft 365, как хранение для судебного разбирательства, поиск контента и политики хранения Microsoft 365, в данные Веризон. Например, вы можете выполнить поиск в Веризон SMS и MMS, используя поиск контента, или сопоставить почтовый ящик, содержащий данные сети Веризон, с хранитель в расширенном случае обнаружения электронных данных. Использование сетевого соединителя Веризон для импорта и архивирования данных в Microsoft 365 поможет обеспечить соответствие организации политикам государственных учреждений и нормативным требованиям.

## <a name="overview-of-archiving-verizon-network-data"></a>Обзор архивации данных сети Веризон

В следующем обзоре описывается процесс использования соединителя для архивации данных сети Веризон в Microsoft 365.

![Рабочий процесс архивации Веризон сети](../media/VerizonNetworkConnectorWorkflow.png)

1. Ваша организация работает с сообщениями и Веризон для настройки сетевого соединителя Веризон. Дополнительные сведения можно найти в статье [Веризон Network WinRAR](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/).

2. Каждые 24 часа SMS-сообщения и MMS-сообщения из сети Веризон вашей организации копируются на сайт для обмена сообщениями.

3. Сетевой соединитель Веризон, который вы создаете в центре соответствия требованиям Microsoft 365, подключается к сайту сообщений каждый день и передает SMS-и MMS-сообщения из предыдущих 24 часов в безопасное место хранения Azure в облаке Майкрософт. Соединитель также Преобразовывает содержимое SMS и MMS сообщения в формат сообщения электронной почты.

4. Соединитель импортирует элементы мобильного взаимодействия в почтовый ящик определенного пользователя. В почтовом ящике конкретного пользователя создается новая папка с именем **ВЕРИЗОН SMS/MMS WinRAR** , в которую будут импортированы элементы. Соединитель выполняет это сопоставление, используя значение свойства *электронного адреса пользователя* . Каждое сообщение SMS и MMS содержит это свойство, которое заполняется адресом электронной почты каждого участника сообщения.

   В дополнение к автоматическому сопоставлению пользователей с использованием значения свойства *электронного адреса пользователя* , можно также реализовать настраиваемое сопоставление путем отправки CSV-файла сопоставления. Этот файл сопоставления содержит номер мобильного телефона и соответствующий адрес электронной почты Microsoft 365 для пользователей в вашей организации. Если вы включаете автоматическое сопоставление пользователей и настраиваемое сопоставление, для каждого элемента Веризон соединительный код сначала выполняет поиск по пользовательскому файлу сопоставления. Если не удается найти действительного пользователя Microsoft 365, который соответствует номеру мобильного телефона пользователя, соединитель будет использовать значения в свойстве адрес электронной почты элемента, который он пытается импортировать. Если соединитель не находит действительных пользователей Microsoft 365 в файле настраиваемого сопоставления или в свойстве адреса электронной почты элемента Веризон, элемент не импортируется.

## <a name="before-you-begin"></a>Прежде чем начать

Многие этапы реализации, необходимые для архивации сетевых данных Веризон, являются внешними по отношению к Microsoft 365 и должны быть завершены, прежде чем можно будет создать соединитель в центре соответствия требованиям.

- Закажите [службу Веризон Network WinRAR из сообщения](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) и получите допустимую учетную запись администрирования для Организации. Вам потребуется войти в эту учетную запись, когда вы создадите соединитель в центре соответствия требованиям.

- Получите свою сетевую учетную запись Веризон и сведения о контактах для выставления счетов, чтобы можно было заполнить формы входящей миграции и упорядочить службу архивации сообщений из Веризон.

- Зарегистрируйте всех пользователей, которым требуется Веризон SMS и MMS в учетной записи для обмена сообщениями. При регистрации пользователей необходимо использовать тот же адрес электронной почты, который используется для своей учетной записи Microsoft 365.

- Ваши сотрудники должны иметь корпоративные и корпоративные мобильные телефоны в сети Веризон Mobile. Архивация сообщений в Microsoft 365 недоступна для устройств, принадлежащих сотрудникам, или для собственных устройств (BYOD).

- Ваша организация должна разрешить службе импорта Office 365 доступ к данным почтовых ящиков в Организации. Вам потребуется предоставить это согласие при создании соединителя. Чтобы согласиться с этим запросом, перейдите на [эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), войдите с помощью учетных данных глобального администратора Office 365 и примите запрос. Необходимо выполнить это действие, прежде чем можно будет успешно создать сетевой соединитель Веризон.

- Пользователю, создающему сетевой соединитель Веризон, должна быть назначена роль импорта почтовых ящиков в Exchange Online. Это необходимо для добавления соединителей на странице " **соединители данных** " в центре соответствия требованиям Microsoft 365. По умолчанию эта роль не назначена ни одной группе ролей в Exchange Online. Вы можете добавить роль экспорта для импорта почтовых ящиков в группу ролей Управление организацией в Exchange Online. Вы также можете создать группу ролей, назначить роль импорта для импорта почтовых ящиков, а затем добавить соответствующих пользователей в качестве участников. Для получения дополнительных сведений обратитесь к разделу [Создание](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) групп ролей или [изменение групп ролей](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) статьи "Управление группами ролей в Exchange Online".

## <a name="create-a-verizon-network-connector"></a>Создание сетевого соединителя Веризон

После выполнения предварительных требований, описанных в предыдущем разделе, можно создать сетевой соединитель Веризон в центре соответствия требованиям Microsoft 365. Соединитель использует предоставленные сведения для подключения к сайту "Служба сообщений" и передачи SMS-и MMS-сообщений в соответствующие поля почтового ящика пользователя в Microsoft 365.

1. Перейдите к [https://compliance.microsoft.com](https://compliance.microsoft.com) пункту **соединители**  >  **Веризон Network**(соединители данных).

2. На странице "Описание **сетевого продукта Веризон** " нажмите кнопку **Добавить соединитель**

3. На странице **условия обслуживания** нажмите кнопку **принять**.

4. На странице " **Вход в систему** " в разделе Шаг 3 Введите необходимые сведения в следующие поля, а затем нажмите кнопку **Далее**.
  
   - **Имя пользователя:** Имя пользователя в вашем почтовом сообщении.

   - **Пароль:** Пароль к своему почтовому сообщению.

5. После создания соединителя можно закрыть всплывающее окно и перейти к следующей странице.

6. На странице **Сопоставление пользователей** включите автоматическое сопоставление пользователей и нажмите кнопку **Далее**. Если вам потребуется настраиваемое сопоставление, отправьте CSV-файл, а затем нажмите кнопку **Далее**.

7. Предоставьте согласие администратора и нажмите кнопку **Далее**.

   Чтобы предоставить согласие администратора, необходимо войти в систему, используя учетные данные глобального администратора Office 365, а затем принять запрос согласия. Если вы не вошли в систему как глобальный администратор, вы можете перейти на [эту страницу](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) и войти, используя учетные данные глобального администратора, чтобы принять запрос.

8. Проверьте параметры и нажмите кнопку **Готово** , чтобы создать соединитель.

9. Перейдите на вкладку Connectors (соединители) на странице **Data Connectors** (соединители), чтобы увидеть ход процесса импорта для нового соединителя.

## <a name="known-issues"></a>Известные проблемы

- Соединитель не импортирует элементы размером более 10 МБ.