---
title: Использование Microsoft Teams классов с помощью Blackboard Learn Ultra
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
description: Использование Microsoft Teams классов с помощью Blackboard Learn Ultra
ms.openlocfilehash: a97d5bf56e1e045ccb0ef7cc66ecef7dfba4041a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454642"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="7d579-103">Использование Microsoft Teams классов с помощью Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="7d579-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="7d579-104">Командная работа является основой каждой современной организации.</span><span class="sxs-lookup"><span data-stu-id="7d579-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="7d579-105">Поощряя совместную работу, это определяющая характеристика каждого успешного учреждения.</span><span class="sxs-lookup"><span data-stu-id="7d579-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="7d579-106">Вы можете расширить все возможности и функции Blackboard Learn Ultra, соеряду их с Microsoft Teams классами.</span><span class="sxs-lookup"><span data-stu-id="7d579-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="7d579-107">Ваши классы могут включать беседы в режиме реального времени, видео-собрания или асинхронные взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="7d579-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="7d579-108">Вы можете добавить обмен файлами и совместное использование файлов для учащихся в одном месте.</span><span class="sxs-lookup"><span data-stu-id="7d579-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="7d579-109">Microsoft Teams с помощью Learn Ultra переопределяет динамику обучения и то, что означает эффективное обучение.</span><span class="sxs-lookup"><span data-stu-id="7d579-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d579-110">Убедитесь, что вы успешно создали поле электронной почты учебного заведения в [учебной информационной системе (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span><span class="sxs-lookup"><span data-stu-id="7d579-110">Ensure that you have successfully set up the Institution Email field in your [Student Information System (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span></span>
>
><span data-ttu-id="7d579-111">Интеграция Microsoft Teams классов зависит от поля электронной почты учреждения в вашем SIS, чтобы соедитировать правильное имя пользователя Microsoft Azure Active Directory (AAD) пользователя [(UPN).](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes)</span><span class="sxs-lookup"><span data-stu-id="7d579-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) [User Principle Name (UPN)](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes).</span></span> <span data-ttu-id="7d579-112">Если электронная почта учреждения не была предусмотрена, это будет по умолчанию для существующей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7d579-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="7d579-113">Рекомендуется установить это поле для каждого пользователя, чтобы обеспечить правильную синхронизацию данных и отсутствие конфликта данных электронной почты между AAD и Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="7d579-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="7d579-114">Если в сопоставлении SIS это поле не установлено надлежащим образом, интеграция будет продолжать работать, но пользователи могут не отображаться в созданных классах Teams и могут возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="7d579-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="7d579-115">Поддержка институционального сопоставления данных — поле SIS электронной почты учреждения</span><span class="sxs-lookup"><span data-stu-id="7d579-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="7d579-116">В рамках эволюции с интеграцией поставщиков облачных решений Blackboard Learn Ultra создала новое поле электронной почты для учреждений в интеграции системы студенческих информационных систем и общедоступных API REST, позволяя учреждениям эффективно управлять процессом синхронизации данных между Blackboard Learn Ultra и AAD. </span><span class="sxs-lookup"><span data-stu-id="7d579-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="7d579-117">Что означает электронная почта учреждения и что она поддерживает?</span><span class="sxs-lookup"><span data-stu-id="7d579-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="7d579-118">Поле **электронной почты** institution позволяет настраивать сопоставления полей между внешними источниками данных клиента и Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="7d579-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="7d579-119">Если источниками данных являются облачные поставщики, такие как Microsoft, имя принципа пользователя (UPN) является основным уникальным идентификатором для каждого пользователя, состоящим из префикса UPN (имя учетной записи пользователя) и суффикса upN (доменное имя DNS), соединяемого вместе с символом @.</span><span class="sxs-lookup"><span data-stu-id="7d579-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="7d579-120">Это создает уникальный адрес электронной почты для каждого конкретного пользователя в Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7d579-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="7d579-121">Чтобы обеспечить точность данных и правильность регистрации или членства между классами Learn Ultra и Microsoft Teams, адрес электронной почты пользователя должен совпадать между обеими системами.</span><span class="sxs-lookup"><span data-stu-id="7d579-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="7d579-122">В Blackboard Learn Ultra пользователи могут изменять или переопределять существующий адрес электронной почты в пользовательском интерфейсе, что может привести к ошибкам синхронизации и неправильному добавлению пользователя в команду классов.</span><span class="sxs-lookup"><span data-stu-id="7d579-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="7d579-123">**Сопоставление полей** электронной почты учреждения обеспечивает правильное управление этим уровнем проверки безопасности и проверки проверки, независимо от того, изменили ли пользователи электронную почту в Blackboard Learn Ultra или нет.</span><span class="sxs-lookup"><span data-stu-id="7d579-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="7d579-124">Если два адреса электронной почты отличаются, либо:</span><span class="sxs-lookup"><span data-stu-id="7d579-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="7d579-125">Необходимо принять решение о том, какой источник имеет приоритет и будет приниматься в качестве электронной почты человека и учреждения.</span><span class="sxs-lookup"><span data-stu-id="7d579-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="7d579-126">или</span><span class="sxs-lookup"><span data-stu-id="7d579-126">Or</span></span>
- <span data-ttu-id="7d579-127">Учреждение может установить настраиваемую сопоставление полей в своей электронной почте institution, что может разрешить потенциальный конфликт.</span><span class="sxs-lookup"><span data-stu-id="7d579-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="7d579-128">**Сопоставление полей электронной** почты учреждения теперь доступно для всех существующих типов интеграции SIS в **Advanced Configuration Параметры** Пользователи узнают сопоставление полей типа  >    >  **объекта.**</span><span class="sxs-lookup"><span data-stu-id="7d579-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="7d579-129">Важно отметить, что по умолчанию электронная почта учреждения  устанавливается для электронной почты человека для всех форматов SIS и должна быть уникальной для каждого человека. </span><span class="sxs-lookup"><span data-stu-id="7d579-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="7d579-130">Все существующие интеграции, которые настроены и запущены, будут иметь это сопоставление данных, так как SIS не сможет импортировать пользователей, если их электронная почта будет дублироваться.</span><span class="sxs-lookup"><span data-stu-id="7d579-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="7d579-131">Если учреждению требуется возможность изменить электронную почту учреждения на настраиваемую,  им потребуется управлять этим с помощью расширенных Параметры в SIS.</span><span class="sxs-lookup"><span data-stu-id="7d579-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d579-132">Требования</span><span class="sxs-lookup"><span data-stu-id="7d579-132">Requirements</span></span>

<span data-ttu-id="7d579-133">Интеграция Microsoft Teams классов доступна только для **курсов Ultra Course View.**</span><span class="sxs-lookup"><span data-stu-id="7d579-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="7d579-134">Чтобы использовать его, вашему учреждению необходимо выполнить эти требования:</span><span class="sxs-lookup"><span data-stu-id="7d579-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="7d579-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span><span class="sxs-lookup"><span data-stu-id="7d579-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

  ![пример функции включен в курсах](media/feature-availability.png)

- <span data-ttu-id="7d579-137">Включить LTI для использования в курсах.</span><span class="sxs-lookup"><span data-stu-id="7d579-137">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="7d579-138">a.</span><span class="sxs-lookup"><span data-stu-id="7d579-138">a.</span></span> <span data-ttu-id="7d579-139">Перейдите в **группу администраторов**  >  **поставщиков инструментов LTI**  >  **Manage Global Properties.**</span><span class="sxs-lookup"><span data-stu-id="7d579-139">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="7d579-140">b.</span><span class="sxs-lookup"><span data-stu-id="7d579-140">b.</span></span> <span data-ttu-id="7d579-141">Выберите **включенную LTI в курсах** и необязательно выберите **Включено в организациях.**</span><span class="sxs-lookup"><span data-stu-id="7d579-141">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="7d579-142">c.</span><span class="sxs-lookup"><span data-stu-id="7d579-142">c.</span></span> <span data-ttu-id="7d579-143">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="7d579-143">Select **Submit**.</span></span>

- <span data-ttu-id="7d579-144">Должно быть настроено LTI</span><span class="sxs-lookup"><span data-stu-id="7d579-144">Must have LTI configured</span></span>

- <span data-ttu-id="7d579-145">Добавление blackboard Learn Ultra Teams LTI Integration</span><span class="sxs-lookup"><span data-stu-id="7d579-145">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="7d579-146">Добавление Microsoft Teams классов LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="7d579-146">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="7d579-147">Добавление инструмента API REST и совместного использования ресурсов поперек происхождения</span><span class="sxs-lookup"><span data-stu-id="7d579-147">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="7d579-148">Настройка и утверждение интеграции Microsoft Teams классов</span><span class="sxs-lookup"><span data-stu-id="7d579-148">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="7d579-149">Добавление средства Blackboard Learn Ultra Teams классов LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="7d579-149">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="7d579-150">Из панели **администраторов** выберите **поставщиков инструментов LTI.**</span><span class="sxs-lookup"><span data-stu-id="7d579-150">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="7d579-151">Выберите **средство реестра LTI 1.3.**</span><span class="sxs-lookup"><span data-stu-id="7d579-151">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="7d579-152">В поле **Client ID** введите или скопируйте и введите этот ID:</span><span class="sxs-lookup"><span data-stu-id="7d579-152">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="7d579-153">Просмотрите все параметры, которые были предварительно заполнены и в **состоянии инструмента,** а затем выберите **Включено**.</span><span class="sxs-lookup"><span data-stu-id="7d579-153">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="7d579-154">В **политиках учреждений** выберите **роль в курсе,** имени и адресе электронной почты, а затем выберите **Да** для обоих. </span><span class="sxs-lookup"><span data-stu-id="7d579-154">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="7d579-155">Выберите **разрешить доступ к службе класса** и разрешить доступ к **службе членства.**</span><span class="sxs-lookup"><span data-stu-id="7d579-155">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="7d579-156">Добавление средства Microsoft Teams классов LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="7d579-156">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="7d579-157">Из панели **администраторов** выберите **поставщиков инструментов LTI.**</span><span class="sxs-lookup"><span data-stu-id="7d579-157">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="7d579-158">Выберите **средство реестра LTI 1.3.**</span><span class="sxs-lookup"><span data-stu-id="7d579-158">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="7d579-159">В поле **Client ID** введите или скопируйте и введите этот ID:</span><span class="sxs-lookup"><span data-stu-id="7d579-159">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="7d579-160">Просмотрите все параметры, которые были предварительно заполнены и в состоянии *инструмента и* выберите *Включено.*</span><span class="sxs-lookup"><span data-stu-id="7d579-160">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="7d579-161">В **политиках учреждений** выберите **роль в курсе, имени и** **адресе электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="7d579-161">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="7d579-162">Выберите **Да** для обоих.</span><span class="sxs-lookup"><span data-stu-id="7d579-162">Select **Yes** for both.</span></span>

6. <span data-ttu-id="7d579-163">Выберите **разрешить доступ к службе класса** и разрешить доступ к **службе членства.**</span><span class="sxs-lookup"><span data-stu-id="7d579-163">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="7d579-164">Добавление инструмента API REST</span><span class="sxs-lookup"><span data-stu-id="7d579-164">Add the REST API tool</span></span>

1. <span data-ttu-id="7d579-165">Из панели **администраторов** перейдите к **интеграциям** и выберите **интеграции API rest.**</span><span class="sxs-lookup"><span data-stu-id="7d579-165">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="7d579-166">Выберите **Создание интеграции.**</span><span class="sxs-lookup"><span data-stu-id="7d579-166">Select **Create Integration**.</span></span>

3. <span data-ttu-id="7d579-167">В поле **Application ID** введите или скопируйте и введите этот ID:</span><span class="sxs-lookup"><span data-stu-id="7d579-167">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="7d579-168">Введите пользователя для этой интеграции.</span><span class="sxs-lookup"><span data-stu-id="7d579-168">Type a user for this integration.</span></span>

   <span data-ttu-id="7d579-169">Этот пользователь будет иметь доступ к домашнему API, с которым связано приложение.</span><span class="sxs-lookup"><span data-stu-id="7d579-169">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="7d579-170">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="7d579-170">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="7d579-171">Добавление совместного доступа к ресурсам по пересеченным ресурсам</span><span class="sxs-lookup"><span data-stu-id="7d579-171">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="7d579-172">Из панели **администратора** перейдите к **интеграции** и выберите \**Cross-origin Resource Sharing*.</span><span class="sxs-lookup"><span data-stu-id="7d579-172">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="7d579-173">Выберите **создание конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="7d579-173">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="7d579-174">В поле **Origin** тип копирования и вклейки этого URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="7d579-174">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="7d579-175">В поле **Разрешенные главы** введите **авторизацию**.</span><span class="sxs-lookup"><span data-stu-id="7d579-175">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="7d579-176">Set **Available** to **Yes**.</span><span class="sxs-lookup"><span data-stu-id="7d579-176">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="7d579-177">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="7d579-177">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="7d579-178">Настройка и утверждение интеграции Microsoft Teams классов</span><span class="sxs-lookup"><span data-stu-id="7d579-178">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="7d579-179">Чтобы успешно интегрировать экземпляр Blackboard Learn Ultra с Microsoft Teams классами, необходимо убедиться, что приложение Blackboard Learn Ultra утверждено для доступа в Microsoft Azure клиенте.</span><span class="sxs-lookup"><span data-stu-id="7d579-179">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="7d579-180">Это процесс, который должен быть завершен глобальным администратором Microsoft 365 учреждения.</span><span class="sxs-lookup"><span data-stu-id="7d579-180">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="7d579-181">Этот процесс можно сделать до или после настройки приложений LTI в вашей blackboard Learn Ultra Instance.</span><span class="sxs-lookup"><span data-stu-id="7d579-181">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="7d579-182">Перед настройкой приложений LTI</span><span class="sxs-lookup"><span data-stu-id="7d579-182">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="7d579-183">Если вы решите утвердить приложение Blackboard Learn Ultra Teams Classes Azure перед настройкой интеграции LTI, вам потребуется перенаправить в конечную точку согласия администратора платформы администрирования Microsoft **Identity.**</span><span class="sxs-lookup"><span data-stu-id="7d579-183">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="7d579-184">Показан URL-адрес:</span><span class="sxs-lookup"><span data-stu-id="7d579-184">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="7d579-185">Вы замените **{Tenant}** определенным Microsoft Azure клиентом.</span><span class="sxs-lookup"><span data-stu-id="7d579-185">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

<span data-ttu-id="7d579-186">Вы увидите окно разрешений, которое объясняет, что вы даете разрешение blackboard Learn Ultra для доступа к Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7d579-186">You'll see a permissions window that explains you're giving permission to Blackboard Learn Ultra to access Microsoft Teams.</span></span>

![окно разрешений для Microsoft и Blackboard](media/permissions1.png)

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="7d579-188">После настройки приложений LTI</span><span class="sxs-lookup"><span data-stu-id="7d579-188">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="7d579-189">На панели **администратора** перейдите к средствам и **утилитам** и выберите **администратор Microsoft Teams интеграции.**</span><span class="sxs-lookup"><span data-stu-id="7d579-189">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="7d579-190">Выберите **Включить Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="7d579-190">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="7d579-191">Добавьте свой **microsoft Tenant ID** в доступное текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="7d579-191">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="7d579-192">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="7d579-192">Choose one of the following options:</span></span>

   - <span data-ttu-id="7d579-193">Если приложение имеет предварительное согласие, оно будет показывать небольшой контрольный знак.</span><span class="sxs-lookup"><span data-stu-id="7d579-193">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="7d579-194">Если закладки появляются, выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="7d579-194">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="7d579-195">Если согласие не утверждено, выполните описанные действия по генерации URL-адреса для согласия и отправьте его в глобальный администратор Microsoft 365 для утверждения.</span><span class="sxs-lookup"><span data-stu-id="7d579-195">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="7d579-196">После подтверждения утверждения выберите **retry,** чтобы подтвердить, а затем выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="7d579-196">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>

   ![Диалоговое окно, которое указывает, что доступ заблокирован](media/blocked-access.png)