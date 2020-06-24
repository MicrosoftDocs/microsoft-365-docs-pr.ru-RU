---
title: Общие сведения о подписках и лицензиях в Microsoft 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: 'Сведения о подписках и лицензиях в Microsoft 365 для бизнеса, а также о том, кто может назначать лицензии и что происходит при назначении лицензии кому-либо. '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: f83b2069bd1b4c86e2198252a54ed2e8e5c55a04
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844684"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Общие сведения о подписках и лицензиях в Microsoft 365 для бизнеса

В этой статье объясняется связь между подписками и лицензиями и предоставляются дополнительные сведения о том [, кто может назначать лицензии](#find-out-who-can-assign-licenses), сведения о том, [что происходит при назначении лицензии другому пользователю](#understand-what-happens-when-you-assign-a-license-to-someone), а [также о количестве устройств, на которых пользователи могут устанавливать Office](#how-many-devices-can-people-install-office-on). Здесь также содержатся ссылки на [Общие сведения о лицензиях для почтовых ящиков, не являющихся пользователями](#understand-licenses-for-non-user-mailboxes), а также [статьи об управлении лицензиями](#articles-about-managing-licenses).
  
При покупке подписки на Microsoft 365 для бизнеса вы регистрируете набор приложений и служб, которые оплачиваются ежемесячно или ежегодно. Приложения и службы, которые вы получаете в рамках вашей подписки, зависят от того, какой продукт вы приобрели, например Microsoft 365 Apps для бизнеса или Microsoft 365 Business Standard. Сведения о том, что поставляется с каждым продуктом, можно узнать на [странице Покупка Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1). 

Вы можете просмотреть различные варианты лицензирования в [Microsoft 365 для малых и средних предприятий](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)

При этом вы можете указать количество лицензий, соответствующее числу пользователей в организации. После этого вы можете создать учетные записи для пользователей, а затем назначить лицензии каждому из них. При необходимости изменения в Организации можно приобрести дополнительные лицензии для новых людей или переназначить лицензии другим пользователям, когда кто-то покидает свою организацию. 

Если у вас несколько подписок, вы можете назначать лицензии различным людям в каждой подписке. Например, все пользователи могут быть назначены всем приложениям и службам Microsoft 365 как часть стандартной подписки на Microsoft 365 бизнес, а подмножество пользователей также можно назначить Visio Online с помощью отдельной подписки Visio. 

  
## <a name="find-out-who-can-assign-licenses"></a>Права администраторов на назначение лицензий

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**Роль администратора**|**Назначение лицензии**|**Удаление лицензии**|**Покупка новых лицензий**|**Удаление учетной записи**|
|:-----|:-----|:-----|:-----|:-----|
|Глобальный администратор  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Администратор выставления счетов  <br/> |Нет  <br/> |Нет  <br/> |Да  <br/> |Нет  <br/> |
|Администратор управления пользователями  <br/> |Да  <br/> |Да  <br/> |Нет  <br/> |Да  <br/> |
|Администратор служб  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Администратор паролей  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a>Что происходит при назначении лицензии пользователю

При назначении пользователю лицензии автоматически выполняются действия, приведенные в таблице ниже.
  
|**Если в подписке есть эта служба**|**Автоматическое действие**|
|:-----|:-----|
|Exchange Online  <br/> |Для пользователя создается почтовый ящик.  <br/> Чтобы узнать о соглашении об уровне обслуживания для завершения этой задачи, ознакомьтесь со статьей ["Настройка..." сообщения в центре администрирования Microsoft 365](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online  <br/> |Назначаются разрешения на изменение стандартного сайта группы SharePoint Online.  <br/> |
|Skype для бизнеса online  <br/> |Пользователь получает доступ к возможностям, связанным с лицензией.  <br/> |
|Приложения Microsoft 365 для предприятий  <br/> |Пользователь сможет скачать Microsoft Office для 5 ПК с Windows или компьютеров Mac, 5 планшетов и 5 смартфонов.  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a>На скольких устройствах можно установить Office?

Если ваша подписка включает один из перечисленных ниже продуктов, каждый пользователь может установить Office на 5 ПК с Windows или компьютерах Mac, 5 планшетах и 5 смартфонах.
  
- Приложения Microsoft 365 для бизнеса
    
- Microsoft 365 бизнес стандарт
    
- Приложения Microsoft 365 для предприятий
    
- Office 365 корпоративный E3
    
- Office 365 корпоративный E5
    
## <a name="understand-licenses-for-non-user-mailboxes"></a>Лицензии для почтовых ящиков, не относящихся к пользователям

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Создание общего почтового ящика](../../admin/email/create-a-shared-mailbox.md)
    
- [Общие почтовые ящики в Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) для всех остальных планов Microsoft 365. 
    
- [Создание почтовых ящиков помещения и управление ими](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [Управление почтовыми ящиками оборудования](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a>Статьи, посвященные управлению лицензиями

- [Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md)
    
- [Удаление лицензий у пользователей](../../admin/manage/remove-licenses-from-users.md)
    
- [Приобретение лицензий для подписки](buy-licenses.md)
    
- [Приобретение дополнительной подписки](../buy-another-subscription.md)
    
- [Покупка и изменение надстроек](../buy-or-edit-an-add-on.md)
    
- [Удаление лицензий из подписки](remove-licenses-from-subscription.md)
    
- [Устранение конфликтов лицензий](../../admin/manage/resolve-license-conflicts.md)
    
- [Управление пользовательскими лицензиями Yammer](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
