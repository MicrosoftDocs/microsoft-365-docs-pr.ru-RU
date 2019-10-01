---
title: Защита файлов SharePoint Online с помощью меток хранения и DLP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: Сводка. Применяйте метки хранения и политики защиты от потери данных для сайтов групп SharePoint Online с различными уровнями защиты информации.
ms.openlocfilehash: 77da4ec44e31fae8db2c37ebc39233f76c5e4dd3
ms.sourcegitcommit: 8e5b799efd3ddd0eae9dd2835c3783103817fb4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "37317611"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="0cbcb-103">Защита файлов SharePoint Online с помощью меток хранения и DLP</span><span class="sxs-lookup"><span data-stu-id="0cbcb-103">Protect SharePoint Online files with retention labels and DLP</span></span>

 <span data-ttu-id="0cbcb-104">**Сводка.** Применяйте метки хранения и политики защиты от потери данных для сайтов групп SharePoint Online с различными уровнями защиты информации.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-104">**Summary:** Apply retention labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="0cbcb-105">В этой статье описано создание и развертывание меток хранения и политик защиты от потери данных для базовых, конфиденциальных и строго конфиденциальных сайтов группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-105">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="0cbcb-106">Дополнительные сведения об этих трех уровнях защиты см. в статье [Защита сайтов и файлов SharePoint Online](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="0cbcb-106">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="0cbcb-107">Как это работает</span><span class="sxs-lookup"><span data-stu-id="0cbcb-107">How this works</span></span>

1. <span data-ttu-id="0cbcb-108">Создайте нужные метки хранения и опубликуйте их.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-108">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="0cbcb-109">Для их публикации может потребоваться до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-109">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="0cbcb-110">Для нужных сайтов SharePoint измените параметры библиотеки документов, чтобы присвоить нужные метки хранения к элементам в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-110">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="0cbcb-111">Создайте политики защиты от потери данных, чтобы выполнять действия на основе меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-111">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="0cbcb-112">Когда пользователи добавляют документ в библиотеку, этот документ получает назначенную метку хранения по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="0cbcb-112">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="0cbcb-113">При необходимости пользователи могут изменить метку.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-113">Users can change the label, if needed.</span></span> <span data-ttu-id="0cbcb-114">Если пользователь делится документом за пределами организации, служба защиты от потери данных проверяет, назначена ли метка, и выполняет действия, если политика защиты от потери данных соответствует метке.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-114">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="0cbcb-115">Служба защиты от потери данных также проверяет соответствие другим политикам, таким как защита файлов с номерами кредитных карт, если этот тип политики настроен.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-115">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="0cbcb-116">Метки хранения для сайтов SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0cbcb-116">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="0cbcb-117">Существует три этапа создания и назначения меток хранения для сайтов группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-117">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="0cbcb-118">Этап 1. Определение имен меток хранения</span><span class="sxs-lookup"><span data-stu-id="0cbcb-118">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="0cbcb-119">На этом этапе нужно определить названия меток хранения для четырех уровней защиты информации, применяемых к сайтам группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-119">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="0cbcb-120">В приведенной ниже таблице перечислены рекомендуемые имена для каждого уровня.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-120">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="0cbcb-121">**Уровень защиты сайта группы SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="0cbcb-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="0cbcb-122">**Имя метки**</span><span class="sxs-lookup"><span data-stu-id="0cbcb-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0cbcb-123">Базовый общедоступный</span><span class="sxs-lookup"><span data-stu-id="0cbcb-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="0cbcb-124">Внутренний общедоступный</span><span class="sxs-lookup"><span data-stu-id="0cbcb-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="0cbcb-125">Базовый частный</span><span class="sxs-lookup"><span data-stu-id="0cbcb-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="0cbcb-126">Частный</span><span class="sxs-lookup"><span data-stu-id="0cbcb-126">Private</span></span>  <br/> |
|<span data-ttu-id="0cbcb-127">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="0cbcb-127">Sensitive</span></span>  <br/> |<span data-ttu-id="0cbcb-128">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="0cbcb-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="0cbcb-129">Строго конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="0cbcb-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="0cbcb-130">Строго конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="0cbcb-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="0cbcb-131">Этап 2. Создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="0cbcb-131">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="0cbcb-132">На этом этапе нужно создать и опубликовать определенные метки для разных уровней защиты информации.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="0cbcb-133">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com), используя учетную запись с ролью администратора компании или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-133">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="0cbcb-134">На вкладке **Главная — соответствие требованиям Microsoft 365** в браузере выберите пункты **Классификации > Метки**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-134">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="0cbcb-135">Щелкните **Метки хранения > Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-135">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="0cbcb-136">В области **Назовите метку** введите название метки и описание для администраторов и пользователей, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-136">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="0cbcb-137">В области **Дескрипторы плана хранения** введите необходимые параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-137">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="0cbcb-138">В области **Параметры метки** при необходимости установите параметр **Хранение** в положение **Вкл.** и настройте параметры хранения.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-138">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="0cbcb-139">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-139">Click **Next**.</span></span>
    
7. <span data-ttu-id="0cbcb-140">В области **Проверьте параметры** нажмите кнопку **Создать эту метку**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-140">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="0cbcb-141">Для создания дополнительных меток нажмите кнопку **Создать метку** и повторите нужные действия с 3 по 7.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-141">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="0cbcb-142">Публикация новых меток</span><span class="sxs-lookup"><span data-stu-id="0cbcb-142">Publish your new labels</span></span>

<span data-ttu-id="0cbcb-143">Для публикации новых меток хранения выполните действия, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-143">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="0cbcb-144">В области **Метки** щелкните вкладку **Метки хранения** и нажмите кнопку **Опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-144">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="0cbcb-145">В области **Выберите метки для публикации** щелкните **Выберите метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-145">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="0cbcb-146">В области **Выбор меток** нажмите кнопку **Добавить**, выберите все четыре метки и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-146">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="0cbcb-147">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-147">Click **Done**.</span></span>
    
5. <span data-ttu-id="0cbcb-148">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-148">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="0cbcb-149">В области **Выбор расположений** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-149">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="0cbcb-150">В области **Назовите политику** введите название для своего набора меток в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-150">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0cbcb-151">В области **Проверьте параметры** последовательно нажмите кнопки **Опубликовать метки** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-151">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="0cbcb-152">Этап 3. Применение меток хранения к сайтам SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0cbcb-152">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="0cbcb-153">Инструкции по применению меток хранения к папкам документов, размещенным на сайтах группы SharePoint Online, приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-153">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="0cbcb-154">Войдите на [портал Office 365](https://www.office.com) и щелкните приложение **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-154">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="0cbcb-155">На новой вкладке **SharePoint** в браузере выберите сайт, которому нужно назначить метку хранения.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-155">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="0cbcb-156">На новой вкладке SharePoint в браузере щелкните **Документы**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-156">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="0cbcb-157">Щелкните значок параметров, а затем **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-157">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="0cbcb-158">В разделе **Разрешения и управление** нажмите **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-158">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="0cbcb-159">В разделе **Параметры — применение метки** выберите соответствующую метку хранения и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-159">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="0cbcb-160">Закройте вкладку сайта SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-160">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="0cbcb-161">Повторите шаги со 2 по 8, чтобы назначить метки хранения для дополнительных сайтов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-161">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="0cbcb-162">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-162">Here is your resulting configuration.</span></span>
  
![Метки хранения для четырех типов сайтов групп SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="0cbcb-164">Политики защиты от потери данных для сайтов SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0cbcb-164">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="0cbcb-165">Выполните указанные ниже действия, чтобы настроить политику защиты от потери данных, которая уведомляет пользователей, когда они предоставляют доступ к документу с конфиденциального сайта группы SharePoint Online пользователям не из организации.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-165">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="0cbcb-166">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com/), используя учетную запись с ролью администратора компании или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-166">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="0cbcb-167">На новой вкладке **Соответствие требованиям Microsoft 365** в браузере выберите пункты **Политики > Защита от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-167">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="0cbcb-168">В области **Главная > Защита от потери данных** нажмите кнопку **Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-168">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="0cbcb-169">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-169">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="0cbcb-170">В области **Назовите политику** введите название для политики защиты от потери конфиденциальных данных в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-170">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="0cbcb-171">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-171">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="0cbcb-172">В списке расположений отключите параметры **Электронная почта Exchange**, **Учетные записи OneDrive** и **Сообщения из чатов и каналов Teams**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-172">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0cbcb-173">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-173">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="0cbcb-174">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-174">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="0cbcb-175">В области **Метки хранения** нажмите кнопку **Добавить**, укажите метку **Конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-175">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="0cbcb-176">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-176">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="0cbcb-177">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-177">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="0cbcb-178">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-178">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="0cbcb-179">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-179">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="0cbcb-180">В текстовом поле введите или вставьте одну из следующих подсказок в зависимости от того, применена ли служба Azure Information Protection, чтобы защитить строго конфиденциальные файлы:</span><span class="sxs-lookup"><span data-stu-id="0cbcb-180">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="0cbcb-p106">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="0cbcb-p107">Строго конфиденциальные файлы защищены с помощью шифрования. Их могут просматривать только те внешние пользователи, которым ваш ИТ-отдел предоставил разрешения для этих файлов.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="0cbcb-186">Вы также можете ввести или вставить собственную подсказку политики, которая укажет пользователям, как делиться файлом с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-186">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="0cbcb-187">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-187">Click **OK**.</span></span>
    
17. <span data-ttu-id="0cbcb-188">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-188">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="0cbcb-189">В области **Вы хотите включить политику или сначала проверить, как все работает?** выберите пункт **Да, включить сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-189">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="0cbcb-190">В области **Проверьте параметры** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-190">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="0cbcb-191">Здесь показана итоговая конфигурация для конфиденциальных сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-191">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Политика защиты от потери данных для изолированного сайта группы SharePoint Online с использованием метки хранения "Конфиденциальный"](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="0cbcb-193">Выполните следующие действия, чтобы настроить политику защиты от потери данных, которая блокирует пользователей, когда они совместно используют документы на строго конфиденциальном сайте группы SharePoint Online за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-193">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="0cbcb-194">На новой вкладке **Соответствие требованиям Microsoft 365** в браузере выберите пункты **Политики > Защита от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-194">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="0cbcb-195">В области **Защита от потери данных** нажмите кнопку **Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-195">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="0cbcb-196">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-196">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="0cbcb-197">В области **Назовите политику** введите название для политики защиты от потери строго конфиденциальных данных в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-197">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="0cbcb-198">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-198">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="0cbcb-199">В списке расположений отключите параметры **Электронная почта Exchange**, **Учетные записи OneDrive** и **Сообщения из чатов и каналов Teams**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-199">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="0cbcb-200">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-200">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="0cbcb-201">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-201">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="0cbcb-202">В области **Метки хранения** нажмите кнопку **Добавить**, укажите метку **Строго конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-202">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="0cbcb-203">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-203">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="0cbcb-204">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-204">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="0cbcb-205">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-205">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="0cbcb-206">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-206">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="0cbcb-207">В текстовом поле введите или вставьте следующее:</span><span class="sxs-lookup"><span data-stu-id="0cbcb-207">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="0cbcb-p108">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="0cbcb-211">Вы также можете ввести или вставить, скопировав, собственную подсказку политики, которая укажет пользователям, как делиться файлом с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-211">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="0cbcb-212">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-212">Click **OK**.</span></span>
    
17. <span data-ttu-id="0cbcb-213">В разделе **Обнаружение случаев разовой отправки определенного объема конфиденциальных данных** области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Ограничение доступа или шифрование содержимого** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-213">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="0cbcb-214">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-214">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="0cbcb-215">В области **Проверьте параметры** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-215">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="0cbcb-216">Ниже показана итоговая конфигурация для строго конфиденциальных сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-216">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Политика защиты от потери данных для изолированного сайта группы SharePoint Online с использованием метки хранения "Строго конфиденциальный"](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="0cbcb-218">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="0cbcb-218">Next step</span></span>

[<span data-ttu-id="0cbcb-219">Защита файлов SharePoint Online с помощью Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="0cbcb-219">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="0cbcb-220">См. также</span><span class="sxs-lookup"><span data-stu-id="0cbcb-220">See Also</span></span>

[<span data-ttu-id="0cbcb-221">Безопасность сайтов и файлов SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0cbcb-221">Secure SharePoint Online sites and files</span></span>](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="0cbcb-222">Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций</span><span class="sxs-lookup"><span data-stu-id="0cbcb-222">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="0cbcb-223">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="0cbcb-223">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


