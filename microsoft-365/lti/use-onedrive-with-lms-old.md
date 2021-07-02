---
title: Использование OneDrive Обучение средств
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Создание и оценка назначений, создание и куратор контента курсов и совместное взаимодействие с файлами в режиме реального времени с новым приложением OneDrive Обучение средства взаимодействия.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257048"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="09da2-103">Использование Microsoft OneDrive LTI с Canvas</span><span class="sxs-lookup"><span data-stu-id="09da2-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09da2-104">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="09da2-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="09da2-105">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="09da2-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="09da2-106">Интеграция с Canvas</span><span class="sxs-lookup"><span data-stu-id="09da2-106">Integrate with Canvas</span></span>

<span data-ttu-id="09da2-107">Человек, который выполняет эту интеграцию, должен быть администратором Canvas и администратором Microsoft 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="09da2-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="09da2-108">Вопишитесь на Microsoft Azure с учетной записью администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="09da2-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="09da2-109">Администратор клиента Azure также должен иметь роль администратора Группы.</span><span class="sxs-lookup"><span data-stu-id="09da2-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![Выделен администратор группы](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="09da2-111">Во входе на портал [Microsoft OneDrive LTI](https://odltiappnl.azurewebsites.net/admin).</span><span class="sxs-lookup"><span data-stu-id="09da2-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="09da2-112">Примите разрешения для завершения регистрации.</span><span class="sxs-lookup"><span data-stu-id="09da2-112">Accept the permissions to complete the sign-in.</span></span>

    ![принимать разрешения](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="09da2-114">Выберите **Добавить клиента LTI**.</span><span class="sxs-lookup"><span data-stu-id="09da2-114">Select **Add LTI Tenant**.</span></span>

     ![добавление клиента LTI](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="09da2-116">Выберите **потребительскую платформу LTI в** **качестве Canvas** из отсева.</span><span class="sxs-lookup"><span data-stu-id="09da2-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="09da2-117">Выберите **URL-адрес базы Canvas** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09da2-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![выберите Canvas и добавьте базовый URL-адрес](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="09da2-119">На следующем экране показаны конфиденциальные для вас поля.</span><span class="sxs-lookup"><span data-stu-id="09da2-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="09da2-120">Выберите **Далее** от ??</span><span class="sxs-lookup"><span data-stu-id="09da2-120">Select **Next** from ??</span></span> <span data-ttu-id="09da2-121">(Почти готово!).</span><span class="sxs-lookup"><span data-stu-id="09da2-121">page.</span></span> <span data-ttu-id="09da2-122">МОГУТ ЛИ РЕЦЕНЗЕНТЫ ЗАПОЛНИТЬ ПРОБЕЛ ЗДЕСЬ?</span><span class="sxs-lookup"><span data-stu-id="09da2-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="09da2-123">Выберите **Далее** на экране, где показаны конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="09da2-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="09da2-124">На заключительном экране портала Azure показаны следующие действия для добавления экземпляра Canvas.</span><span class="sxs-lookup"><span data-stu-id="09da2-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="09da2-125">Скопируйте клавиши разработчика с этого экрана.</span><span class="sxs-lookup"><span data-stu-id="09da2-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="09da2-126">Вы будете использовать при создании экземпляра Canvas.</span><span class="sxs-lookup"><span data-stu-id="09da2-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="09da2-127">Добавление экземпляра Canvas</span><span class="sxs-lookup"><span data-stu-id="09da2-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="09da2-128">В экземпляре Canvas высеките **клавиши**  >  **разработчика администрирования.**</span><span class="sxs-lookup"><span data-stu-id="09da2-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="09da2-129">Выберите **клавишу LTI в** отсеве в **ключе разработчика.**</span><span class="sxs-lookup"><span data-stu-id="09da2-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![Получить ключи разработчика LTI](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="09da2-131">Вклеить ключи разработчика здесь.</span><span class="sxs-lookup"><span data-stu-id="09da2-131">Paste the developer keys here.</span></span>

     ![Вклеить ключи разработчика](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="09da2-133">Ключ создается в **режиме OFF**</span><span class="sxs-lookup"><span data-stu-id="09da2-133">The key gets created in **OFF** mode</span></span>

   ![Созданные ключи разработчика в выключенном режиме](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="09da2-135">Скопируйте выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="09da2-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="09da2-136">Это служит в качестве ID клиента на Microsoft OneDrive портале LTI.</span><span class="sxs-lookup"><span data-stu-id="09da2-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="09da2-137">Вклеить текст в **поле client ID** на Microsoft OneDrive портале LTI, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09da2-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="09da2-138">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09da2-138">Select **Save**.</span></span>

7. <span data-ttu-id="09da2-139">Просмотр параметров, выбрав **View LTI Tenants**.</span><span class="sxs-lookup"><span data-stu-id="09da2-139">View the settings by selecting **View LTI Tenants**.</span></span>
