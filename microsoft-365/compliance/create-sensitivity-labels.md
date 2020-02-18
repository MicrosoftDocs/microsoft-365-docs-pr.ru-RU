---
title: Создание и публикация меток конфиденциальности
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 'Требование для всех решений Microsoft Information Protection: создание, настройка и публикация меток конфиденциальности для классификации и защиты документов и сообщений электронной почты организации.'
ms.openlocfilehash: d2300a54583c0b2d12de86e3dbb5f3116daf6460
ms.sourcegitcommit: 7dc36305721a92e19a6e397f906e19dcafa0073b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2020
ms.locfileid: "42101229"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="f8507-103">Создание и настройка меток конфиденциальности и соответствующих политик</span><span class="sxs-lookup"><span data-stu-id="f8507-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="f8507-104">Все решения Microsoft Information Protection (сокращенное название — MIP) реализуются с помощью [меток конфиденциальности](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="f8507-104">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="f8507-105">Чтобы создать и опубликовать эти метки, перейдите в центр администрирования меток, например в [Центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f8507-105">To create and publish these labels, go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="f8507-106">Вы также можете использовать Центр безопасности Microsoft 365 или Центр безопасности и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8507-106">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="f8507-107">Сначала создайте и настройте метки конфиденциальности, которые должны быть доступны для приложений и других служб.</span><span class="sxs-lookup"><span data-stu-id="f8507-107">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="f8507-108">Например, метки, которые пользователям нужно найти и применить из приложений Office.</span><span class="sxs-lookup"><span data-stu-id="f8507-108">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="f8507-109">Затем создайте одну или несколько политик меток, содержащих настраиваемые метки и параметры политики.</span><span class="sxs-lookup"><span data-stu-id="f8507-109">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="f8507-110">Публикацию меток и параметров для выбранных пользователей и расположений осуществляет политика меток.</span><span class="sxs-lookup"><span data-stu-id="f8507-110">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f8507-111">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f8507-111">Before you begin</span></span>

<span data-ttu-id="f8507-112">Глобальный администратор организации имеет все разрешения на создание меток конфиденциальности и управление всеми их аспектами.</span><span class="sxs-lookup"><span data-stu-id="f8507-112">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="f8507-113">Если вы входите не как глобальный администратор, см. раздел [Создание меток конфиденциальности и управление ими](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="f8507-113">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="f8507-114">Создание и настройка меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="f8507-114">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="f8507-115">В своем центре администрирования меток перейдите к меткам конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="f8507-115">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="f8507-116">Центр соответствия требованиям Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f8507-116">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="f8507-117">**Решения** > **Защита информации**</span><span class="sxs-lookup"><span data-stu-id="f8507-117">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="f8507-118">Если этот параметр не отображается сразу, сначала выберите пункт **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="f8507-118">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="f8507-119">Центр безопасности Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f8507-119">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="f8507-120">**Классификация** > **Метки конфиденциальности**</span><span class="sxs-lookup"><span data-stu-id="f8507-120">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="f8507-121">Центр безопасности и соответствия требованиям Office 365:</span><span class="sxs-lookup"><span data-stu-id="f8507-121">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="f8507-122">**Классификация** > **Метки конфиденциальности**</span><span class="sxs-lookup"><span data-stu-id="f8507-122">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="f8507-123">На вкладке **Метки** нажмите **+ Создать метку**, чтобы запустить мастер **Создание метки конфиденциальности**.</span><span class="sxs-lookup"><span data-stu-id="f8507-123">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="f8507-124">Следуйте инструкциям для настройки параметров метки.</span><span class="sxs-lookup"><span data-stu-id="f8507-124">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="f8507-125">Дополнительные сведения о параметрах меток см. в разделе [Возможности меток конфиденциальности](sensitivity-labels.md#what-sensitivity-labels-can-do) обзорной статьи.</span><span class="sxs-lookup"><span data-stu-id="f8507-125">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="f8507-126">Повторите эти действия для создания дополнительных меток.</span><span class="sxs-lookup"><span data-stu-id="f8507-126">Repeat these steps to create more labels.</span></span> <span data-ttu-id="f8507-127">Но если вы хотите создать дочернюю метку, сначала выберите родительскую метку и нажмите **...**, чтобы увидеть **дополнительные действия**, и выберите команду **Добавить дочернюю метку**.</span><span class="sxs-lookup"><span data-stu-id="f8507-127">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="f8507-128">Создав все нужные метки, проверьте их порядок и при необходимости переместите их вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="f8507-128">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="f8507-129">Чтобы изменить порядок меток, нажмите **...**, чтобы увидеть **дополнительные действия**, и выберите параметр **Выше** или **Ниже**.</span><span class="sxs-lookup"><span data-stu-id="f8507-129">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="f8507-130">Дополнительные сведения см. в разделе [Приоритет метки (важен порядок)](sensitivity-labels.md#label-priority-order-matters) обзорной статьи.</span><span class="sxs-lookup"><span data-stu-id="f8507-130">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="f8507-131">Чтобы изменить существующую метку, выберите ее и нажмите кнопку **Изменить метку**.</span><span class="sxs-lookup"><span data-stu-id="f8507-131">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="f8507-132">В результате запустится мастер **Изменить метку конфиденциальности**, позволяющий поменять любые параметры из действия 3.</span><span class="sxs-lookup"><span data-stu-id="f8507-132">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="f8507-133">При изменении метки, уже опубликованной с помощью политики меток, после завершения работы мастера никаких дополнительных действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="f8507-133">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="f8507-134">Например, вам не нужно добавлять ее в новую политику меток, чтобы сделать изменения доступными для тех же пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8507-134">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="f8507-135">Однако репликация этих изменений для пользователей и служб может занять до 24 часов. </span><span class="sxs-lookup"><span data-stu-id="f8507-135">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="f8507-136">Пока вы не опубликуете метки, они будут недоступны для выбора в приложениях и службах.</span><span class="sxs-lookup"><span data-stu-id="f8507-136">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="f8507-137">Чтобы опубликовать метки, их нужно [добавить в политику меток](#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="f8507-137">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8507-138">На этой вкладке **Метки** не нажимайте вкладку **Опубликовать метки** (или кнопку **Опубликовать метку** при изменении метки), если не нужно создавать политику меток.</span><span class="sxs-lookup"><span data-stu-id="f8507-138">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="f8507-139">Несколько политик меток требуются только в том случае, если пользователям необходимы разные метки или другие параметры политики.</span><span class="sxs-lookup"><span data-stu-id="f8507-139">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="f8507-140">Целью является минимально возможное число политик меток. Часто в организациях используется только одна политика меток.</span><span class="sxs-lookup"><span data-stu-id="f8507-140">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="f8507-141">Дополнительные параметры меток, доступные с помощью PowerShell Центра безопасности и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="f8507-141">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="f8507-142">Дополнительные параметры меток доступны с помощью командлета [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) из [PowerShell Центра безопасности и соответствия требованиям Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="f8507-142">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="f8507-143">Используйте параметр *LocaleSettings* для развертывания в многоязычной среде, чтобы пользователи видели имя метки и подсказку на своем языке.</span><span class="sxs-lookup"><span data-stu-id="f8507-143">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="f8507-144">Пример настройки представлен в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f8507-144">See the following section for an example configuration.</span></span> 

<span data-ttu-id="f8507-145">С помощью этого командлета вы также можете указать [дополнительные параметры](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) для клиента унифицированных меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="f8507-145">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="f8507-146">Эти дополнительные параметры включают настройку цвета метки и применение пользовательского свойства при использовании метки.</span><span class="sxs-lookup"><span data-stu-id="f8507-146">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="f8507-147">Полный список см. в разделе [Доступные дополнительные параметры для политик меток](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span><span class="sxs-lookup"><span data-stu-id="f8507-147">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="f8507-148">Пример настройки метки конфиденциальности для различных языков</span><span class="sxs-lookup"><span data-stu-id="f8507-148">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="f8507-149">В приведенном ниже примере показана конфигурация метки "Общедоступные" в PowerShell с замещающим текстом для подсказки.</span><span class="sxs-lookup"><span data-stu-id="f8507-149">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="f8507-150">В этом примере имя метки и текст подсказки настраиваются для французского, итальянского и немецкого языков.</span><span class="sxs-lookup"><span data-stu-id="f8507-150">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="f8507-151">В результате такой настройки пользователи, имеющие приложения Office, в которых используются указанные выше языки интерфейса, видят имена меток и подсказки на этих языках.</span><span class="sxs-lookup"><span data-stu-id="f8507-151">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="f8507-152">Кроме того, если у вас установлен клиент унифицированных меток Azure Information Protection, чтобы помечать файлы из проводника, пользователи, у которых есть указанные выше языковые версии Windows, видят имена меток и подсказки на своем языке при щелчке правой кнопкой мыши для применения меток.</span><span class="sxs-lookup"><span data-stu-id="f8507-152">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="f8507-153">Для языков, которые вам нужны, используйте [идентификаторы языков](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) в Office (также именуемые тегами языков) и укажите свой перевод для имени метки и подсказки.</span><span class="sxs-lookup"><span data-stu-id="f8507-153">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="f8507-154">Перед выполнением команд в PowerShell необходимо сначала [подключиться к PowerShell Центра безопасности и соответствия требованиям Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="f8507-154">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress)
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="f8507-155">Публикация меток конфиденциальности путем создания политики меток</span><span class="sxs-lookup"><span data-stu-id="f8507-155">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="f8507-156">В своем центре администрирования меток перейдите к меткам конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="f8507-156">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="f8507-157">Центр соответствия требованиям Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f8507-157">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="f8507-158">**Решения** > **Защита информации**</span><span class="sxs-lookup"><span data-stu-id="f8507-158">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="f8507-159">Если этот параметр не отображается сразу, сначала выберите пункт **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="f8507-159">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="f8507-160">Центр безопасности Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f8507-160">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="f8507-161">**Классификация** > **Метки конфиденциальности**</span><span class="sxs-lookup"><span data-stu-id="f8507-161">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="f8507-162">Центр безопасности и соответствия требованиям Office 365:</span><span class="sxs-lookup"><span data-stu-id="f8507-162">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="f8507-163">**Классификация** > **Метки конфиденциальности**</span><span class="sxs-lookup"><span data-stu-id="f8507-163">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="f8507-164">Откройте вкладку **Политики меток**.</span><span class="sxs-lookup"><span data-stu-id="f8507-164">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="f8507-165">Нажмите **Опубликовать метки**, чтобы запустить **мастера создания политики**.</span><span class="sxs-lookup"><span data-stu-id="f8507-165">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="f8507-166">Щелкните ссылку **Выберите метки конфиденциальности для публикации**.</span><span class="sxs-lookup"><span data-stu-id="f8507-166">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="f8507-167">Выберите метки, которые нужно сделать доступными в приложениях и службах, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f8507-167">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="f8507-168">Проверьте выбранные метки. Чтобы внести изменения, щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="f8507-168">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="f8507-169">В противном случае нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f8507-169">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="f8507-170">Следуйте инструкциям, чтобы настроить параметры политики.</span><span class="sxs-lookup"><span data-stu-id="f8507-170">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="f8507-171">Дополнительные сведения о параметрах см. в разделе [Возможности политик меток](sensitivity-labels.md#what-label-policies-can-do) обзорной статьи.</span><span class="sxs-lookup"><span data-stu-id="f8507-171">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="f8507-172">Повторите эти действия, если вам требуются разные параметры политики для разных пользователей или расположений.</span><span class="sxs-lookup"><span data-stu-id="f8507-172">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="f8507-173">Например, вы можете использовать дополнительные метки для группы пользователей или другую метку по умолчанию для подмножества пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8507-173">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="f8507-174">Если вы создаете несколько политик меток, которые могут конфликтовать при применении для пользователей или расположений, проверьте порядок политик и при необходимости измените их очередность.</span><span class="sxs-lookup"><span data-stu-id="f8507-174">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="f8507-175">Чтобы изменить порядок политик меток, нажмите **...**, чтобы увидеть **дополнительные действия**, и выберите параметр **Выше** или **Ниже**.</span><span class="sxs-lookup"><span data-stu-id="f8507-175">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="f8507-176">Дополнительные сведения см. в разделе [Приоритет политики меток (важен порядок)](sensitivity-labels.md#label-policy-priority-order-matters) обзорной статьи.</span><span class="sxs-lookup"><span data-stu-id="f8507-176">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="f8507-177">После завершения работы мастера политика меток автоматически публикуется.</span><span class="sxs-lookup"><span data-stu-id="f8507-177">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="f8507-178">Чтобы внести изменения в опубликованную политику, просто отредактируйте ее.</span><span class="sxs-lookup"><span data-stu-id="f8507-178">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="f8507-179">Вам не требуется выбирать какие-либо определенные действия публикации или повторной публикации.</span><span class="sxs-lookup"><span data-stu-id="f8507-179">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="f8507-180">Чтобы изменить существующую политику меток, выберите ее и нажмите кнопку **Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="f8507-180">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="f8507-181">В результате запустится мастер **Создать политику**, позволяющий изменить включенные метки, а также параметры меток.</span><span class="sxs-lookup"><span data-stu-id="f8507-181">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="f8507-182">После завершения работы мастера все изменения автоматически реплицируются для выбранных пользователей и служб.</span><span class="sxs-lookup"><span data-stu-id="f8507-182">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="f8507-183">Как правило, пользователи видят метки в своих приложениях Office через несколько часов.</span><span class="sxs-lookup"><span data-stu-id="f8507-183">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="f8507-184">Однако репликация политик меток и изменений, внесенных в них, для всех пользователей и служб может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="f8507-184">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="f8507-185">Дополнительные параметры политики меток, доступные с помощью PowerShell Центра безопасности и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="f8507-185">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="f8507-186">Дополнительные параметры политики меток доступны с помощью командлета [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) из [PowerShell Центра безопасности и соответствия требованиям Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="f8507-186">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="f8507-187">С помощью этого командлета вы можете указать [дополнительные параметры](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) для клиента унифицированных меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="f8507-187">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="f8507-188">К этим дополнительным параметрам относится настройка другой метки по умолчанию для Outlook и внедрение всплывающих сообщений в Outlook для предупреждения, объяснения или блокирования отправляемых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f8507-188">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="f8507-189">Полный список см. в разделе [Доступные дополнительные параметры для меток](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span><span class="sxs-lookup"><span data-stu-id="f8507-189">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="f8507-190">С помощью этого командлета вы также можете добавлять и удалять метки в политике меток.</span><span class="sxs-lookup"><span data-stu-id="f8507-190">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="f8507-191">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f8507-191">Next steps</span></span>

<span data-ttu-id="f8507-192">Сведения о настройке и использовании меток конфиденциальности для конкретных сценариев см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="f8507-192">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="f8507-193">Ограничение доступа к контенту с помощью шифрования в метках конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="f8507-193">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="f8507-194">Автоматическое применение метки конфиденциальности к содержимому</span><span class="sxs-lookup"><span data-stu-id="f8507-194">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="f8507-195">Использование меток конфиденциальности для команд, групп и сайтов</span><span class="sxs-lookup"><span data-stu-id="f8507-195">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="f8507-196">Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="f8507-196">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="f8507-197">Сведения об отслеживании использования меток см. в статье [Просмотр использования меток с помощью аналитики меток](label-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="f8507-197">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>
