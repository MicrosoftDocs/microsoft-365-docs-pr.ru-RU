---
title: Добавление и проверка контактов администратора на портале администрирования
description: Сообщите нам, к кому обращаться для каждой области фокуса.
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289265"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="b0311-104">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="b0311-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="b0311-105">Существует несколько способов взаимодействия службы microsoft Managed Desktop с клиентами.</span><span class="sxs-lookup"><span data-stu-id="b0311-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="b0311-106">Чтобы упростить взаимодействие и убедиться, что мы проверяем нужных людей, необходимо предоставить набор контактов администратора.</span><span class="sxs-lookup"><span data-stu-id="b0311-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="b0311-107">ИТ-операции microsoft Managed Desktop Будут обращаться к этим людям за помощью в устранении неполадок с клиентом.</span><span class="sxs-lookup"><span data-stu-id="b0311-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0311-108">Возможно, вы уже добавили эти контакты на портал администрирования.</span><span class="sxs-lookup"><span data-stu-id="b0311-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="b0311-109">Если да, проверьте точность списка контактов, так как компьютеры,  управляемые Майкрософт, должны иметь возможность связаться с ними в случае серьезного инцидента.</span><span class="sxs-lookup"><span data-stu-id="b0311-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="b0311-110">Доступ к Azure Active Directory для портала администрирования управляемых компьютеров (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b0311-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="b0311-111">Портал администрирования управляемых компьютеров (Майкрософт) требует, чтобы у пользователей, которые имеют доступ к порталу, была одна из этих ролей Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="b0311-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="b0311-112">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="b0311-112">Global Administrator</span></span>
- <span data-ttu-id="b0311-113">Администратор службы Intune</span><span class="sxs-lookup"><span data-stu-id="b0311-113">Intune Service Administrator</span></span>
- <span data-ttu-id="b0311-114">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="b0311-114">Global Reader</span></span>
- <span data-ttu-id="b0311-115">Администратор службы поддержки</span><span class="sxs-lookup"><span data-stu-id="b0311-115">Service Support Administrator</span></span>

<span data-ttu-id="b0311-116">Глобальный администратор должен зарегистрировать вашу организацию на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b0311-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="b0311-117">Все пять ролей имеют одинаковый доступ на портале администрирования для инициирования и просмотра задач.</span><span class="sxs-lookup"><span data-stu-id="b0311-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="b0311-118">Дополнительные сведения о назначении этих ролей в Azure AD см. в сведениях о разрешениях роли [администратора в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="b0311-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="b0311-119">Области фокуса для контактов администратора</span><span class="sxs-lookup"><span data-stu-id="b0311-119">Admin contact areas of focus</span></span>

<span data-ttu-id="b0311-120">Контакты администратора должны быть лучшим человеком или группой, которые могут отвечать на вопросы и принимать решения для различных областей фокуса.</span><span class="sxs-lookup"><span data-stu-id="b0311-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="b0311-121">**Операции microsoft Managed Desktop Operations будут обращаться к этим контактам администратора за вопросами, связанными с запросами в службу поддержки, поданным клиентом.**</span><span class="sxs-lookup"><span data-stu-id="b0311-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="b0311-122">Эти контакты администратора будут получать уведомления об обновлениях запросов в службу поддержки и новых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="b0311-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="b0311-123">К этим областям относятся:</span><span class="sxs-lookup"><span data-stu-id="b0311-123">These areas include:</span></span>

<span data-ttu-id="b0311-124">Область фокуса</span><span class="sxs-lookup"><span data-stu-id="b0311-124">Area of focus</span></span> | <span data-ttu-id="b0311-125">Вопросы о</span><span class="sxs-lookup"><span data-stu-id="b0311-125">For questions about</span></span>
--- | ---
<span data-ttu-id="b0311-126">Упаковка приложений</span><span class="sxs-lookup"><span data-stu-id="b0311-126">App packaging</span></span> | <span data-ttu-id="b0311-127">Устранение неполадок упаковки приложений</span><span class="sxs-lookup"><span data-stu-id="b0311-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="b0311-128">Устройства</span><span class="sxs-lookup"><span data-stu-id="b0311-128">Devices</span></span> | <span data-ttu-id="b0311-129">Состояние устройства, устранение неполадок на настольных устройствах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b0311-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="b0311-130">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b0311-130">Security</span></span> | <span data-ttu-id="b0311-131">Устранение проблем безопасности на настольных устройствах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b0311-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="b0311-132">ИТ-службы поддержки</span><span class="sxs-lookup"><span data-stu-id="b0311-132">IT help desk</span></span> | <span data-ttu-id="b0311-133">в случаях, когда сотрудники службы поддержки перенаправат билеты пользователей за пределы областей поддержки управляемых Майкрософт компьютеров</span><span class="sxs-lookup"><span data-stu-id="b0311-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="b0311-134">Другое</span><span class="sxs-lookup"><span data-stu-id="b0311-134">Other</span></span> | <span data-ttu-id="b0311-135">Для проблем, не охватываемых другими областями</span><span class="sxs-lookup"><span data-stu-id="b0311-135">For issues not covered by other areas</span></span>

<span data-ttu-id="b0311-136">**Любой человек, который вы выбрали для этих контактов, должен иметь знания и полномочия для принятия решений для среды компьютеров, управляемых Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="b0311-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="b0311-137">При подстройке среды microsoft Managed Desktop вам будет предложено добавить контакты для локальной службы поддержки и безопасности.</span><span class="sxs-lookup"><span data-stu-id="b0311-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="b0311-138">Контакты администратора необходимы при отправке [запроса в службу поддержки.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="b0311-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="b0311-139">Вам потребуется контакт администратора для области фокуса запроса в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="b0311-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="b0311-140">**Добавление контактов администратора**</span><span class="sxs-lookup"><span data-stu-id="b0311-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="b0311-141">Во sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="b0311-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="b0311-142">В **области "Поддержка"** выберите **"Контакты администратора".**</span><span class="sxs-lookup"><span data-stu-id="b0311-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Меню поддержки, контакты администратора в верхней части выбранного](../../media/admincontacts.png)

3. <span data-ttu-id="b0311-144">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b0311-144">Select **Add**.</span></span>

    ![Портал администрирования, кнопка "Добавить" слева от кнопки "Экспорт и обновление"](../../media/adminadd.png)

4.  <span data-ttu-id="b0311-146">Выберите область **фокуса и** введите сведения для контакта.</span><span class="sxs-lookup"><span data-stu-id="b0311-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![список областей фокуса, таких как "Другие", "Приложения" и "Безопасность"](../../media/areaoffocus.png)

5. <span data-ttu-id="b0311-148">Повторите это для каждой области фокуса.</span><span class="sxs-lookup"><span data-stu-id="b0311-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="b0311-149">Действия по началу работы с компьютером, управляемым Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b0311-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="b0311-150">Добавление и проверка контактов администратора на портале администрирования (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="b0311-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="b0311-151">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="b0311-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="b0311-152">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="b0311-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="b0311-153">Установка корпоративного портала Intune на устройствах</span><span class="sxs-lookup"><span data-stu-id="b0311-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="b0311-154">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="b0311-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="b0311-155">Настройка компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b0311-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="b0311-156">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="b0311-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="b0311-157">Развертывание приложений на устройствах</span><span class="sxs-lookup"><span data-stu-id="b0311-157">Deploy apps to devices</span></span>](deploy-apps.md)
