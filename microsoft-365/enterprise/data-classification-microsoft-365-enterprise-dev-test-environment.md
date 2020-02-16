---
title: Классификация данных для тестовой среды Microsoft 365 корпоративный
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
description: Используйте это руководство по лаборатории тестирования для создания и использования меток хранения Office 365 для документов в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: 6534eff67e9c91423eb6f81415cb3ef2e965dcc1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067996"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9b6f7-103">Классификация данных для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9b6f7-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9b6f7-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="9b6f7-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9b6f7-105">С помощью инструкций, описанных в этой статье, вы настраиваете классификацию данных с помощью меток хранения Office 365 в тестовой среде Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="9b6f7-107">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9b6f7-108">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9b6f7-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9b6f7-109">Если вы просто хотите настроить метки хранения Office 365 в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9b6f7-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9b6f7-110">Если вы хотите настроить метки хранения Office 365 на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9b6f7-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b6f7-111">Для тестирования меток хранения Office 365 не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="9b6f7-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9b6f7-112">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="9b6f7-113">Этап 2: создание меток хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="9b6f7-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="9b6f7-114">На этом этапе создаются метки хранения для различных уровней хранения для папок документов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="9b6f7-115">Войдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/homepage) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="9b6f7-116">На вкладке " **безопасность 365 (дом** .............)" в браузере щелкните **классификация > меток хранения**</span><span class="sxs-lookup"><span data-stu-id="9b6f7-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="9b6f7-117">Нажмите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="9b6f7-118">В области **имя введите подпись** введите для метки значение **внутренний общедоступный** в поле **имя**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="9b6f7-119">В области " **дескрипторы плана файлов** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="9b6f7-120">В области **параметры метки** при необходимости задайте для параметра **срок хранения** значение **вкл**., а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="9b6f7-121">В области **Проверка параметров** нажмите кнопку **создать метку**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="9b6f7-122">Повторите шаги 3–7 для дополнительных меток с этими именами:</span><span class="sxs-lookup"><span data-stu-id="9b6f7-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="9b6f7-123">частные</span><span class="sxs-lookup"><span data-stu-id="9b6f7-123">Private</span></span>
    
  - <span data-ttu-id="9b6f7-124">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="9b6f7-124">Sensitive</span></span>
    
  - <span data-ttu-id="9b6f7-125">Строго конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="9b6f7-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="9b6f7-126">В области **метки хранения** щелкните **опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="9b6f7-127">В области **Выбор меток для публикации** нажмите кнопку **выбрать метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="9b6f7-128">В области **Выбор меток** нажмите кнопку **Добавить** и выберите все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="9b6f7-129">Нажмите кнопку **Добавить**, а затем кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="9b6f7-130">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="9b6f7-131">В области **Выберите расположения** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="9b6f7-132">В области **Укажите имя для политики** введите **Пример организации** в поле **Имя** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="9b6f7-133">В области **Проверка параметров** нажмите кнопку **опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="9b6f7-134">Обратите внимание, что для публикации меток хранения может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="9b6f7-135">Этап 3: применение меток хранения Office 365 к документам</span><span class="sxs-lookup"><span data-stu-id="9b6f7-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="9b6f7-136">На этом этапе вы обнаружите поведение меток хранения по умолчанию для файлов в папке "документы" сайта SharePoint Online и вручную измените метку хранения документа.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="9b6f7-137">Сначала создайте сайт группы SharePoint Online на конфиденциальном уровне:</span><span class="sxs-lookup"><span data-stu-id="9b6f7-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="9b6f7-138">С помощью закрытого экземпляра браузера Войдите на [портал Office 365](https://portal.office.com) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="9b6f7-139">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="9b6f7-140">На новой вкладке **SharePoint** в браузере выберите **создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="9b6f7-141">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="9b6f7-142">В окне **имя сайта группы**введите **сенситивефилес**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="9b6f7-143">В поле **Описание сайта группы**введите **сайт SharePoint для конфиденциальных файлов**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="9b6f7-144">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="9b6f7-145">В области **кому вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="9b6f7-146">Затем настройте папку документов на сайте группы Сенситивефилес для конфиденциальной метки хранения.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="9b6f7-147">На вкладке **сенситивефилес** в браузере выберите **документы**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="9b6f7-148">Щелкните значок параметров, а затем **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="9b6f7-149">В разделе **разрешения и управление**щелкните **Применить метку к элементам в этом списке или библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="9b6f7-150">Если этот параметр не отображается, метки хранения еще не опубликованы.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="9b6f7-151">Повторите этот шаг позже.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="9b6f7-152">В разделе **Параметры — применение метки**выберите пункт **конфиденциальный** в раскрывающемся списке и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="9b6f7-153">Затем создайте новый документ на сайте Сенситивефилес и измените его метку хранения.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="9b6f7-154">В папке Документы щелкните **создать > документ Word**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="9b6f7-155">Введите некоторый текст в пустом документе.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-155">Type some text in the blank document.</span></span> <span data-ttu-id="9b6f7-156">Дождитесь сохранения текста.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="9b6f7-157">В строке меню выберите пункт **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="9b6f7-158">Щелкните вертикальное многоточие рядом с именем файла **Document. docx** , а затем нажмите кнопку **сведения**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="9b6f7-159">В области справа в разделе **Свойства** в разделе **Применить метку хранения**Обратите внимание, что в документе была автоматически применена метка хранения **конфиденциальной** информации.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="9b6f7-160">Нажмите кнопку **изменить все**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="9b6f7-161">В области **документ. docx** в разделе **Применение метки хранения**выберите метку **строго конфиденциальный** и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="9b6f7-162">Сведения и ссылки на сведения о том, как развертывать метки хранения Office 365 в рабочей среде, можно найти в разделе [Настройка классификации для среды](infoprotect-configure-classification.md) на этапе **защиты информации** .</span><span class="sxs-lookup"><span data-stu-id="9b6f7-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="9b6f7-163">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="9b6f7-163">Next step</span></span>

<span data-ttu-id="9b6f7-164">Узнайте о дополнительных возможностях и возможностях [защиты информации](m365-enterprise-test-lab-guides.md#information-protection) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="9b6f7-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b6f7-165">См. также</span><span class="sxs-lookup"><span data-stu-id="9b6f7-165">See also</span></span>

[<span data-ttu-id="9b6f7-166">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9b6f7-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9b6f7-167">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9b6f7-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9b6f7-168">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="9b6f7-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
