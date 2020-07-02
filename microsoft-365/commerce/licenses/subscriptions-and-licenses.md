---
title: Общие сведения о подписках и лицензиях в Microsoft 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Сведения о подписках и лицензиях в Microsoft 365 для бизнеса.
ms.date: 07/01/2020
ms.openlocfilehash: 9f8576b00b942c4b38d6192770bd2128afb4b104
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015963"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Общие сведения о подписках и лицензиях в Microsoft 365 для бизнеса

Если вы приобретаете подписку на Microsoft 365 для бизнеса, вы подписываетесь на набор приложений и служб, которые оплачиваются ежемесячно или ежегодно. Приложения и службы, которые вы получаете в рамках вашей подписки, зависят от того, какой продукт вы приобрели, например Microsoft 365 Apps для бизнеса или Microsoft 365 Business Standard. Вы можете узнать, что поставляется с каждым продуктом на странице [Microsoft 365 для малых и средних предприятий](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) .

При этом вы можете указать количество лицензий, соответствующее числу пользователей в организации. После приобретения подписки необходимо создать учетные записи для людей в Организации, а затем назначить им лицензию. При необходимости изменения в Организации можно приобрести дополнительные лицензии для новых людей или переназначить лицензии другим пользователям, когда кто-то покидает свою организацию.

Если у вас несколько подписок, вы можете назначать лицензии различным людям в каждой подписке. Например, вы можете назначить всех пользователей всем приложениям и службам Microsoft 365 в рамках стандартной подписки Microsoft 365 бизнес. Вы также можете назначить для Visio Online подмножество пользователей с помощью отдельной подписки Visio.

## <a name="how-many-devices-can-people-install-office-on"></a>На скольких устройствах можно установить Office?

Если ваша подписка включает любой из следующих продуктов, каждый пользователь может установить Office на пяти ПК или Mac, пяти планшетах и пяти телефонах.

:::row:::
   :::column span="":::
        -Приложения Майкрософт 365 для бизнеса — приложения Майкрософт 365 для предприятий — Майкрософт 365 бизнес Standard — Microsoft 365 Бизнес Premium — Microsoft 365 a3 — Майкрософт 365 A5
   :::column-end:::
   :::column span="":::
        — Microsoft 365 E3 — Microsoft 365 3 – Office 365 a1 и Office 365 a3 — Office 365 A5 — Office 365 E3 — Office 365
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Что происходит при назначении лицензии пользователю?

При назначении пользователю лицензии автоматически выполняются действия, приведенные в таблице ниже.
  
|**Если в подписке есть эта служба**|**Автоматическое действие**|
|:-----|:-----|
|Exchange Online  <br/> |Для пользователя создается почтовый ящик. <br/> Чтобы узнать о соглашении об уровне обслуживания для завершения этой задачи, ознакомьтесь со статьей ["Настройка..." сообщения в центре администрирования Microsoft 365](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online  <br/> |Назначаются разрешения на изменение стандартного сайта группы SharePoint Online.  <br/> |
|Skype для бизнеса online  <br/> |У пользователя есть доступ к функциям, связанным с лицензией.  <br/> |
|Приложения Microsoft 365 для предприятий  <br/> |Пользователь может скачать приложения Office на пяти компьютерах Макинтош или компьютерах, пяти планшетах и пяти смартфонах.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Лицензии для почтовых ящиков, не относящихся к пользователям

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Создание общего почтового ящика](../../admin/email/create-a-shared-mailbox.md)
- [Удаление лицензии из общего почтового ящика](../../admin/email/remove-license-from-shared-mailbox.md)
- [Общие почтовые ящики в Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes) для всех остальных планов Microsoft 365.
- [Создание почтовых ящиков помещения и управление ими](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Управление почтовыми ящиками оборудования](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Кто может назначать лицензии?

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**Роль администратора**|**Назначение лицензии**|**Отмена назначения лицензии**|**Приобретение дополнительных лицензий**|**Удаление учетной записи**|
|:-----|:-----|:-----|:-----|:-----|
|Администратор выставления счетов  <br/> |Нет  <br/> |Нет  <br/> |Да  <br/> |Нет  <br/> |
|Глобальный администратор  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Администратор лицензий <br/> |Да <br/>|Да <br/> |Нет <br/> |Нет <br/> |
|Администратор службы поддержки  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Администратор пользователей  <br/> |Да  <br/> |Да  <br/> |Нет  <br/> |Да  <br/> |

## <a name="related-content"></a>Связанные материалы

[Приобретение или удаление лицензий для вашей бизнес-подписки](buy-licenses.md) (статья) \
[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья) \
[Отмена назначения лицензий пользователям](../../admin/manage/remove-licenses-from-users.md) (статья) \
[Удаление лицензии из общего почтового ящика](../../admin/email/remove-license-from-shared-mailbox.md) (статья)