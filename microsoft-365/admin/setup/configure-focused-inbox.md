---
title: Настройка сортировки почты для всех пользователей в организации
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: 'Узнайте, как настроить сортировку почты для всех или отдельных пользователей организации. '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779933"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Настройка сортировки почты для всех пользователей в организации

  Если вы отвечаете за настройку работы электронной почты для всех сотрудников организации, эта статья для вас. В ней объясняется порядок ее настройки или выключения в пределах организации, а также здесь вы найдете [ответы на часто задаваемые вопросы](#faq-for-focused-inbox).  <br/> Если вы хотите выключить сортировку почты только для себя, см. статью [Выключение сортировки почты](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  
   
If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Включение и отключение сортировки почты в организации

Вы используете PowerShell для включения и выключения сортировки почты для всех пользователей в своей организации. Хотите, чтобы эта возможность была доступна в Центре администрирования Microsoft 365? Сообщите об этом нашей команде разработчиков. **[Проголосуйте здесь!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **Отключение сортировки почты**
  
The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients. 
  
1. [Подключитесь к Exchange Online с помощью удаленного сеанса PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
3. Запустите командлет **Get-OrganizationConfig**. 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. Найдите параметр **FocusedInboxOn**, чтобы узнать его текущее значение. 
    
    ![Ответ PowerShell о состоянии сортировки почты.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Чтобы отключить сортировку, запустите следующий командлет:
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. Запустите командлет **Get-OrganizationConfig** еще раз, и вы увидите, что параметр FocusedInboxOn имеет значение $false, то есть сортировка почты отключена. 
    
 **Включение сортировки почты**
  
- Чтобы включить сортировку, на шаге 5 описанной выше процедуры запустите следующий командлет:
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>Что увидят пользователи, когда я включу сортировку почты? 

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![Вид папки "Отсортированные" при первом открытии Outlook в Интернете.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![Изображение папки "Отсортированные", которая развернута для пользователей, после повторного открытия Outlook.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Включение и отключение сортировки почты для определенных пользователей

This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients. 
  
1. [Подключитесь к Exchange Online с помощью удаленного сеанса PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.
    
3. Запустите командлет **Get-FocusedInbox**, например: 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. Найдите параметр FocusedInboxOn, чтобы узнать его текущее значение.
    
    ![Ответ PowerShell о состоянии сортировки почты.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Запустите следующий командлет, чтобы отключить сортировку почты:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. ИЛИ запустите следующий командлет, чтобы включить сортировку почты:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Создание правила транспорта, которое выводит сообщения в представлении "Отсортированные" для всех пользователей, через пользовательский интерфейс

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.
    
2. Откройте раздел **Поток почты** \> **Правила**. Нажмите значок ![Добавить в EAC](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) и выберите пункт **Создать новое правило**. 
    
3. После создания правила нажмите **Сохранить**, чтобы запустить правило. 
    
    В примере на приведенном ниже рисунке все сообщения с отправителем "Отдел выплат" будут выводиться в представлении "Отсортированные".
    
    ![focusedinbox Payroll](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Создание правила транспорта для вывода сообщений в представление "Отсортированные" для всех пользователей с помощью PowerShell

1. [Подключитесь к Exchange Online с помощью удаленного сеанса PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).

3. Чтобы все сообщения, например, с отправителем "Отдел выплат" выводились в представлении "Отсортированные", выполните следующую команду.
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> В данном примере для параметров X-MS-Exchange-Organization-BypassFocusedInbox и true учитывается регистр.
> Итак, функция сортировки почты будет учитывать X-заголовок, обходящий папку несрочных сообщений, поэтому если вы используете эту настройку в папке "Несрочные", она будет использоваться при сортировке. Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).

### <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться в том, что правило транспорта "Сортировка" применяется к сообщениям, проверьте их заголовки. Выберите сообщение из почтового ящика в вашей организации, к которому применяется правило транспорта "Сортировка". Просмотрите его заголовок: в нем должно быть указано **X-MS-Exchange-Organization-BypassFocusedInbox: true**. Это значит, что обход работает. Дополнительные сведения о том, как найти данные в заголовке, см. в статье [Просмотр сведений заголовка Интернета для сообщения электронной почты](https://go.microsoft.com/fwlink/p/?LinkId=822530). 
 
## <a name="turn-onoff-clutter"></a>Включение и отключение функции "Несрочные"
 
We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>Сортировка почты: вопросы и ответы

Ниже приведены ответы на часто задаваемые вопросы о сортировке почты. 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Можно ли управлять развертыванием функции "Сортировка почты" в организации?

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>Функция сортировки почты доступна только пользователям Office 2016?

Да. Функция действует только для пользователей Office 2016. Ее применение в Outlook 2013 и более ранних версиях не предусмотрено.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Когда изменения в настройке сортировки почты отобразятся в Outlook?

Чтобы изменения вступили в силу после включения или отключения сортировки почты, пользователям нужно закрыть и снова запустить Outlook.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>Что произойдет с папкой "Несрочные" после включения сортировки почты?

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
Ознакомьтесь со статьей Тони Редмонда ([Tony Redmond](https://www.petri.com/author/tony-redmond)), специалиста со статусом Microsoft MVP: [Как сортировка почты заменяет функцию "Несрочные" в Office 365](https://www.petri.com/focused-inbox-office-365) (на английском языке).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>Можно ли оставить пользователям функцию "Несрочные"? Что рекомендует Майкрософт при выборе между функцией "Несрочные" и сортировкой почты?

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>Нужно ли мне отключить функцию "Несрочные" для конечных пользователей, если мы собираемся перевести их всех на сортировку почты?

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Почему для управления сортировкой используются два разных командлета?

Состояние сортировки почты определяется на двух уровнях:
  
- **Уровень организации**: состояние сортировки и метка времени его последнего обновления. 
    
- **Уровень почтового ящика**: состояние сортировки и метка времени его последнего обновления. 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Как эти два состояния учитываются в Outlook при отображении представления "Отсортированные"?

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Почему командлет Get-FocusedInbox возвращает значение true, хотя сортировка для организации выключена?

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>Можно ли запустить сценарий, чтобы узнать, кто включил сортировку почты?

No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.
