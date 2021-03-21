---
title: Настройка advanced eDiscovery в Microsoft 365
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
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: В этой статье описано, как настроить advanced eDiscovery, чтобы можно было приступить к созданию и управлению делами. В нем также описываются необходимые подписки и лицензирование Майкрософт. После выполнения нескольких быстрых действий средство advanced eDiscovery готово к использованию.
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919753"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="50a75-105">Настройка microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="50a75-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="50a75-106">Advanced eDiscovery in Microsoft 365 предоставляет конечный рабочий процесс для сохранения, сбора, проверки, анализа и экспорта данных, которые реагируют на внутренние и внешние расследования вашей организации.</span><span class="sxs-lookup"><span data-stu-id="50a75-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="50a75-107">Для развертывания advanced eDiscovery ничего не требуется, но перед организацией для управления расследованиями необходимо выполнить некоторые обязательные задачи, которые должен выполнить ИТ-администратор и менеджер по обнаружению электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="50a75-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="50a75-108">В этой статье обсуждаются следующие действия, необходимые для набора advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="50a75-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![Действия по настройкам advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="50a75-110">Это включает в себя обеспечение надлежащего лицензирования, необходимого для доступа к advanced eDiscovery и добавления хранителей в дела, а также назначение разрешений вашей юридической и следственной группе, чтобы они могли получать доступ к делам и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="50a75-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="50a75-111">Шаг 1. Проверка и назначение соответствующих лицензий</span><span class="sxs-lookup"><span data-stu-id="50a75-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="50a75-112">Лицензирование для предварительного получения информации об обнаружении электронных данных требует соответствующей подписки на организацию и лицензирования для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="50a75-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="50a75-113">Список требований к лицензированию для расширенных электронных открытий см. в журнале [Subscriptions and licensing.](overview-ediscovery-20.md#subscriptions-and-licensing)</span><span class="sxs-lookup"><span data-stu-id="50a75-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="50a75-114">Шаг 2. Назначение разрешений на открытие электронной почты</span><span class="sxs-lookup"><span data-stu-id="50a75-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="50a75-115">Чтобы получить доступ к advanced eDiscovery или добавить его в качестве участника дела advanced eDiscovery, пользователю должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="50a75-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="50a75-116">В частности, пользователь должен быть добавлен в качестве члена группы ролей диспетчера электронных данных в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="50a75-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="50a75-117">Члены этой группы ролей могут создавать и управлять делами по предварительному обнаружению электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="50a75-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="50a75-118">Они могут добавлять и удалять членов, задерживать хранители и расположения контента, управлять уведомлениями о удержании, создавать и изменять поиски, связанные с делом, добавлять результаты поиска в набор отзывов, анализировать данные в наборе отзывов и экспортировать и скачивать из дела advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="50a75-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="50a75-119">Выполните следующие действия, чтобы добавить пользователей в группу ролей диспетчера электронных данных:</span><span class="sxs-lookup"><span data-stu-id="50a75-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="50a75-120">Перейдите к учетным данным учетной записи администратора в организации <https://protection.office.com/permissions> Microsoft 365 и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="50a75-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="50a75-121">На странице **Разрешения выберите** группу **ролей диспетчера** электронных открытий.</span><span class="sxs-lookup"><span data-stu-id="50a75-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="50a75-122">На странице флажок диспетчера электронных обнаружений нажмите **кнопку Изменить** рядом с разделом Диспетчер по обнаружению **электронных обнаружений.**</span><span class="sxs-lookup"><span data-stu-id="50a75-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="50a75-123">На странице **Choose eDiscovery Manager** в мастере группы редактирования ролей нажмите **кнопку Выберите диспетчер по обнаружению электронных обнаружений.**</span><span class="sxs-lookup"><span data-stu-id="50a75-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="50a75-124">Нажмите **кнопку Добавить,** а затем выберите почтовый ящик для всех пользователей, которые необходимо добавить в группу ролей.</span><span class="sxs-lookup"><span data-stu-id="50a75-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="50a75-125">Нажмите **кнопку Добавить,** чтобы добавить выбранных пользователей, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="50a75-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="50a75-126">Нажмите **Кнопку Сохранить,** чтобы добавить пользователей в группу ролей, а затем нажмите **кнопку Закрыть,** чтобы завершить шаг.</span><span class="sxs-lookup"><span data-stu-id="50a75-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="50a75-127">Дополнительные сведения о группе ролей диспетчера электронных данных</span><span class="sxs-lookup"><span data-stu-id="50a75-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="50a75-128">В группе ролей диспетчера электронных обнаружений есть две подгруппы.</span><span class="sxs-lookup"><span data-stu-id="50a75-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="50a75-129">Разница между этими подгруппами заключается в области их действия.</span><span class="sxs-lookup"><span data-stu-id="50a75-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="50a75-130">**Диспетчер по обнаружению** электронных обнаружений: может просматривать и управлять случаями, которые они создают или являются членами advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="50a75-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="50a75-131">Если другой диспетчер по обнаружению электронных данных создает дело, но не добавляет второго диспетчера по обнаружению электронных данных в качестве участника этого дела, второй диспетчер по обнаружению электронных данных не сможет просмотреть или открыть дело на странице Advanced eDiscovery в центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="50a75-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="50a75-132">Как правило, большинство людей в вашей организации могут быть добавлены в подгруппу диспетчера электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="50a75-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="50a75-133">**Администратор по обнаружению** электронной почты: может выполнять все задачи по управлению случаями, которые может выполнять диспетчер по обнаружению электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="50a75-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="50a75-134">Кроме того, администратор, ответственный за обнаружение электронных данных, может выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="50a75-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="50a75-135">Просмотр всех случаев, перечисленных на странице Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="50a75-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="50a75-136">Управление любым случаем в организации после добавления в качестве участника дела.</span><span class="sxs-lookup"><span data-stu-id="50a75-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="50a75-137">Доступ и экспорт данных кейсов для любого случая в организации.</span><span class="sxs-lookup"><span data-stu-id="50a75-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="50a75-138">В связи с широким доступом организация должна иметь только несколько администраторов, которые являются членами подгруппы администраторов по электронным данным.</span><span class="sxs-lookup"><span data-stu-id="50a75-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="50a75-139">Дополнительные сведения о разрешениях на открытие электронных данных и описании каждой роли, назначенной группе ролей диспетчера электронных данных, см. в руб. Назначение разрешений на открытие [электронных данных.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="50a75-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="50a75-140">Шаг 3. Настройка глобальных параметров для advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="50a75-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="50a75-141">Последний шаг, который необходимо выполнить, прежде чем люди в организации начнут создавать и использовать случаи, это настройка глобальных параметров, применимых к всем случаям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="50a75-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="50a75-142">В настоящее время единственным глобальным параметром является обнаружение привилегий между адвокатом и клиентом *(в* будущем будут доступны более глобальные параметры).</span><span class="sxs-lookup"><span data-stu-id="50a75-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="50a75-143">Этот параметр позволяет модели привилегий адвоката и клиента работать при анализе данных в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="50a75-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="50a75-144">Модель использует машинное обучение для определения вероятности того, что документ содержит содержимое, которое является законным по своему характеру.</span><span class="sxs-lookup"><span data-stu-id="50a75-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="50a75-145">Он также сравнивает участников документов со списком адвокатов (который вы представляете при настройке модели), чтобы определить, имеется ли в документе по крайней мере один участник, который является адвокатом.</span><span class="sxs-lookup"><span data-stu-id="50a75-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="50a75-146">Дополнительные сведения о настройке и использовании модели обнаружения привилегий между адвокатом и клиентом см. в примере [Set up attorney-client privilege detection in Advanced eDiscovery.](attorney-privilege-detection.md)</span><span class="sxs-lookup"><span data-stu-id="50a75-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="50a75-147">Это необязательный шаг, который можно выполнить в любое время.</span><span class="sxs-lookup"><span data-stu-id="50a75-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="50a75-148">Не внедрение модели обнаружения привилегий между адвокатом и клиентом не мешает вам создавать и использовать расширенные случаи обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="50a75-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="50a75-149">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="50a75-149">Next steps</span></span>

<span data-ttu-id="50a75-150">После создания advanced eDiscovery вы будете готовы [создать случай.](create-and-manage-advanced-ediscoveryv2-case.md)</span><span class="sxs-lookup"><span data-stu-id="50a75-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>