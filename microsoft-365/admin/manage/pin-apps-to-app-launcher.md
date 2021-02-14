---
title: Закрепление приложений в запуске приложений пользователей
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
description: Как глобальный администратор вы можете закрепить до трех приложений в запуске приложений пользователей.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310879"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="5b911-103">Закрепление приложений в запуске приложений пользователей</span><span class="sxs-lookup"><span data-stu-id="5b911-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="5b911-104">Элементы управления на портале Azure Active Directory можно использовать для закрепления до трех приложений для Office.com и средства запуска приложений для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="5b911-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="5b911-105">Вы также можете организовать группы приложений.</span><span class="sxs-lookup"><span data-stu-id="5b911-105">You can also organize groups of applications.</span></span> <span data-ttu-id="5b911-106">Любое приложение, которое вы добавляете, может быть в любое время открепить пользователем.</span><span class="sxs-lookup"><span data-stu-id="5b911-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="5b911-107">Чтобы закрепить приложение для пользователей, необходимо быть администратором облачных приложений, администратором приложений в Azure Active Directory или глобальным администратором в Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b911-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="5b911-108">Дополнительные сведения о ролях администраторов см. в ролях администратора [в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) и ролях администратора [в Microsoft 365.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5b911-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="5b911-109">Дополнительные сведения о запуске и Office.com приложений [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) см. в статье о запуске приложений и обновлениях для office.com и статье блога о запуске приложений [Office 365.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)</span><span class="sxs-lookup"><span data-stu-id="5b911-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="5b911-110">Закрепление приложений с помощью портала Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5b911-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="5b911-111">Перейдите в Центр администрирования Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> по</span><span class="sxs-lookup"><span data-stu-id="5b911-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="5b911-112">In the left nav, choose **Show all**, and under **Admin centers,** choose **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5b911-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5b911-113">В **Azure Active Directory выберите** параметры пользователя   >  **корпоративных приложений.**</span><span class="sxs-lookup"><span data-stu-id="5b911-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="5b911-114">В разделе **"Параметры Office 365"** выберите **"Добавить приложение".**</span><span class="sxs-lookup"><span data-stu-id="5b911-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="5b911-115">Выберите приложения, которые вы хотите закрепить в запуске приложений пользователей, а затем выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="5b911-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Параметры Microsoft 365 для закрепления приложений.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="5b911-117">Закрепление пользовательского приложения</span><span class="sxs-lookup"><span data-stu-id="5b911-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="5b911-118">В пользовательском интерфейсе будет указано, нужно ли приобрести дополнительные лицензии Azure AD для использования этой функции.</span><span class="sxs-lookup"><span data-stu-id="5b911-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="5b911-119">Дополнительные сведения [см. в ценах Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="5b911-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="5b911-120">В **Azure Active Directory** выберите новое приложение **для** корпоративных приложений в верхней части страницы  >   **"Все приложения".**</span><span class="sxs-lookup"><span data-stu-id="5b911-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="5b911-121">На странице **"Добавление приложения"** выберите приложение  не из коллекции или создайте собственное приложение, если вы находитесь в предварительной версии Azure Active Directory. </span><span class="sxs-lookup"><span data-stu-id="5b911-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="5b911-122">Введите имя приложения и назначьте пользователя на вкладке **"Пользователи и группы".**</span><span class="sxs-lookup"><span data-stu-id="5b911-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="5b911-123">Вкладка **"Свойства"** используется для отправки значка приложения.</span><span class="sxs-lookup"><span data-stu-id="5b911-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="5b911-124">Чтобы назначить **URL-адрес** приложению, на вкладке  "Единый вход" выберите "Связанный" и введите URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="5b911-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="5b911-125">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5b911-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="5b911-126">Создание коллекций приложений</span><span class="sxs-lookup"><span data-stu-id="5b911-126">Create application collections</span></span>

<span data-ttu-id="5b911-127">Вы также можете создавать коллекции приложений для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="5b911-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="5b911-128">Инструкции см. в создании коллекций на портале [My Apps на портале Azure.](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)</span><span class="sxs-lookup"><span data-stu-id="5b911-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>