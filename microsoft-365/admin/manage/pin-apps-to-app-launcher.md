---
title: Pin apps to your users' app launcher
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
description: В качестве глобального администратора вы можете прикрепить до трех приложений к запуску приложений пользователей.
ms.openlocfilehash: 965fcbbb3f0e22074e3f6c5476d65ade98fea94c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915222"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="3408d-103">Pin apps to your users' app launcher</span><span class="sxs-lookup"><span data-stu-id="3408d-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="3408d-104">Вы можете использовать элементы управления на портале Azure Active Directory для закрепления трех приложений для Office.com и запуска приложений для всех пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3408d-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="3408d-105">Можно также организовать группы приложений.</span><span class="sxs-lookup"><span data-stu-id="3408d-105">You can also organize groups of applications.</span></span> <span data-ttu-id="3408d-106">Любое приложение, которое вы добавляете, может быть впоследствии открепить пользователем в любое время.</span><span class="sxs-lookup"><span data-stu-id="3408d-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="3408d-107">Чтобы прикрепить приложение для пользователей, необходимо быть администратором облачных приложений или администратором приложений в Azure Active Directory или глобальным администратором в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3408d-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="3408d-108">Дополнительные сведения о роли администратора см. в видеоролике Роли администратора в [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) и роли администратора [в Microsoft 365.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3408d-108">For more information about admin roles, see [admin roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="3408d-109">Дополнительные сведения о запуске и Office.com приложения см. в статье Meet [the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and updates to office.com и в статье Блог запуска приложения [Office 365.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)</span><span class="sxs-lookup"><span data-stu-id="3408d-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="3408d-110">Использование портала Azure Active Directory для пин-кода приложений</span><span class="sxs-lookup"><span data-stu-id="3408d-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="3408d-111">Перейдите в центр администрирования Microsoft 365 по <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> крайней .</span><span class="sxs-lookup"><span data-stu-id="3408d-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="3408d-112">В левом nav выберите **Показать все,** а в центрах **администрирования** выберите **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="3408d-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="3408d-113">В **Azure Active Directory** выберите **параметры пользователя**  >  **корпоративных приложений.**</span><span class="sxs-lookup"><span data-stu-id="3408d-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="3408d-114">В разделе **Параметры Office 365** выберите **приложение Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3408d-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="3408d-115">Выберите приложения, которые необходимо прикрепить к запуску приложений пользователей, а затем **добавьте**.</span><span class="sxs-lookup"><span data-stu-id="3408d-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Параметры Microsoft 365 для закрепления приложений.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="3408d-117">Пин-код настраиваемой приложения</span><span class="sxs-lookup"><span data-stu-id="3408d-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="3408d-118">Пользовательский интерфейс указывает, нужно ли приобретать дополнительные лицензии Azure AD для использования этой функции.</span><span class="sxs-lookup"><span data-stu-id="3408d-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="3408d-119">Дополнительные сведения см. в [расценки Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="3408d-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="3408d-120">В **Azure Active Directory** выберите **корпоративные** приложения Новое приложение в верхней части страницы  >   Все **приложения.**</span><span class="sxs-lookup"><span data-stu-id="3408d-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="3408d-121">На странице **Добавление приложения** выберите приложение **Non-gallery** или **Создайте** собственное приложение, если вы находитесь в предварительной версии Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3408d-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="3408d-122">Введите имя приложения и назначьте пользователю вкладку **"Пользователи и группы".**</span><span class="sxs-lookup"><span data-stu-id="3408d-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="3408d-123">Чтобы загрузить значок для приложения, используйте вкладку **Свойства.**</span><span class="sxs-lookup"><span data-stu-id="3408d-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="3408d-124">Чтобы назначить URL-адрес приложения на вкладке **"Единый вход",** выберите **Linked** и введите URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="3408d-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="3408d-125">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3408d-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="3408d-126">Создание коллекций приложений</span><span class="sxs-lookup"><span data-stu-id="3408d-126">Create application collections</span></span>

<span data-ttu-id="3408d-127">Вы также можете создать коллекции приложений для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="3408d-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="3408d-128">Дополнительные инструкции [см. в инструкции по созданию коллекций на портале Мои приложения на портале Azure.](/azure/active-directory/manage-apps/access-panel-collections)</span><span class="sxs-lookup"><span data-stu-id="3408d-128">For instructions, see [create collections on the My Apps portal in the Azure portal](/azure/active-directory/manage-apps/access-panel-collections).</span></span>