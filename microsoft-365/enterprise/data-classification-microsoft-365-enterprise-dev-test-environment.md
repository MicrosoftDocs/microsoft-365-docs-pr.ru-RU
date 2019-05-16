---
title: Классификация данных для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по лаборатории тестирования для создания и использования меток хранения Office 365 для документов в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: 66e06f9a89b102c131bc29af17c4564fabbab9b4
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072419"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8872c-103">Классификация данных для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8872c-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8872c-104">С помощью инструкций, описанных в этой статье, вы настраиваете классификацию данных с помощью меток хранения Office 365 в тестовой среде Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="8872c-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="8872c-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="8872c-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8872c-107">Этап 1: создание тестовой среды Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8872c-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8872c-108">Если вы просто хотите настроить метки хранения Office 365 в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8872c-108">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8872c-109">Если вы хотите настроить метки хранения Office 365 на имитации предприятия, следуйте инструкциям в [сквозной проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="8872c-109">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8872c-110">Для тестирования меток хранения Office 365 не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="8872c-110">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="8872c-111">Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="8872c-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="8872c-112">Этап 2: создание меток хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="8872c-112">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="8872c-113">На этом этапе создаются метки хранения для различных уровней хранения для папок документов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8872c-113">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="8872c-114">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8872c-114">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="8872c-115">На вкладке **Главная — соответствие требованиям Microsoft 365** в браузере выберите пункты **Классификации > Метки**.</span><span class="sxs-lookup"><span data-stu-id="8872c-115">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="8872c-116">Щелкните **Метки хранения > Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="8872c-116">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="8872c-117">В области **Назовите метку** введите **Внутренний общедоступный** в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8872c-117">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="8872c-118">В области **Дескрипторы плана файлов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8872c-118">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="8872c-119">В области **Параметры метки** при необходимости установите параметр **Хранение** в положение **Вкл.** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8872c-119">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="8872c-120">В области **Проверьте параметры** нажмите кнопку **Создать эту метку**.</span><span class="sxs-lookup"><span data-stu-id="8872c-120">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="8872c-121">Повторите шаги 3–7 для дополнительных меток с этими именами:</span><span class="sxs-lookup"><span data-stu-id="8872c-121">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="8872c-122">частные</span><span class="sxs-lookup"><span data-stu-id="8872c-122">Private</span></span>
    
  - <span data-ttu-id="8872c-123">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="8872c-123">Sensitive</span></span>
    
  - <span data-ttu-id="8872c-124">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="8872c-124">Highly Confidential</span></span>
  
9. <span data-ttu-id="8872c-125">В области **Главная > Метки** щелкните **Опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="8872c-125">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="8872c-126">В области **Выберите метки для публикации** щелкните **Выберите метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="8872c-126">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="8872c-127">В области **Выбор меток** нажмите кнопку **Добавить** и выберите все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="8872c-127">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="8872c-128">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8872c-128">Click **Done**.</span></span>
    
13. <span data-ttu-id="8872c-129">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8872c-129">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="8872c-130">В области **Выберите расположения** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8872c-130">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="8872c-131">В области **Укажите имя для политики** введите **Пример организации** в поле **Имя** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8872c-131">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="8872c-132">В области **Проверьте параметры** последовательно нажмите кнопки **Опубликовать метки** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8872c-132">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="8872c-133">Обратите внимание, что для публикации меток хранения может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="8872c-133">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="8872c-134">Этап 3: применение меток хранения Office 365 к документам</span><span class="sxs-lookup"><span data-stu-id="8872c-134">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="8872c-135">На этом этапе вы обнаружите поведение меток хранения по умолчанию для файлов в папке "документы" сайта SharePoint Online и вручную измените метку хранения документа.</span><span class="sxs-lookup"><span data-stu-id="8872c-135">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="8872c-136">Сначала создайте сайт группы SharePoint Online на конфиденциальном уровне:</span><span class="sxs-lookup"><span data-stu-id="8872c-136">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="8872c-137">С помощью браузера на локальном компьютере войдите на [портал Office 365](https://portal.office.com) , используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8872c-137">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="8872c-138">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8872c-138">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="8872c-139">На новой вкладке **SharePoint** в браузере выберите **создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="8872c-139">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="8872c-140">На странице **Создайте сайт** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="8872c-140">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="8872c-141">В окне **имя сайта группы**введите **сенситивефилес**.</span><span class="sxs-lookup"><span data-stu-id="8872c-141">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="8872c-142">В поле **Описание сайта группы**введите **сайт SharePoint для конфиденциальных файлов**.</span><span class="sxs-lookup"><span data-stu-id="8872c-142">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="8872c-143">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8872c-143">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="8872c-144">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8872c-144">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="8872c-145">Затем настройте папку документов на сайте группы Сенситивефилес для конфиденциальной метки хранения.</span><span class="sxs-lookup"><span data-stu-id="8872c-145">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="8872c-146">На вкладке **Сенситивефилес** в браузере выберите **документы**.</span><span class="sxs-lookup"><span data-stu-id="8872c-146">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="8872c-147">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="8872c-147">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="8872c-148">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="8872c-148">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="8872c-149">В разделе **Параметры — применение метки**выберите пункт **конфиденциальный** в раскрывающемся списке и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8872c-149">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="8872c-150">Затем создайте новый документ на сайте Сенситивефилес и измените его метку хранения.</span><span class="sxs-lookup"><span data-stu-id="8872c-150">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="8872c-151">В папке Документы щелкните **новый документ Word _гт_**.</span><span class="sxs-lookup"><span data-stu-id="8872c-151">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="8872c-152">Введите некоторый текст в пустом документе.</span><span class="sxs-lookup"><span data-stu-id="8872c-152">Type some text in the blank document.</span></span> <span data-ttu-id="8872c-153">Дождитесь сохранения текста.</span><span class="sxs-lookup"><span data-stu-id="8872c-153">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="8872c-154">В строке меню выберите пункт **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="8872c-154">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="8872c-155">Щелкните значок Word рядом с именем файла **Document. docx** .</span><span class="sxs-lookup"><span data-stu-id="8872c-155">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="8872c-156">В области справа в разделе **Свойства** в разделе **Применить метку хранения**Обратите внимание, что в документе была автоматически применена метка **конфиденциальной** информации.</span><span class="sxs-lookup"><span data-stu-id="8872c-156">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="8872c-157">Нажмите кнопку **изменить все**.</span><span class="sxs-lookup"><span data-stu-id="8872c-157">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="8872c-158">В области **документ. docx** в разделе **Применение метки**выберите метку **строго конфиденциальный** и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8872c-158">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="8872c-159">Сведения и ссылки на сведения о том, как развертывать метки хранения Office 365 в рабочей среде, можно найти в разделе [Настройка классификации для среды](infoprotect-configure-classification.md) на этапе **защиты информации** .</span><span class="sxs-lookup"><span data-stu-id="8872c-159">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8872c-160">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8872c-160">Next step</span></span>

<span data-ttu-id="8872c-161">Узнайте о дополнительных возможностях и возможностях [защиты информации](m365-enterprise-test-lab-guides.md#information-protection) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="8872c-161">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8872c-162">См. также</span><span class="sxs-lookup"><span data-stu-id="8872c-162">See also</span></span>

[<span data-ttu-id="8872c-163">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8872c-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8872c-164">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8872c-164">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8872c-165">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8872c-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 