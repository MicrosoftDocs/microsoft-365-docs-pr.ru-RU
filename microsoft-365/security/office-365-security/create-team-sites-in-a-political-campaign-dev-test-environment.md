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
ms.openlocfilehash: 1f3488b479b4d37b7e38e4ced0d612e8fb5ae8a0
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165479"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="627b8-103">Создание сайтов групп в среде разработки и тестирования для политической кампании</span><span class="sxs-lookup"><span data-stu-id="627b8-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="627b8-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="627b8-104">**Applies to**</span></span>

- [<span data-ttu-id="627b8-105">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="627b8-105">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- 
 <span data-ttu-id="627b8-106">**Сводка.** Сведения о том, как создавать общедоступные, частные, конфиденциальные и строго конфиденциальные сайты групп SharePoint Online в среде разработки и тестирования для политической кампании.</span><span class="sxs-lookup"><span data-stu-id="627b8-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
   
<span data-ttu-id="627b8-p101">Инструкции из этой статьи позволят создать среду разработки и тестирования, которая включает четыре разных типа сайтов групп SharePoint Online для решения [Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Эти сайты подробно описаны в 10-й статье под названием **SharePoint и OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="627b8-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="627b8-109">Этап 1. Создание среды разработки и тестирования для политической кампании</span><span class="sxs-lookup"><span data-stu-id="627b8-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="627b8-110">Сначала создайте подписки, пользователей и группы, следуя инструкциям из статьи [Настройка групп и пользователей в случае среды разработки и тестирования для политической кампании](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="627b8-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="627b8-111">Этап 2. Создание меток.</span><span class="sxs-lookup"><span data-stu-id="627b8-111">Phase 2: Create labels</span></span>

<span data-ttu-id="627b8-112">На этом этапе вы создадите метки разных уровней защиты для папок документов на сайтах групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="627b8-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="627b8-113">При необходимости войдите в Центр администрирования, используя учетные данные глобального администратора пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="627b8-113">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="627b8-114">Справку см. в статье [Вход в Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="627b8-114">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="627b8-115">На вкладке **Домашняя страница Microsoft Office** щелкните плитку **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="627b8-115">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>

3. <span data-ttu-id="627b8-116">На новой вкладке браузера **Центр администрирования Microsoft 365** выберите **Центры администрирования > Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="627b8-116">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>

4. <span data-ttu-id="627b8-117">На новой вкладке браузера **Главная — безопасность и соответствие требованиям** выберите **Классификации > Метки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-117">From the new **Home - Security & Compliance** tab of your browser, click **Classifications > Labels**.</span></span>

5. <span data-ttu-id="627b8-118">В области **Главная > Метки** нажмите кнопку **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="627b8-118">From the **Home > Labels** pane, click **Create a label**.</span></span>

6. <span data-ttu-id="627b8-119">В области **Назовите метку** введите **Внутренний**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-119">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>

7. <span data-ttu-id="627b8-120">В области **Параметры метки** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-120">On the **Label settings** pane, click **Next**.</span></span>

8. <span data-ttu-id="627b8-121">В области **Проверьте параметры** нажмите **Создать эту метку**, а затем — кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="627b8-121">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

9. <span data-ttu-id="627b8-122">Повторите действия 5–8 для следующих меток:</span><span class="sxs-lookup"><span data-stu-id="627b8-122">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="627b8-123">Private</span><span class="sxs-lookup"><span data-stu-id="627b8-123">Private</span></span>
   - <span data-ttu-id="627b8-124">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="627b8-124">Sensitive</span></span>
   - <span data-ttu-id="627b8-125">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="627b8-125">Highly Confidential</span></span>

10. <span data-ttu-id="627b8-126">В области **Главная > Метки** щелкните **Опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>

11. <span data-ttu-id="627b8-127">В области **Выберите метки для публикации** щелкните **Выберите метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="627b8-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

12. <span data-ttu-id="627b8-128">В области **Выбор меток** нажмите кнопку **Добавить** и выберите все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="627b8-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

13. <span data-ttu-id="627b8-129">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="627b8-129">Click **Done**.</span></span>

14. <span data-ttu-id="627b8-130">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-130">On the **Choose labels to publish** pane, click **Next**.</span></span>

15. <span data-ttu-id="627b8-131">В области **Выберите расположения** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-131">On the **Choose locations** pane, click **Next**.</span></span>

16. <span data-ttu-id="627b8-132">В области **Назовите политику** введите **Кампания** в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-132">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

17. <span data-ttu-id="627b8-133">В области **Проверьте параметры** последовательно нажмите кнопки **Опубликовать метки** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="627b8-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="627b8-134">Этап 3. Создание сайтов групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="627b8-134">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="627b8-135">На этом этапе мы создадим и настроим сайты групп SharePoint Online для политической кампании, соответствующие четырем типам сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="627b8-135">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="627b8-136">Общий сайт группы для кампании</span><span class="sxs-lookup"><span data-stu-id="627b8-136">Campaign wide team site</span></span>

<span data-ttu-id="627b8-137">Чтобы создать общедоступный сайт группы SharePoint Online с базовым уровнем защиты, выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="627b8-137">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="627b8-138">При необходимости используйте браузер на локальном компьютере и войдите в Центр администрирования (<https://admin.microsoft.com>), используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="627b8-138">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="627b8-139">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="627b8-139">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="627b8-140">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="627b8-140">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="627b8-141">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-141">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="627b8-142">В поле **Имя сайта** введите **Общий сайт кампании**.</span><span class="sxs-lookup"><span data-stu-id="627b8-142">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="627b8-143">В поле **Описание сайта группы** введите **Общий сайт SharePoint для кампании**.</span><span class="sxs-lookup"><span data-stu-id="627b8-143">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="627b8-144">В разделе **Параметры конфиденциальности** выберите **Общедоступная группа: все в организации имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-144">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="627b8-145">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="627b8-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="627b8-146">Затем настройте папку документов на сайте группы "Общий сайт кампании" для использования метки "Внутренний".</span><span class="sxs-lookup"><span data-stu-id="627b8-146">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="627b8-147">На вкладке **Общий сайт кампании — главная** в браузере выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-147">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="627b8-148">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-148">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="627b8-149">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="627b8-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="627b8-150">В разделе **Параметры — применение метки** выберите метку **Внутренний** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-150">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="627b8-151">Сайт группы "Проект кампании 1"</span><span class="sxs-lookup"><span data-stu-id="627b8-151">Campaign project 1 team site</span></span>

<span data-ttu-id="627b8-152">Чтобы создать частный сайт группы SharePoint Online с базовым уровнем защиты для проекта в рамках кампании, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="627b8-152">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="627b8-153">При необходимости используйте браузер на локальном компьютере и войдите в Центр администрирования (<https://admin.microsoft.com>), используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="627b8-153">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="627b8-154">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="627b8-154">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="627b8-155">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="627b8-155">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="627b8-156">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-156">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="627b8-157">В поле **Имя сайта** введите **Проект кампании 1**. </span><span class="sxs-lookup"><span data-stu-id="627b8-157">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="627b8-158">В поле **Описание сайта группы** введите **Сайт SharePoint для проекта кампании 1**.</span><span class="sxs-lookup"><span data-stu-id="627b8-158">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="627b8-159">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-159">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="627b8-160">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="627b8-160">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="627b8-161">Затем настройте папку документов на сайте группы "Проект кампании 1" на использование метки "Частный".</span><span class="sxs-lookup"><span data-stu-id="627b8-161">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="627b8-162">На вкладке **Проект кампании 1 — главная** в браузере выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-162">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="627b8-163">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-163">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="627b8-164">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="627b8-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="627b8-165">В разделе **Параметры — применение метки** выберите метку **Частный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-165">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="627b8-166">Сайт группы "Маркетинг кампании"</span><span class="sxs-lookup"><span data-stu-id="627b8-166">Campaign marketing team site</span></span>

<span data-ttu-id="627b8-167">Чтобы создать изолированный сайт группы SharePoint Online с уровнем защиты для конфиденциальных данных в случае маркетинговых ресурсов кампании, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="627b8-167">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="627b8-168">С помощью браузера на локальном компьютере войдите в Центр администрирования (<https://admin.microsoft.com>), используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="627b8-168">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="627b8-169">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="627b8-169">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="627b8-170">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="627b8-170">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="627b8-171">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-171">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="627b8-172">В поле **Имя сайта группы** введите **Маркетинг кампании**.</span><span class="sxs-lookup"><span data-stu-id="627b8-172">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="627b8-173">В поле **Описание сайта группы** введите **Сайт SharePoint для маркетингового отдела кампании (конфиденциальный)**.</span><span class="sxs-lookup"><span data-stu-id="627b8-173">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="627b8-174">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-174">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="627b8-175">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="627b8-175">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="627b8-176">Перейдите к новой вкладке **Маркетинг кампании** в браузере, а затем на панели инструментов нажмите значок параметров и выберите **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="627b8-176">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="627b8-177">В области **Разрешения для сайта** щелкните **Дополнительные параметры разрешений**.</span><span class="sxs-lookup"><span data-stu-id="627b8-177">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="627b8-178">На новой вкладке браузера **Разрешения** щелкните **Параметры запросов на доступ**.</span><span class="sxs-lookup"><span data-stu-id="627b8-178">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="627b8-179">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить участникам приглашать других пользователей в группу участников сайта**, введите **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** в поле **Отправлять все запросы на доступ**, а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-179">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="627b8-180">Выберите в списке пункт **Маркетинг кампании — участники**.</span><span class="sxs-lookup"><span data-stu-id="627b8-180">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="627b8-181">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="627b8-181">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="627b8-182">В диалоговом окне **Общий доступ** введите **Старший и стратегический персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="627b8-182">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="627b8-183">Повторите этапы 14 и 15 для группы **Персонал отдела аналитики** и учетной записи **Обычная1**.</span><span class="sxs-lookup"><span data-stu-id="627b8-183">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="627b8-184">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="627b8-184">Click the back button on your browser.</span></span>

18. <span data-ttu-id="627b8-185">Выберите в списке пункт **Маркетинг кампании — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-185">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="627b8-186">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="627b8-186">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="627b8-187">В диалоговом окне **Общий доступ** введите **ИТ-персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="627b8-187">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="627b8-188">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="627b8-188">Click the back button on your browser.</span></span>

22. <span data-ttu-id="627b8-189">Закройте вкладку **Пользователи и группы** в браузере, перейдите на вкладку **Маркетинг кампании — главная** в браузере и закройте область **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="627b8-189">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="627b8-190">Ниже приведены результаты настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="627b8-190">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="627b8-191">Группа SharePoint **Маркетинг кампании — участники** содержит только группу **Старший и стратегический персонал** (которая включает учетные записи "Кандидат", "НачальникШтаба" и "Стратег1"), группу **Маркетинг кампании** (которая включает учетную запись глобального администратора), группу **Персонал отдела аналитики** (которая включает учетную запись "ОбработчикДанных1") и учетную запись пользователя **Обычная1**.</span><span class="sxs-lookup"><span data-stu-id="627b8-191">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="627b8-192">Группа SharePoint **Маркетинг кампании — владельцы** содержит только группу **ИТ-персонал**, которая включает только учетные записи ITAdmin1 и ITAdmin2.</span><span class="sxs-lookup"><span data-stu-id="627b8-192">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="627b8-193">Группа SharePoint **Маркетинг кампании — посетители** не содержит ни групп, ни учетных записей.</span><span class="sxs-lookup"><span data-stu-id="627b8-193">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="627b8-194">Участники не могут менять разрешения на уровне сайта (это могут делать только члены группы **Маркетинг кампании — владельцы**).</span><span class="sxs-lookup"><span data-stu-id="627b8-194">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="627b8-195">У других учетных записей нет доступа к сайту и его ресурсам, но они могут запрашивать доступ к сайту. При этом в почтовый ящик пользователя "ИТ-администратор1" отправляется электронное сообщение.</span><span class="sxs-lookup"><span data-stu-id="627b8-195">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="627b8-196">Теперь настройте папку документов на сайте группы "Маркетинг кампании" на использование метки "Конфиденциальный".</span><span class="sxs-lookup"><span data-stu-id="627b8-196">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="627b8-197">На вкладке **Маркетинг кампании — главная** в браузере выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-197">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="627b8-198">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-198">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="627b8-199">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="627b8-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="627b8-200">В разделе **Параметры — применение метки** выберите метку **Конфиденциальный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-200">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="627b8-p103">Настройте политику защиты от потери данных (DLP), которая уведомляет пользователей, когда они предоставляют доступ к документу на сайте группы SharePoint Online с меткой "Конфиденциальный" внешним пользователям. Такая политика будет применяться к ресурсам на сайте "Маркетинг кампании".</span><span class="sxs-lookup"><span data-stu-id="627b8-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="627b8-203">На вкладке браузера **Домашняя страница Microsoft Office** щелкните плитку **Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="627b8-203">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="627b8-204">На новой вкладке **Безопасность и соответствие требованиям** выберите **Защита от потери данных > Политика**.</span><span class="sxs-lookup"><span data-stu-id="627b8-204">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="627b8-205">В области **Защита от потери данных** нажмите **+ Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="627b8-205">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="627b8-206">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-206">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="627b8-207">В области **Назовите политику** введите **Сайты групп SharePoint Online с меткой "Конфиденциальный"** в поле **Имя**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-207">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="627b8-208">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-208">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="627b8-209">В списке расположений отключите параметры **Электронная почта Exchange** и **Учетные записи OneDrive**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-209">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="627b8-210">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-210">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="627b8-211">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-211">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="627b8-212">В области **Метки** нажмите кнопку **+ Добавить**, укажите метку **Конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="627b8-212">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="627b8-213">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-213">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="627b8-214">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-214">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="627b8-215">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="627b8-215">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="627b8-216">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="627b8-216">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="627b8-217">В текстовом поле введите или вставьте следующее:</span><span class="sxs-lookup"><span data-stu-id="627b8-217">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="627b8-p104">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="627b8-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="627b8-221">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-221">Click **OK**.</span></span>

17. <span data-ttu-id="627b8-222">В области **Что делать при обнаружении конфиденциальной информации?** снимите флажки **Запретить пользователям делиться контентом и ограничить доступ к совместно используемому содержимому**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-222">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="627b8-223">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-223">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="627b8-224">В области **Проверка параметров** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="627b8-224">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="627b8-225">Сайт группы "Стратегия кампании"</span><span class="sxs-lookup"><span data-stu-id="627b8-225">Campaign strategy team site</span></span>

<span data-ttu-id="627b8-226">Чтобы создать изолированный сайт группы SharePoint Online с уровнем защиты строго конфиденциальных данных для стратегических ресурсов кампании, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="627b8-226">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="627b8-227">При необходимости используйте браузер на локальном компьютере и войдите в Центр администрирования (<https://admin.microsoft.com>), используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="627b8-227">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="627b8-228">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="627b8-228">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="627b8-229">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="627b8-229">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="627b8-230">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-230">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="627b8-231">В поле **Имя сайта группы** введите **Стратегия кампании**.</span><span class="sxs-lookup"><span data-stu-id="627b8-231">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="627b8-232">В поле **Описание сайта группы** введите **Сайт SharePoint для стратегии кампании (строго конфиденциальный)**.</span><span class="sxs-lookup"><span data-stu-id="627b8-232">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="627b8-233">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-233">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="627b8-234">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="627b8-234">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="627b8-235">На новой вкладке **Стратегия кампании** браузера нажмите значок параметров на панели инструментов и выберите **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="627b8-235">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="627b8-236">В области **Разрешения для сайта** щелкните **Дополнительные параметры разрешений**.</span><span class="sxs-lookup"><span data-stu-id="627b8-236">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="627b8-237">На новой вкладке браузера **Разрешения** щелкните **Параметры запросов на доступ**.</span><span class="sxs-lookup"><span data-stu-id="627b8-237">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="627b8-238">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить участникам приглашать других пользователей в группу участников сайта** (все три флажка должны быть сняты) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-238">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="627b8-239">Выберите в списке пункт **Стратегия кампании — участники**.</span><span class="sxs-lookup"><span data-stu-id="627b8-239">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="627b8-240">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="627b8-240">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="627b8-241">В диалоговом окне **Общий доступ** введите **Старший и стратегический персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="627b8-241">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="627b8-242">Выберите в списке группу **Стратегия кампании — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-242">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="627b8-243">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="627b8-243">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="627b8-244">В диалоговом окне **Общий доступ** введите **ИТ-персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="627b8-244">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="627b8-245">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="627b8-245">Click the back button on your browser.</span></span>

20. <span data-ttu-id="627b8-246">Закройте вкладку **Пользователи и группы** в браузере, перейдите на вкладку **Стратегия кампании — главная** в браузере и закройте область **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="627b8-246">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="627b8-247">Ниже приведены результаты настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="627b8-247">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="627b8-248">Группа SharePoint **Стратегия кампании — участники** содержит только группу **Старший и стратегический персонал** (которая включает только учетные записи "Кандидат", "НачальникШтаба" и "Стратег1") и группу **Стратегия кампании** (которая включает только учетную запись глобального администратора).
</span><span class="sxs-lookup"><span data-stu-id="627b8-248">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="627b8-249">Группа SharePoint **Стратегия кампании — владельцы** содержит только группу **ИТ-персонал**, которая включает только учетные записи ITAdmin1 и ITAdmin2.</span><span class="sxs-lookup"><span data-stu-id="627b8-249">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="627b8-250">Группа SharePoint **Стратегия кампании — посетители** не содержит ни групп, ни учетных записей.</span><span class="sxs-lookup"><span data-stu-id="627b8-250">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="627b8-251">Участники не могут менять разрешения на уровне сайта (это могут делать только члены группы **Стратегия кампании — владельцы**).</span><span class="sxs-lookup"><span data-stu-id="627b8-251">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="627b8-p105">Другие учетные записи пользователей не могут получать доступ к сайту и его ресурсам, а также запрашивать доступ к нему. Дополнительные разрешения для сайта должен задавать глобальный администратор или участник группы **Стратегия кампании — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="627b8-254">Затем настройте папку документов на сайте стратегической группы кампании на использование метки "Строго конфиденциальный".</span><span class="sxs-lookup"><span data-stu-id="627b8-254">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="627b8-255">На вкладке **Стратегия кампании — главная** в браузере выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-255">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="627b8-256">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-256">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="627b8-257">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="627b8-257">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="627b8-258">В разделе **Параметры — применение метки** выберите метку **Строго конфиденциальный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-258">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="627b8-p106">Настройте политику защиты от потери данных, которая блокирует попытки предоставить внешним пользователям доступ к документу на сайте группы SharePoint Online с меткой "Строго конфиденциальный". Такая политика будет применяться к ресурсам на сайте "Стратегия кампании".</span><span class="sxs-lookup"><span data-stu-id="627b8-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="627b8-261">При необходимости используйте браузер на локальном компьютере и войдите в Центр администрирования (<https://admin.microsoft.com>) с помощью учетной записи, у которой есть роль администратора безопасности или администратора компании.</span><span class="sxs-lookup"><span data-stu-id="627b8-261">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="627b8-262">На вкладке браузера **Домашняя страница Microsoft Office** щелкните плитку **Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="627b8-262">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="627b8-263">На новой вкладке **Безопасность и соответствие требованиям** выберите **Защита от потери данных > Политика**.</span><span class="sxs-lookup"><span data-stu-id="627b8-263">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="627b8-264">В области **Защита от потери данных** нажмите **+ Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="627b8-264">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="627b8-265">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-265">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="627b8-266">В области **Назовите политику** введите **Сайты групп SharePoint Online с меткой "Строго конфиденциальный"** в поле **Имя**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-266">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="627b8-267">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-267">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="627b8-268">В списке расположений отключите параметры **Электронная почта Exchange** и **Учетные записи OneDrive**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-268">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="627b8-269">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-269">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="627b8-270">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-270">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="627b8-271">В области **Метки** нажмите кнопку **+ Добавить**, выберите метку **Строго конфиденциальный**, нажмите **Добавить**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="627b8-271">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="627b8-272">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-272">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="627b8-273">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-273">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="627b8-274">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="627b8-274">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="627b8-275">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="627b8-275">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="627b8-276">В текстовом поле введите или вставьте следующее:</span><span class="sxs-lookup"><span data-stu-id="627b8-276">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="627b8-p107">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="627b8-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="627b8-280">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-280">Click **OK**.</span></span>

18. <span data-ttu-id="627b8-281">В области **Что делать при обнаружении конфиденциальной информации?** выберите **Требовать коммерческое обоснование для переопределения**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-281">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="627b8-282">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="627b8-282">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="627b8-283">В области **Проверка параметров** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="627b8-283">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="627b8-284">Следуйте инструкциям, приведенным в статье [Активация службы управления правами Azure с помощью центра администрирования Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="627b8-284">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="627b8-285">Затем настройте для Azure Information Protection новую политику области и вложенную метку для защиты и разрешений, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="627b8-285">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="627b8-286">Войдите в Центр администрирования, используя учетную запись с ролью администратора компании или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="627b8-286">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="627b8-287">Дополнительные сведения см. в статье [Вход в Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="627b8-287">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="627b8-288">Перейдите на портал Azure (<https://portal.azure.com>), открыв отдельную вкладку браузера.</span><span class="sxs-lookup"><span data-stu-id="627b8-288">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="627b8-289">Введите в области поиска запрос **information**, а затем выберите **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="627b8-289">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="627b8-290">Выберите **Метки**.</span><span class="sxs-lookup"><span data-stu-id="627b8-290">Click **Labels**.</span></span>

5. <span data-ttu-id="627b8-291">Щелкните правой кнопкой мыши метку **Строго конфиденциально** и выберите элемент **Добавить подчин. метку**.</span><span class="sxs-lookup"><span data-stu-id="627b8-291">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="627b8-292">Введите **СтратегияКампании** в поле **Имя** и **Метка для документов на сайте группы "Стратегия кампании"** в поле **Описание**.</span><span class="sxs-lookup"><span data-stu-id="627b8-292">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="627b8-293">В разделе **Задайте разрешения для документов и электронных писем, имеющих эту метку** нажмите кнопку **Защитить**.</span><span class="sxs-lookup"><span data-stu-id="627b8-293">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="627b8-294">В разделе **Защита** выберите элемент **Azure (облачный ключ)**.</span><span class="sxs-lookup"><span data-stu-id="627b8-294">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="627b8-295">В колонке **Защита** в разделе **Параметры защиты** нажмите кнопку **+ Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="627b8-295">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="627b8-296">Перейдите к колонке **Добавление разрешений** и выберите **+ Обзор каталога** в разделе **Укажите пользователей и группы**.</span><span class="sxs-lookup"><span data-stu-id="627b8-296">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="627b8-297">В области **Пользователи и группы AAD** выберите группу **Старший и стратегический персонал** и нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="627b8-297">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="627b8-298">В разделе **Выбрать из предустановленных разрешений или задать пользовательские** выберите вариант **Пользовательские**, а затем установите флажки **Просмотреть права**, **Изменить контент**, **Сохранить**, **Ответить** и **Ответить всем**.</span><span class="sxs-lookup"><span data-stu-id="627b8-298">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="627b8-299">Дважды нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-299">Click **OK** twice.</span></span>

14. <span data-ttu-id="627b8-300">В колонке **Подчиненная метка** нажмите кнопку **Сохранить**, а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-300">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="627b8-301">В колонке **Azure Information Protection** щелкните элементы **Политики > + Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="627b8-301">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="627b8-302">Введите **СтратегияКампании** в поле **Имя** и **Документы на сайте группы "Стратегия кампании"** в поле **Описание**.</span><span class="sxs-lookup"><span data-stu-id="627b8-302">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="627b8-303">Щелкните **Выберите, к каким пользователям или группам будет применяться эта политика > Пользователи или группы**, а затем выберите **Старший и стратегический персонал**.</span><span class="sxs-lookup"><span data-stu-id="627b8-303">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="627b8-304">Щелкните **Выбрать\> ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-304">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="627b8-p109">Выберите элемент **Добавить или удалить метки**. На панели **Политики: добавление и удаление меток** нажмите **СтратегияКампании**, а затем — **ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="627b8-307">Нажмите кнопку **Сохранить**, а затем — **ОК**.</span><span class="sxs-lookup"><span data-stu-id="627b8-307">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="627b8-308">Теперь вы можете создавать документы на этих четырех сайтах и тестировать доступ к ним с помощью различных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="627b8-308">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="627b8-309">Чтобы защитить документ с помощью Azure Information Protection и этой новой метки, необходимо [установить клиент Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) на тестовой машине, установить Office с помощью центра администрирования и затем выполнить вход из Microsoft Word с помощью учетной записи в группе пробной подписки **старшего персонала и специалистов по стратегии**.</span><span class="sxs-lookup"><span data-stu-id="627b8-309">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="627b8-310">См. также</span><span class="sxs-lookup"><span data-stu-id="627b8-310">See Also</span></span>

[<span data-ttu-id="627b8-311">Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций</span><span class="sxs-lookup"><span data-stu-id="627b8-311">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="627b8-312">Настройка групп и пользователей в случае среды разработки и тестирования для политической кампании</span><span class="sxs-lookup"><span data-stu-id="627b8-312">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="627b8-313">Руководства по лаборатории тестирования для облачных решений</span><span class="sxs-lookup"><span data-stu-id="627b8-313">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="627b8-314">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="627b8-314">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
