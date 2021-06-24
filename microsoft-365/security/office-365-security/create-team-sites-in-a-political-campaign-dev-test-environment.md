---
title: Создание сайтов группы в среде разработки и тестирования для политической кампании
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: Сводка. Сведения о том, как создавать общедоступные, частные, конфиденциальные и строго конфиденциальные сайты групп SharePoint Online в среде разработки и тестирования для политической кампании.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80c975cd181f326fc2766c6ebfbd0d7f8a5164f2
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108155"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="9c44c-103">Создание сайтов групп в среде разработки и тестирования для политической кампании</span><span class="sxs-lookup"><span data-stu-id="9c44c-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9c44c-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="9c44c-104">**Applies to**</span></span>

- [<span data-ttu-id="9c44c-105">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="9c44c-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="9c44c-106">**Сводка.** Сведения о том, как создавать общедоступные, частные, конфиденциальные и строго конфиденциальные сайты групп SharePoint Online в среде разработки и тестирования для политической кампании.</span><span class="sxs-lookup"><span data-stu-id="9c44c-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span>

<span data-ttu-id="9c44c-p101">Инструкции из этой статьи позволят создать среду разработки и тестирования, которая включает четыре разных типа сайтов групп SharePoint Online для решения [Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Эти сайты подробно описаны в 10-й статье под названием **SharePoint и OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="9c44c-109">Этап 1. Создание среды разработки и тестирования для политической кампании</span><span class="sxs-lookup"><span data-stu-id="9c44c-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="9c44c-110">Сначала создайте подписки, пользователей и группы, следуя инструкциям из статьи [Настройка групп и пользователей в случае среды разработки и тестирования для политической кампании](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9c44c-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="9c44c-111">Этап 2. Создание меток.</span><span class="sxs-lookup"><span data-stu-id="9c44c-111">Phase 2: Create labels</span></span>

<span data-ttu-id="9c44c-112">На этом этапе вы создадите метки разных уровней защиты для папок документов на сайтах групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9c44c-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="9c44c-p102">При необходимости войдите в Центр администрирования Microsoft 365 (<https://admin.microsoft.com>) с использованием учетных данных учетной записи глобального администратора пробной подписки. Справочные сведения см. в статье [Вход в Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="9c44c-p102">If needed, sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) with the credentials of the global administrator account of your trial subscription. For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="9c44c-115">На **домашней странице** нажмите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-115">From the **Home** page where you start, click **Show all**.</span></span> <span data-ttu-id="9c44c-116">В появившемся разделе **Центры администрирования** нажмите **Соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-116">In the **Admin centers** section that appears, click **Compliance**.</span></span>

3. <span data-ttu-id="9c44c-117">С **домашней страницы** Центра соответствия требованиям Microsoft 365 перейдите в раздел **Решения** \> **Защита информации**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-117">From the **Home** page of the Microsoft 365 compliance center, go to the **Solutions** section \> **Information protection**.</span></span> <span data-ttu-id="9c44c-118">Чтобы сразу перейти на страницу **Защита информации**, используйте ссылку <https://compliance.microsoft.com//informationprotection>.</span><span class="sxs-lookup"><span data-stu-id="9c44c-118">To go directly to the **Information protection** page, use <https://compliance.microsoft.com//informationprotection>.</span></span>

4. <span data-ttu-id="9c44c-119">На странице **Защита информации** убедитесь, что выбран тег **Метка** и нажмите ![Значок "Создать метку"](../../media/m365-cc-sc-create-icon.png) **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-119">On the **Information protection** page, verify that the **Label** tag is selected, and then click  ![Create a label icon](../../media/m365-cc-sc-create-icon.png) **Create a label**.</span></span>

5. <span data-ttu-id="9c44c-120">Откроется мастер **Новая метка конфиденциальности**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-120">The **New sensitivity label** wizard opens.</span></span> <span data-ttu-id="9c44c-121">На шаге **Имя и описание** введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9c44c-121">On the **Name & description** step, enter the following values:</span></span>
   - <span data-ttu-id="9c44c-122">**Имя**: Тип **Внутренний**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-122">**Name**: Type **Internal**.</span></span>
   - <span data-ttu-id="9c44c-123">**Отображаемое имя**</span><span class="sxs-lookup"><span data-stu-id="9c44c-123">**Display name**</span></span>
   - <span data-ttu-id="9c44c-124">**Описание для пользователей**</span><span class="sxs-lookup"><span data-stu-id="9c44c-124">**Description for users**</span></span>

   <span data-ttu-id="9c44c-125">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-125">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9c44c-126">В области **Параметры метки** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-126">On the **Label settings** pane, click **Next**.</span></span>

7. <span data-ttu-id="9c44c-127">В области **Проверьте параметры** нажмите **Создать эту метку**, а затем — кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-127">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

8. <span data-ttu-id="9c44c-128">Повторите действия 5–8 для следующих меток:</span><span class="sxs-lookup"><span data-stu-id="9c44c-128">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="9c44c-129">Private</span><span class="sxs-lookup"><span data-stu-id="9c44c-129">Private</span></span>
   - <span data-ttu-id="9c44c-130">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="9c44c-130">Sensitive</span></span>
   - <span data-ttu-id="9c44c-131">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="9c44c-131">Highly Confidential</span></span>

9. <span data-ttu-id="9c44c-132">В области **Главная > Метки** щелкните **Опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-132">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="9c44c-133">В области **Выберите метки для публикации** щелкните **Выберите метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-133">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="9c44c-134">В области **Выбор меток** нажмите кнопку **Добавить** и выберите все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="9c44c-134">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="9c44c-135">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-135">Click **Done**.</span></span>

13. <span data-ttu-id="9c44c-136">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-136">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="9c44c-137">В области **Выберите расположения** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-137">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="9c44c-138">В области **Назовите политику** введите **Кампания** в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-138">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="9c44c-139">В области **Проверьте параметры** последовательно нажмите кнопки **Опубликовать метки** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-139">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="9c44c-140">Этап 3. Создание сайтов групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9c44c-140">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="9c44c-141">На этом этапе мы создадим и настроим сайты групп SharePoint Online для политической кампании, соответствующие четырем типам сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9c44c-141">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="9c44c-142">Общий сайт группы для кампании</span><span class="sxs-lookup"><span data-stu-id="9c44c-142">Campaign wide team site</span></span>

<span data-ttu-id="9c44c-143">Чтобы создать общедоступный сайт группы SharePoint Online с базовым уровнем защиты, выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9c44c-143">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="9c44c-144">При необходимости используйте браузер на локальном компьютере и войдите в Центр администрирования (<https://admin.microsoft.com>), используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9c44c-144">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="9c44c-145">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-145">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="9c44c-146">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-146">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="9c44c-147">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-147">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="9c44c-148">В поле **Имя сайта** введите **Общий сайт кампании**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-148">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="9c44c-149">В поле **Описание сайта группы** введите **Общий сайт SharePoint для кампании**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-149">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="9c44c-150">В разделе **Параметры конфиденциальности** выберите **Общедоступная группа: все в организации имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-150">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="9c44c-151">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-151">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="9c44c-152">Затем настройте папку документов на сайте группы "Общий сайт кампании" для использования метки "Внутренний".</span><span class="sxs-lookup"><span data-stu-id="9c44c-152">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="9c44c-153">На вкладке **Общий сайт кампании — главная** в браузере выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-153">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="9c44c-154">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-154">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="9c44c-155">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-155">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="9c44c-156">В разделе **Параметры — применение метки** выберите метку **Внутренний** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-156">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="9c44c-157">Сайт группы "Проект кампании 1"</span><span class="sxs-lookup"><span data-stu-id="9c44c-157">Campaign project 1 team site</span></span>

<span data-ttu-id="9c44c-158">Чтобы создать частный сайт группы SharePoint Online с базовым уровнем защиты для проекта в рамках кампании, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9c44c-158">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="9c44c-159">При необходимости используйте браузер на локальном компьютере и войдите в Центр администрирования (<https://admin.microsoft.com>), используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9c44c-159">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="9c44c-160">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-160">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="9c44c-161">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-161">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="9c44c-162">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-162">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="9c44c-163">В поле **Имя сайта** введите **Проект кампании 1**. </span><span class="sxs-lookup"><span data-stu-id="9c44c-163">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="9c44c-164">В поле **Описание сайта группы** введите **Сайт SharePoint для проекта кампании 1**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-164">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="9c44c-165">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-165">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="9c44c-166">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-166">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="9c44c-167">Затем настройте папку документов на сайте группы "Проект кампании 1" на использование метки "Частный".</span><span class="sxs-lookup"><span data-stu-id="9c44c-167">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="9c44c-168">На вкладке **Проект кампании 1 — главная** в браузере выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-168">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="9c44c-169">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-169">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="9c44c-170">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-170">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="9c44c-171">В разделе **Параметры — применение метки** выберите метку **Частный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-171">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="9c44c-172">Сайт группы "Маркетинг кампании"</span><span class="sxs-lookup"><span data-stu-id="9c44c-172">Campaign marketing team site</span></span>

<span data-ttu-id="9c44c-173">Чтобы создать изолированный сайт группы SharePoint Online с уровнем защиты для конфиденциальных данных в случае маркетинговых ресурсов кампании, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9c44c-173">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="9c44c-174">С помощью браузера на локальном компьютере войдите в Центр администрирования (<https://admin.microsoft.com>), используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9c44c-174">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="9c44c-175">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-175">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="9c44c-176">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-176">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="9c44c-177">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-177">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="9c44c-178">В поле **Имя сайта группы** введите **Маркетинг кампании**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-178">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="9c44c-179">В поле **Описание сайта группы** введите **Сайт SharePoint для маркетингового отдела кампании (конфиденциальный)**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-179">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="9c44c-180">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-180">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="9c44c-181">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-181">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="9c44c-182">Перейдите к новой вкладке **Маркетинг кампании** в браузере, а затем на панели инструментов нажмите значок параметров и выберите **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-182">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="9c44c-183">В области **Разрешения для сайта** щелкните **Дополнительные параметры разрешений**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="9c44c-184">На новой вкладке браузера **Разрешения** щелкните **Параметры запросов на доступ**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-184">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="9c44c-185">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить участникам приглашать других пользователей в группу участников сайта**, введите **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** в поле **Отправлять все запросы на доступ**, а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-185">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="9c44c-186">Выберите в списке пункт **Маркетинг кампании — участники**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-186">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="9c44c-187">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-187">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="9c44c-188">В диалоговом окне **Общий доступ** введите **Старший и стратегический персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-188">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="9c44c-189">Повторите этапы 14 и 15 для группы **Персонал отдела аналитики** и учетной записи **Обычная1**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-189">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="9c44c-190">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="9c44c-190">Click the back button on your browser.</span></span>

18. <span data-ttu-id="9c44c-191">Выберите в списке пункт **Маркетинг кампании — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-191">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="9c44c-192">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-192">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="9c44c-193">В диалоговом окне **Общий доступ** введите **ИТ-персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-193">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="9c44c-194">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="9c44c-194">Click the back button on your browser.</span></span>

22. <span data-ttu-id="9c44c-195">Закройте вкладку **Пользователи и группы** в браузере, перейдите на вкладку **Маркетинг кампании — главная** в браузере и закройте область **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-195">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="9c44c-196">Ниже приведены результаты настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="9c44c-196">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="9c44c-197">Группа SharePoint **Маркетинг кампании — участники** содержит только группу **Старший и стратегический персонал** (которая включает учетные записи "Кандидат", "НачальникШтаба" и "Стратег1"), группу **Маркетинг кампании** (которая включает учетную запись глобального администратора), группу **Персонал отдела аналитики** (которая включает учетную запись "ОбработчикДанных1") и учетную запись пользователя **Обычная1**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-197">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="9c44c-198">Группа SharePoint **Маркетинг кампании — владельцы** содержит только группу **ИТ-персонал**, которая включает только учетные записи ITAdmin1 и ITAdmin2.</span><span class="sxs-lookup"><span data-stu-id="9c44c-198">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="9c44c-199">Группа SharePoint **Маркетинг кампании — посетители** не содержит ни групп, ни учетных записей.</span><span class="sxs-lookup"><span data-stu-id="9c44c-199">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="9c44c-200">Участники не могут менять разрешения на уровне сайта (это могут делать только члены группы **Маркетинг кампании — владельцы**).</span><span class="sxs-lookup"><span data-stu-id="9c44c-200">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="9c44c-201">У других учетных записей нет доступа к сайту и его ресурсам, но они могут запрашивать доступ к сайту. При этом в почтовый ящик пользователя "ИТ-администратор1" отправляется электронное сообщение.</span><span class="sxs-lookup"><span data-stu-id="9c44c-201">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="9c44c-202">Теперь настройте папку документов на сайте группы "Маркетинг кампании" на использование метки "Конфиденциальный".</span><span class="sxs-lookup"><span data-stu-id="9c44c-202">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="9c44c-203">На вкладке **Маркетинг кампании — главная** в браузере выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-203">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="9c44c-204">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-204">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="9c44c-205">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-205">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="9c44c-206">В разделе **Параметры — применение метки** выберите метку **Конфиденциальный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-206">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="9c44c-p106">Настройте политику защиты от потери данных (DLP), которая уведомляет пользователей, когда они предоставляют доступ к документу на сайте группы SharePoint Online с меткой "Конфиденциальный" внешним пользователям. Такая политика будет применяться к ресурсам на сайте "Маркетинг кампании".</span><span class="sxs-lookup"><span data-stu-id="9c44c-p106">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="9c44c-209">На вкладке браузера **Домашняя страница Microsoft Office** щелкните плитку **Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-209">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="9c44c-210">На новой вкладке **Безопасность и соответствие требованиям** выберите **Защита от потери данных > Политика**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-210">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="9c44c-211">В области **Защита от потери данных** нажмите **+ Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-211">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="9c44c-212">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-212">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="9c44c-213">В области **Назовите политику** введите **Сайты групп SharePoint Online с меткой "Конфиденциальный"** в поле **Имя**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-213">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="9c44c-214">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-214">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="9c44c-215">В списке расположений отключите параметры **Электронная почта Exchange** и **Учетные записи OneDrive**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-215">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="9c44c-216">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-216">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="9c44c-217">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-217">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="9c44c-218">В области **Метки** нажмите кнопку **+ Добавить**, укажите метку **Конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-218">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="9c44c-219">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-219">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="9c44c-220">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-220">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="9c44c-221">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-221">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="9c44c-222">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-222">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="9c44c-223">В текстовом поле введите или вставьте следующее:</span><span class="sxs-lookup"><span data-stu-id="9c44c-223">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="9c44c-p107">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="9c44c-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="9c44c-227">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-227">Click **OK**.</span></span>

17. <span data-ttu-id="9c44c-228">В области **Что делать при обнаружении конфиденциальной информации?** снимите флажки **Запретить пользователям делиться контентом и ограничить доступ к совместно используемому содержимому**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-228">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="9c44c-229">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="9c44c-230">В области **Проверка параметров** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-230">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="9c44c-231">Сайт группы "Стратегия кампании"</span><span class="sxs-lookup"><span data-stu-id="9c44c-231">Campaign strategy team site</span></span>

<span data-ttu-id="9c44c-232">Чтобы создать изолированный сайт группы SharePoint Online с уровнем защиты строго конфиденциальных данных для стратегических ресурсов кампании, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9c44c-232">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="9c44c-233">При необходимости используйте браузер на локальном компьютере и войдите в Центр администрирования (<https://admin.microsoft.com>), используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9c44c-233">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="9c44c-234">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-234">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="9c44c-235">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-235">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="9c44c-236">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-236">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="9c44c-237">В поле **Имя сайта группы** введите **Стратегия кампании**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-237">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="9c44c-238">В поле **Описание сайта группы** введите **Сайт SharePoint для стратегии кампании (строго конфиденциальный)**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-238">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="9c44c-239">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-239">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="9c44c-240">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-240">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="9c44c-241">На новой вкладке **Стратегия кампании** браузера нажмите значок параметров на панели инструментов и выберите **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-241">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="9c44c-242">В области **Разрешения для сайта** щелкните **Дополнительные параметры разрешений**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-242">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="9c44c-243">На новой вкладке браузера **Разрешения** щелкните **Параметры запросов на доступ**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-243">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="9c44c-244">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить участникам приглашать других пользователей в группу участников сайта** (все три флажка должны быть сняты) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-244">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="9c44c-245">Выберите в списке пункт **Стратегия кампании — участники**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-245">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="9c44c-246">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-246">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="9c44c-247">В диалоговом окне **Общий доступ** введите **Старший и стратегический персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-247">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="9c44c-248">Выберите в списке группу **Стратегия кампании — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-248">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="9c44c-249">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-249">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="9c44c-250">В диалоговом окне **Общий доступ** введите **ИТ-персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-250">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="9c44c-251">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="9c44c-251">Click the back button on your browser.</span></span>

20. <span data-ttu-id="9c44c-252">Закройте вкладку **Пользователи и группы** в браузере, перейдите на вкладку **Стратегия кампании — главная** в браузере и закройте область **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-252">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="9c44c-253">Ниже приведены результаты настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="9c44c-253">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="9c44c-254">Группа SharePoint **Стратегия кампании — участники** содержит только группу **Старший и стратегический персонал** (которая включает только учетные записи "Кандидат", "НачальникШтаба" и "Стратег1") и группу **Стратегия кампании** (которая включает только учетную запись глобального администратора).
</span><span class="sxs-lookup"><span data-stu-id="9c44c-254">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="9c44c-255">Группа SharePoint **Стратегия кампании — владельцы** содержит только группу **ИТ-персонал**, которая включает только учетные записи ITAdmin1 и ITAdmin2.</span><span class="sxs-lookup"><span data-stu-id="9c44c-255">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="9c44c-256">Группа SharePoint **Стратегия кампании — посетители** не содержит ни групп, ни учетных записей.</span><span class="sxs-lookup"><span data-stu-id="9c44c-256">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="9c44c-257">Участники не могут менять разрешения на уровне сайта (это могут делать только члены группы **Стратегия кампании — владельцы**).</span><span class="sxs-lookup"><span data-stu-id="9c44c-257">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="9c44c-p108">Другие учетные записи пользователей не могут получать доступ к сайту и его ресурсам, а также запрашивать доступ к нему. Дополнительные разрешения для сайта должен задавать глобальный администратор или участник группы **Стратегия кампании — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-p108">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="9c44c-260">Затем настройте папку документов на сайте стратегической группы кампании на использование метки "Строго конфиденциальный".</span><span class="sxs-lookup"><span data-stu-id="9c44c-260">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="9c44c-261">На вкладке **Стратегия кампании — главная** в браузере выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-261">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="9c44c-262">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-262">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="9c44c-263">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-263">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="9c44c-264">В разделе **Параметры — применение метки** выберите метку **Строго конфиденциальный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-264">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="9c44c-p109">Настройте политику защиты от потери данных, которая блокирует попытки предоставить внешним пользователям доступ к документу на сайте группы SharePoint Online с меткой "Строго конфиденциальный". Такая политика будет применяться к ресурсам на сайте "Стратегия кампании".</span><span class="sxs-lookup"><span data-stu-id="9c44c-p109">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="9c44c-267">При необходимости используйте браузер на локальном компьютере и войдите в Центр администрирования (<https://admin.microsoft.com>) с помощью учетной записи, у которой есть роль администратора безопасности или администратора компании.</span><span class="sxs-lookup"><span data-stu-id="9c44c-267">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="9c44c-268">На вкладке браузера **Домашняя страница Microsoft Office** щелкните плитку **Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-268">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="9c44c-269">На новой вкладке **Безопасность и соответствие требованиям** выберите **Защита от потери данных > Политика**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-269">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="9c44c-270">В области **Защита от потери данных** нажмите **+ Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-270">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="9c44c-271">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-271">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="9c44c-272">В области **Назовите политику** введите **Сайты групп SharePoint Online с меткой "Строго конфиденциальный"** в поле **Имя**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-272">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="9c44c-273">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-273">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="9c44c-274">В списке расположений отключите параметры **Электронная почта Exchange** и **Учетные записи OneDrive**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-274">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="9c44c-275">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-275">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="9c44c-276">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-276">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="9c44c-277">В области **Метки** нажмите кнопку **+ Добавить**, выберите метку **Строго конфиденциальный**, нажмите **Добавить**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-277">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="9c44c-278">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-278">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="9c44c-279">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-279">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="9c44c-280">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-280">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="9c44c-281">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-281">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="9c44c-282">В текстовом поле введите или вставьте следующее:</span><span class="sxs-lookup"><span data-stu-id="9c44c-282">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="9c44c-p110">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="9c44c-p110">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="9c44c-286">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-286">Click **OK**.</span></span>

18. <span data-ttu-id="9c44c-287">В области **Что делать при обнаружении конфиденциальной информации?** выберите **Требовать коммерческое обоснование для переопределения**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-287">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="9c44c-288">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-288">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="9c44c-289">В области **Проверка параметров** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-289">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="9c44c-290">Следуйте инструкциям, приведенным в статье [Активация службы управления правами Azure с помощью центра администрирования Microsoft 365](/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="9c44c-290">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="9c44c-291">Затем настройте для Azure Information Protection новую политику области и вложенную метку для защиты и разрешений, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9c44c-291">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="9c44c-p111">Войдите в центр администрирования, используя учетную запись с ролью администратора компании или администратора безопасности. Справочные сведения см. в статье [Вход в Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="9c44c-p111">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="9c44c-294">Перейдите на портал Azure (<https://portal.azure.com>), открыв отдельную вкладку браузера.</span><span class="sxs-lookup"><span data-stu-id="9c44c-294">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="9c44c-295">Введите в области поиска запрос **information**, а затем выберите **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-295">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="9c44c-296">Выберите **Метки**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-296">Click **Labels**.</span></span>

5. <span data-ttu-id="9c44c-297">Щелкните правой кнопкой мыши метку **Строго конфиденциально** и выберите элемент **Добавить подчин. метку**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-297">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="9c44c-298">Введите **СтратегияКампании** в поле **Имя** и **Метка для документов на сайте группы "Стратегия кампании"** в поле **Описание**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-298">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="9c44c-299">В разделе **Задайте разрешения для документов и электронных писем, имеющих эту метку** нажмите кнопку **Защитить**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-299">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="9c44c-300">В разделе **Защита** выберите элемент **Azure (облачный ключ)**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-300">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="9c44c-301">В колонке **Защита** в разделе **Параметры защиты** нажмите кнопку **+ Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-301">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="9c44c-302">Перейдите к колонке **Добавление разрешений** и выберите **+ Обзор каталога** в разделе **Укажите пользователей и группы**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-302">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="9c44c-303">В области **Пользователи и группы AAD** выберите группу **Старший и стратегический персонал** и нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-303">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="9c44c-304">В разделе **Выбрать из предустановленных разрешений или задать пользовательские** выберите вариант **Пользовательские**, а затем установите флажки **Просмотреть права**, **Изменить контент**, **Сохранить**, **Ответить** и **Ответить всем**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-304">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="9c44c-305">Дважды нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-305">Click **OK** twice.</span></span>

14. <span data-ttu-id="9c44c-306">В колонке **Подчиненная метка** нажмите кнопку **Сохранить**, а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-306">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="9c44c-307">В колонке **Azure Information Protection** щелкните элементы **Политики > + Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-307">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="9c44c-308">Введите **СтратегияКампании** в поле **Имя** и **Документы на сайте группы "Стратегия кампании"** в поле **Описание**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-308">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="9c44c-309">Щелкните **Выберите, к каким пользователям или группам будет применяться эта политика > Пользователи или группы**, а затем выберите **Старший и стратегический персонал**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-309">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="9c44c-310">Щелкните **Выбрать\> ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-310">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="9c44c-p112">Выберите элемент **Добавить или удалить метки**. На панели **Политики: добавление и удаление меток** нажмите **СтратегияКампании**, а затем — **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-p112">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="9c44c-313">Нажмите кнопку **Сохранить**, а затем — **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-313">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="9c44c-314">Теперь вы можете создавать документы на этих четырех сайтах и тестировать доступ к ним с помощью различных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="9c44c-314">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="9c44c-315">Чтобы защитить документ с помощью Azure Information Protection и этой новой метки, необходимо [установить клиент Azure Information Protection](/information-protection/rms-client/install-client-app) на тестовой машине, установить Office с помощью центра администрирования и затем выполнить вход из Microsoft Word с помощью учетной записи в группе пробной подписки **старшего персонала и специалистов по стратегии**.</span><span class="sxs-lookup"><span data-stu-id="9c44c-315">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c44c-316">См. также</span><span class="sxs-lookup"><span data-stu-id="9c44c-316">See Also</span></span>

[<span data-ttu-id="9c44c-317">Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций</span><span class="sxs-lookup"><span data-stu-id="9c44c-317">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="9c44c-318">Настройка групп и пользователей в случае среды разработки и тестирования для политической кампании</span><span class="sxs-lookup"><span data-stu-id="9c44c-318">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="9c44c-319">Руководства по лаборатории тестирования для облачных решений</span><span class="sxs-lookup"><span data-stu-id="9c44c-319">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="9c44c-320">Центр архитектуры и решений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c44c-320">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)
