---
title: Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Администраторы могут включить поддержку меток конфиденциальности для файлов Word, Excel и PowerPoint в SharePoint и OneDrive.
ms.openlocfilehash: c050aefb9feebbb3ff37a8504ba1b8385fb0ff49
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "38687470"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="7e063-103">Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7e063-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="7e063-104">Ранее при применении меток конфиденциальности, которые включали шифрование к файлам Office, хранящимся в SharePoint и OneDrive, службе не удалось обработать содержимое этих файлов.</span><span class="sxs-lookup"><span data-stu-id="7e063-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="7e063-105">В таких обстоятельствах не работают совместное редактирование, обнаружение электронных данных, защита от потери данных, поиск, delve и другие функции совместной работы.</span><span class="sxs-lookup"><span data-stu-id="7e063-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="7e063-106">Этот предварительный просмотр включает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="7e063-106">This preview enables these features:</span></span>

- <span data-ttu-id="7e063-107">В SharePoint распознаются метки конфиденциальности, применяемые к файлам Word, Excel и PowerPoint в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7e063-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="7e063-108">В SharePoint также применяются параметры, соответствующие каждой метке.</span><span class="sxs-lookup"><span data-stu-id="7e063-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="7e063-109">При загрузке файла из SharePoint или OneDrive метка чувствительности перемещается вместе с файлом, а параметры применяются к нему.</span><span class="sxs-lookup"><span data-stu-id="7e063-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="7e063-110">Примените метки конфиденциальности к файлам Office, а также откройте и измените файлы, к которым применены метки конфиденциальности (если это разрешено разрешениями метки), с помощью веб-версий Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7e063-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="7e063-111">С помощью Word в Интернете вы также можете использовать автоматические метки при редактировании документов.</span><span class="sxs-lookup"><span data-stu-id="7e063-111">With Word on the web, you can also use Auto labeling when you edit documents.</span></span>

- <span data-ttu-id="7e063-112">Обнаружение электронных данных Office 365 поддерживает полнотекстовый поиск в файлах, к которым применены метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="7e063-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="7e063-113">Политики защиты от потери данных охватывают содержимое этих файлов.</span><span class="sxs-lookup"><span data-stu-id="7e063-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="7e063-114">Для мониторинга меток конфиденциальности доступны три новых события аудита.</span><span class="sxs-lookup"><span data-stu-id="7e063-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="7e063-115">филесенситивитяпплиед</span><span class="sxs-lookup"><span data-stu-id="7e063-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="7e063-116">филесенситивитилабелчанжед</span><span class="sxs-lookup"><span data-stu-id="7e063-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="7e063-117">филесенситивитилабелремовед</span><span class="sxs-lookup"><span data-stu-id="7e063-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="7e063-118">Вы также можете применять метки конфиденциальности к Microsoft Teams, группам Office 365 и сайтам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e063-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="7e063-119">[Подробнее](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="7e063-119">[Learn more](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="7e063-120">При необходимости вы можете отказаться от предварительного просмотра в любое время.</span><span class="sxs-lookup"><span data-stu-id="7e063-120">If necessary, you can opt out of the preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e063-121">Требования</span><span class="sxs-lookup"><span data-stu-id="7e063-121">Requirements</span></span>

<span data-ttu-id="7e063-122">Эти функции работают только с [метками конфиденциальности](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="7e063-122">These features work only with [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="7e063-123">Если вы использовали метки Azure Information Protection, вы можете преобразовать их в метки конфиденциальности, чтобы включить эти функции для новых файлов, которые вы отправляете.</span><span class="sxs-lookup"><span data-stu-id="7e063-123">If you used Azure Information Protection labels, you can convert them to sensitivity labels to enable these features for new files that you upload.</span></span> [<span data-ttu-id="7e063-124">Узнайте, как</span><span class="sxs-lookup"><span data-stu-id="7e063-124">Learn how</span></span>](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

<span data-ttu-id="7e063-125">Для этого предварительный просмотр используйте приложение OneDrive Sync версии 19.002.0121.0008 или более поздней версии для Windows и версии 19.002.0107.0008 или более поздней версии на компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="7e063-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="7e063-126">Обе эти версии выпущены 28 января 2019 и в настоящее время выпускаются для всех звонков.</span><span class="sxs-lookup"><span data-stu-id="7e063-126">Both of these versions were released on January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="7e063-127">[Ознакомьтесь с заметками о выпуске OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="7e063-127">[See the OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="7e063-128">После включения этого предварительного просмотра пользователям, запускающим старую версию приложения синхронизации, будет предложено обновить его.</span><span class="sxs-lookup"><span data-stu-id="7e063-128">After you enable this preview, users who run an older version of the sync app will be prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="7e063-129">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7e063-129">Limitations</span></span>

- <span data-ttu-id="7e063-130">Если вы включите этот предварительный просмотр, пользователи, которые применяют метку к файлу с помощью настольного компьютера или мобильного приложения Office, могут не сохранить другие изменения, внесенные в файл.</span><span class="sxs-lookup"><span data-stu-id="7e063-130">When you enable this preview, users who apply a label to a file by using the Office desktop or mobile apps might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="7e063-131">Вместо этого приложение предлагает пользователям сохранить или отменить локальные изменения.</span><span class="sxs-lookup"><span data-stu-id="7e063-131">Instead, the app prompts users to Save As or Discard local changes.</span></span> <span data-ttu-id="7e063-132">Чтобы избежать потери работы, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="7e063-132">To avoid losing work, do one of these actions:</span></span>

  - <span data-ttu-id="7e063-133">Чтобы применить метки, используйте веб-версии приложений Office.</span><span class="sxs-lookup"><span data-stu-id="7e063-133">To apply labels, use the web versions of the Office apps.</span></span>

  - <span data-ttu-id="7e063-134">Закройте файл после применения метки и повторно откройте файл, чтобы внести другие изменения.</span><span class="sxs-lookup"><span data-stu-id="7e063-134">Close a file after you apply a label and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="7e063-135">SharePoint не автоматически применяет новые метки к существующим файлам, которые вы уже зашифровале с помощью меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="7e063-135">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="7e063-136">Чтобы обеспечить работу функций после включения этого предварительного просмотра, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7e063-136">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>

  - <span data-ttu-id="7e063-137">Преобразуйте метки Azure Information Protection в метки чувствительности.</span><span class="sxs-lookup"><span data-stu-id="7e063-137">Convert the Azure Information Protection labels to sensitivity labels.</span></span>

  - <span data-ttu-id="7e063-138">Скачайте файлы и отправьте их в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e063-138">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="7e063-139">SharePoint не может обрабатывать метки с настраиваемыми разрешениями и метками с датами истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="7e063-139">SharePoint can't process labels with custom permissions and labels with expiration dates.</span></span>

- <span data-ttu-id="7e063-140">Если у пользователей есть разрешения на изменение, веб-версии приложений Office разрешают копирование независимо от параметра copy Policy в метке.</span><span class="sxs-lookup"><span data-stu-id="7e063-140">When users have edit permissions, the web versions of the Office apps allow copying regardless of the copy policy setting in the label.</span></span>

- <span data-ttu-id="7e063-141">Отзыв, отслеживание и отчеты RMS не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7e063-141">RMS revocation, tracking, and reporting are unsupported.</span></span>

- <span data-ttu-id="7e063-142">Приложения Office для настольных ПК и мобильных устройств не поддерживают совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="7e063-142">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="7e063-143">Вместо этого эти приложения продолжают открывать файлы в монопольном режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="7e063-143">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="7e063-144">Если метка включает шифрование, Microsoft Cloud App Security не сможет прочитать сведения о метках файлов в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e063-144">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="7e063-145">Подготовка командной консоли SharePoint Online к предварительной версии</span><span class="sxs-lookup"><span data-stu-id="7e063-145">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="7e063-146">Перед включением предварительной версии убедитесь, что вы используете последнюю версию командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7e063-146">Before you enable the preview, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="7e063-147">Если у вас уже есть последняя версия, вы можете включить предварительный просмотр.</span><span class="sxs-lookup"><span data-stu-id="7e063-147">If you already have the latest version, you can go ahead and enable the preview.</span></span>

<span data-ttu-id="7e063-148">Подготовка командной консоли SharePoint Online для предварительного просмотра:</span><span class="sxs-lookup"><span data-stu-id="7e063-148">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="7e063-149">Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу **Установка и удаление программ** и удаление "консоль управления SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="7e063-149">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell.”</span></span>

2. <span data-ttu-id="7e063-150">В веб-браузере перейдите на страницу центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="7e063-150">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="7e063-151">Выберите язык и нажмите кнопку **скачать**.</span><span class="sxs-lookup"><span data-stu-id="7e063-151">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="7e063-152">Выберите файл в формате x64 и x86. msi.</span><span class="sxs-lookup"><span data-stu-id="7e063-152">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="7e063-153">Скачайте файл x64, если вы запускаете 64-разрядную версию Windows или файл x86 при запуске 32-разрядной версии.</span><span class="sxs-lookup"><span data-stu-id="7e063-153">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="7e063-154">Если вы не знаете, посмотрите, [какая версия операционной системы Windows работает?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="7e063-154">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="7e063-155">После загрузки файла запустите его и следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="7e063-155">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="7e063-156">Включение предварительного просмотра с помощью Microsoft PowerShell (необязательно)</span><span class="sxs-lookup"><span data-stu-id="7e063-156">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="7e063-157">Чтобы включить предварительный просмотр, используйте командлет Set – SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="7e063-157">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="7e063-158">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e063-158">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="7e063-159">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="7e063-159">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="7e063-160">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7e063-160">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="7e063-161">Планирование развертывания после создания или изменения метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="7e063-161">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="7e063-162">После создания или изменения метки конфиденциальности в центре соответствия требованиям Microsoft 365 опубликуйте ее поэтапно.</span><span class="sxs-lookup"><span data-stu-id="7e063-162">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="7e063-163">Если вы публикуете метки, которые не были полностью синхронизированы, когда пользователи применяют метки к файлам и отправляют их в SharePoint, они не могут быть открыты в веб-версиях приложений Office.</span><span class="sxs-lookup"><span data-stu-id="7e063-163">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="7e063-164">Поиск и обнаружение электронных данных также не работают для файлов.</span><span class="sxs-lookup"><span data-stu-id="7e063-164">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="7e063-165">Рекомендуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7e063-165">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="7e063-166">Публикация новой или измененной метки конфиденциальности только для одного или двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="7e063-166">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="7e063-167">Подождите не менее 24 часов после первоначальной публикации.</span><span class="sxs-lookup"><span data-stu-id="7e063-167">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="7e063-168">Убедитесь, что метка полностью синхронизирована.</span><span class="sxs-lookup"><span data-stu-id="7e063-168">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="7e063-169">Более широкое опубликование метки.</span><span class="sxs-lookup"><span data-stu-id="7e063-169">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="7e063-170">Отключение предварительного просмотра с помощью Microsoft PowerShell (явный отказ)</span><span class="sxs-lookup"><span data-stu-id="7e063-170">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="7e063-171">Если отключить этот предварительный просмотр, файлы, отправленные во время предварительной версии, останутся защищенными с помощью метки.</span><span class="sxs-lookup"><span data-stu-id="7e063-171">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="7e063-172">Соответствующие параметры по прежнему применяются.</span><span class="sxs-lookup"><span data-stu-id="7e063-172">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="7e063-173">Когда вы применяете метки к новым файлам после отключения предварительной версии, полнотекстового поиска, обнаружения электронных данных и совместного редактирования, больше не будут работать.</span><span class="sxs-lookup"><span data-stu-id="7e063-173">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="7e063-174">Чтобы отключить предварительный просмотр, используйте командлет Set – SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="7e063-174">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="7e063-175">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e063-175">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="7e063-176">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="7e063-176">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="7e063-177">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7e063-177">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
