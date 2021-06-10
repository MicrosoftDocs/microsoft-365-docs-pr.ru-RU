---
title: Классификация данных для Microsoft 365 для тестовой среды предприятия
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
description: Используйте это руководство по тестовой лаборатории для создания и использования меток хранения документов в Microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919192"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7f615-103">Классификация данных для Microsoft 365 для тестовой среды предприятия</span><span class="sxs-lookup"><span data-stu-id="7f615-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7f615-104">*Это руководство по тестовой лаборатории можно использовать как для Microsoft 365, так и для Office 365 корпоративный среды тестирования.*</span><span class="sxs-lookup"><span data-stu-id="7f615-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7f615-105">В этой статье описывается настройка классификации данных с помощью меток хранения в Microsoft 365 для корпоративной тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="7f615-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="7f615-106">Классификация данных в тестовой среде включает три этапа:</span><span class="sxs-lookup"><span data-stu-id="7f615-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="7f615-107">Этап 1. Создание Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="7f615-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="7f615-108">Этап 2. Создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="7f615-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="7f615-109">Этап 3. Применение меток хранения к документам</span><span class="sxs-lookup"><span data-stu-id="7f615-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7f615-111">Чтобы получить визуальную карту для всех статей в стеке руководства по Microsoft 365 для корпоративной лаборатории тестирования, перейдите Microsoft 365 для корпоративного руководства по [лаборатории тестирования.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="7f615-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7f615-112">Этап 1. Создание Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="7f615-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7f615-113">Если вы просто хотите настроить метки хранения легким способом с минимальными требованиями, следуйте инструкциям в [легкой базовой конфигурации.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="7f615-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7f615-114">Если вы хотите настроить метки хранения в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="7f615-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f615-115">Тестирование меток хранения не требует имитации тестовой среды предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7f615-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7f615-116">Он предоставляется здесь в качестве параметра, чтобы можно было протестировать автоматическое лицензирование и членство в группе и поэкспериментировать с ним в среде, которая представляет собой типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="7f615-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="7f615-117">Этап 2. Создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="7f615-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="7f615-118">На этом этапе создайте метки хранения для различных уровней хранения для папок документов SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="7f615-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="7f615-119">Вопишитесь в [центр Microsoft 365 безопасности](https://security.microsoft.com/homepage) с учетной записью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="7f615-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="7f615-120">На **вкладке Home - Microsoft 365** безопасности браузера выберите метки **хранения**  >  **классификации.**</span><span class="sxs-lookup"><span data-stu-id="7f615-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="7f615-121">Нажмите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="7f615-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="7f615-122">В области **Имя метки** **введите** внутреннюю публику в **Имя** метки, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f615-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="7f615-123">В области **дескрипторов плана файлов** выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f615-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="7f615-124">В области **параметров Метки** при необходимости установите **удержание** **в on** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f615-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="7f615-125">В области **Обзор параметров** выберите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="7f615-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="7f615-126">Повторите шаги 3–7 для дополнительных меток с этими именами:</span><span class="sxs-lookup"><span data-stu-id="7f615-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="7f615-127">частные</span><span class="sxs-lookup"><span data-stu-id="7f615-127">Private</span></span>
  - <span data-ttu-id="7f615-128">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="7f615-128">Sensitive</span></span>
  - <span data-ttu-id="7f615-129">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="7f615-129">Highly Confidential</span></span>
1. <span data-ttu-id="7f615-130">В области **меток хранения** выберите **Метки Публикации**.</span><span class="sxs-lookup"><span data-stu-id="7f615-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="7f615-131">В **метке Выбор для публикации** выберите **метки для публикации.**</span><span class="sxs-lookup"><span data-stu-id="7f615-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="7f615-132">В области **Выберите метки** выберите **Добавить** и выбрать все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="7f615-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="7f615-133">Выберите **Добавить,** а затем выберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7f615-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="7f615-134">На **метке Выберите для публикации** области выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f615-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="7f615-135">На области **Выбор расположения** выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f615-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="7f615-136">На области **Имя политики** введите **организацию Пример** в **Name** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f615-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="7f615-137">На области **Обзор параметров** выберите **Метки Публикации.**</span><span class="sxs-lookup"><span data-stu-id="7f615-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="7f615-138">Публикация меток хранения может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="7f615-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="7f615-139">Этап 3. Применение меток хранения к документам</span><span class="sxs-lookup"><span data-stu-id="7f615-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="7f615-140">На этом этапе вы обнаружите поведение метки хранения по умолчанию для файлов в папке Документы сайта SharePoint Online и вручную измените метку хранения документа.</span><span class="sxs-lookup"><span data-stu-id="7f615-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="7f615-141">Сначала создайте веб-сайт SharePoint на конфиденциальном уровне:</span><span class="sxs-lookup"><span data-stu-id="7f615-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="7f615-142">С помощью частного экземпляра браузера вопишитесь в центр администрирования Microsoft 365 с [помощью](https://admin.microsoft.com) глобальной учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="7f615-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="7f615-143">В списке плитки **выберите** SharePoint .</span><span class="sxs-lookup"><span data-stu-id="7f615-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="7f615-144">На **вкладке SharePoint** в браузере выберите **Создать сайт.**</span><span class="sxs-lookup"><span data-stu-id="7f615-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="7f615-145">На странице **Создать сайт** нажмите **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="7f615-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="7f615-146">В поле **имя сайта Team** введите **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="7f615-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="7f615-147">В поле **описание сайта Team** введите SharePoint для **конфиденциальных файлов.**</span><span class="sxs-lookup"><span data-stu-id="7f615-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="7f615-148">В **параметрах конфиденциальности** выберите **Private — доступ** к этому сайту могут получить только участники, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f615-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="7f615-149">В Кто **вы хотите добавить?** области, выберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7f615-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="7f615-150">Далее настройте папку Documents сайта команды SensitiveFiles для метки хранения Sensitive.</span><span class="sxs-lookup"><span data-stu-id="7f615-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="7f615-151">На **вкладке SensitiveFiles** браузера выберите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="7f615-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="7f615-152">Выберите **значок Параметры,** а затем выберите **параметры Библиотеки.**</span><span class="sxs-lookup"><span data-stu-id="7f615-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="7f615-153">В **статье Разрешения и управление** выберите Нанесите метку на элементы в этом **списке или библиотеке.**</span><span class="sxs-lookup"><span data-stu-id="7f615-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="7f615-154">Если этот параметр не появится, метки хранения еще не опубликованы.</span><span class="sxs-lookup"><span data-stu-id="7f615-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="7f615-155">Попробуйте сделать этот шаг позже.</span><span class="sxs-lookup"><span data-stu-id="7f615-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="7f615-156">В **Параметры-Apply Label** выберите **Sensitive** в выпадаемом поле, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f615-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="7f615-157">Затем создайте новый документ на сайте SensitiveFiles и измените метку хранения.</span><span class="sxs-lookup"><span data-stu-id="7f615-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="7f615-158">В папке документов выберите **документ New**  >  **Word**.</span><span class="sxs-lookup"><span data-stu-id="7f615-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="7f615-159">Введите текст в пустом документе.</span><span class="sxs-lookup"><span data-stu-id="7f615-159">Enter some text in the blank document.</span></span> <span data-ttu-id="7f615-160">Подождите, пока текст будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="7f615-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="7f615-161">В панели меню выберите **общие документы.**</span><span class="sxs-lookup"><span data-stu-id="7f615-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="7f615-162">Рядом с **именемDocument.docx** выберите вертикальный эллипсис, а затем выберите **Details**.</span><span class="sxs-lookup"><span data-stu-id="7f615-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="7f615-163">В правой области в разделе **Свойства** в разделе **Применить** метку хранения обратите внимание, что в документе автоматически применена метка хранения **Sensitive.**</span><span class="sxs-lookup"><span data-stu-id="7f615-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="7f615-164">Нажмите **Изменить все**.</span><span class="sxs-lookup"><span data-stu-id="7f615-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="7f615-165">В области **Document.docx** в статье **Применить** метку хранения выберите метку **Highly Confidential,** а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f615-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="7f615-166">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="7f615-166">Next step</span></span>

<span data-ttu-id="7f615-167">Ознакомьтесь [с дополнительными функциями](m365-enterprise-test-lab-guides.md#information-protection) и возможностями защиты информации в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="7f615-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f615-168">См. также</span><span class="sxs-lookup"><span data-stu-id="7f615-168">See also</span></span>

[<span data-ttu-id="7f615-169">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7f615-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7f615-170">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7f615-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7f615-171">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7f615-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)