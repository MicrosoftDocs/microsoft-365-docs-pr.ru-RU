---
title: Подписки и лицензии в Microsoft 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Узнайте о подписках и лицензиях в Microsoft 365 для бизнеса.
ms.date: 07/01/2020
ms.openlocfilehash: ccfcb52548fb79267c550afba63c2f5a96b99ed1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928514"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Подписки и лицензии в Microsoft 365 для бизнеса

При покупке подписки на Microsoft 365 для бизнеса вы подписывались на набор приложений и служб, которые вы платите ежемесячно или ежегодно. Приложения и службы, которые вы получаете в рамках подписки, зависят от того, какой продукт вы приобрели, например приложения Microsoft 365 для бизнеса или Microsoft 365 бизнес стандарт. Что входит в каждый продукт, можно узнать на странице [Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) для малого и среднего бизнеса.

При этом вы можете указать количество лицензий, соответствующее числу пользователей в организации. После покупки подписки вы создаете учетные записи для пользователей в вашей организации, а затем назначаете лицензию каждому человеку. По мере изменения потребностей организации вы можете приобрести дополнительные лицензии для новых пользователей или перенаправление лицензий другим пользователям, когда кто-то уедет из вашей организации.

Если у вас несколько подписок, вы можете назначать лицензии различным людям в каждой подписке. Например, вы можете назначить всех пользователей всем приложениям и службам Microsoft 365 в рамках подписки Microsoft 365 бизнес стандартный. Вы также можете назначить подмножество пользователей Visio Online с помощью отдельной подписки На Visio.

## <a name="how-many-devices-can-people-install-office-on"></a>На скольких устройствах можно установить Office?

Если ваша подписка включает любой из следующих продуктов, каждый человек может установить Office на пяти ПК или Mac, пяти планшетах и пяти телефонах.

:::row:::
   :::column span="":::
        - Приложения Microsoft 365 для бизнеса - Приложения Microsoft 365 для предприятий - Microsoft 365 бизнес стандарт - Microsoft 365 бизнес премиум - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 — Microsoft 365 E5 — Office 365 A1 Plus — Office 365 A3 — Office 365 A5 — Office 365 E3 — Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Что происходит при назначении лицензии другому человеку?

При назначении пользователю лицензии автоматически выполняются действия, приведенные в таблице ниже.
  
|**Если в подписке есть эта служба**|**Автоматическое действие**|
|:-----|:-----|
|Exchange Online  <br/> |Для пользователя создается почтовый ящик. <br/> Чтобы узнать о SLA для завершения этой задачи, см. [статью "Настройка..." сообщения в Центре администрирования Microsoft 365.](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center) |
|SharePoint Online  <br/> |Назначаются разрешения на изменение стандартного сайта группы SharePoint Online.  <br/> |
|Skype для бизнеса online  <br/> |У человека есть доступ к функциям, связанным с лицензией.  <br/> |
|Приложения Microsoft 365 для предприятий  <br/> |Этот человек может скачать приложения Office на пяти mac или ПК, пяти планшетах и пяти смартфонах.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Лицензии для почтовых ящиков, не относящихся к пользователям

Назначать лицензии почтовым ящикам ресурсов, помещений и общим почтовым ящикам требуется только в том случае, если для них превышена квота хранилища, равная 50 гигабайтам (ГБ). Дополнительные сведения о почтовых ящиках, не связанных с пользователями, см. в приведенных ниже статьях.
  
- [Создание общего почтового ящика](../../admin/email/create-a-shared-mailbox.md)
- [Удаление лицензии из общего почтового ящика](../../admin/email/remove-license-from-shared-mailbox.md)
- [Общие почтовые ящики в Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes) для всех остальных планов Microsoft 365.
- [Создание почтовых ящиков помещения и управление ими](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Управление почтовыми ящиками оборудования](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Кто может назначать лицензии?

Возможности работы с лицензиями, доступные администраторам, зависят от их ролей. Наиболее распространенные варианты указаны в приведенной ниже таблице. Полный список ролей и привилегий администраторов см. в статье [Роли администраторов в Office 365](../../admin/add-users/about-admin-roles.md).
  
|**Роль администратора**|**Назначение лицензии**|**Unassign a license**|**Покупка дополнительных лицензий**|**Удаление учетной записи**|
|:-----|:-----|:-----|:-----|:-----|
|Администратор выставления счетов  <br/> |Нет  <br/> |Нет  <br/> |Да  <br/> |Нет  <br/> |
|Глобальный администратор  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Администратор лицензий <br/> |Да <br/>|Да <br/> |Нет <br/> |Нет <br/> |
|Администратор поддержки служб  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Администратор пользователей  <br/> |Да  <br/> |Да  <br/> |Нет  <br/> |Да  <br/> |

## <a name="related-content"></a>Связанные материалы

[Покупка и удаление лицензий для подписки для бизнеса](buy-licenses.md) (статья)\
[Назначение лицензий пользователям](../../admin/manage/assign-licenses-to-users.md) (статья)\
[Отмена назначения лицензий пользователям](../../admin/manage/remove-licenses-from-users.md) (статья)\
[Удаление лицензии из общего почтового ящика](../../admin/email/remove-license-from-shared-mailbox.md) (статья)