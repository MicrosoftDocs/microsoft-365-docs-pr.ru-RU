---
title: Настройка Advanced eDiscovery в Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: В этой статье описывается, как настроить Advanced eDiscovery, чтобы можно было создавать дела и управлять их. В ней также описываются необходимые подписки и лицензирование Майкрософт. После выполнения нескольких быстрых действий средство Advanced eDiscovery готово к использованию.
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841180"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="128a1-105">Настройка Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="128a1-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="128a1-106">Advanced eDiscovery в Microsoft 365 предоставляет конечный рабочий процесс для сохранения, сбора, анализа, анализа и экспорта данных, которые реагируют на внутренние и внешние исследования в организации. [](overview-ediscovery-20.md#advanced-ediscovery-workflow)</span><span class="sxs-lookup"><span data-stu-id="128a1-106">Advanced eDiscovery in Microsoft 365 provides an [end-to-end workflow](overview-ediscovery-20.md#advanced-ediscovery-workflow) to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="128a1-107">Для развертывания Advanced eDiscovery ничего не требуется, но для управления расследованиями ИТ-администратору и менеджеру по обнаружению электронных данным необходимо выполнить ряд предварительных задач.</span><span class="sxs-lookup"><span data-stu-id="128a1-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="128a1-108">В этой статье обсуждаются действия, необходимые для настойки Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="128a1-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="128a1-109">Это включает в себя обеспечение надлежащего лицензирования, необходимого для доступа к Advanced eDiscovery и добавления хранителей в дела, а также назначение разрешений юридическим отделам и группе расследования, чтобы они могли получать доступ к делам и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="128a1-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="128a1-110">Шаг 1. Проверка и назначение соответствующих лицензий</span><span class="sxs-lookup"><span data-stu-id="128a1-110">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="128a1-111">Для лицензирования Advanced eDiscovery требуется соответствующая подписка организации и лицензирование на пользователя.</span><span class="sxs-lookup"><span data-stu-id="128a1-111">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="128a1-112">**Подписка на организацию:** Чтобы получить доступ к Advanced eDiscovery в Центре соответствия требованиям Microsoft 365 или Центре безопасности & соответствия требованиям, в вашей организации должно быть одно из следующих требований:</span><span class="sxs-lookup"><span data-stu-id="128a1-112">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="128a1-113">Подписка Microsoft 365 E5 или Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="128a1-113">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="128a1-114">Подписка Microsoft 365 E3 с дополнительной надстройкой для соответствия требованиям E5</span><span class="sxs-lookup"><span data-stu-id="128a1-114">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="128a1-115">Подписка Microsoft 365 E3 с надстройка E5 для eDiscovery и аудита</span><span class="sxs-lookup"><span data-stu-id="128a1-115">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="128a1-116">Если у вас нет существующего плана Microsoft 365 E5 и вы хотите попробовать Advanced eDiscovery, [](https://www.microsoft.com/microsoft-365/enterprise) вы можете добавить [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) в существующую подписку или зарегистрироваться для пробной подписки на Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="128a1-116">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="128a1-117">**Лицензирование на пользователя:** Чтобы добавить пользователя в качестве хранителя в дело Advance eDiscovery, этому пользователю должна быть назначена одна из следующих лицензий в зависимости от подписки организации:</span><span class="sxs-lookup"><span data-stu-id="128a1-117">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="128a1-118">Microsoft 365: пользователям должна быть назначена лицензия Microsoft 365 E5, лицензия на надстройки соответствия E5 или лицензия на надстройки E5 eDiscovery и audit.</span><span class="sxs-lookup"><span data-stu-id="128a1-118">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="128a1-119">Office 365: пользователям должна быть назначена лицензия Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="128a1-119">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="128a1-120">Сведения о назначении лицензий см. в подсети ["Назначение лицензий пользователям".](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="128a1-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="128a1-121">Пользователям нужна только лицензия E5 (или соответствующая лицензия на надстройки), которая будет добавлена в качестве хранителей в дело Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="128a1-121">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="128a1-122">ИТ-администраторам, менеджерам по обнаружению электронных данных, юристам, юристам или следователям, которые используют Advanced eDiscovery для управления делами и просмотра данных дела, не требуется лицензия E5 или надстройка.</span><span class="sxs-lookup"><span data-stu-id="128a1-122">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="128a1-123">Шаг 2. Назначение разрешений на eDiscovery</span><span class="sxs-lookup"><span data-stu-id="128a1-123">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="128a1-124">Чтобы получить доступ к Advanced eDiscovery или добавить его в качестве участника дела Advanced eDiscovery, пользователю должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="128a1-124">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="128a1-125">В частности, пользователь должен быть добавлен в качестве члена группы ролей "Менеджер по обнаружению электронных данных" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="128a1-125">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="128a1-126">Члены этой группы ролей могут создавать дела Advanced eDiscovery и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="128a1-126">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="128a1-127">Они могут добавлять и удалять участников, добавлять хранителей и расположения контента на удержание, управлять уведомлениями об удержании по юридическим основаниям, создавать и редактировать операции поиска, связанные с делом, добавлять результаты поиска в набор для проверки, анализировать данные в наборе для проверки, а также экспортировать и загружать данные из дела Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="128a1-127">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="128a1-128">Выполните следующие действия, чтобы добавить пользователей в группу ролей "Руководитель eDiscovery":</span><span class="sxs-lookup"><span data-stu-id="128a1-128">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="128a1-129">Войдите и войдите, используя учетные данные учетной записи [https://protection.office.com/permissions](https://protection.office.com/permissions) администратора в вашей организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="128a1-129">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="128a1-130">На странице **"Разрешения"** выберите группу ролей **"Диспетчер eDiscovery".**</span><span class="sxs-lookup"><span data-stu-id="128a1-130">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="128a1-131">На странице "Диспетчер eDiscovery Manager" нажмите кнопку **"Изменить"** рядом с разделом **"Диспетчер eDiscovery".**</span><span class="sxs-lookup"><span data-stu-id="128a1-131">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="128a1-132">На странице **"Выбор диспетчера eDiscovery"** в мастере редактирования группы ролей щелкните "Выбрать диспетчер **eDiscovery".**</span><span class="sxs-lookup"><span data-stu-id="128a1-132">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="128a1-133">Нажмите **кнопку** "Добавить", а затем выберите этот контрольный ящик для всех пользователей, которые нужно добавить в группу ролей.</span><span class="sxs-lookup"><span data-stu-id="128a1-133">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="128a1-134">Нажмите **кнопку** "Добавить", чтобы добавить выбранных пользователей, а затем нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="128a1-134">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="128a1-135">Нажмите **кнопку** "Сохранить", чтобы добавить пользователей в группу ролей, а затем нажмите кнопку **"Закрыть",** чтобы завершить шаг.</span><span class="sxs-lookup"><span data-stu-id="128a1-135">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="128a1-136">Дополнительные сведения о группе ролей "Руководитель eDiscovery"</span><span class="sxs-lookup"><span data-stu-id="128a1-136">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="128a1-137">В группе ролей "Диспетчер eDiscovery" есть две подгруппы.</span><span class="sxs-lookup"><span data-stu-id="128a1-137">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="128a1-138">Разница между этими подгруппами заключается в области их действия.</span><span class="sxs-lookup"><span data-stu-id="128a1-138">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="128a1-139">**Диспетчер eDiscovery:** Можно просматривать и управлять делами Advanced eDiscovery, которые они создают или являются членами.</span><span class="sxs-lookup"><span data-stu-id="128a1-139">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="128a1-140">Если другой менеджер по обнаружению электронных данных создает дело, но не добавляет второго менеджера по обнаружению электронных данных в качестве участника этого дела, второй менеджер по обнаружению электронных данных не сможет просмотреть или открыть дело на странице Advanced eDiscovery в Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="128a1-140">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="128a1-141">Как правило, большинство людей в вашей организации можно добавить в подгруппу диспетчера eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="128a1-141">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="128a1-142">**Администратор eDiscovery:** Может выполнять все задачи управления делами, которые может выполнять руководитель eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="128a1-142">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="128a1-143">Кроме того, администратор, ответственный за обнаружение электронных данных, может выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="128a1-143">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="128a1-144">Просмотр всех дел, перечисленных на странице Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="128a1-144">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="128a1-145">Управляйте любыми случаями в организации после того, как они добавят себя в качестве участника дела.</span><span class="sxs-lookup"><span data-stu-id="128a1-145">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="128a1-146">Доступ и экспорт данных дела для любого случая в организации.</span><span class="sxs-lookup"><span data-stu-id="128a1-146">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="128a1-147">Из-за широкой области доступа в организации должно быть только несколько администраторов, которые являются членами подгруппы администраторов eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="128a1-147">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="128a1-148">Дополнительные сведения о разрешениях на eDiscovery и описание каждой роли, назначенной группе ролей "Менеджер по обнаружению электронных данных", см. в описании назначения разрешений на [eDiscovery.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="128a1-148">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="128a1-149">Шаг 3. Настройка глобальных параметров для Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="128a1-149">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="128a1-150">Последний шаг, который необходимо выполнить, прежде чем люди в организации начнут создавать и использовать дела, — это настройка глобальных параметров, которые применяются во всех случаях в организации.</span><span class="sxs-lookup"><span data-stu-id="128a1-150">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="128a1-151">В настоящее время единственным глобальным параметром *является* обнаружение адвокатских прав (в будущем будут доступны более глобальные параметры).</span><span class="sxs-lookup"><span data-stu-id="128a1-151">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="128a1-152">Этот параметр позволяет запускать модель адвокатских прав при анализе данных в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="128a1-152">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="128a1-153">Модель использует машинное обучение для определения вероятности того, что документ содержит юридический контент.</span><span class="sxs-lookup"><span data-stu-id="128a1-153">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="128a1-154">Он также сравнивает участников документов со списком юристов (который вы передаете при настройке модели), чтобы определить, есть ли в документе хотя бы один участник, который является адвокатом.</span><span class="sxs-lookup"><span data-stu-id="128a1-154">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="128a1-155">Дополнительные сведения о настройке и использовании модели обнаружения адвокатских привилегий см. в подстройке "Настройка обнаружения адвокатских привилегий" в [Advanced eDiscovery.](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="128a1-155">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="128a1-156">Это необязательный шаг, который можно выполнить в любое время.</span><span class="sxs-lookup"><span data-stu-id="128a1-156">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="128a1-157">Если не реализовать модель обнаружения адвокатских привилегий, вы не сможете создавать и использовать дела Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="128a1-157">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="128a1-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="128a1-158">Next steps</span></span>

<span data-ttu-id="128a1-159">После того как вы настроили Advanced eDiscovery, вы можете [создать дело.](create-and-manage-advanced-ediscoveryv2-case.md)</span><span class="sxs-lookup"><span data-stu-id="128a1-159">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>
