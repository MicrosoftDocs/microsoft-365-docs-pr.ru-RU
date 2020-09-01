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
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="1d52f-103">Закрепление приложений для запуска приложений пользователя</span><span class="sxs-lookup"><span data-stu-id="1d52f-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="1d52f-104">Вы можете использовать элементы управления на портале Azure Active Directory, чтобы закрепить до трех приложений в Office.com и средство запуска приложений для всех пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="1d52f-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="1d52f-105">Вы также можете упорядочивать группы приложений.</span><span class="sxs-lookup"><span data-stu-id="1d52f-105">You can also organize groups of applications.</span></span> <span data-ttu-id="1d52f-106">Любое добавляемое приложение позже может быть откреплено пользователем в любое время.</span><span class="sxs-lookup"><span data-stu-id="1d52f-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="1d52f-107">Чтобы закрепить приложение для пользователей, необходимо быть администратором облачного приложения или администратором приложения в Azure Active Directory или глобальным администратором в Office 365.</span><span class="sxs-lookup"><span data-stu-id="1d52f-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="1d52f-108">Дополнительные сведения о ролях администратора можно найти [в статье роли администраторов в роли администраторов Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) и [в Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1d52f-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="1d52f-109">Для получения дополнительных сведений о средстве запуска приложений и Office.com, ознакомьтесь со статьей " [Запуск приложений"](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) и ["обновления для Office.com и" — блог о средстве запуска приложений для Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) .</span><span class="sxs-lookup"><span data-stu-id="1d52f-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="1d52f-110">Использование портала Azure Active Directory для закрепления приложений</span><span class="sxs-lookup"><span data-stu-id="1d52f-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="1d52f-111">Перейдите в центр администрирования Microsoft 365 по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="1d52f-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="1d52f-112">В левой панели навигации выберите **Показать все**, а затем в разделе **центр администрирования**выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="1d52f-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="1d52f-113">В **Azure Active Directory**выберите параметры пользователя для **корпоративных приложений**  >  **User settings**.</span><span class="sxs-lookup"><span data-stu-id="1d52f-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="1d52f-114">В разделе **Параметры Office 365** нажмите кнопку **Добавить приложение**.</span><span class="sxs-lookup"><span data-stu-id="1d52f-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="1d52f-115">Выберите приложения, которые нужно закрепить в средстве запуска приложений для пользователей, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1d52f-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Параметры Microsoft 365 для закрепления приложений.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="1d52f-117">Закрепление настраиваемого приложения</span><span class="sxs-lookup"><span data-stu-id="1d52f-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="1d52f-118">Пользовательский интерфейс будет указывать на необходимость приобретения дополнительных лицензий Azure AD, чтобы использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="1d52f-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="1d52f-119">Дополнительные сведения см. в статье " [цены Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/)".</span><span class="sxs-lookup"><span data-stu-id="1d52f-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="1d52f-120">В **Azure Active Directory**в **Enterprise applications**  >  верхней части страницы " **все приложения** " выберите пункт Корпоративные приложения —**новое приложение** .</span><span class="sxs-lookup"><span data-stu-id="1d52f-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="1d52f-121">На странице " **Добавление приложения** " выберите **приложение, не являющееся галереей** , или **Создайте собственное приложение** , если вы используете ознакомительную версию Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d52f-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="1d52f-122">Введите имя приложения, а затем назначьте пользователя на вкладке **Пользователи и группы** .</span><span class="sxs-lookup"><span data-stu-id="1d52f-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="1d52f-123">Используйте вкладку **Свойства** , чтобы отправить значок для приложения.</span><span class="sxs-lookup"><span data-stu-id="1d52f-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="1d52f-124">Чтобы назначить URL-адрес приложению, на вкладке **единый вход** выберите элемент **связанный** и введите URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="1d52f-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="1d52f-125">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1d52f-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="1d52f-126">Создание коллекций приложений</span><span class="sxs-lookup"><span data-stu-id="1d52f-126">Create application collections</span></span>

<span data-ttu-id="1d52f-127">Вы также можете создавать коллекции приложений для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="1d52f-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="1d52f-128">Инструкции можно найти в разделе [Создание коллекций на портале "Мои приложения" на портале Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span><span class="sxs-lookup"><span data-stu-id="1d52f-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>