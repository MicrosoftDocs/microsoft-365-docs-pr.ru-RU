---
title: Просмотр сведений о вредоносных файлах, обнаруженных в Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Сведения о том, как перейти к сведениям о вредоносных файлах, обнаруженных в SharePoint, OneDrive или Teams, а также о том, как выполнять действия с этими файлами.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47b1fea4b3b5713a8f69e8f4b2c0e2ad0f6dd6b8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036648"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="d7b8f-103">Просмотр сведений о вредоносных файлах, обнаруженных в SharePoint, OneDrive или Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7b8f-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="d7b8f-104">[Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md) защищает вашу организацию от вредоносных файлов в библиотеках документов и на сайтах групп.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="d7b8f-105">При обнаружении вредоносного файла этот файл блокируется, чтобы никто не мог открыть, скопировать, переместить или предоставить к нему общий доступ до тех пор, пока не будут предприняты дальнейшие действия группы безопасности Организации.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="d7b8f-106">В этой статье приведены инструкции по просмотру сведений об обнаруженных файлах и действиях, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="d7b8f-107">Для выполнения задач, описанных в этой статье, необходимы соответствующие [разрешения для центра безопасности &amp; и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d7b8f-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="d7b8f-108">Просмотр отчетов с информацией об обнаруженных файлах</span><span class="sxs-lookup"><span data-stu-id="d7b8f-108">View reports with information about detected files</span></span>

<span data-ttu-id="d7b8f-109">Чтобы просмотреть состояние и подробные сведения о файлах, обнаруженных в Office 365 ATP, вы можете использовать отчет о состоянии защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="d7b8f-110">В [центре безопасности &amp; и соответствия требованиям](https://protection.office.com)выберите **состояние защиты от угроз**для **панели мониторинга** \> **отчетов** \> .</span><span class="sxs-lookup"><span data-stu-id="d7b8f-110">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="d7b8f-111">В правом верхнем углу отчета выберите пункт **Просмотреть таблицу сведений**.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="d7b8f-112">Просмотр списка файлов, обнаруженных в отчете.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="d7b8f-113">Выберите элемент в списке, чтобы просмотреть подробные сведения, в том числе выполненные действия, имя файла, путь к файлу и многое другое.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="d7b8f-114">Перейдите на вкладку **Расширенный анализ** , чтобы просмотреть сведения, такие как наблюдаемое поведение и сведения анализа.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="d7b8f-115">Просмотр и инициация действий с файлами в карантине</span><span class="sxs-lookup"><span data-stu-id="d7b8f-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="d7b8f-116">В центре безопасности &amp; и соответствия требованиям выберите **Карантин** \> **Обзор** \> **управления угрозами** .</span><span class="sxs-lookup"><span data-stu-id="d7b8f-116">In the Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="d7b8f-117">(Вы также можете перейти к [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span><span class="sxs-lookup"><span data-stu-id="d7b8f-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="d7b8f-118">В верхнем левом углу раскрывающийся меню следует изменить с **сообщения** на **файлы**.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="d7b8f-119">Если список результатов содержит слишком много элементов, используйте функцию **фильтрации** для сужения выделенного фрагмента.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="d7b8f-120">Выберите элемент в списке, чтобы просмотреть подробные сведения, в том числе URL-адрес файла.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="d7b8f-121">Выберите доступное действие.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-121">Choose an available action.</span></span>
    
    - <span data-ttu-id="d7b8f-122">Выберите пункт **освободить файл** , чтобы разблокировать файл.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-122">Choose **Release file** to unblock the file.</span></span> 

      <span data-ttu-id="d7b8f-123">Выберите **Отправить отчет в корпорацию Майкрософт** , чтобы сообщить файлу о ложных срабатываниях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 

    - <span data-ttu-id="d7b8f-124">Нажмите кнопку **скачать файл** , чтобы дополнительно изучить файл.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-124">Choose **Download file** to investigate the file further.</span></span> 

    - <span data-ttu-id="d7b8f-125">Выберите **удалить из карантина** , чтобы удалить файл из списка элементов, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="d7b8f-126">Если выбран этот параметр, необходимо также удалить файл из соответствующей библиотеки в SharePoint Online, OneDrive для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="d7b8f-127">Этот параметр не разблокирует открытие или совместное открытие файла.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="d7b8f-128">Нажмите кнопку **Закрыть** , чтобы закрыть сведения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="d7b8f-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

