---
title: Классификации данных на предприятии 365 Microsoft тестовой среды
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: В этом документе Test Lab Guide используйте для создания и использования Office 365 меток на документы в тестовой среде Microsoft 365 для предприятия.
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871053"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e4558-103">Классификации данных на предприятии 365 Microsoft тестовой среды</span><span class="sxs-lookup"><span data-stu-id="e4558-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e4558-104">С помощью инструкции в этом разделе Настройка классификации данных с помощью Office 365 хранения метки в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="e4558-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e4558-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="e4558-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e4558-107">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="e4558-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e4558-108">Если необходимо настроить метки Office 365 в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e4558-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e4558-109">Если вы хотите настроить Office 365 меток имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e4558-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4558-p101">Тестирование меток Office 365 не требует тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверка автоматической лицензирования и членство в группах и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="e4558-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="e4558-112">Этап 2. Создание меток Office 365</span><span class="sxs-lookup"><span data-stu-id="e4558-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="e4558-113">На этом этапе создается метки для разных уровнях хранения для папки документы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e4558-113">In this phase, you create the labels for the different levels of retention for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="e4558-p102">При необходимости использовать закрытый экземпляр веб-браузер и войдите в портал Office, используя свою учетную запись глобального администратора. Дополнительные сведения см [Where для входа в Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="e4558-p102">If needed, use a private instance of your Internet browser and sign in to the Office portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="e4558-116">На вкладке **Домашняя страница Microsoft Office** щелкните плитку **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="e4558-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="e4558-117">На новой вкладке браузера **Центр администрирования Office** выберите **Центры администрирования > Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="e4558-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="e4558-p103">От нового **Home — безопасности &amp; соответствия** вкладки браузера, нажмите кнопку **классификаций > меток**. Из **Домашняя страница > меток** области, перейдите на вкладку **хранения** .</span><span class="sxs-lookup"><span data-stu-id="e4558-p103">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**. From the **Home > Labels** pane, click the **Retention** tab.</span></span>
    
5. <span data-ttu-id="e4558-120">Щелкните **создать метку**.</span><span class="sxs-lookup"><span data-stu-id="e4558-120">Click **Create a label**.</span></span>
    
6. <span data-ttu-id="e4558-121">В области **Задайте имя для метки** введите **Внутренний общедоступный** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e4558-121">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e4558-122">В области **Параметры метки** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e4558-122">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="e4558-123">В области **Проверьте параметры** нажмите **Создать эту метку**, а затем — кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e4558-123">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="e4558-124">Повторите действия 5–8 для следующих меток:</span><span class="sxs-lookup"><span data-stu-id="e4558-124">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="e4558-125">Private</span><span class="sxs-lookup"><span data-stu-id="e4558-125">Private</span></span>
    
  - <span data-ttu-id="e4558-126">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="e4558-126">Sensitive</span></span>
    
  - <span data-ttu-id="e4558-127">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="e4558-127">Highly Confidential</span></span>
    
10. <span data-ttu-id="e4558-128">В области **Главная > Метки** щелкните **Опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="e4558-128">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="e4558-129">В области **Выберите метки для публикации** щелкните **Выберите метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="e4558-129">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="e4558-130">В области **Выбор меток** нажмите кнопку **Добавить** и выберите все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="e4558-130">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="e4558-131">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e4558-131">Click **Done**.</span></span>
    
14. <span data-ttu-id="e4558-132">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e4558-132">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="e4558-133">В области **Выберите расположения** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e4558-133">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="e4558-134">В области **Укажите имя для политики** введите **Пример организации** в поле **Имя** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e4558-134">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="e4558-135">В области **Проверьте параметры** последовательно нажмите кнопки **Опубликовать метки** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e4558-135">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="e4558-136">Обратите внимание, что может занять несколько минут для меток для публикации.</span><span class="sxs-lookup"><span data-stu-id="e4558-136">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="e4558-137">Этап 3: Применять к документам Office 365 хранения меток</span><span class="sxs-lookup"><span data-stu-id="e4558-137">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="e4558-138">На этом этапе обнаружение метки по умолчанию для файлов в папке документы сайта SharePoint Online и вручную измените значение параметра метка документа.</span><span class="sxs-lookup"><span data-stu-id="e4558-138">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="e4558-139">Во-первых Создайте сайт группы SharePoint Online конфиденциальные уровень:</span><span class="sxs-lookup"><span data-stu-id="e4558-139">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="e4558-p104">С помощью браузера на локальном компьютере, выполните вход в портал Office, с помощью учетной записи глобального администратора. Дополнительные сведения см [Where для входа в Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="e4558-p104">Using a browser on your local computer, sign in to the Office portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="e4558-142">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e4558-142">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="e4558-143">На новой вкладке **SharePoint** в браузере щелкните **Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="e4558-143">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="e4558-144">На странице **Создание сайта** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="e4558-144">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="e4558-145">В поле **имя сайта группы**введите **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="e4558-145">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="e4558-146">В поле **Описание сайта группы**введите **сайт SharePoint для конфиденциальных файлов**.</span><span class="sxs-lookup"><span data-stu-id="e4558-146">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="e4558-147">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e4558-147">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e4558-148">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e4558-148">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="e4558-149">Настройте папку «документы» сайта группы SensitiveFiles конфиденциальных надписи.</span><span class="sxs-lookup"><span data-stu-id="e4558-149">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="e4558-150">На вкладке **SensitiveFiles** браузера щелкните **документы**.</span><span class="sxs-lookup"><span data-stu-id="e4558-150">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="e4558-151">Щелкните значок параметров, а затем **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="e4558-151">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="e4558-152">В разделе **Разрешения и управление** нажмите **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="e4558-152">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="e4558-153">В поле **Применить параметры метки**в раскрывающемся списке выберите **конфиденциальных** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e4558-153">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="e4558-154">Затем создайте новый документ на сайте SensitiveFiles и измените его метку.</span><span class="sxs-lookup"><span data-stu-id="e4558-154">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="e4558-155">В папку «документы» щелкните **Создать > документ Word**.</span><span class="sxs-lookup"><span data-stu-id="e4558-155">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="e4558-p105">Введите текст в новый документ. Дождитесь текст будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="e4558-p105">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="e4558-158">В строке меню щелкните **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="e4558-158">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="e4558-159">Щелкните значок рядом с полем Имя файла **Document.docx** Word.</span><span class="sxs-lookup"><span data-stu-id="e4558-159">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="e4558-160">В правой области в разделе **Свойства** в разделе **Применить хранения метки**Обратите внимание на то, что документ был метку **конфиденциальных** автоматически применяется.</span><span class="sxs-lookup"><span data-stu-id="e4558-160">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="e4558-161">Нажмите кнопку **Изменить все**.</span><span class="sxs-lookup"><span data-stu-id="e4558-161">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="e4558-162">В области **Document.docx** в разделе **Применить label**выберите метку **Конфиденциальными** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e4558-162">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="e4558-163">Увидеть на этапе [настроить классификации для вашей среды](infoprotect-configure-classification.md) в **сведения о** защите сведения и ссылки на Office 365 меток хранения в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="e4558-163">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="e4558-164">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="e4558-164">Next step</span></span>

<span data-ttu-id="e4558-165">Изучите дополнительные [сведения о защите](m365-enterprise-test-lab-guides.md#information-protection) функций и возможностей в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="e4558-165">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4558-166">См. также</span><span class="sxs-lookup"><span data-stu-id="e4558-166">See also</span></span>

[<span data-ttu-id="e4558-167">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e4558-167">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e4558-168">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e4558-168">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e4558-169">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e4558-169">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 