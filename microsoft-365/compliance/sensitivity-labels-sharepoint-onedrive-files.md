---
title: Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 5946fc193b0f96501a2f8168eef0d3e694d9cfcb
ms.sourcegitcommit: 21be88a1b38b6554ffa1bc5b743c129fe8547704
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41830983"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="832bd-103">Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="832bd-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="832bd-104">Перед выполнением предварительной версии, когда вы примените метки конфиденциальности, которые включали шифрование к файлам Office, хранящимся в SharePoint и OneDrive, службе не удалось обработать содержимое этих файлов.</span><span class="sxs-lookup"><span data-stu-id="832bd-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="832bd-105">В таких обстоятельствах не работают совместное редактирование, обнаружение электронных данных, защита от потери данных, поиск, delve и другие функции совместной работы.</span><span class="sxs-lookup"><span data-stu-id="832bd-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="832bd-106">Этот предварительный просмотр включает эти функции при применении шифрования с облачным ключом:</span><span class="sxs-lookup"><span data-stu-id="832bd-106">This preview enables these features when the encryption has been applied with a cloud-based key:</span></span>

- <span data-ttu-id="832bd-107">В SharePoint распознаются метки конфиденциальности, применяемые к файлам Word, Excel и PowerPoint в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="832bd-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="832bd-108">В SharePoint также применяются параметры, соответствующие каждой метке.</span><span class="sxs-lookup"><span data-stu-id="832bd-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="832bd-109">При загрузке файла из SharePoint или OneDrive метка чувствительности перемещается вместе с файлом, а параметры применяются к нему.</span><span class="sxs-lookup"><span data-stu-id="832bd-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="832bd-110">Примените метки конфиденциальности к файлам Office, а также откройте и измените файлы, к которым применены метки конфиденциальности (если это разрешено разрешениями метки), с помощью веб-версий Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="832bd-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="832bd-111">С помощью Word в Интернете вы также можете использовать автоматические метки при редактировании документов.</span><span class="sxs-lookup"><span data-stu-id="832bd-111">With Word on the web, you can also use auto labeling when you edit documents.</span></span>

- <span data-ttu-id="832bd-112">Обнаружение электронных данных Office 365 поддерживает полнотекстовый поиск в файлах, к которым применены метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="832bd-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="832bd-113">Политики защиты от потери данных охватывают содержимое этих файлов.</span><span class="sxs-lookup"><span data-stu-id="832bd-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="832bd-114">Для мониторинга меток конфиденциальности доступны три новых события аудита.</span><span class="sxs-lookup"><span data-stu-id="832bd-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="832bd-115">филесенситивитяпплиед</span><span class="sxs-lookup"><span data-stu-id="832bd-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="832bd-116">филесенситивитилабелчанжед</span><span class="sxs-lookup"><span data-stu-id="832bd-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="832bd-117">филесенситивитилабелремовед</span><span class="sxs-lookup"><span data-stu-id="832bd-117">FileSensitivityLabelRemoved</span></span>

> [!NOTE]
> <span data-ttu-id="832bd-118">Если шифрование еще не применено к облачному ключу, но является локальным, топология управления ключами часто называется "удержание собственного ключа" (ХЙОК), но поведение SharePoint не изменяется с предварительной версией.</span><span class="sxs-lookup"><span data-stu-id="832bd-118">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span> 

<span data-ttu-id="832bd-119">Вы также можете применять метки конфиденциальности к Microsoft Teams, группам Office 365 и сайтам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="832bd-119">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="832bd-120">Для получения дополнительных сведений об этом отдельном предварительном просмотре ознакомьтесь со статьей [Использование меток конфиденциальности в Microsoft Teams, Office 365 Groups и сайты SharePoint (общедоступная Предварительная версия)](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="832bd-120">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="832bd-121">Вы всегда можете отказаться от этого предварительного просмотра в любое время.</span><span class="sxs-lookup"><span data-stu-id="832bd-121">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="832bd-122">Просмотрите следующее видео (без звука), чтобы увидеть новые возможности в действии:</span><span class="sxs-lookup"><span data-stu-id="832bd-122">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="832bd-123">Requirements</span><span class="sxs-lookup"><span data-stu-id="832bd-123">Requirements</span></span>

<span data-ttu-id="832bd-124">Эти функции работают только с [метками конфиденциальности](sensitivity-labels.md) .</span><span class="sxs-lookup"><span data-stu-id="832bd-124">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="832bd-125">Если у вас есть метки Azure Information Protection, сначала необходимо перенести их в метки конфиденциальности, чтобы можно было включить эти функции для новых файлов, которые вы отправляете.</span><span class="sxs-lookup"><span data-stu-id="832bd-125">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="832bd-126">Инструкции можно посмотреть, [как перенести метки Azure Information Protection в единые метки конфиденциальности](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="832bd-126">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="832bd-127">Для этого предварительный просмотр используйте приложение OneDrive Sync версии 19.002.0121.0008 или более поздней версии для Windows, а также версию 19.002.0107.0008 или более поздней версии на компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="832bd-127">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="832bd-128">Обе эти версии выпущены 28 января 2019 и в настоящее время выпускаются для всех звонков.</span><span class="sxs-lookup"><span data-stu-id="832bd-128">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="832bd-129">Дополнительные сведения можно найти в статье [заметки о выпуске OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="832bd-129">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="832bd-130">После включения этого предварительного просмотра пользователям, запускающим старую версию приложения синхронизации, будет предложено обновить его.</span><span class="sxs-lookup"><span data-stu-id="832bd-130">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="832bd-131">Ограничения</span><span class="sxs-lookup"><span data-stu-id="832bd-131">Limitations</span></span>

- <span data-ttu-id="832bd-132">Если вы включите этот предварительный просмотр, пользователи, которые изменяют метку в файле в папке синхронизации OneDrive, могут не сохранить другие изменения, внесенные в файл.</span><span class="sxs-lookup"><span data-stu-id="832bd-132">When you enable this preview, users who change a label on a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="832bd-133">Пользователи видят [красный круг с белым крестиком](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), и им предлагается сохранить новые изменения как отдельную копию.</span><span class="sxs-lookup"><span data-stu-id="832bd-133">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="832bd-134">В дополнение к изменениям меток, инициированных пользователями, такое же поведение может произойти, если администратор изменяет параметры опубликованной метки, которая уже применена к файлам, загруженным в клиент синхронизации пользователей.</span><span class="sxs-lookup"><span data-stu-id="832bd-134">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="832bd-135">Чтобы избежать потери работы для этих сценариев, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="832bd-135">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="832bd-136">Чтобы применить метки, используйте веб-версии приложений Office.</span><span class="sxs-lookup"><span data-stu-id="832bd-136">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="832bd-137">Закройте файл после применения метки, а затем снова откройте файл, чтобы внести другие изменения.</span><span class="sxs-lookup"><span data-stu-id="832bd-137">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="832bd-138">SharePoint не автоматически применяет новые метки к существующим файлам, которые вы уже зашифровале с помощью меток Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="832bd-138">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="832bd-139">Чтобы обеспечить работу функций после включения этого предварительного просмотра, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="832bd-139">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="832bd-140">Убедитесь, что вы перенесли метки Azure Information Protection в метки конфиденциальности и опубликовали их в центре соответствия требованиям Microsoft 365 или эквивалентной метке в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="832bd-140">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="832bd-141">Скачайте файлы и отправьте их в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="832bd-141">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="832bd-142">SharePoint не может обрабатывать зашифрованные файлы, если метка, к которой применено шифрование, имеет один из следующих конфигураций для шифрования:</span><span class="sxs-lookup"><span data-stu-id="832bd-142">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="832bd-143">**Разрешить пользователям назначать разрешения при применении метки** и **в приложениях Word, PowerPoint и Excel, предложит пользователям указать разрешения**</span><span class="sxs-lookup"><span data-stu-id="832bd-143">**Let users assign permissions when they apply the label** and **In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>
    - <span data-ttu-id="832bd-144">Для **доступа пользователей к сроку действия контента** задается значение, отличное от **Never**.</span><span class="sxs-lookup"><span data-stu-id="832bd-144">**User access to content expires** is set to a value other than **Never**.</span></span>

- <span data-ttu-id="832bd-145">Для зашифрованного документа, предоставляющего пользователю разрешения на изменение, копирование невозможно блокировать в веб-версиях приложений Office.</span><span class="sxs-lookup"><span data-stu-id="832bd-145">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="832bd-146">Сайт отслеживания документов для Azure Information Protection не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="832bd-146">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="832bd-147">Приложения Office для настольных ПК и мобильных устройств не поддерживают совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="832bd-147">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="832bd-148">Вместо этого эти приложения продолжают открывать файлы в монопольном режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="832bd-148">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="832bd-149">Если метка включает шифрование, Microsoft Cloud App Security не сможет прочитать сведения о метках файлов в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="832bd-149">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

- <span data-ttu-id="832bd-150">Если помеченный документ передается в SharePoint и применяется шифрование с помощью учетной записи с именем участника-службы, документ невозможно открыть в Office в Интернете.</span><span class="sxs-lookup"><span data-stu-id="832bd-150">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="832bd-151">Примеры сценариев включают Microsoft Cloud App Security и файл, отправленный в Teams по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="832bd-151">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="832bd-152">Документы, зашифрованные с помощью следующих способов, невозможно открыть в Office в Интернете:</span><span class="sxs-lookup"><span data-stu-id="832bd-152">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="832bd-153">Шифрование, использующее локальный ключ ("удержание собственного ключа" или ХЙОК)</span><span class="sxs-lookup"><span data-stu-id="832bd-153">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="832bd-154">Шифрование, которое было применено независимо от метки, например, путем непосредственного применения шаблона защиты управления правами.</span><span class="sxs-lookup"><span data-stu-id="832bd-154">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="832bd-155">Подготовка командной консоли SharePoint Online к предварительной версии</span><span class="sxs-lookup"><span data-stu-id="832bd-155">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="832bd-156">Перед включением предварительного просмотра убедитесь, что вы используете командную консоль SharePoint Online версии 16.0.19418.12000 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="832bd-156">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="832bd-157">Если у вас уже есть последняя версия, вы можете включить предварительный просмотр.</span><span class="sxs-lookup"><span data-stu-id="832bd-157">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="832bd-158">Если вы установили в коллекции PowerShell предыдущую версию командной консоли SharePoint Online, вы можете обновить модуль, выполнив следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="832bd-158">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="832bd-159">Кроме того, если вы установили предыдущую версию командной консоли SharePoint Online в центре загрузки Майкрософт, вы также можете перейти к разделу **Установка и удаление программ** и удаление командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="832bd-159">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="832bd-160">В веб-браузере перейдите на страницу Центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="832bd-160">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="832bd-161">Выберите язык и нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="832bd-161">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="832bd-162">Выберите разрядность файла MSI (x64 или x86).</span><span class="sxs-lookup"><span data-stu-id="832bd-162">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="832bd-163">Скачайте файл x64, если вы запускаете 64-разрядную версию Windows или файл x86 при запуске 32-разрядной версии.</span><span class="sxs-lookup"><span data-stu-id="832bd-163">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="832bd-164">Если вы не знаете, как узнать, [какая версия операционной системы Windows работает?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="832bd-164">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="832bd-165">После загрузки файла запустите его и следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="832bd-165">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="832bd-166">Включение предварительного просмотра с помощью Microsoft PowerShell (необязательно)</span><span class="sxs-lookup"><span data-stu-id="832bd-166">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="832bd-167">Чтобы включить предварительный просмотр, используйте командлет Set – SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="832bd-167">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="832bd-168">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к SharePoint.</span><span class="sxs-lookup"><span data-stu-id="832bd-168">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="832bd-169">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="832bd-169">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="832bd-170">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="832bd-170">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="832bd-171">Планирование развертывания после создания или изменения метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="832bd-171">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="832bd-172">После создания или изменения метки конфиденциальности в центре соответствия требованиям Microsoft 365 опубликуйте ее поэтапно.</span><span class="sxs-lookup"><span data-stu-id="832bd-172">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="832bd-173">Если вы публикуете метки, которые не были полностью синхронизированы, когда пользователи применяют метки к файлам и отправляют их в SharePoint, они не могут быть открыты в веб-версиях приложений Office.</span><span class="sxs-lookup"><span data-stu-id="832bd-173">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="832bd-174">Поиск и обнаружение электронных данных также не работают для файлов.</span><span class="sxs-lookup"><span data-stu-id="832bd-174">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="832bd-175">Рекомендуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="832bd-175">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="832bd-176">Публикация новой или измененной метки конфиденциальности только для одного или двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="832bd-176">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="832bd-177">Подождите не менее 24 часов после первоначальной публикации.</span><span class="sxs-lookup"><span data-stu-id="832bd-177">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="832bd-178">Убедитесь, что метка полностью синхронизирована.</span><span class="sxs-lookup"><span data-stu-id="832bd-178">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="832bd-179">Более широкое опубликование метки.</span><span class="sxs-lookup"><span data-stu-id="832bd-179">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="832bd-180">Отключение предварительного просмотра с помощью Microsoft PowerShell (явный отказ)</span><span class="sxs-lookup"><span data-stu-id="832bd-180">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="832bd-181">Если отключить этот предварительный просмотр, файлы, отправленные во время предварительной версии, останутся защищенными с помощью метки.</span><span class="sxs-lookup"><span data-stu-id="832bd-181">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="832bd-182">Соответствующие параметры по прежнему применяются.</span><span class="sxs-lookup"><span data-stu-id="832bd-182">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="832bd-183">Когда вы применяете метки к новым файлам после отключения предварительной версии, полнотекстового поиска, обнаружения электронных данных и совместного редактирования, больше не будут работать.</span><span class="sxs-lookup"><span data-stu-id="832bd-183">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="832bd-184">Чтобы отключить предварительный просмотр, используйте командлет Set – SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="832bd-184">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="832bd-185">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к SharePoint.</span><span class="sxs-lookup"><span data-stu-id="832bd-185">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="832bd-186">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="832bd-186">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="832bd-187">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="832bd-187">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
