---
title: Понимание подписок и лицензий в Microsoft 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Узнайте о подписках и лицензиях в Microsoft 365 для бизнеса.
ms.date: 07/01/2020
ms.openlocfilehash: a8ec5b0716a5ceaa02526520e76dc390a6fba0f7
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331494"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Понимание подписок и лицензий в Microsoft 365 для бизнеса

Когда вы покупаете подписку на Microsoft 365 для бизнеса, вы подписывались на набор приложений и служб, за которые вы платите ежемесячно или ежегодно. Приложения и службы, которые вы получаете в рамках подписки, зависят от того, какой продукт вы приобрели, например Microsoft 365 Apps для бизнеса или Microsoft 365 Business Standard. На странице [Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) для малого и среднего бизнеса можно увидеть, что происходит с каждым продуктом.

При этом вы можете указать количество лицензий, соответствующее числу пользователей в организации. После покупки подписки создайте учетные записи для людей в организации, а затем назначите лицензию каждому человеку. По мере изменения организационных потребностей можно приобрести дополнительные лицензии для размещения новых пользователей или перенаправление лицензий другим пользователям, когда кто-то покинет организацию.

Если у вас несколько подписок, вы можете назначать лицензии различным людям в каждой подписке. Например, вы можете назначить всех пользователей всем приложениям и службам Microsoft 365 в рамках подписки Microsoft 365 Business Standard. Вы также можете назначить подмножество пользователей Visio Online с помощью отдельной подписки Visio.

## <a name="how-many-devices-can-people-install-office-on"></a>На скольких устройствах можно установить Office?

Если подписка включает любой из следующих продуктов, каждый человек может установить Office на пять компьютеров или Mac, пять планшетов и пять телефонов.

:::row:::
   :::column span="":::
        - Microsoft 365 Приложения для бизнеса - Microsoft 365 Apps для предприятия - Microsoft 365 Бизнес Стандарт - Microsoft 365 Бизнес Премиум - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Что происходит при назначении лицензии кому-либо?

При назначении пользователю лицензии автоматически выполняются действия, приведенные в таблице ниже.
  
|**Если в подписке есть эта служба**|**Автоматическое действие**|
|:-----|:-----|
|Exchange Online  <br/> |Для пользователя создается почтовый ящик. <br/> Чтобы узнать о SLA для завершения этой задачи, см. в статью ["Настройка...". сообщения в центре администрирования Microsoft 365](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online  <br/> |Назначаются разрешения на изменение стандартного сайта группы SharePoint Online.  <br/> |
|Skype для бизнеса online  <br/> |У человека есть доступ к функциям, связанным с лицензией.  <br/> |
|Приложения Microsoft 365 для предприятий  <br/> |Пользователи могут загружать приложения Office на пять компьютеров или компьютеров Mac, пять планшетов и пять смартфонов.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Лицензии для почтовых ящиков, не относящихся к пользователям

Назначать лицензии почтовым ящикам ресурсов, помещений и общим почтовым ящикам требуется только в том случае, если для них превышена квота хранилища, равная 50 гигабайтам (ГБ). Дополнительные сведения о почтовых ящиках, не связанных с пользователями, см. в приведенных ниже статьях.
  
- [Создание общего почтового ящика](../../admin/email/create-a-shared-mailbox.md)
- [Удаление лицензии из общего почтового ящика](../../admin/email/remove-license-from-shared-mailbox.md)
- [Общие почтовые ящики в Exchange Online](/exchange/collaboration-exo/shared-mailboxes) для всех остальных планов Microsoft 365.
- [Создание почтовых ящиков помещения и управление ими](/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Управление почтовыми ящиками оборудования](/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Кто может назначать лицензии?

Возможности работы с лицензиями, доступные администраторам, зависят от их ролей. Наиболее распространенные варианты указаны в приведенной ниже таблице. Полный список ролей и привилегий администраторов см. в статье [Роли администраторов в Office 365](../../admin/add-users/about-admin-roles.md).
  
|**Роль администратора**|**Назначение лицензии**|**Отогнать лицензию**|**Покупка дополнительных лицензий**|**Удаление учетной записи**|
|:-----|:-----|:-----|:-----|:-----|
|Администратор выставления счетов  <br/> |Нет  <br/> |Нет  <br/> |Да  <br/> |Нет  <br/> |
|Глобальный администратор  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Администратор лицензий <br/> |Да <br/>|Да <br/> |Нет <br/> |Нет <br/> |
|Администратор поддержки служб  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Администратор пользователей  <br/> |Да  <br/> |Да  <br/> |Нет  <br/> |Да  <br/> |

## <a name="related-content"></a>Связанные материалы

[Покупка или удаление лицензий для подписки](buy-licenses.md) на бизнес (статья)\
[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья)\
[Отмена назначения лицензий пользователям](../../admin/manage/remove-licenses-from-users.md) (статья)\
[Удаление лицензии из общего почтового ящика](../../admin/email/remove-license-from-shared-mailbox.md) (статья)
