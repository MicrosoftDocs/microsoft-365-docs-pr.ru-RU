---
title: Отмена назначения лицензий пользователям
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Метод, который используется для ненамеряния лицензий на продукты, зависит от того, вы отозвале лицензии у определенных пользователей или от конкретного продукта.
ms.date: 07/01/2020
ms.openlocfilehash: f79ffecc22fe4531076ccacd83c25e44b81052a6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53006977"
---
# <a name="unassign-licenses-from-users"></a>Отмена назначения лицензий пользователям

Лицензии можно отогнать от пользователей на странице **Активные** пользователи или на странице **Лицензии.** Метод, который вы используете, зависит от того, хотите ли вы отогнать лицензии на продукт от определенных пользователей или отогнать лицензии пользователей от конкретного продукта.

> [!NOTE]
> В качестве администратора вы не можете назначить лицензии или отменить их назначение для подписок, самостоятельно приобретенных пользователем в организации. Вы можете [получить контроль над самостоятельно приобретенной подпиской](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), а затем назначить лицензии или отменить их назначение.

## <a name="before-you-begin"></a>Прежде чем начать

- Чтобы отогнать лицензии, необходимо быть администратором глобальной лицензии, лицензии и пользователя. Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).
- Вы можете [удалить лицензии из учетных записей пользователей с помощью Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- Вы также можете [удалить учетные записи пользователей,](../add-users/delete-a-user.md) которые были назначены лицензии, чтобы сделать их лицензию доступной для других пользователей. При удалении учетной записи пользователя их лицензия сразу же доступна для назначения другому пользователю.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Использование страницы Лицензии для ненамеряния лицензий

При использовании страницы **Лицензии** для отозвал лицензии, вы отозвал лицензии для определенного продукта для до 20 пользователей.

::: moniker range="o365-worldwide"

1. В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Лицензии</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. В Центре администрирования выберите **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Лицензии</a>.

::: moniker-end

2. Выберите продукт, для которого необходимо отогнать лицензии.
3. Выберите пользователей, для которых необходимо отогнать лицензии.
4. Выберите **лицензии unassign**.
5. В поле **Unassign licenses** выберите **Unassign**.

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Используйте страницу Активные пользователи для ненамеряния лицензий

Если вы используете **страницу Активные** пользователи для ненамеряния лицензий, вы не передаете лицензии на продукты от пользователей.

### <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

::: moniker-end

2. Выберите строку пользователя, для чего необходимо отогнать лицензию.
3. В области справа выберите **Лицензии и приложения**.
4. **Расширите раздел Лицензии,** очистите поля для лицензий, которые необходимо отостановить, а затем выберите **Сохранить изменения.**

### <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

::: moniker-end

2. Выберите круги рядом с именами пользователей, для которых необходимо отогнать лицензии.
3. В верхней части выберите **Управление лицензиями на продукты.**
4. В области **Управление лицензиями продуктов** выберите **Unassign все изменения**  >  **Сохранить.**
5. В нижней части области выберите **Готово**.  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Что происходит с данными пользователя при удале лицензии?

- При удалении лицензии у пользователя Exchange данные, связанные с этой учетной записью, в течение 30 дней. После 30-дневного льготного периода данные удаляются и не могут быть восстановлены.
- Файлы, сохраненные в OneDrive для бизнеса, не удаляются, если пользователь не удаляется из Центр администрирования Microsoft 365 или удаляется с помощью синхронизации Active Directory. Дополнительные сведения см. [в OneDrive хранения и удаления.](/onedrive/retention-and-deletion)
- При удалении лицензии почтовый ящик пользователя больше не будет искаться с помощью средства поиска электронных данных, например поиска контента или Advanced eDiscovery. Дополнительные сведения см. в материалах "Поиск отключенных или от лицензированных почтовых ящиков" в области поиска контента [в Microsoft 365.](../../compliance/content-search.md)
- Если у Enterprise подписка, например Office 365 корпоративный E3, Exchange Online позволяет сохранять данные почтовых ящиков удаленных учетных записей пользователей с помощью неактивных почтовых [ящиков.](../../compliance/inactive-mailboxes-in-office-365.md) Дополнительные сведения см. в [сообщении Create and manage inactive mailboxes in Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)
- Сведения о том, как заблокировать доступ пользователя к данным Microsoft 365 после удаления лицензии, а также как получить доступ к данным после этого, см. в этой записи [Remove a former employee.](../add-users/remove-former-employee.md)
- Если вы удалите лицензию пользователя и Office установлены приложения, [](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) они увидят ошибки без лицензии на продукт и активацию Office при использовании Office приложений.

## <a name="next-steps"></a>Дальнейшие действия

Если вы не собираетесь перенаходить неиспользование лицензий другим [](../../commerce/licenses/buy-licenses.md) [пользователям,](../../managed-desktop/get-started/assign-licenses.md)рассмотрите возможность удаления лицензий из подписки, чтобы не платить за больше лицензий, чем нужно.

## <a name="related-content"></a>См. также:

[Удаление лицензий из подписки](../../commerce/licenses/buy-licenses.md) (статья)\
[Назначение лицензий пользователям](assign-licenses-to-users.md) (статья)\
[Понимание подписок и лицензий в Microsoft 365 для бизнеса](../../commerce/licenses/subscriptions-and-licenses.md) (статья)
