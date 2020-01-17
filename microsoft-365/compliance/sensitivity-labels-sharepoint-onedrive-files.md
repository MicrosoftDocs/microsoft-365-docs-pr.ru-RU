---
title: Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Администраторы могут включить поддержку меток конфиденциальности для файлов Word, Excel и PowerPoint в SharePoint и OneDrive.
ms.openlocfilehash: 0e164afca97818d2082ddf4053df791317e29ac5
ms.sourcegitcommit: 7705fdbcee4f8714ce044c9e120a431023f7a367
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "41218589"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="09adb-103">Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="09adb-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="09adb-104">Ранее при применении меток конфиденциальности, которые включали шифрование к файлам Office, хранящимся в SharePoint и OneDrive, службе не удалось обработать содержимое этих файлов.</span><span class="sxs-lookup"><span data-stu-id="09adb-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="09adb-105">В таких обстоятельствах не работают совместное редактирование, обнаружение электронных данных, защита от потери данных, поиск, delve и другие функции совместной работы.</span><span class="sxs-lookup"><span data-stu-id="09adb-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="09adb-106">Этот предварительный просмотр включает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="09adb-106">This preview enables these features:</span></span>

- <span data-ttu-id="09adb-107">В SharePoint распознаются метки конфиденциальности, применяемые к файлам Word, Excel и PowerPoint в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="09adb-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="09adb-108">В SharePoint также применяются параметры, соответствующие каждой метке.</span><span class="sxs-lookup"><span data-stu-id="09adb-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="09adb-109">При загрузке файла из SharePoint или OneDrive метка чувствительности перемещается вместе с файлом, а параметры применяются к нему.</span><span class="sxs-lookup"><span data-stu-id="09adb-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="09adb-110">Примените метки конфиденциальности к файлам Office, а также откройте и измените файлы, к которым применены метки конфиденциальности (если это разрешено разрешениями метки), с помощью веб-версий Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="09adb-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="09adb-111">С помощью Word в Интернете вы также можете использовать автоматические метки при редактировании документов.</span><span class="sxs-lookup"><span data-stu-id="09adb-111">With Word on the web, you can also use auto labeling when you edit documents.</span></span>

- <span data-ttu-id="09adb-112">Обнаружение электронных данных Office 365 поддерживает полнотекстовый поиск в файлах, к которым применены метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="09adb-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="09adb-113">Политики защиты от потери данных охватывают содержимое этих файлов.</span><span class="sxs-lookup"><span data-stu-id="09adb-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="09adb-114">Для мониторинга меток конфиденциальности доступны три новых события аудита.</span><span class="sxs-lookup"><span data-stu-id="09adb-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="09adb-115">филесенситивитяпплиед</span><span class="sxs-lookup"><span data-stu-id="09adb-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="09adb-116">филесенситивитилабелчанжед</span><span class="sxs-lookup"><span data-stu-id="09adb-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="09adb-117">филесенситивитилабелремовед</span><span class="sxs-lookup"><span data-stu-id="09adb-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="09adb-118">Вы также можете применять метки конфиденциальности к Microsoft Teams, группам Office 365 и сайтам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="09adb-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="09adb-119">Для получения дополнительных сведений об этом отдельном предварительном просмотре ознакомьтесь со статьей [Использование меток конфиденциальности в Microsoft Teams, Office 365 Groups и сайты SharePoint (общедоступная Предварительная версия)](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="09adb-119">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="09adb-120">Вы всегда можете отказаться от этого предварительного просмотра в любое время.</span><span class="sxs-lookup"><span data-stu-id="09adb-120">You always have the choice to opt out of this preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="09adb-121">Requirements</span><span class="sxs-lookup"><span data-stu-id="09adb-121">Requirements</span></span>

<span data-ttu-id="09adb-122">Эти функции работают только с [метками конфиденциальности](sensitivity-labels.md) .</span><span class="sxs-lookup"><span data-stu-id="09adb-122">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="09adb-123">Если у вас есть метки Azure Information Protection, сначала необходимо перенести их в метки конфиденциальности, чтобы можно было включить эти функции для новых файлов, которые вы отправляете.</span><span class="sxs-lookup"><span data-stu-id="09adb-123">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="09adb-124">Инструкции можно посмотреть, [как перенести метки Azure Information Protection в единые метки конфиденциальности](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="09adb-124">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="09adb-125">Для этого предварительный просмотр используйте приложение OneDrive Sync версии 19.002.0121.0008 или более поздней версии для Windows, а также версию 19.002.0107.0008 или более поздней версии на компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="09adb-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="09adb-126">Обе эти версии выпущены 28 января 2019 и в настоящее время выпускаются для всех звонков.</span><span class="sxs-lookup"><span data-stu-id="09adb-126">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="09adb-127">Дополнительные сведения можно найти в статье [заметки о выпуске OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="09adb-127">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="09adb-128">После включения этого предварительного просмотра пользователям, запускающим старую версию приложения синхронизации, будет предложено обновить его.</span><span class="sxs-lookup"><span data-stu-id="09adb-128">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="09adb-129">Ограничения</span><span class="sxs-lookup"><span data-stu-id="09adb-129">Limitations</span></span>

- <span data-ttu-id="09adb-130">Если вы включите этот предварительный просмотр, пользователи, которые меняют метку на файл в папке синхронизации OneDrive, могут не сохранить другие изменения, внесенные в файл.</span><span class="sxs-lookup"><span data-stu-id="09adb-130">When you enable this preview, users who change a label to a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="09adb-131">Пользователи видят [красный круг с белым крестиком](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), и им предлагается сохранить новые изменения как отдельную копию.</span><span class="sxs-lookup"><span data-stu-id="09adb-131">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="09adb-132">В дополнение к изменениям меток, инициированных пользователями, такое же поведение может произойти, если администратор изменяет параметры опубликованной метки, которая уже применена к файлам, загруженным в клиент синхронизации пользователей.</span><span class="sxs-lookup"><span data-stu-id="09adb-132">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="09adb-133">Чтобы избежать потери работы для этих сценариев, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="09adb-133">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="09adb-134">Чтобы применить метки, используйте веб-версии приложений Office.</span><span class="sxs-lookup"><span data-stu-id="09adb-134">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="09adb-135">Закройте файл после применения метки, а затем снова откройте файл, чтобы внести другие изменения.</span><span class="sxs-lookup"><span data-stu-id="09adb-135">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="09adb-136">SharePoint не автоматически применяет новые метки к существующим файлам, которые вы уже зашифровале с помощью меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="09adb-136">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="09adb-137">Чтобы обеспечить работу функций после включения этого предварительного просмотра, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="09adb-137">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="09adb-138">Убедитесь, что вы перенесли метки Azure Information Protection в метки конфиденциальности и опубликовали их в центре соответствия требованиям Microsoft 365 или эквивалентной метке в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="09adb-138">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="09adb-139">Скачайте файлы и отправьте их в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="09adb-139">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="09adb-140">SharePoint не может обрабатывать зашифрованные файлы, если метка, к которой применено шифрование, имеет один из следующих конфигураций для шифрования:</span><span class="sxs-lookup"><span data-stu-id="09adb-140">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="09adb-141">**Разрешить пользователям назначать разрешения при применении метки** и **в приложениях Word, PowerPoint и Excel, предложит пользователям указать разрешения**</span><span class="sxs-lookup"><span data-stu-id="09adb-141">**Let users assign permissions when they apply the label** and **In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>
    - <span data-ttu-id="09adb-142">Для **доступа пользователей к сроку действия контента** задается значение, отличное от **Never**.</span><span class="sxs-lookup"><span data-stu-id="09adb-142">**User access to content expires** is set to a value other than **Never**.</span></span>

- <span data-ttu-id="09adb-143">Для зашифрованного документа, предоставляющего пользователю разрешения на изменение, копирование невозможно блокировать в веб-версиях приложений Office.</span><span class="sxs-lookup"><span data-stu-id="09adb-143">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="09adb-144">Сайт отслеживания документов для Azure Information Protection не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="09adb-144">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="09adb-145">Приложения Office для настольных ПК и мобильных устройств не поддерживают совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="09adb-145">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="09adb-146">Вместо этого эти приложения продолжают открывать файлы в монопольном режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="09adb-146">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="09adb-147">Если метка включает шифрование, Microsoft Cloud App Security не сможет прочитать сведения о метках файлов в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="09adb-147">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="09adb-148">Подготовка командной консоли SharePoint Online к предварительной версии</span><span class="sxs-lookup"><span data-stu-id="09adb-148">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="09adb-149">Перед включением предварительного просмотра убедитесь, что вы используете командную консоль SharePoint Online версии 16.0.19418.12000 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="09adb-149">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="09adb-150">Если у вас уже есть последняя версия, вы можете включить предварительный просмотр.</span><span class="sxs-lookup"><span data-stu-id="09adb-150">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="09adb-151">Если вы установили в коллекции PowerShell предыдущую версию командной консоли SharePoint Online, вы можете обновить модуль, выполнив следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="09adb-151">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="09adb-152">Кроме того, если вы установили предыдущую версию командной консоли SharePoint Online в центре загрузки Майкрософт, вы также можете перейти к разделу **Установка и удаление программ** и удаление командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="09adb-152">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="09adb-153">В веб-браузере перейдите на страницу Центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="09adb-153">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="09adb-154">Выберите язык и нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="09adb-154">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="09adb-155">Выберите разрядность файла MSI (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="09adb-155">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="09adb-156">Скачайте файл x64, если вы запускаете 64-разрядную версию Windows или файл x86 при запуске 32-разрядной версии.</span><span class="sxs-lookup"><span data-stu-id="09adb-156">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="09adb-157">Если вы не знаете, как узнать, [какая версия операционной системы Windows работает?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="09adb-157">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="09adb-158">После загрузки файла запустите его и следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="09adb-158">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="09adb-159">Включение предварительного просмотра с помощью Microsoft PowerShell (необязательно)</span><span class="sxs-lookup"><span data-stu-id="09adb-159">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="09adb-160">Чтобы включить предварительный просмотр, используйте командлет Set – SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="09adb-160">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="09adb-161">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к SharePoint.</span><span class="sxs-lookup"><span data-stu-id="09adb-161">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="09adb-162">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="09adb-162">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="09adb-163">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="09adb-163">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="09adb-164">Планирование развертывания после создания или изменения метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="09adb-164">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="09adb-165">После создания или изменения метки конфиденциальности в центре соответствия требованиям Microsoft 365 опубликуйте ее поэтапно.</span><span class="sxs-lookup"><span data-stu-id="09adb-165">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="09adb-166">Если вы публикуете метки, которые не были полностью синхронизированы, когда пользователи применяют метки к файлам и отправляют их в SharePoint, они не могут быть открыты в веб-версиях приложений Office.</span><span class="sxs-lookup"><span data-stu-id="09adb-166">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="09adb-167">Поиск и обнаружение электронных данных также не работают для файлов.</span><span class="sxs-lookup"><span data-stu-id="09adb-167">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="09adb-168">Рекомендуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="09adb-168">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="09adb-169">Публикация новой или измененной метки конфиденциальности только для одного или двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="09adb-169">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="09adb-170">Подождите не менее 24 часов после первоначальной публикации.</span><span class="sxs-lookup"><span data-stu-id="09adb-170">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="09adb-171">Убедитесь, что метка полностью синхронизирована.</span><span class="sxs-lookup"><span data-stu-id="09adb-171">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="09adb-172">Более широкое опубликование метки.</span><span class="sxs-lookup"><span data-stu-id="09adb-172">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="09adb-173">Отключение предварительного просмотра с помощью Microsoft PowerShell (явный отказ)</span><span class="sxs-lookup"><span data-stu-id="09adb-173">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="09adb-174">Если отключить этот предварительный просмотр, файлы, отправленные во время предварительной версии, останутся защищенными с помощью метки.</span><span class="sxs-lookup"><span data-stu-id="09adb-174">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="09adb-175">Соответствующие параметры по прежнему применяются.</span><span class="sxs-lookup"><span data-stu-id="09adb-175">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="09adb-176">Когда вы применяете метки к новым файлам после отключения предварительной версии, полнотекстового поиска, обнаружения электронных данных и совместного редактирования, больше не будут работать.</span><span class="sxs-lookup"><span data-stu-id="09adb-176">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="09adb-177">Чтобы отключить предварительный просмотр, используйте командлет Set – SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="09adb-177">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="09adb-178">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к SharePoint.</span><span class="sxs-lookup"><span data-stu-id="09adb-178">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="09adb-179">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="09adb-179">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="09adb-180">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="09adb-180">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
