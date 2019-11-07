---
title: Добавление и проверка контактов администратора на портале администрирования
description: Расскажите нам, кому следует обращаться по каждой области фокуса.
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3f77a5f6f0af83ea82d2ab3cea0798b95e27c2d2
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012070"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="eadf5-104">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="eadf5-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="eadf5-105">Существует несколько способов, которыми служба настольных компьютеров Майкрософт обменивается данными с клиентами.</span><span class="sxs-lookup"><span data-stu-id="eadf5-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="eadf5-106">Чтобы упростить обмен данными и убедиться в том, что вы ищете нужных людей, вам нужно предоставить набор контактов администратора.</span><span class="sxs-lookup"><span data-stu-id="eadf5-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="eadf5-107">Управляемые корпорацией Майкрософт ИТ ИТ, которые будут обращаться к этим сотрудникам за устранение неполадок, связанных с клиентом.</span><span class="sxs-lookup"><span data-stu-id="eadf5-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eadf5-108">Возможно, вы уже добавили эти контакты на портале администрирования.</span><span class="sxs-lookup"><span data-stu-id="eadf5-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="eadf5-109">Если это так, проверьте, что список контактов является точным, так как компьютер, управляемый Майкрософт, **должен** иметь возможность обращаться к ним при возникновении серьезных инцидентов.</span><span class="sxs-lookup"><span data-stu-id="eadf5-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="eadf5-110">Доступ к порталу администрирования рабочих столов с управлением Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="eadf5-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="eadf5-111">На портале администрирования рабочих столов Майкрософт необходимо, чтобы у пользователей, обращающихся к портале, была одна из этих ролей Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="eadf5-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="eadf5-112">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="eadf5-112">Global Administrator</span></span>
- <span data-ttu-id="eadf5-113">Администратор службы Intune</span><span class="sxs-lookup"><span data-stu-id="eadf5-113">Intune Service Administrator</span></span>
- <span data-ttu-id="eadf5-114">Администратор выставления счетов</span><span class="sxs-lookup"><span data-stu-id="eadf5-114">Billing Administrator</span></span>
- <span data-ttu-id="eadf5-115">Администратор поддержки службы</span><span class="sxs-lookup"><span data-stu-id="eadf5-115">Service Support Administrator</span></span>

<span data-ttu-id="eadf5-116">Глобальный администратор должен быть администратором, который зарегистрирует вашу организацию на настольном компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eadf5-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="eadf5-117">Все пять ролей имеют одинаковый доступ в портале администрирования для инициирования и просмотра задач.</span><span class="sxs-lookup"><span data-stu-id="eadf5-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="eadf5-118">Для получения дополнительных сведений о назначении этих ролей в Azure AD, ознакомьтесь с [разрешениями роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="eadf5-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="eadf5-119">Область контактного лица для администраторов</span><span class="sxs-lookup"><span data-stu-id="eadf5-119">Admin contact areas of focus</span></span>

<span data-ttu-id="eadf5-120">Контакты администратора должны быть наиболее подходящие лицами или группами, которые могут отвечать на вопросы и принимать решения для различных областей фокусировки.</span><span class="sxs-lookup"><span data-stu-id="eadf5-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="eadf5-121">**Операции с рабочими столами, управляемыми Майкрософт, будут обращаться к этим административным контактам для получения вопросов, связанных с запросами на поддержку, которые**</span><span class="sxs-lookup"><span data-stu-id="eadf5-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="eadf5-122">Эти контакты администрирования будут получать уведомления об обновлениях запросов в службу поддержки и новых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="eadf5-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="eadf5-123">К этим областям относятся:</span><span class="sxs-lookup"><span data-stu-id="eadf5-123">These areas include:</span></span>

<span data-ttu-id="eadf5-124">Область фокуса</span><span class="sxs-lookup"><span data-stu-id="eadf5-124">Area of focus</span></span> | <span data-ttu-id="eadf5-125">Для вопросов о</span><span class="sxs-lookup"><span data-stu-id="eadf5-125">For questions about</span></span>
--- | ---
<span data-ttu-id="eadf5-126">Упаковка приложений</span><span class="sxs-lookup"><span data-stu-id="eadf5-126">App packaging</span></span> | <span data-ttu-id="eadf5-127">Устранение неполадок при упаковке приложений</span><span class="sxs-lookup"><span data-stu-id="eadf5-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="eadf5-128">Устройства</span><span class="sxs-lookup"><span data-stu-id="eadf5-128">Devices</span></span> | <span data-ttu-id="eadf5-129">Работоспособность устройств, устранение неполадок с настольными устройствами, управляемыми Майкрософт</span><span class="sxs-lookup"><span data-stu-id="eadf5-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="eadf5-130">Безопасность</span><span class="sxs-lookup"><span data-stu-id="eadf5-130">Security</span></span> | <span data-ttu-id="eadf5-131">Устранение неполадок безопасности, связанных с настольными устройствами, управляемыми Майкрософт</span><span class="sxs-lookup"><span data-stu-id="eadf5-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="eadf5-132">Служба технической поддержки ИТ</span><span class="sxs-lookup"><span data-stu-id="eadf5-132">IT help desk</span></span> | <span data-ttu-id="eadf5-133">в тех случаях, когда наши сотрудники службы поддержки переносят билеты на конечные пользователи за пределами областей поддержки для управляемых компьютеров Майкрософт</span><span class="sxs-lookup"><span data-stu-id="eadf5-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="eadf5-134">Other</span><span class="sxs-lookup"><span data-stu-id="eadf5-134">Other</span></span> | <span data-ttu-id="eadf5-135">Для проблем, не охваченных другими областями</span><span class="sxs-lookup"><span data-stu-id="eadf5-135">For issues not covered by other areas</span></span>

<span data-ttu-id="eadf5-136">**Любой пользователь, который вы выбираете для этих контактов, должен иметь знания и полномочия для принятия решений по вашей среде для настольных компьютеров, управляемой Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="eadf5-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="eadf5-137">При подключении вашей рабочей среды под управлением Майкрософт вам будет предложено добавить контакты для локальной службы поддержки и безопасности.</span><span class="sxs-lookup"><span data-stu-id="eadf5-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="eadf5-138">При [отсылке запроса поддержки](../working-with-managed-desktop/support.md)требуются Контакты администратора.</span><span class="sxs-lookup"><span data-stu-id="eadf5-138">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="eadf5-139">Вам потребуется связаться с администратором, чтобы получить фокусную область запроса на поддержку.</span><span class="sxs-lookup"><span data-stu-id="eadf5-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="eadf5-140">**Добавление контактов администратора**</span><span class="sxs-lookup"><span data-stu-id="eadf5-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="eadf5-141">Войдите на [портал администрирования рабочих столов с управляемыми правами Майкрософт](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="eadf5-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="eadf5-142">В разделе **Поддержка**выберите **Контакты для администраторов**.</span><span class="sxs-lookup"><span data-stu-id="eadf5-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Меню поддержки, контакты администратора](images/admincontacts.png)

3. <span data-ttu-id="eadf5-144">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eadf5-144">Select **Add**.</span></span>

    ![Кнопка "Добавить" на портале администрирования](images/adminadd.png)

4.  <span data-ttu-id="eadf5-146">Выберите **область фокуса** и введите сведения о контакте.</span><span class="sxs-lookup"><span data-stu-id="eadf5-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![список областей фокуса](images/areaoffocus.png)

5. <span data-ttu-id="eadf5-148">Повторите эти действия для каждой области фокуса.</span><span class="sxs-lookup"><span data-stu-id="eadf5-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="eadf5-149">Действия для начала работы с управляемым рабочим столом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="eadf5-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="eadf5-150">Добавление и проверка контактов администратора на портале администрирования (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="eadf5-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="eadf5-151">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="eadf5-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="eadf5-152">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="eadf5-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="eadf5-153">Установка корпоративного портала Intune на устройствах</span><span class="sxs-lookup"><span data-stu-id="eadf5-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="eadf5-154">Включение роуминга состояния предприятия</span><span class="sxs-lookup"><span data-stu-id="eadf5-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="eadf5-155">Настройка управляемых устройств для настольных ПК Майкрософт</span><span class="sxs-lookup"><span data-stu-id="eadf5-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="eadf5-156">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="eadf5-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="eadf5-157">Развертывание приложений на устройствах</span><span class="sxs-lookup"><span data-stu-id="eadf5-157">Deploy apps to devices</span></span>](deploy-apps.md)