---
title: Отмена назначения лицензий пользователям
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Узнайте, как отоименовать лицензии из учетных записей пользователей.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114481"
---
# <a name="unassign-licenses-from-users"></a>Отмена назначения лицензий пользователям

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

::: moniker range="o365-worldwide"

Вы можете отоименовать лицензии у пользователей на странице **"Активные** пользователи" или на странице **"Лицензии".** Способ, который вы используете, зависит от того, хотите ли вы оторовать лицензии на продукт у определенных пользователей или отоименовть лицензии пользователей для определенного продукта.

::: moniker-end

## <a name="before-you-begin"></a>Прежде чем начать

- Для отзыва лицензий необходимо быть глобальным администратором, администратором лицензий, администратором пользователей. Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).
- Вы можете [удалить лицензии из учетных записей пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- Вы также можете [удалить учетные](../add-users/delete-a-user.md) записи пользователей, которые были назначены лицензией, чтобы сделать их лицензии доступными для других пользователей. При удалении учетной записи пользователя его лицензия сразу же доступна для назначения другому пользователю.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Использование страницы "Лицензии" для отзыва лицензий

При использовании страницы **"Лицензии"** для отзыва лицензий вы отзываете лицензии на определенный продукт для 20 пользователей.

1. В Центре администрирования выберите **Выставление счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Лицензии</a>.
2. Выберите продукт, для которого нужно отоименовать лицензии.
3. Выберите пользователей, для которых нужно отоименовать лицензии.
4. Выберите **"Отоименуть лицензии".**
5. В поле **"Отоименуем лицензии"** выберите **"Отоименование".**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Использование страницы "Активные пользователи" для отзыва лицензий

При использовании страницы **"Активные пользователи"** для отзыва лицензий лицензии на продукты от пользователей будут отозшены.

### <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user
  
1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.
2. Выберите строку пользователя, для который нужно отоименовать лицензию.
3. В области справа выберите **Лицензии и приложения**.
4. **Разоберите раздел** "Лицензии", уберите флажки для лицензий, которые нужно отоименовать, а затем выберите "Сохранить **изменения".**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.
2. Выберите пользователя, для который вы хотите отоименовать лицензию.
3. Справа в строке **"Лицензии на** продукты" выберите "Изменить". 
4. В области **"Лицензии** на продукты" переключите переключатель в положение "Выкл." для лицензии, которая будет отознана пользователю.  Например, если вы отключите лицензию Office 365 корпоративный E3, она отключит эту лицензию и все службы по этой лицензии для этого пользователя.
5. В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.
2. Выберите пользователя, для который вы хотите отоименовать лицензию.
3. Справа в строке **"Лицензии на** продукты" выберите "Изменить". 
4. В области **"Лицензии** на продукты" переключите переключатель в положение "Выкл." для лицензии, которая будет отознана пользователю.  Например, если вы отключите лицензию Office 365 корпоративный E3, она отключит эту лицензию и все службы по этой лицензии для этого пользователя.
5. В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.
2. Выберите круги рядом с именами пользователей, для которых нужно отоименовать лицензии.
3. Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.
4. В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.
5. At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.
2. Выберите поля рядом с именами пользователей, для которых нужно отоименовать все лицензии.
3. В области **Массовые действия** выберите **Изменить лицензии продуктов**.
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
5. At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users
  
1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.
2. Выберите поля рядом с именами пользователей, для которых нужно отоименовать все лицензии.
3. В области **Массовые действия** выберите **Изменить лицензии продуктов**.
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
5. At the bottom of the **Replace existing products** pane, select the Remove all product **licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Что происходит с данными пользователя при удалите его лицензию?

- При удалении лицензии у пользователя данные, связанные с этой учетной записью, удерживаются в течение 30 дней. После 30-дневного льготного периода данные удаляются и не могут быть восстановлены.
- Файлы, сохраненные в OneDrive для бизнеса, не удаляются, если пользователь не удален из Центра администрирования Microsoft 365 или не удален с помощью синхронизации Active Directory. Дополнительные сведения [см. в сведениях о хранении и удалении OneDrive.](https://docs.microsoft.com/onedrive/retention-and-deletion)
- При удалении лицензии поиск в почтовом ящике пользователя перестает быть поиском с помощью средства eDiscovery, такого как "Поиск контента" или "Advanced eDiscovery". Дополнительные сведения см. в подключении "Поиск в отключенных или отключенных почтовых ящиках" в поиске контента [в Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)
- Если у вас есть корпоративная подписка, например Office 365 корпоративный E3, Exchange Online позволяет сохранять данные почтового ящика удаленной учетной записи пользователя с помощью неактивных почтовых [ящиков.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) Дополнительные сведения см. в [теме "Создание неактивных](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)почтовых ящиков в Exchange Online" и управление ими.
- Сведения о блокировке доступа пользователя к данным Microsoft 365 после удаления лицензии, а также о том, как получить доступ к этим данным после удаления, см. в записи "Удаление бывшего [сотрудника".](../add-users/remove-former-employee.md)
- Если вы удалите лицензию пользователя и у него по-прежнему будут установлены приложения Office, то при использовании приложений Office в [Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) будут отсут уже нелицензироваться продукты и ошибки активации.

## <a name="next-steps"></a>Дальнейшие действия

Если вы не собираетесь переначивать неиспользование лицензий другим [](../../commerce/licenses/buy-licenses.md) [пользователям,](../../managed-desktop/get-started/assign-licenses.md)рассмотрите возможность удаления лицензий из подписки, чтобы не платить за дополнительные лицензии, чем нужно.

## <a name="related-content"></a>Связанные материалы

[Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md) (статья)\
[Назначение лицензий пользователям](assign-licenses-to-users.md) (статья)\
[Подписки и лицензии в Microsoft 365 для бизнеса](../../commerce/licenses/subscriptions-and-licenses.md) (статья)