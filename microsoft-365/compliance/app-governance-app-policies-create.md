---
title: Создание политик приложений
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Создание политик приложений.
ms.openlocfilehash: 17417d7fac80f2763edbbaa8dbb2c8be16e47371
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420426"
---
# <a name="create-app-policies"></a><span data-ttu-id="a63d9-103">Создание политик приложений</span><span class="sxs-lookup"><span data-stu-id="a63d9-103">Create app policies</span></span>

><span data-ttu-id="a63d9-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a63d9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a63d9-105">Наряду со встроенным набором возможностей для обнаружения аномального поведения приложений и создания оповещений, политики приложений в системе управления приложениями Майкрософт позволяют:</span><span class="sxs-lookup"><span data-stu-id="a63d9-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="a63d9-106">Указывать условия, на основании которых система управления приложениями может оповещать вас о поведении приложений для автоматического или ручного исправления.</span><span class="sxs-lookup"><span data-stu-id="a63d9-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="a63d9-107">Реализовать политики приложений по соответствию требованиям для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a63d9-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="a63d9-108">Политики приложений можно создавать на основе предоставленных настраиваемых шаблонов, а также можно создать собственную политику приложений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="a63d9-109">Чтобы создать новую политику приложений, перейдите в раздел **Центр соответствия требованиям Microsoft 365 > Защита приложений и управление ими > Обзор > Политики**:</span><span class="sxs-lookup"><span data-stu-id="a63d9-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App protection & governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="a63d9-110">Чтобы создать политику приложений на основе шаблонов, предназначенных для использования приложений, выберите **Создать политику** в разделе **Создание политики использования приложений**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="a63d9-111">Чтобы создать политику приложений на основе шаблонов, предназначенных для разрешений приложений, выберите **Создать политику** в разделе **Создание политики разрешений**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="a63d9-112">Чтобы создать политику приложений для сертификации приложения или для настраиваемой политики, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="a63d9-113">Шаблоны политики приложений</span><span class="sxs-lookup"><span data-stu-id="a63d9-113">App policy templates</span></span>

<span data-ttu-id="a63d9-114">Чтобы создать политику приложений на основе шаблона политики приложений, на странице **Выбор шаблона политики приложений** выберите категорию шаблона приложения, задайте имя шаблона и затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="a63d9-115">В системе управления приложениями есть три категории шаблонов политик приложений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="a63d9-116">Доступ пользователей и данных к приложению</span><span class="sxs-lookup"><span data-stu-id="a63d9-116">App users and data access</span></span>

<span data-ttu-id="a63d9-117">Управление приложениями включает следующие шаблоны для создания оповещений об использовании приложений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="a63d9-118">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="a63d9-118">Template name</span></span> | <span data-ttu-id="a63d9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a63d9-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="a63d9-120">Новое приложение с доступом к большому объему данных</span><span class="sxs-lookup"><span data-stu-id="a63d9-120">New app with a high volume of data access</span></span> | <span data-ttu-id="a63d9-121">Выделяет недавно зарегистрированные приложения с доступом к большому объему данных, чтобы обеспечить предсказуемость шаблонов этих данных.</span><span class="sxs-lookup"><span data-stu-id="a63d9-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="a63d9-122">По умолчанию эта политика помечает все приложения, которые были зарегистрированы за последние 7 дней и которые имели доступ к более чем 1 ГБ данных за этот период.</span><span class="sxs-lookup"><span data-stu-id="a63d9-122">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period.</span></span> <span data-ttu-id="a63d9-123">Эту политику можно настроить с помощью дополнительных условий и действий.</span><span class="sxs-lookup"><span data-stu-id="a63d9-123">This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="a63d9-124">Разрешения приложений</span><span class="sxs-lookup"><span data-stu-id="a63d9-124">App Permissions</span></span>

<span data-ttu-id="a63d9-125">Управление приложениями включает следующие шаблоны для создания оповещений для разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="a63d9-126">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="a63d9-126">Template name</span></span> | <span data-ttu-id="a63d9-127">Описание</span><span class="sxs-lookup"><span data-stu-id="a63d9-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="a63d9-128">Приложения с избыточными правами</span><span class="sxs-lookup"><span data-stu-id="a63d9-128">Overprivileged apps</span></span> | <span data-ttu-id="a63d9-129">Выделяет все приложения, которым предоставлено больше разрешений, чем они используют, для выявления возможностей сокращения разрешений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="a63d9-130">По умолчанию эта политика помечает все приложения, которые помечены как приложения с избыточными правами, если они не используются в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="a63d9-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="a63d9-131">Фильтр периода времени можно настроить с помощью дополнительных условий и действий.</span><span class="sxs-lookup"><span data-stu-id="a63d9-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="a63d9-132">Новое приложение с разрешениями с высоким уровнем привилегий</span><span class="sxs-lookup"><span data-stu-id="a63d9-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="a63d9-133">Выделяет все новые приложения с разрешениями с высоким уровнем привилегий для выявления потенциально важных приложений, которые могут потребовать дальнейших исследований.</span><span class="sxs-lookup"><span data-stu-id="a63d9-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="a63d9-134">По умолчанию эта политика помечает все приложения, зарегистрированные за последние 7 дней и имеющие широкий спектр разрешений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="a63d9-135">Сертификация приложения</span><span class="sxs-lookup"><span data-stu-id="a63d9-135">App certification</span></span>

<span data-ttu-id="a63d9-136">Управление приложениями включает следующие шаблоны для создания оповещений для сертификации приложений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="a63d9-137">Имя шаблона</span><span class="sxs-lookup"><span data-stu-id="a63d9-137">Template name</span></span> | <span data-ttu-id="a63d9-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a63d9-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="a63d9-139">Новое несертифицированное приложение</span><span class="sxs-lookup"><span data-stu-id="a63d9-139">New uncertified app</span></span> | <span data-ttu-id="a63d9-140">Выделяет новые приложения, которые еще не прошли сертификацию, чтобы убедиться, что они ожидаются в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a63d9-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="a63d9-141">По умолчанию эта политика помечает все приложения, зарегистрированные за последние 7 дней и не прошедшие сертификацию.</span><span class="sxs-lookup"><span data-stu-id="a63d9-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="a63d9-142">Настраиваемые политики приложений</span><span class="sxs-lookup"><span data-stu-id="a63d9-142">Custom app policies</span></span>

<span data-ttu-id="a63d9-143">Используйте настраиваемую политику приложений, когда необходимое вам действие не покрывается ни одним из встроенных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="a63d9-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="a63d9-144">Чтобы создать настраиваемую политику приложений, сначала выберите **Создать** на странице **Политики**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="a63d9-145">На странице **Выбор шаблона политики приложений** выберите категорию **Настраиваемая**, затем шаблон **Настраиваемая политика**, а после нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="a63d9-146">На странице **Название и описание** настройте следующее:</span><span class="sxs-lookup"><span data-stu-id="a63d9-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="a63d9-147">Имя политики</span><span class="sxs-lookup"><span data-stu-id="a63d9-147">Policy Name</span></span>

- <span data-ttu-id="a63d9-148">Описание политики</span><span class="sxs-lookup"><span data-stu-id="a63d9-148">Policy Description</span></span>

- <span data-ttu-id="a63d9-149">Выберите уровень серьезности политики, который определяет уровень серьезности оповещений, создаваемых этой политикой.</span><span class="sxs-lookup"><span data-stu-id="a63d9-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="a63d9-150">Высокий</span><span class="sxs-lookup"><span data-stu-id="a63d9-150">High</span></span>
  - <span data-ttu-id="a63d9-151">Средний</span><span class="sxs-lookup"><span data-stu-id="a63d9-151">Medium</span></span>
  - <span data-ttu-id="a63d9-152">Низкий</span><span class="sxs-lookup"><span data-stu-id="a63d9-152">Low</span></span>

<span data-ttu-id="a63d9-153">На странице **Выбор параметров и условий политики** в разделе **Выбор приложений, к которым применима эта политика** выберите:</span><span class="sxs-lookup"><span data-stu-id="a63d9-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="a63d9-154">Все приложения</span><span class="sxs-lookup"><span data-stu-id="a63d9-154">All Apps</span></span>
- <span data-ttu-id="a63d9-155">Выбор определенных приложений</span><span class="sxs-lookup"><span data-stu-id="a63d9-155">Choose specific apps</span></span>

  <span data-ttu-id="a63d9-156">На панели можно выбрать одно или несколько приложений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="a63d9-157">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-157">Select **Add**.</span></span>

<span data-ttu-id="a63d9-158">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-158">Select **Next**.</span></span>

<span data-ttu-id="a63d9-159">На странице **Выбор параметров и условий политики** выберите **Установить новые условия для политики**, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="a63d9-160">На панели **Создание правила** можно выбрать условия для нового правила.</span><span class="sxs-lookup"><span data-stu-id="a63d9-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="a63d9-161">Нажмите **Добавить условие** и выберите условие из списка, а затем укажите значение условия.</span><span class="sxs-lookup"><span data-stu-id="a63d9-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="a63d9-162">Можно добавлять несколько условий.</span><span class="sxs-lookup"><span data-stu-id="a63d9-162">You can add multiple conditions.</span></span>

<span data-ttu-id="a63d9-163">Ниже перечислены доступные условия для настраиваемой политики приложений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="a63d9-164">Условие</span><span class="sxs-lookup"><span data-stu-id="a63d9-164">Condition</span></span> | <span data-ttu-id="a63d9-165">Допустимые значения условия</span><span class="sxs-lookup"><span data-stu-id="a63d9-165">Condition values accepted</span></span> | <span data-ttu-id="a63d9-166">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a63d9-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="a63d9-167">Возраст регистрации приложения</span><span class="sxs-lookup"><span data-stu-id="a63d9-167">App registration age</span></span> | <span data-ttu-id="a63d9-168">В течение последних X дней</span><span class="sxs-lookup"><span data-stu-id="a63d9-168">Within last X days</span></span> |  |
| <span data-ttu-id="a63d9-169">Сертификация приложения</span><span class="sxs-lookup"><span data-stu-id="a63d9-169">App certification</span></span> | <span data-ttu-id="a63d9-170">Базовое соответствие требованиям, соответствие требованиям MCAS или не применимо</span><span class="sxs-lookup"><span data-stu-id="a63d9-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="a63d9-171">Сертификация Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a63d9-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="a63d9-172">Проверка издателя</span><span class="sxs-lookup"><span data-stu-id="a63d9-172">Publisher verification</span></span> | <span data-ttu-id="a63d9-173">Да или нет</span><span class="sxs-lookup"><span data-stu-id="a63d9-173">Yes or No</span></span> | [<span data-ttu-id="a63d9-174">Проверка издателя</span><span class="sxs-lookup"><span data-stu-id="a63d9-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="a63d9-175">Разрешение приложения</span><span class="sxs-lookup"><span data-stu-id="a63d9-175">Application Permission</span></span> | <span data-ttu-id="a63d9-176">Выберите одно или несколько разрешений API из списка</span><span class="sxs-lookup"><span data-stu-id="a63d9-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="a63d9-177">Справочник по разрешениям Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="a63d9-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="a63d9-178">Делегированное разрешение</span><span class="sxs-lookup"><span data-stu-id="a63d9-178">Delegated Permission</span></span> | <span data-ttu-id="a63d9-179">Выберите одно или несколько разрешений API из списка</span><span class="sxs-lookup"><span data-stu-id="a63d9-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="a63d9-180">Справочник по разрешениям Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="a63d9-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="a63d9-181">Высокий уровень привилегий</span><span class="sxs-lookup"><span data-stu-id="a63d9-181">High privilege</span></span> | <span data-ttu-id="a63d9-182">Да или нет</span><span class="sxs-lookup"><span data-stu-id="a63d9-182">Yes or No</span></span> | <span data-ttu-id="a63d9-183">Это внутреннее обозначение, основанное на той же логике, которая используется MCAS.</span><span class="sxs-lookup"><span data-stu-id="a63d9-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="a63d9-184">Приложение с избыточными правами</span><span class="sxs-lookup"><span data-stu-id="a63d9-184">Overprivileged app</span></span> | <span data-ttu-id="a63d9-185">Да или нет</span><span class="sxs-lookup"><span data-stu-id="a63d9-185">Yes or No</span></span> | <span data-ttu-id="a63d9-186">Приложения, которым предоставлено больше разрешений, чем ими используется.</span><span class="sxs-lookup"><span data-stu-id="a63d9-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="a63d9-187">Доступ приложения к данным</span><span class="sxs-lookup"><span data-stu-id="a63d9-187">App data access</span></span> | <span data-ttu-id="a63d9-188">Доступ к данным размером более X ГБ в час</span><span class="sxs-lookup"><span data-stu-id="a63d9-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="a63d9-189">Тенденция доступа приложения к данным</span><span class="sxs-lookup"><span data-stu-id="a63d9-189">App data access trend</span></span> | <span data-ttu-id="a63d9-190">Увеличение использования данных на X% за последние 7 дней</span><span class="sxs-lookup"><span data-stu-id="a63d9-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="a63d9-191">Доступ приложения к API</span><span class="sxs-lookup"><span data-stu-id="a63d9-191">App API Access</span></span> | <span data-ttu-id="a63d9-192">Число вызовов API, превышающее X в час</span><span class="sxs-lookup"><span data-stu-id="a63d9-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="a63d9-193">Тенденция доступа приложения к API</span><span class="sxs-lookup"><span data-stu-id="a63d9-193">App API Access trend</span></span> | <span data-ttu-id="a63d9-194">Увеличение вызовов API на X% за последние 7 дней</span><span class="sxs-lookup"><span data-stu-id="a63d9-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="a63d9-195">Пользователи, давшие согласие</span><span class="sxs-lookup"><span data-stu-id="a63d9-195">Users consented</span></span> | <span data-ttu-id="a63d9-196">Пользователей, давших согласие: (более или менее) X</span><span class="sxs-lookup"><span data-stu-id="a63d9-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="a63d9-197">Приоритетный пользователь дал согласие</span><span class="sxs-lookup"><span data-stu-id="a63d9-197">Priority user consented</span></span> | <span data-ttu-id="a63d9-198">Да или нет</span><span class="sxs-lookup"><span data-stu-id="a63d9-198">Yes or No</span></span> | <span data-ttu-id="a63d9-199">Пользователь с [приоритетной учетной записью](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="a63d9-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="a63d9-200">Согласие на приложение получено от</span><span class="sxs-lookup"><span data-stu-id="a63d9-200">App consented by</span></span> | <span data-ttu-id="a63d9-201">Выберите пользователей из списка</span><span class="sxs-lookup"><span data-stu-id="a63d9-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="a63d9-202">Роль пользователя, давшего согласие</span><span class="sxs-lookup"><span data-stu-id="a63d9-202">Consenting user’s role</span></span> | <span data-ttu-id="a63d9-203">Выберите одну или несколько ролей: администратор Teams, читатели каталогов, читатель сведений о безопасности, администратор соответствия требованиям, администратор безопасности, администратор службы поддержки, администратор SharePoint, администратор Exchange, глобальный читатель, глобальный администратор, администратор данных соответствия требованиям, администратор пользователя, администратор поддержки служб</span><span class="sxs-lookup"><span data-stu-id="a63d9-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="a63d9-204">Разрешен выбор нескольких вариантов.</span><span class="sxs-lookup"><span data-stu-id="a63d9-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="a63d9-205">В этом списке должна быть доступна любая роль Azure AD с назначенным участником.</span><span class="sxs-lookup"><span data-stu-id="a63d9-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="a63d9-206">Рабочая нагрузка, к которой получен доступ</span><span class="sxs-lookup"><span data-stu-id="a63d9-206">Workload accessed</span></span> | <span data-ttu-id="a63d9-207">OneDrive и/или SharePoint и/или Exchange</span><span class="sxs-lookup"><span data-stu-id="a63d9-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="a63d9-208">Разрешен выбор нескольких вариантов.</span><span class="sxs-lookup"><span data-stu-id="a63d9-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="a63d9-209">Частота ошибок</span><span class="sxs-lookup"><span data-stu-id="a63d9-209">Error rate</span></span> | <span data-ttu-id="a63d9-210">Частота ошибок превышает X% за последние 7 дней, где значение X определяется администратором</span><span class="sxs-lookup"><span data-stu-id="a63d9-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="a63d9-211">Чтобы эта политика приложений применялась, должны быть выполнены все указанные условия.</span><span class="sxs-lookup"><span data-stu-id="a63d9-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="a63d9-212">После указания условий нажмите **Сохранить**, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="a63d9-213">Если вы хотите, чтобы система управления приложениями отключила приложение при создании оповещения на основе этой политики, на странице **Определение действий политики** выберите **Отключить приложение**, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="a63d9-214">На странице **Определение состояния политики** выберите один из перечисленных вариантов.</span><span class="sxs-lookup"><span data-stu-id="a63d9-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="a63d9-215">**Режим аудита**: политики оцениваются, но настроенные действия не выполняются.</span><span class="sxs-lookup"><span data-stu-id="a63d9-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="a63d9-216">Политики в режиме аудита отображаются с состоянием **Аудит** в списке политик.</span><span class="sxs-lookup"><span data-stu-id="a63d9-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="a63d9-217">**Активная**: политики оцениваются, и выполняются настроенные действия.</span><span class="sxs-lookup"><span data-stu-id="a63d9-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="a63d9-218">**Неактивная**: политики не оцениваются, и настроенные действия не выполняются.</span><span class="sxs-lookup"><span data-stu-id="a63d9-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="a63d9-219">Тестирование и мониторинг новой политики приложений</span><span class="sxs-lookup"><span data-stu-id="a63d9-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="a63d9-220">Теперь, когда политика приложений создана, необходимо отслеживать ее на странице **Политики**, чтобы убедиться, что она регистрирует ожидаемое количество активных оповещений и общее количество оповещений во время тестирования.</span><span class="sxs-lookup"><span data-stu-id="a63d9-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![Страница сводки политик MAPG в Центре соответствия требованиям Microsoft 365 с выделенной политикой](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="a63d9-222">Если количество оповещений неожиданно низкое, перед установкой состояния политики приложений отредактируйте ее параметры, чтобы убедиться, что настройка сделана правильно.</span><span class="sxs-lookup"><span data-stu-id="a63d9-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="a63d9-223">Ниже показан пример процесса создания новой политики, ее тестирования и активации.</span><span class="sxs-lookup"><span data-stu-id="a63d9-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="a63d9-224">Создайте новую политику с начальными значениями для уровня серьезности, приложений, условий и действий и со значением состояния **Режим аудита**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="a63d9-225">Проверьте ожидаемое поведение, например созданные оповещения.</span><span class="sxs-lookup"><span data-stu-id="a63d9-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="a63d9-226">Если поведение не соответствует ожидаемому, отредактируйте приложения политики, условия и параметры действий по мере необходимости и вернитесь к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="a63d9-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="a63d9-227">Если поведение соответствует ожидаемому, измените политику и переведите ее состояние в **Активная**.</span><span class="sxs-lookup"><span data-stu-id="a63d9-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![Рабочий процесс создания политики приложений](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="a63d9-229">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="a63d9-229">Next step</span></span>

[<span data-ttu-id="a63d9-230">Управление политиками приложений.</span><span class="sxs-lookup"><span data-stu-id="a63d9-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
