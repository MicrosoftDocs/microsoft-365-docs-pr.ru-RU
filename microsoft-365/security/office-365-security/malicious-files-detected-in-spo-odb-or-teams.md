---
title: Просмотр сведений о вредоносных файлах, обнаруженных в SharePoint, OneDrive или Microsoft Teams
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: b16ba88cd4984754f92fac2917f0f2b393600692
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091329"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="d220f-103">Просмотр сведений о вредоносных файлах, обнаруженных в SharePoint, OneDrive или Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d220f-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="d220f-104">[Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md) защищает вашу организацию от вредоносных файлов в библиотеках документов и на сайтах групп.</span><span class="sxs-lookup"><span data-stu-id="d220f-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="d220f-105">При обнаружении вредоносного файла этот файл блокируется, чтобы никто не мог открыть, скопировать, переместить или предоставить к нему общий доступ до тех пор, пока не будут предприняты дальнейшие действия группы безопасности Организации.</span><span class="sxs-lookup"><span data-stu-id="d220f-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="d220f-106">В этой статье приведены инструкции по просмотру сведений об обнаруженных файлах и действиях, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="d220f-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="d220f-107">Для выполнения задач, описанных в этой статье, необходимы разрешения, необходимые [для центра безопасности &amp; Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d220f-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="d220f-108">Просмотр отчетов с информацией об обнаруженных файлах</span><span class="sxs-lookup"><span data-stu-id="d220f-108">View reports with information about detected files</span></span>

<span data-ttu-id="d220f-109">Чтобы просмотреть состояние и подробные сведения о файлах, обнаруженных в Office 365 ATP, вы можете использовать отчет о состоянии защиты от угроз.</span><span class="sxs-lookup"><span data-stu-id="d220f-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="d220f-110">В [центре безопасности &amp; и соответствия требованиям Office 365](https://protection.office.com)выберите **состояние защиты от угроз**для **панели мониторинга** \> **отчетов** \> .</span><span class="sxs-lookup"><span data-stu-id="d220f-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="d220f-111">В правом верхнем углу отчета выберите пункт **Просмотреть таблицу сведений**.</span><span class="sxs-lookup"><span data-stu-id="d220f-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="d220f-112">Просмотр списка файлов, обнаруженных в отчете.</span><span class="sxs-lookup"><span data-stu-id="d220f-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="d220f-113">Выберите элемент в списке, чтобы просмотреть подробные сведения, в том числе выполненные действия, имя файла, путь к файлу и многое другое.</span><span class="sxs-lookup"><span data-stu-id="d220f-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="d220f-114">Перейдите на вкладку **Расширенный анализ** , чтобы просмотреть сведения, такие как наблюдаемое поведение и сведения анализа.</span><span class="sxs-lookup"><span data-stu-id="d220f-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="d220f-115">Просмотр и инициация действий с файлами в карантине</span><span class="sxs-lookup"><span data-stu-id="d220f-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="d220f-116">В центре безопасности &amp; и соответствия требованиям Office 365 выберите **Карантин** **Обзор** \> **управления** \> угрозами.</span><span class="sxs-lookup"><span data-stu-id="d220f-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="d220f-117">В левом верхнем углу измените фильтр с " **Электронная почта** " на " **содержимое**".</span><span class="sxs-lookup"><span data-stu-id="d220f-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="d220f-118">Выберите элемент в списке, чтобы просмотреть подробные сведения, в том числе URL-адрес файла.</span><span class="sxs-lookup"><span data-stu-id="d220f-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="d220f-119">Выберите доступное действие.</span><span class="sxs-lookup"><span data-stu-id="d220f-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="d220f-120">Выберите **отпустить &amp; отчет** , чтобы разблокировать файл.</span><span class="sxs-lookup"><span data-stu-id="d220f-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="d220f-121">Выберите **Отправить отчет в корпорацию Майкрософт** , чтобы сообщить файлу о ложных срабатываниях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d220f-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="d220f-122">Нажмите кнопку **скачать файл** , чтобы дополнительно изучить файл.</span><span class="sxs-lookup"><span data-stu-id="d220f-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="d220f-123">Нажмите кнопку **Удалить** , чтобы удалить файл из списка элементов, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="d220f-123">Choose **Delete** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="d220f-124">Если выбран этот параметр, необходимо также удалить файл из соответствующей библиотеки в SharePoint Online, OneDrive для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d220f-124">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="d220f-125">Этот параметр не разблокирует открытие или совместное открытие файла.</span><span class="sxs-lookup"><span data-stu-id="d220f-125">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="d220f-126">Нажмите кнопку **Закрыть** , чтобы закрыть сведения для выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="d220f-126">Choose **Close** to close the details for a selected item.</span></span> 
  
  

