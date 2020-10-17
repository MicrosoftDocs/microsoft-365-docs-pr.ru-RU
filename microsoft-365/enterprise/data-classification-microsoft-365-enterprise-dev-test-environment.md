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
description: Используйте это руководство по лаборатории тестирования для создания и использования меток хранения в документах, включенных в тестовую среду Microsoft 365 для предприятий.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487736"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="98a2c-103">Классификация данных для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="98a2c-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="98a2c-104">*Это руководство по лаборатории тестирования можно использовать как для Microsoft 365 Enterprise, так и для корпоративных тестовых сред Office 365.*</span><span class="sxs-lookup"><span data-stu-id="98a2c-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="98a2c-105">В этой статье описано, как настроить классификацию данных с помощью меток хранения в тестовой среде Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="98a2c-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="98a2c-106">Классификация данных в тестовой среде состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="98a2c-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="98a2c-107">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="98a2c-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="98a2c-108">Этап 2: создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="98a2c-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="98a2c-109">Этап 3: применение меток хранения к документам</span><span class="sxs-lookup"><span data-stu-id="98a2c-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="98a2c-111">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="98a2c-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="98a2c-112">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="98a2c-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="98a2c-113">Если вы хотите просто настроить метки хранения в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="98a2c-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="98a2c-114">Если вы хотите настроить метки хранения на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="98a2c-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a2c-115">Для тестирования меток хранения не требуется моделируемая среда тестирования предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="98a2c-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="98a2c-116">Он предоставляется в качестве варианта, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="98a2c-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="98a2c-117">Этап 2: создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="98a2c-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="98a2c-118">На этом этапе Создайте метки хранения для различных уровней хранения для папок документов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="98a2c-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="98a2c-119">Войдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/homepage) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="98a2c-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="98a2c-120">На вкладке **Microsoft 365 безопасность** в браузере выберите **Classification**  >  **метки хранения**классификации.</span><span class="sxs-lookup"><span data-stu-id="98a2c-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="98a2c-121">Нажмите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="98a2c-122">В области **назвать метку** введите подпись **внутренний общедоступный** в поле **имя**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="98a2c-123">В области **дескрипторы плана файлов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="98a2c-124">В области **параметры метки** при необходимости задайте для параметра **срок хранения** значение **вкл**., а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="98a2c-125">В области **Проверьте параметры** выберите **создать метку**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="98a2c-126">Повторите шаги 3–7 для дополнительных меток с этими именами:</span><span class="sxs-lookup"><span data-stu-id="98a2c-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="98a2c-127">частные</span><span class="sxs-lookup"><span data-stu-id="98a2c-127">Private</span></span>
  - <span data-ttu-id="98a2c-128">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="98a2c-128">Sensitive</span></span>
  - <span data-ttu-id="98a2c-129">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="98a2c-129">Highly Confidential</span></span>
1. <span data-ttu-id="98a2c-130">В области **метки хранения** выберите пункт **опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="98a2c-131">В области **Выбор меток для публикации** выберите **пункт выбрать метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="98a2c-132">В области **Выбор меток** нажмите кнопку **Добавить** и выберите все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="98a2c-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="98a2c-133">Нажмите кнопку **Добавить**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="98a2c-134">В области **Выбор меток для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="98a2c-135">В области **Выбор расположений** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="98a2c-136">В области **имя политики** введите **Пример организации** в **поле имя**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="98a2c-137">В области **Проверьте параметры** выберите пункт **опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="98a2c-138">Публикация меток хранения может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="98a2c-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="98a2c-139">Этап 3: применение меток хранения к документам</span><span class="sxs-lookup"><span data-stu-id="98a2c-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="98a2c-140">На этом этапе вы обнаружите поведение меток хранения по умолчанию для файлов в папке "документы" сайта SharePoint Online и вручную измените метку хранения документа.</span><span class="sxs-lookup"><span data-stu-id="98a2c-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="98a2c-141">Сначала создайте сайт группы SharePoint Online на конфиденциальном уровне:</span><span class="sxs-lookup"><span data-stu-id="98a2c-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="98a2c-142">С помощью закрытого экземпляра браузера Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="98a2c-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="98a2c-143">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="98a2c-144">На новой вкладке **SharePoint** в браузере выберите **создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="98a2c-145">На странице **Создать сайт** нажмите **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="98a2c-146">В поле **имя сайта группы** введите **сенситивефилес**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="98a2c-147">В поле **Описание сайта группы** введите **сайт SharePoint для конфиденциальных файлов**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="98a2c-148">В окне **Параметры конфиденциальности**выберите пункт **частные пользователи могут получить доступ к этому сайту**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="98a2c-149">В области **кому вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="98a2c-150">Затем настройте папку документов на сайте группы Сенситивефилес для конфиденциальной метки хранения.</span><span class="sxs-lookup"><span data-stu-id="98a2c-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="98a2c-151">На вкладке **сенситивефилес** в браузере выберите **документы**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="98a2c-152">Нажмите значок **Параметры** , а затем выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="98a2c-153">В разделе **разрешения и управление**выберите **Применить метку к элементам в этом списке или библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="98a2c-154">Если этот параметр не отображается, метки хранения еще не опубликованы.</span><span class="sxs-lookup"><span data-stu-id="98a2c-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="98a2c-155">Повторите этот шаг позже.</span><span class="sxs-lookup"><span data-stu-id="98a2c-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="98a2c-156">В разделе **Параметры — применение метки**выберите пункт **конфиденциальный** в раскрывающемся списке и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="98a2c-157">Затем создайте новый документ на сайте Сенситивефилес и измените его метку хранения.</span><span class="sxs-lookup"><span data-stu-id="98a2c-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="98a2c-158">В папке документы выберите **Новый**  >  **документ Word**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="98a2c-159">Введите текст в пустой документ.</span><span class="sxs-lookup"><span data-stu-id="98a2c-159">Enter some text in the blank document.</span></span> <span data-ttu-id="98a2c-160">Дождитесь сохранения текста.</span><span class="sxs-lookup"><span data-stu-id="98a2c-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="98a2c-161">В строке меню выберите пункт **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="98a2c-162">Рядом с именем файла **Document.docx** выберите вертикальное многоточие, а затем нажмите кнопку **сведения**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="98a2c-163">В правой области в разделе **Свойства** в разделе **Применить метку хранения**Обратите внимание, что в документе была автоматически применена метка хранения **конфиденциальной** информации.</span><span class="sxs-lookup"><span data-stu-id="98a2c-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="98a2c-164">Нажмите **Изменить все**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="98a2c-165">В области **Document.docx** в разделе **Применить метку хранения**выберите метку **строго конфиденциальный** , а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="98a2c-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="98a2c-166">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="98a2c-166">Next step</span></span>

<span data-ttu-id="98a2c-167">Узнайте о дополнительных возможностях и возможностях [защиты информации](m365-enterprise-test-lab-guides.md#information-protection) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="98a2c-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="98a2c-168">См. также</span><span class="sxs-lookup"><span data-stu-id="98a2c-168">See also</span></span>

[<span data-ttu-id="98a2c-169">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="98a2c-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="98a2c-170">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="98a2c-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="98a2c-171">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="98a2c-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
