---
title: Классификация данных для тестовой среды Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по лаборатории тестирования, чтобы создавать и использовать метки хранения для документов в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487736"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="da05f-103">Классификация данных для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="da05f-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="da05f-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 для предприятий и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="da05f-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="da05f-105">В этой статье описывается настройка классификации данных с помощью меток хранения в тестовой среде Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="da05f-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="da05f-106">Классификация данных в тестовой среде состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="da05f-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="da05f-107">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="da05f-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="da05f-108">Этап 2. Создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="da05f-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="da05f-109">Этап 3. Применение меток хранения к документам</span><span class="sxs-lookup"><span data-stu-id="da05f-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="da05f-111">Чтобы получить визуальную карту всех статей в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="da05f-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="da05f-112">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="da05f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="da05f-113">Если вы просто хотите настроить метки хранения облегченным способом с минимальными требованиями, следуйте инструкциям в базовой конфигурации [lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="da05f-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="da05f-114">Если вы хотите настроить метки хранения в имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="da05f-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="da05f-115">Для тестирования меток хранения не требуется тестовая среда имитации предприятия, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="da05f-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="da05f-116">Он предоставляется здесь в качестве варианта, чтобы вы могли протестировать автоматическое лицензирование и членство в группах и поэкспериментировать с ним в типичной для организации среде.</span><span class="sxs-lookup"><span data-stu-id="da05f-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="da05f-117">Этап 2. Создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="da05f-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="da05f-118">На этом этапе создайте метки хранения для различных уровней хранения для папок документов SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="da05f-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="da05f-119">Во sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span><span class="sxs-lookup"><span data-stu-id="da05f-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="da05f-120">На **вкладке "Главная — Безопасность Microsoft 365"** в браузере выберите метки хранения   >  **классификации.**</span><span class="sxs-lookup"><span data-stu-id="da05f-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="da05f-121">Нажмите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="da05f-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="da05f-122">In the **Name your label** pane, enter Internal **Public** in Name **your label,** and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="da05f-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="da05f-123">В области **дескрипторов** плана файлов выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da05f-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="da05f-124">В области **параметров** метки при необходимости установите для параметра **"Хранение"** параметр **"В",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da05f-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="da05f-125">В области **"Просмотр параметров"** выберите **"Создать метку".**</span><span class="sxs-lookup"><span data-stu-id="da05f-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="da05f-126">Повторите шаги 3–7 для дополнительных меток с этими именами:</span><span class="sxs-lookup"><span data-stu-id="da05f-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="da05f-127">частные</span><span class="sxs-lookup"><span data-stu-id="da05f-127">Private</span></span>
  - <span data-ttu-id="da05f-128">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="da05f-128">Sensitive</span></span>
  - <span data-ttu-id="da05f-129">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="da05f-129">Highly Confidential</span></span>
1. <span data-ttu-id="da05f-130">В области **меток хранения выберите** **"Опубликовать метки".**</span><span class="sxs-lookup"><span data-stu-id="da05f-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="da05f-131">В области **"Выбор меток** для публикации" выберите **"Выбрать метки для публикации".**</span><span class="sxs-lookup"><span data-stu-id="da05f-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="da05f-132">В области **"Выбор меток"** выберите **"Добавить"** и выберите все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="da05f-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="da05f-133">Выберите **"Добавить"** и **"Готово"**</span><span class="sxs-lookup"><span data-stu-id="da05f-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="da05f-134">В области **"Выбор меток** для публикации" выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da05f-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="da05f-135">В области **"Выбор местоположений"** выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da05f-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="da05f-136">В области **"Имя политики"** введите "Пример **организации"** в **"Имя"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da05f-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="da05f-137">В области **"Просмотр параметров"** выберите **"Опубликовать метки".**</span><span class="sxs-lookup"><span data-stu-id="da05f-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="da05f-138">Публикация меток хранения может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="da05f-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="da05f-139">Этап 3. Применение меток хранения к документам</span><span class="sxs-lookup"><span data-stu-id="da05f-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="da05f-140">На этом этапе вы обнаружите поведение меток хранения по умолчанию для файлов в папке "Документы" сайта SharePoint Online и вручную измените метку хранения документа.</span><span class="sxs-lookup"><span data-stu-id="da05f-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="da05f-141">Сначала создайте сайт группы SharePoint Online с конфиденциальным уровнем.</span><span class="sxs-lookup"><span data-stu-id="da05f-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="da05f-142">Используя частный экземпляр браузера, во sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span><span class="sxs-lookup"><span data-stu-id="da05f-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="da05f-143">В списке плиток выберите **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="da05f-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="da05f-144">На новой **вкладке SharePoint** в браузере выберите **"Создать сайт".**</span><span class="sxs-lookup"><span data-stu-id="da05f-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="da05f-145">На странице **Создать сайт** нажмите **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="da05f-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="da05f-146">В поле **"Имя сайта группы"** введите **SensitiveFiles.**</span><span class="sxs-lookup"><span data-stu-id="da05f-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="da05f-147">В поле **описания сайта группы** введите сайт **SharePoint для конфиденциальных файлов.**</span><span class="sxs-lookup"><span data-stu-id="da05f-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="da05f-148">В **параметрах конфиденциальности выберите** **"Частное" —** только участники смогут получить доступ к этому сайту, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da05f-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="da05f-149">В области **"Кому нужно добавить?",** выберите **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="da05f-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="da05f-150">Затем настройте папку "Документы" на сайте группы SensitiveFiles для метки хранения "Конфиденциальный".</span><span class="sxs-lookup"><span data-stu-id="da05f-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="da05f-151">На **вкладке SensitiveFiles** браузера выберите **"Документы".**</span><span class="sxs-lookup"><span data-stu-id="da05f-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="da05f-152">Выберите **значок "Параметры"** и выберите **параметры библиотеки.**</span><span class="sxs-lookup"><span data-stu-id="da05f-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="da05f-153">В **области "Разрешения и управление"** выберите "Применить метку к элементу **в этом списке или библиотеке".**</span><span class="sxs-lookup"><span data-stu-id="da05f-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="da05f-154">Если этот параметр не появляется, ваши метки хранения еще не опубликованы.</span><span class="sxs-lookup"><span data-stu-id="da05f-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="da05f-155">Попробуйте сделать это позже.</span><span class="sxs-lookup"><span data-stu-id="da05f-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="da05f-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span><span class="sxs-lookup"><span data-stu-id="da05f-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="da05f-157">Затем создайте новый документ на сайте SensitiveFiles и измените его метку хранения.</span><span class="sxs-lookup"><span data-stu-id="da05f-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="da05f-158">В папке документов выберите **"Новый**  >  **документ Word".**</span><span class="sxs-lookup"><span data-stu-id="da05f-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="da05f-159">Введите текст в пустой документ.</span><span class="sxs-lookup"><span data-stu-id="da05f-159">Enter some text in the blank document.</span></span> <span data-ttu-id="da05f-160">Подождите, пока текст будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="da05f-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="da05f-161">В панели меню выберите **"Общие документы".**</span><span class="sxs-lookup"><span data-stu-id="da05f-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="da05f-162">Рядом с **именемDocument.docx** выберите вертикальную многопоковую линию, а затем выберите **"Сведения".**</span><span class="sxs-lookup"><span data-stu-id="da05f-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="da05f-163">В правой области в разделе **"Свойства"** в разделе "Применение метки  хранения" обратите **внимание,** что к документу автоматически применена метка хранения "Конфиденциальный".</span><span class="sxs-lookup"><span data-stu-id="da05f-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="da05f-164">Нажмите **Изменить все**.</span><span class="sxs-lookup"><span data-stu-id="da05f-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="da05f-165">В области **Document.docx** в области "Применить метку  **хранения"** выберите метку "Строго конфиденциальный" и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="da05f-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="da05f-166">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="da05f-166">Next step</span></span>

<span data-ttu-id="da05f-167">Изучите [дополнительные функции](m365-enterprise-test-lab-guides.md#information-protection) и возможности защиты информации в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="da05f-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="da05f-168">См. также</span><span class="sxs-lookup"><span data-stu-id="da05f-168">See also</span></span>

[<span data-ttu-id="da05f-169">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="da05f-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="da05f-170">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="da05f-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="da05f-171">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="da05f-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
