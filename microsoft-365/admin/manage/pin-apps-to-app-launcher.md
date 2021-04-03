---
title: Pin apps to your users' app launcher
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: В качестве глобального администратора вы можете прикрепить до трех приложений к запуску приложений пользователей.
ms.openlocfilehash: 786368f1236c7a86a6fbd0dd863ad0296cb65fac
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579270"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Pin apps to your users' app launcher

Вы можете использовать элементы управления на портале Azure Active Directory для закрепления трех приложений для Office.com и запуска приложений для всех пользователей в вашей организации. Можно также организовать группы приложений. Любое приложение, которое вы добавляете, может быть впоследствии открепить пользователем в любое время. Чтобы прикрепить приложение для пользователей, необходимо быть администратором облачных приложений или администратором приложений в Azure Active Directory или глобальным администратором в Office 365. Дополнительные сведения о роли администратора см. в видеоролике Роли администратора в [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) и роли администратора [в Microsoft 365.](../add-users/about-admin-roles.md) 

Дополнительные сведения о запуске и Office.com приложения см. в статье Meet [the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and updates to office.com и в статье Блог запуска приложения [Office 365.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Использование портала Azure Active Directory для пин-кода приложений

1. Перейдите в центр администрирования Microsoft 365 по <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> крайней .
2. В левом nav выберите **Показать все,** а в центрах **администрирования** выберите **Azure Active Directory.**
3. В **Azure Active Directory** выберите **параметры пользователя**  >  **корпоративных приложений.**
4. В разделе **Параметры Office 365** выберите **приложение Добавить**.
5. Выберите приложения, которые необходимо прикрепить к запуску приложений пользователей, а затем **добавьте**.

:::image type="content" source="../../media/add-apps.png" alt-text="Параметры Microsoft 365 для закрепления приложений.":::

### <a name="pin-a-custom-app"></a>Пин-код настраиваемой приложения

> [!NOTE]
> Пользовательский интерфейс указывает, нужно ли приобретать дополнительные лицензии Azure AD для использования этой функции. Дополнительные сведения см. в [расценки Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)

1. В **Azure Active Directory** выберите **корпоративные** приложения Новое приложение в верхней части страницы  >   Все **приложения.**
2. На странице **Добавление приложения** выберите приложение **Non-gallery** или **Создайте** собственное приложение, если вы находитесь в предварительной версии Azure Active Directory. 
3. Введите имя приложения и назначьте пользователю вкладку **"Пользователи и группы".**
4. Чтобы загрузить значок для приложения, используйте вкладку **Свойства.**
5. Чтобы назначить URL-адрес приложения на вкладке **"Единый вход",** выберите **Linked** и введите URL-адрес.
6. Выберите **Сохранить**.

## <a name="create-application-collections"></a>Создание коллекций приложений

Вы также можете создать коллекции приложений для пользователей в организации. Дополнительные инструкции [см. в инструкции по созданию коллекций на портале Мои приложения на портале Azure.](/azure/active-directory/manage-apps/access-panel-collections)