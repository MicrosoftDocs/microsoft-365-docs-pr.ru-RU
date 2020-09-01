---
title: Закрепление приложений для запуска приложений пользователя
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Как глобальный администратор вы можете закрепить до трех приложений в средстве запуска приложений пользователей.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310879"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Закрепление приложений для запуска приложений пользователя

Вы можете использовать элементы управления на портале Azure Active Directory, чтобы закрепить до трех приложений в Office.com и средство запуска приложений для всех пользователей в Организации. Вы также можете упорядочивать группы приложений. Любое добавляемое приложение позже может быть откреплено пользователем в любое время. Чтобы закрепить приложение для пользователей, необходимо быть администратором облачного приложения или администратором приложения в Azure Active Directory или глобальным администратором в Office 365. Дополнительные сведения о ролях администратора можно найти [в статье роли администраторов в роли администраторов Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) и [в Microsoft 365](../add-users/about-admin-roles.md). 

Для получения дополнительных сведений о средстве запуска приложений и Office.com, ознакомьтесь со статьей " [Запуск приложений"](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) и ["обновления для Office.com и" — блог о средстве запуска приложений для Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) .

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Использование портала Azure Active Directory для закрепления приложений

1. Перейдите в центр администрирования Microsoft 365 по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. В левой панели навигации выберите **Показать все**, а затем в разделе **центр администрирования**выберите **Azure Active Directory**.
3. В **Azure Active Directory**выберите параметры пользователя для **корпоративных приложений**  >  **User settings**.
4. В разделе **Параметры Office 365** нажмите кнопку **Добавить приложение**.
5. Выберите приложения, которые нужно закрепить в средстве запуска приложений для пользователей, а затем нажмите кнопку **Добавить**.

:::image type="content" source="../../media/add-apps.png" alt-text="Параметры Microsoft 365 для закрепления приложений.":::

### <a name="pin-a-custom-app"></a>Закрепление настраиваемого приложения

> [!NOTE]
> Пользовательский интерфейс будет указывать на необходимость приобретения дополнительных лицензий Azure AD, чтобы использовать эту функцию. Дополнительные сведения см. в статье " [цены Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/)".

1. В **Azure Active Directory**в **Enterprise applications**  >  верхней части страницы " **все приложения** " выберите пункт Корпоративные приложения —**новое приложение** .
2. На странице " **Добавление приложения** " выберите **приложение, не являющееся галереей** , или **Создайте собственное приложение** , если вы используете ознакомительную версию Azure Active Directory. 
3. Введите имя приложения, а затем назначьте пользователя на вкладке **Пользователи и группы** .
4. Используйте вкладку **Свойства** , чтобы отправить значок для приложения.
5. Чтобы назначить URL-адрес приложению, на вкладке **единый вход** выберите элемент **связанный** и введите URL-адрес.
6. Выберите **Сохранить**.

## <a name="create-application-collections"></a>Создание коллекций приложений

Вы также можете создавать коллекции приложений для пользователей в Организации. Инструкции можно найти в разделе [Создание коллекций на портале "Мои приложения" на портале Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).