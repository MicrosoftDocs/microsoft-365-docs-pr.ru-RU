---
title: Закрытие учетной записи
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Узнайте, как закрыть учетную запись в Корпорации Майкрософт.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376321"
---
# <a name="close-your-account"></a>Закрытие учетной записи

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Когда вы закрываете свою учетную запись в Microsoft, вся информация, связанная с вашей учетной записью, удаляется. Эта информация включает в себя подписки, лицензии, способы оплаты, пользователей и пользовательские данные.

## <a name="before-you-begin"></a>Прежде чем начать

Перед началом этого процесса обязательно сделайте резервную копию любых данных, которые вы хотите сохранить.

Для выполнения задач в этой статье необходимо быть глобальным администратором или администратором вы выставления счета. Дополнительные сведения см. в статье [О ролях администраторов](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Шаг 1. Удаление пользователей

Удалите всех пользователей, кроме одного глобального администратора. Глобальный администратор завершает действия по закрытию учетной записи. Перед удалением каталога в конце этого процесса необходимо удалить всех остальных пользователей.

Если пользователи синхронизируются из локальной сети, сначала отключите синхронизацию, а затем удалите пользователей в облачном каталоге с помощью портала Azure или с помощью cmdlets Azure PowerShell.

Чтобы удалить пользователей, см. <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">"Администратор управления пользователями: удаление одного или более пользователей"</a>

Для массового удаления пользователей можно также использовать <a href="https://go.microsoft.com/fwlink/?linkid=842230">msolUser</a> PowerShell.

Если ваша организация использует Active Directory, синхронизируются с Microsoft Azure Active Directory (Azure AD), удалите учетную запись пользователя из Active Directory. Инструкции см. в <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">подсети "Массовое удаление пользователей в Azure Active Directory".</a>

## <a name="step-2-cancel-all-active-subscriptions"></a>Шаг 2. Отмена всех активных подписок

1. В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.
2. На **вкладке** "Продукты" найдите активную подписку. Нажмите **Дополнительные действия** (три точки) и выберите **Отменить подписку**.
3. В области **Отмена подписки** выберите причину, по которой вы отменяете подписку. Вы можете предоставить отзыв.
4. Нажмите **Сохранить**.
5. Повторите шаги 1-4, чтобы отменить все активные подписки.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Шаг 3. Удаление всех отключенных подписок

1. В Центре администрирования перейдите на страницу **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.
2. На **вкладке** "Продукты" выберите отключенную подписку.
3. На странице сведений о подписке в **разделе** "Параметры подписки и оплаты" выберите **"Удалить подписку".**
4. В области **"Удаление подписки"** выберите **"Удалить подписку".**
5. В **диалоговом окне** "Удаление подписки" выберите **"Да".**
6. Для каждой отключенной подписки повторите шаги 3–5, пока не будут удалены все подписки.

> [!NOTE]
> Если вы не можете сразу удалить отключенную подписку, обратитесь <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">в службу поддержки</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Шаг 4. Отключение многофакторной проверки подлинности

1. Во sign in to the admin center with a Global administrator account. Чтобы проверить, какие роли у вас есть, см. "Проверка ролей [администратора" в организации.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)
2. Перейдите на **страницу**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">"Активные пользователи".</a>
3. Выберите **многофакторную проверку подлинности.**
4. На странице многофакторной проверки подлинности отключать все учетные записи, кроме используемой учетной записи глобального администратора.

Вы также <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">можете использовать PowerShell, чтобы</a>отключить многофакторную проверку подлинности для нескольких пользователей.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Шаг 5. Удаление каталога в Azure Active Directory

1. Во sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.
2. Выберите **Azure Active Directory**.
3. Переключиться на организацию, которую нужно удалить.
4. Выберите **"Удалить клиент"**.
5. Если в организации не удается пройти одну или несколько проверок, вы увидите ссылку на дополнительные сведения о том, как их пройти. После выполнения всех проверок выберите **"Удалить",** чтобы завершить процесс.

После завершения этого заключительного шага ваша учетная запись в Майкрософт будет закрыта и удалена.