---
title: Добавление и проверка контактов администратора на портале администрирования
description: Сообщите нам, с кем обращаться для каждой области фокусии.
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925896"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="ed7dd-104">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="ed7dd-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="ed7dd-105">Существует несколько способов, компьютеры, управляемые Майкрософт служба взаимодействует с клиентами.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="ed7dd-106">Чтобы упростить связь и убедиться, что мы проверяем нужных людей, необходимо предоставить набор контактов администратора.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="ed7dd-107">компьютеры, управляемые Майкрософт It Operations will contact these people for assistance troubleshooting issues for your tenant.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed7dd-108">Возможно, вы уже добавили эти контакты на портале Admin.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="ed7dd-109">Если да, удостоверимся, что список контактов является точным,  так как компьютеры, управляемые Майкрософт должны быть в состоянии связаться с ними в случае серьезного инцидента.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="ed7dd-110">Azure Active Directory доступа для компьютеры, управляемые Майкрософт администратора</span><span class="sxs-lookup"><span data-stu-id="ed7dd-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="ed7dd-111">компьютеры, управляемые Майкрософт Портал администрирования требует, чтобы у людей, которые имеют доступ к порталу, одна из Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="ed7dd-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="ed7dd-112">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="ed7dd-112">Global Administrator</span></span>
- <span data-ttu-id="ed7dd-113">Администратор службы Intune</span><span class="sxs-lookup"><span data-stu-id="ed7dd-113">Intune Service Administrator</span></span>
- <span data-ttu-id="ed7dd-114">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="ed7dd-114">Global Reader</span></span>
- <span data-ttu-id="ed7dd-115">Администратор службы поддержки</span><span class="sxs-lookup"><span data-stu-id="ed7dd-115">Service Support Administrator</span></span>

<span data-ttu-id="ed7dd-116">Глобальный администратор должен зарегистрировать организацию в компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ed7dd-117">Все пять ролей имеют одинаковый доступ на портале Администрирование для инициировать и просматривать задачи.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="ed7dd-118">Дополнительные сведения о назначении этих ролей в Azure AD см. в [Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="ed7dd-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="ed7dd-119">Области контактов администратора</span><span class="sxs-lookup"><span data-stu-id="ed7dd-119">Admin contact areas of focus</span></span>

<span data-ttu-id="ed7dd-120">Контакты администратора должны быть лучшими людьми или группой, которые могут отвечать на вопросы и принимать решения для различных областей внимания.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="ed7dd-121">**компьютеры, управляемые Майкрософт Операции будут обращаться к этим контактам администратора для вопросов, связанных с запросами поддержки, поданных клиентом.**</span><span class="sxs-lookup"><span data-stu-id="ed7dd-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="ed7dd-122">Эти контакты администратора будут получать уведомления об обновлениях запросов на поддержку и новых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="ed7dd-123">К этим областям относятся:</span><span class="sxs-lookup"><span data-stu-id="ed7dd-123">These areas include:</span></span>

<span data-ttu-id="ed7dd-124">Область фокуса</span><span class="sxs-lookup"><span data-stu-id="ed7dd-124">Area of focus</span></span> | <span data-ttu-id="ed7dd-125">Вопросы о</span><span class="sxs-lookup"><span data-stu-id="ed7dd-125">For questions about</span></span>
--- | ---
<span data-ttu-id="ed7dd-126">Упаковка приложений</span><span class="sxs-lookup"><span data-stu-id="ed7dd-126">App packaging</span></span> | <span data-ttu-id="ed7dd-127">Устранение неполадок при упаковке приложений</span><span class="sxs-lookup"><span data-stu-id="ed7dd-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="ed7dd-128">Устройства</span><span class="sxs-lookup"><span data-stu-id="ed7dd-128">Devices</span></span> | <span data-ttu-id="ed7dd-129">Состояние устройства, устранение неполадок с помощью компьютеры, управляемые Майкрософт устройств</span><span class="sxs-lookup"><span data-stu-id="ed7dd-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ed7dd-130">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ed7dd-130">Security</span></span> | <span data-ttu-id="ed7dd-131">Устранение неполадок с безопасностью с компьютеры, управляемые Майкрософт устройствами</span><span class="sxs-lookup"><span data-stu-id="ed7dd-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ed7dd-132">ИТ-службы</span><span class="sxs-lookup"><span data-stu-id="ed7dd-132">IT help desk</span></span> | <span data-ttu-id="ed7dd-133">в тех случаях, когда сотрудники компьютеры, управляемые Майкрософт службы поддержки совме-</span><span class="sxs-lookup"><span data-stu-id="ed7dd-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="ed7dd-134">Другое</span><span class="sxs-lookup"><span data-stu-id="ed7dd-134">Other</span></span> | <span data-ttu-id="ed7dd-135">Для проблем, не охваченных другими областями</span><span class="sxs-lookup"><span data-stu-id="ed7dd-135">For issues not covered by other areas</span></span>

<span data-ttu-id="ed7dd-136">**Тот, кто выбирает для этих контактов, должен иметь знания и полномочия для принятия решений для компьютеры, управляемые Майкрософт среды.**</span><span class="sxs-lookup"><span data-stu-id="ed7dd-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="ed7dd-137">Когда вы на компьютеры, управляемые Майкрософт среде, вам будет предложено добавить контакты для локальной службы helpdesk и Security.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="ed7dd-138">Контакты администратора необходимы при отправке [запроса на поддержку.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="ed7dd-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="ed7dd-139">Вам потребуется связаться с администратором для области фокусии запроса поддержки.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="ed7dd-140">**Добавление контактов администратора**</span><span class="sxs-lookup"><span data-stu-id="ed7dd-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="ed7dd-141">Во входе [на компьютеры, управляемые Майкрософт портал администрирования](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="ed7dd-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="ed7dd-142">В **статье Поддержка** выберите контакты **администратора**.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Меню поддержки, контакты администратора в верхней части выбранного](../../media/admincontacts.png)

3. <span data-ttu-id="ed7dd-144">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-144">Select **Add**.</span></span>

    ![Портал администрирования, кнопка Добавить слева от экспорта и обновления](../../media/adminadd.png)

4.  <span data-ttu-id="ed7dd-146">Выберите область **фокуса** и введите сведения для контакта.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![список областей фокусиза, таких как Other, Apps и Security](../../media/areaoffocus.png)

5. <span data-ttu-id="ed7dd-148">Повторите для каждой области фокуса.</span><span class="sxs-lookup"><span data-stu-id="ed7dd-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="ed7dd-149">Шаги для начала работы с компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ed7dd-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="ed7dd-150">Добавление и проверка контактов администратора на портале Admin (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="ed7dd-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="ed7dd-151">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="ed7dd-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="ed7dd-152">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="ed7dd-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="ed7dd-153">Установка корпоративного портала Intune на устройствах</span><span class="sxs-lookup"><span data-stu-id="ed7dd-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="ed7dd-154">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="ed7dd-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="ed7dd-155">Настройка компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ed7dd-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="ed7dd-156">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="ed7dd-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="ed7dd-157">Развертывание приложений на устройствах</span><span class="sxs-lookup"><span data-stu-id="ed7dd-157">Deploy apps to devices</span></span>](deploy-apps.md)