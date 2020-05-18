---
title: Защита файлов SharePoint Online с помощью меток хранения и DLP
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: Сводка. Применяйте метки хранения и политики защиты от потери данных для сайтов групп SharePoint Online с различными уровнями защиты информации.
ms.openlocfilehash: b924b0d62d7c66a008739dfa12c0d1dd00deac9b
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262400"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="342c7-103">Защита файлов SharePoint Online с помощью меток хранения и DLP</span><span class="sxs-lookup"><span data-stu-id="342c7-103">Protect SharePoint Online files with retention labels and DLP</span></span>

<span data-ttu-id="342c7-104">В этой статье описано создание и развертывание меток хранения и политик защиты от потери данных для базовых, конфиденциальных и строго конфиденциальных сайтов группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="342c7-104">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="342c7-105">Дополнительные сведения об этих трех уровнях защиты см. в статье [Защита сайтов и файлов SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="342c7-105">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="342c7-106">Как это работает</span><span class="sxs-lookup"><span data-stu-id="342c7-106">How this works</span></span>

1. <span data-ttu-id="342c7-107">Создайте нужные метки хранения и опубликуйте их.</span><span class="sxs-lookup"><span data-stu-id="342c7-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="342c7-108">Для их публикации может потребоваться до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="342c7-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="342c7-109">Для нужных сайтов SharePoint измените параметры библиотеки документов, чтобы присвоить нужные метки хранения к элементам в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="342c7-109">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="342c7-110">Создайте политики защиты от потери данных, чтобы выполнять действия на основе меток хранения.</span><span class="sxs-lookup"><span data-stu-id="342c7-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="342c7-111">Когда пользователи добавляют документ в библиотеку, этот документ получает назначенную метку хранения по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="342c7-111">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="342c7-112">При необходимости пользователи могут изменить метку.</span><span class="sxs-lookup"><span data-stu-id="342c7-112">Users can change the label, if needed.</span></span> <span data-ttu-id="342c7-113">Если пользователь делится документом за пределами организации, служба защиты от потери данных проверяет, назначена ли метка, и выполняет действия, если политика защиты от потери данных соответствует метке.</span><span class="sxs-lookup"><span data-stu-id="342c7-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="342c7-114">Служба защиты от потери данных также проверяет соответствие другим политикам, таким как защита файлов с номерами кредитных карт, если этот тип политики настроен.</span><span class="sxs-lookup"><span data-stu-id="342c7-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="342c7-115">Метки хранения для сайтов SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="342c7-115">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="342c7-116">Существует три этапа создания и назначения меток хранения для сайтов группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="342c7-116">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="342c7-117">Этап 1. Определение имен меток хранения</span><span class="sxs-lookup"><span data-stu-id="342c7-117">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="342c7-118">На этом этапе нужно определить названия меток хранения для четырех уровней защиты информации, применяемых к сайтам группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="342c7-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="342c7-119">В приведенной ниже таблице перечислены рекомендуемые имена для каждого уровня.</span><span class="sxs-lookup"><span data-stu-id="342c7-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="342c7-120">**Уровень защиты сайта группы SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="342c7-120">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="342c7-121">**Имя метки**</span><span class="sxs-lookup"><span data-stu-id="342c7-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="342c7-122">Базовый общедоступный</span><span class="sxs-lookup"><span data-stu-id="342c7-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="342c7-123">Внутренний общедоступный</span><span class="sxs-lookup"><span data-stu-id="342c7-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="342c7-124">Базовый частный</span><span class="sxs-lookup"><span data-stu-id="342c7-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="342c7-125">Частный</span><span class="sxs-lookup"><span data-stu-id="342c7-125">Private</span></span>  <br/> |
|<span data-ttu-id="342c7-126">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="342c7-126">Sensitive</span></span>  <br/> |<span data-ttu-id="342c7-127">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="342c7-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="342c7-128">Строго конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="342c7-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="342c7-129">Строго конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="342c7-129">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="342c7-130">Этап 2. Создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="342c7-130">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="342c7-131">На этом этапе нужно создать и опубликовать определенные метки для разных уровней защиты информации.</span><span class="sxs-lookup"><span data-stu-id="342c7-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="342c7-132">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com), используя учетную запись с ролью администратора компании или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="342c7-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="342c7-133">На вкладке **Главная — соответствие требованиям Microsoft 365** в браузере выберите пункты **Классификации > Метки**.</span><span class="sxs-lookup"><span data-stu-id="342c7-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="342c7-134">Щелкните **Метки хранения > Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="342c7-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="342c7-135">В области **Назовите метку** введите название метки и описание для администраторов и пользователей, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="342c7-136">В области **Дескрипторы плана хранения** введите необходимые параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="342c7-137">В области **Параметры метки** при необходимости установите параметр **Хранение** в положение **Вкл.** и настройте параметры хранения.</span><span class="sxs-lookup"><span data-stu-id="342c7-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="342c7-138">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="342c7-139">В области **Проверьте параметры** нажмите кнопку **Создать эту метку**.</span><span class="sxs-lookup"><span data-stu-id="342c7-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="342c7-140">Для создания дополнительных меток нажмите кнопку **Создать метку** и повторите нужные действия с 3 по 7.</span><span class="sxs-lookup"><span data-stu-id="342c7-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="342c7-141">Публикация новых меток</span><span class="sxs-lookup"><span data-stu-id="342c7-141">Publish your new labels</span></span>

<span data-ttu-id="342c7-142">Для публикации новых меток хранения выполните действия, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="342c7-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="342c7-143">В области **Метки** щелкните вкладку **Метки хранения** и нажмите кнопку **Опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="342c7-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="342c7-144">В области **Выберите метки для публикации** щелкните **Выберите метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="342c7-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="342c7-145">В области **Выбор меток** нажмите кнопку **Добавить**, выберите все четыре метки и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="342c7-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="342c7-146">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="342c7-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="342c7-147">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="342c7-148">В области **Выбор расположений** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="342c7-149">В области **Назовите политику** введите название для своего набора меток в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="342c7-150">В области **Проверьте параметры** последовательно нажмите кнопки **Опубликовать метки** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="342c7-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="342c7-151">Этап 3. Применение меток хранения к сайтам SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="342c7-151">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="342c7-152">Инструкции по применению меток хранения к папкам документов, размещенным на сайтах группы SharePoint Online, приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="342c7-152">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="342c7-153">Войдите на [портал Office 365](https://www.office.com) и щелкните приложение **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="342c7-153">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="342c7-154">На новой вкладке **SharePoint** в браузере выберите сайт, которому нужно назначить метку хранения.</span><span class="sxs-lookup"><span data-stu-id="342c7-154">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="342c7-155">На новой вкладке SharePoint в браузере щелкните **Документы**.</span><span class="sxs-lookup"><span data-stu-id="342c7-155">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="342c7-156">Щелкните значок параметров, а затем **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="342c7-156">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="342c7-157">В разделе **Разрешения и управление** нажмите **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="342c7-157">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="342c7-158">В разделе **Параметры — применение метки** выберите соответствующую метку хранения и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="342c7-158">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="342c7-159">Закройте вкладку сайта SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="342c7-159">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="342c7-160">Повторите шаги со 2 по 8, чтобы назначить метки хранения для дополнительных сайтов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="342c7-160">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="342c7-161">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="342c7-161">Here is your resulting configuration.</span></span>
  
![Метки хранения для четырех типов сайтов групп SharePoint Online.](../media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="342c7-163">Политики защиты от потери данных для сайтов SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="342c7-163">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="342c7-164">Выполните указанные ниже действия, чтобы настроить политику защиты от потери данных, которая уведомляет пользователей, когда они предоставляют доступ к документу с конфиденциального сайта группы SharePoint Online пользователям не из организации.</span><span class="sxs-lookup"><span data-stu-id="342c7-164">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="342c7-165">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com/), используя учетную запись с ролью администратора компании или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="342c7-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="342c7-166">На новой вкладке **Соответствие требованиям Microsoft 365** в браузере выберите пункты **Политики > Защита от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="342c7-166">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="342c7-167">В области **Главная > Защита от потери данных** нажмите кнопку **Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="342c7-167">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="342c7-168">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-168">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="342c7-169">В области **Назовите политику** введите название для политики защиты от потери конфиденциальных данных в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-169">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="342c7-170">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-170">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="342c7-171">В списке расположений отключите параметры **Электронная почта Exchange**, **Учетные записи OneDrive** и **Сообщения из чатов и каналов Teams**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-171">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="342c7-172">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="342c7-172">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="342c7-173">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="342c7-173">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="342c7-174">В области **Метки хранения** нажмите кнопку **Добавить**, укажите метку **Конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="342c7-174">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="342c7-175">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="342c7-175">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="342c7-176">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-176">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="342c7-177">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="342c7-177">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="342c7-178">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="342c7-178">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="342c7-179">В текстовом поле введите или вставьте одну из следующих подсказок в зависимости от того, используются ли необязательные метки конфиденциальности, чтобы защитить конфиденциальные файлы:</span><span class="sxs-lookup"><span data-stu-id="342c7-179">In the text box, type or paste in one of the following tips, depending on if you are optionallyusing sensitivity labels to protect sensitive files:</span></span>
    
  - <span data-ttu-id="342c7-p106">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="342c7-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="342c7-p107">Строго конфиденциальные файлы защищены с помощью шифрования. Их могут просматривать только те внешние пользователи, которым ваш ИТ-отдел предоставил разрешения для этих файлов.</span><span class="sxs-lookup"><span data-stu-id="342c7-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="342c7-185">Вы также можете ввести или вставить собственную подсказку политики, которая укажет пользователям, как делиться файлом с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="342c7-185">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="342c7-186">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="342c7-186">Click **OK**.</span></span>
    
17. <span data-ttu-id="342c7-187">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-187">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="342c7-188">В области **Вы хотите включить политику или сначала проверить, как все работает?** выберите пункт **Да, включить сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-188">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="342c7-189">В области **Проверьте параметры** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="342c7-189">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="342c7-190">Здесь показана итоговая конфигурация для конфиденциальных сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="342c7-190">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Политика защиты от потери данных для изолированного сайта группы SharePoint Online с использованием метки хранения "Конфиденциальный"](../media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="342c7-192">Выполните следующие действия, чтобы настроить политику защиты от потери данных, которая блокирует пользователей, когда они совместно используют документы на строго конфиденциальном сайте группы SharePoint Online за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="342c7-192">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="342c7-193">На новой вкладке **Соответствие требованиям Microsoft 365** в браузере выберите пункты **Политики > Защита от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="342c7-193">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="342c7-194">В области **Защита от потери данных** нажмите кнопку **Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="342c7-194">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="342c7-195">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-195">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="342c7-196">В области **Назовите политику** введите название для политики защиты от потери строго конфиденциальных данных в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-196">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="342c7-197">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-197">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="342c7-198">В списке расположений отключите параметры **Электронная почта Exchange**, **Учетные записи OneDrive** и **Сообщения из чатов и каналов Teams**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-198">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="342c7-199">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="342c7-199">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="342c7-200">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="342c7-200">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="342c7-201">В области **Метки хранения** нажмите кнопку **Добавить**, укажите метку **Строго конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="342c7-201">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="342c7-202">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="342c7-202">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="342c7-203">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-203">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="342c7-204">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="342c7-204">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="342c7-205">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="342c7-205">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="342c7-206">В текстовом поле введите или вставьте следующее:</span><span class="sxs-lookup"><span data-stu-id="342c7-206">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="342c7-p108">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="342c7-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="342c7-210">Вы также можете ввести или вставить, скопировав, собственную подсказку политики, которая укажет пользователям, как делиться файлом с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="342c7-210">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="342c7-211">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="342c7-211">Click **OK**.</span></span>
    
17. <span data-ttu-id="342c7-212">В разделе **Обнаружение случаев разовой отправки определенного объема конфиденциальных данных** области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Ограничение доступа или шифрование содержимого** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-212">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="342c7-213">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="342c7-213">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="342c7-214">В области **Проверьте параметры** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="342c7-214">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="342c7-215">Ниже показана итоговая конфигурация для строго конфиденциальных сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="342c7-215">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Политика защиты от потери данных для изолированного сайта группы SharePoint Online с использованием метки хранения "Строго конфиденциальный"](../media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="342c7-217">Поддержка меток конфиденциальности появится в ближайшее время</span><span class="sxs-lookup"><span data-stu-id="342c7-217">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="342c7-218">На данный момент в качестве условия можно использовать только метки хранения, а не [метки конфиденциальности](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="342c7-218">You can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md).</span></span> <span data-ttu-id="342c7-219">Сейчас мы работаем над поддержкой меток конфиденциальности для этого условия.</span><span class="sxs-lookup"><span data-stu-id="342c7-219">We're currently working on support for using a sensitivity label in this condition.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="342c7-220">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="342c7-220">Next step</span></span>

[<span data-ttu-id="342c7-221">Защита файлов SharePoint Online с помощью меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="342c7-221">Protect SharePoint Online files with sensitivity labels</span></span>](protect-sharepoint-online-files-with-sensitivity-label.md)
    
## <a name="see-also"></a><span data-ttu-id="342c7-222">См. также</span><span class="sxs-lookup"><span data-stu-id="342c7-222">See Also</span></span>

[<span data-ttu-id="342c7-223">Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций</span><span class="sxs-lookup"><span data-stu-id="342c7-223">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="342c7-224">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="342c7-224">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


