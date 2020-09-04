---
title: Использование скрипта для добавления пользователей в удержание в основном варианте обнаружения электронных данных в центре безопасности & соответствия требованиям
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Узнайте, как запустить сценарий для добавления почтовых ящиков & сайтов OneDrive для бизнеса в новое удержание, связанное с вариантом обнаружения электронных данных в центре безопасности &.
ms.openlocfilehash: 454fd4ea4517a46410c9d0922cc83b141fdbd893
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357679"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="4bc16-103">Использование скрипта для добавления пользователей в удержание в базовом варианте обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="4bc16-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="4bc16-104">Центр безопасности & соответствия требованиям содержит командлеты PowerShell, позволяющие автоматизировать задачи, связанные с созданием и управлением делами обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="4bc16-104">The Security & Compliance Center provides PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="4bc16-105">В настоящее время с помощью средства обнаружения электронных данных в центре безопасности & соответствия требованиям для размещения большого количества расположений содержимого хранитель на удержание занимается время и подготовка.</span><span class="sxs-lookup"><span data-stu-id="4bc16-105">Currently, using the eDiscovery case tool in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="4bc16-106">Например, перед созданием удержания необходимо собрать URL-адрес для каждого сайта OneDrive для бизнеса, который необходимо разместить на удержании.</span><span class="sxs-lookup"><span data-stu-id="4bc16-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="4bc16-107">Затем для каждого пользователя, который необходимо разместить на удержании, необходимо добавить свой почтовый ящик и сайт OneDrive для бизнеса в удержание.</span><span class="sxs-lookup"><span data-stu-id="4bc16-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="4bc16-108">В будущих выпусках центра безопасности & соответствия требованиям это будет проще.</span><span class="sxs-lookup"><span data-stu-id="4bc16-108">In future releases of the Security & Compliance Center, this will get easier to do.</span></span> <span data-ttu-id="4bc16-109">До этого вы можете автоматизировать этот процесс с помощью сценария, описанного в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4bc16-109">Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="4bc16-110">В сценарии запрашивается имя домена личных сайтов Организации (например, **contoso** в URL-адресе https://contoso-my.sharepoint.com) , имя существующего случая обнаружения электронных данных, имя нового удержания, связанное с обращением, список адресов электронной почты пользователей, которые необходимо включить в удержание, а также поисковый запрос, который будет использоваться, если требуется создать удержание на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="4bc16-110">The script prompts you for the name of your organization's My Site domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="4bc16-111">Затем сценарий получает URL-адрес сайта OneDrive для бизнеса для каждого пользователя в списке, создает новое удержание, а затем добавляет сайт "почтовый ящик и OneDrive для бизнеса" для каждого пользователя из списка в удержание.</span><span class="sxs-lookup"><span data-stu-id="4bc16-111">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="4bc16-112">Скрипт также создает файлы журнала, содержащие сведения о новом удержании.</span><span class="sxs-lookup"><span data-stu-id="4bc16-112">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="4bc16-113">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4bc16-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="4bc16-114">Шаг 1. Установка командной консоли SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4bc16-114">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="4bc16-115">Шаг 2: Создание списка пользователей</span><span class="sxs-lookup"><span data-stu-id="4bc16-115">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="4bc16-116">Шаг 3: запуск скрипта для создания удержания и добавления пользователей</span><span class="sxs-lookup"><span data-stu-id="4bc16-116">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="4bc16-117">Перед добавлением пользователей в удержание</span><span class="sxs-lookup"><span data-stu-id="4bc16-117">Before you add users to a hold</span></span>

- <span data-ttu-id="4bc16-118">Необходимо быть участником группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям и администратор SharePoint Online для запуска сценария на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="4bc16-118">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="4bc16-119">Дополнительные сведения см в статье [Назначение разрешений обнаружения электронных данных в центре безопасности & соответствия требованиям Office 365](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4bc16-119">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="4bc16-120">Максимальное количество почтовых ящиков 1 000 и 100 можно добавить в удержание, связанное с вариантом обнаружения электронных данных в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4bc16-120">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="4bc16-121">Если предполагается, что у каждого пользователя, который вы хотите разместить на удержании, есть сайт OneDrive для бизнеса, вы можете добавить в удержание не более 100 пользователей с помощью сценария, описанного в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4bc16-121">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="4bc16-122">Не забудьте сохранить список пользователей, созданных в действии 2, и сценарий, приведенный в шаге 3, в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="4bc16-122">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="4bc16-123">Это облегчит выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="4bc16-123">That will make it easier to run the script.</span></span>

- <span data-ttu-id="4bc16-124">Сценарий добавляет список пользователей в новое удержание, связанное с существующим обращением.</span><span class="sxs-lookup"><span data-stu-id="4bc16-124">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="4bc16-125">Перед выполнением скрипта убедитесь, что вы хотите связать удержание с учетом.</span><span class="sxs-lookup"><span data-stu-id="4bc16-125">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="4bc16-126">Каждый раз при запуске скрипта создаются новые сеансы безопасности & соответствия PowerShell и SharePoint Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bc16-126">Each time you run the script, new Security & Compliance PowerShell and SharePoint Online PowerShell sessions are created.</span></span> <span data-ttu-id="4bc16-127">Таким образом, вы можете использовать все сеансы PowerShell, доступные вам.</span><span class="sxs-lookup"><span data-stu-id="4bc16-127">So you could use up all the PowerShell sessions available to you.</span></span> <span data-ttu-id="4bc16-128">Чтобы избежать этого, можно выполнить следующие команды, чтобы отключить активные сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bc16-128">To prevent this from happening, you can run the following commands to disconnect your active PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

   ```powershell
   Disconnect-SPOService
   ```

- <span data-ttu-id="4bc16-129">Сценарий включает в себя минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="4bc16-129">The script includes minimal error handling.</span></span> <span data-ttu-id="4bc16-130">Его основная цель — быстро и легко разместить почтовый ящик и сайт OneDrive для бизнеса для каждого пользователя на удержании.</span><span class="sxs-lookup"><span data-stu-id="4bc16-130">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="4bc16-p109">Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="4bc16-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="4bc16-136">Шаг 1. Установка командной консоли SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4bc16-136">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="4bc16-137">Первый шаг — установка командной консоли SharePoint Online, если она еще не установлена на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4bc16-137">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="4bc16-138">В этой процедуре не нужно использовать командную консоль, но ее необходимо установить, так как она содержит необходимые условия, необходимые для сценария, выполняемого на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="4bc16-138">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="4bc16-139">Эти условия позволяют сценарию связываться с SharePoint Online для получения URL-адресов сайтов OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4bc16-139">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="4bc16-140">Перейдите к разделу [Настройка среды Windows PowerShell в командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) и выполните действия 1 и 2, чтобы установить командную консоль SharePoint Online на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="4bc16-140">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="4bc16-141">Шаг 2: Создание списка пользователей</span><span class="sxs-lookup"><span data-stu-id="4bc16-141">Step 2: Generate a list of users</span></span>

<span data-ttu-id="4bc16-142">Сценарий в действии 3 создаст удержание, связанное с вариантом обнаружения электронных данных, а также сайты "Добавление почтовых ящиков и OneDrive для бизнеса" списка пользователей в удержание.</span><span class="sxs-lookup"><span data-stu-id="4bc16-142">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="4bc16-143">Вы можете просто ввести адреса электронной почты в текстовом файле или выполнить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файле (расположенном в той же папке, в которой вы сохранили сценарий на шаге 3).</span><span class="sxs-lookup"><span data-stu-id="4bc16-143">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="4bc16-144">Вот команда PowerShell (которая запускается с помощью удаленной оболочки PowerShell, подключенной к организации Exchange Online), чтобы получить список адресов электронной почты для всех пользователей в Организации и сохранить их в текстовый файл с именем HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="4bc16-144">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="4bc16-145">После выполнения этой команды откройте текстовый файл и удалите заголовок, содержащий имя свойства  `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="4bc16-145">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="4bc16-146">Затем удалите все адреса электронной почты, кроме тех, для пользователей, которые нужно добавить в удержание, созданное на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="4bc16-146">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="4bc16-147">Убедитесь, что в списке адресов электронной почты нет пустых строк.</span><span class="sxs-lookup"><span data-stu-id="4bc16-147">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="4bc16-148">Шаг 3: запуск скрипта для создания удержания и добавления пользователей</span><span class="sxs-lookup"><span data-stu-id="4bc16-148">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="4bc16-149">При выполнении скрипта на этом этапе будут предложены следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="4bc16-149">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="4bc16-150">Перед выполнением скрипта обязательно убедитесь, что эти сведения готовы к работе.</span><span class="sxs-lookup"><span data-stu-id="4bc16-150">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="4bc16-151">**Ваши учетные данные пользователя:** Сценарий будет использовать ваши учетные данные для подключения к центру безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bc16-151">**Your user credentials:** The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="4bc16-152">Он также будет использовать эти учетные данные для доступа к SharePoint Online, чтобы получить URL-адреса OneDrive для бизнеса для списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="4bc16-152">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="4bc16-153">**Имя домена личных сайтов:** Домен личных сайтов — это домен, который содержит все сайты OneDrive для бизнеса в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4bc16-153">**Name of your My Site domain:** The My Site domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="4bc16-154">Например, если URL-адрес вашего домена "мой сайт" **https://contoso-my.sharepoint.com** , то при вводе  `contoso` скрипта для имени домена личного сайта необходимо ввести запрос.</span><span class="sxs-lookup"><span data-stu-id="4bc16-154">For example, if the URL for your My Site domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your My Site domain.</span></span>

- <span data-ttu-id="4bc16-155">**Имя дела:** Имя существующего дела.</span><span class="sxs-lookup"><span data-stu-id="4bc16-155">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="4bc16-156">Скрипт создаст новое удержание, связанное с этим случаем.</span><span class="sxs-lookup"><span data-stu-id="4bc16-156">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="4bc16-157">**Имя удержания:** Имя удержания скрипта, который будет создан и связан с заданным регистром.</span><span class="sxs-lookup"><span data-stu-id="4bc16-157">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="4bc16-158">**Поисковый запрос на удержание на основе запроса:** Вы можете создать удержание на основе запроса, чтобы на хранение помещается только контент, соответствующий указанным условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="4bc16-158">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="4bc16-159">Чтобы поместить все содержимое на удержании, просто нажмите клавишу **Ввод** , когда появится запрос на поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="4bc16-159">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="4bc16-160">**Включение удержания или нет:** Вы можете сделать так, чтобы сценарий включил удержание после того, как оно будет создано, или вы можете создать блокировку без включения.</span><span class="sxs-lookup"><span data-stu-id="4bc16-160">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="4bc16-161">Если у вас нет скрипта, который включает удержание, вы можете включить его позже в центре безопасности & соответствия требованиям или выполнив следующие команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4bc16-161">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="4bc16-162">**Имя текстового файла со списком пользователей** — имя текстового файла из шага 2, содержащего список пользователей, которые требуется добавить в удержание.</span><span class="sxs-lookup"><span data-stu-id="4bc16-162">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="4bc16-163">Если этот файл находится в той же папке, что и скрипт, просто введите имя файла (например, HoldUsers.txt).</span><span class="sxs-lookup"><span data-stu-id="4bc16-163">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="4bc16-164">Если текстовый файл находится в другой папке, введите полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="4bc16-164">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="4bc16-165">После сбора сведений, которые будут предлагаться сценарием, последним этапом является выполнение сценария для создания нового удержания и добавления в него пользователей.</span><span class="sxs-lookup"><span data-stu-id="4bc16-165">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="4bc16-166">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell с помощью суффикса имени файла `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="4bc16-166">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="4bc16-167">Например, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="4bc16-167">For example, `AddUsersToHold.ps1`.</span></span>

   ```powershell
   #script begin
   " " 
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
   write-host "***********************************************"
   " " 
   # Get user credentials &amp; Connect to Office 365 SCC, SPO
   $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
   $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
   $a = Import-PSSession $s -AllowClobber
       if (!$s)
       {
           Write-Error "Couldn't create PowerShell session."
           return;
       }
   # Load the SharePoint assemblies from the SharePoint Online Management Shell
   # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
   if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
   {
       $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
       $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
       $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
       if (!$SharePointClient)
       {
           Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
           return;
       }
   }
   if (!$spCreds)
   {
       $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
   }
   # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
   ""
   $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
   ""
   # Get other required information
   do{
   $casename = Read-Host "Enter the name of the case"
   $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
   if($caseexists -ne 'True')
   {""
   write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
   ""}
   }While($caseexists -ne 'True')
   ""
   do{
   $holdName = Read-Host "Enter the name of the new hold"
   $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
   if($holdexists -eq 'True')
   {""
   write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
   ""}
   }While($holdexists -eq 'True')
   ""
   $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
   ""
   $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
   do{
   ""
   $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
   ""
   $fileexists = test-path -path $inputfile
   if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
   }while($fileexists -ne 'True')
   #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
       #in the list are unique.
     [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
     [int]$dupl = $emailAddresses.count
     [array]$emailAddresses = $emailAddresses | select-object -unique
     $dupl -= $emailAddresses.count
   #Validate email addresses so the hold creation does not run in to an error.
   if($emailaddresses.count -gt 0){
   write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
   ""
   Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
   ""
   $finallist =@()
   foreach($emailAddress in $emailAddresses)
   {
   if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
   {$finallist += $emailaddress}
   else {"Unable to find the user $emailaddress"
   [array]$excludedlist += $emailaddress}
   }
   ""
   #find user's OneDrive Site URL using email address
   Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
   ""
   $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
   $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
   # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
   $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
   $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False 
   $UserProfileService.Credentials = $credentials
   # Take care of auth cookies
   $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
   $uri = New-Object System.Uri($AdminUrl)
   $container = New-Object System.Net.CookieContainer
   $container.SetCookies($uri, $strAuthCookie)
   $UserProfileService.CookieContainer = $container
   $urls = @()
   foreach($emailAddress in $emailAddresses)
   {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
   }
   if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
   ""
   Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
   if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
   }
   else{
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
   }
   ""
   }
   else {"No valid locations were identified. Therefore, the hold wasn't created."}
   #write log files (if needed)
   $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
   $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
   if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
   {
   Write-Host "Generating output files..." -foregroundColor Yellow
   if($ODAdded.count -gt 0){
   "OneDrive Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
   if($ODExluded.count -gt 0){ 
   "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
   "================================" | add-content .\LocationsNotOnHold.txt
   $ODExluded | add-content .\LocationsNotOnHold.txt}
   if($finallist.count -gt 0){
   " " | add-content .\LocationsOnHold.txt
   "Exchange Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
   if($excludedlist.count -gt 0){
   " "| add-content .\LocationsNotOnHold.txt
   "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
   "===============================" | add-content .\LocationsNotOnHold.txt
   $excludedlist | add-content .\LocationsNotOnHold.txt}
   $FormatEnumerationLimit=-1
   if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
   if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
   }
   }
   else {"The hold wasn't created because no valid entries were found in the text file."}
   ""
   Write-host "Script complete!" -foregroundColor Yellow
   ""
   #script end
   ```

2. <span data-ttu-id="4bc16-168">На локальном компьютере откройте Windows PowerShell и перейдите к папке, в которой был сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="4bc16-168">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="4bc16-169">Запуск скрипта; Например:</span><span class="sxs-lookup"><span data-stu-id="4bc16-169">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="4bc16-170">Введите сведения, которые будут запрашиваться сценарием.</span><span class="sxs-lookup"><span data-stu-id="4bc16-170">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="4bc16-171">Сценарий подключается к PowerShell центра безопасности & соответствия требованиям, а затем создает новое удержание в случае обнаружения электронных данных и добавляет почтовые ящики и OneDrive для бизнеса для пользователей из списка.</span><span class="sxs-lookup"><span data-stu-id="4bc16-171">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="4bc16-172">Вы можете перейти к этому случаю на странице **Обнаружение электронных** данных в центре безопасности & соответствия требованиям для просмотра нового удержания.</span><span class="sxs-lookup"><span data-stu-id="4bc16-172">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span> 

<span data-ttu-id="4bc16-173">После завершения выполнения скрипта он создает следующие файлы журнала и сохраняет их в папке, в которой расположен сценарий.</span><span class="sxs-lookup"><span data-stu-id="4bc16-173">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="4bc16-174">**LocationsOnHold.txt:** Содержит список почтовых ящиков и сайтов OneDrive для бизнеса, которые сценарий успешно поместил в удержание.</span><span class="sxs-lookup"><span data-stu-id="4bc16-174">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="4bc16-175">**LocationsNotOnHold.txt:** Содержит список почтовых ящиков и сайтов OneDrive для бизнеса, которые не были размещены в сценарии на удержании.</span><span class="sxs-lookup"><span data-stu-id="4bc16-175">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="4bc16-176">Если у пользователя есть почтовый ящик, но не сайт OneDrive для бизнеса, он будет включен в список сайтов OneDrive для бизнеса, не включенных в удержание.</span><span class="sxs-lookup"><span data-stu-id="4bc16-176">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="4bc16-177">**GetCaseHoldPolicy.txt:** Содержит выходные данные командлета **Get – caseholdpolicy позволяет** для нового удержания, который выполнялся сценарием после создания нового удержания.</span><span class="sxs-lookup"><span data-stu-id="4bc16-177">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="4bc16-178">Сведения, возвращаемые этим командлетом, включают список пользователей, чьи почтовые ящики и сайты OneDrive для бизнеса были размещены при удержании, а также включено или отключено удержание.</span><span class="sxs-lookup"><span data-stu-id="4bc16-178">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="4bc16-179">**GetCaseHoldRule.txt:** Содержит выходные данные командлета **Get – caseholdrule позволяет** для нового удержания, который выполнялся сценарием после создания нового удержания.</span><span class="sxs-lookup"><span data-stu-id="4bc16-179">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="4bc16-180">Сведения, возвращаемые этим командлетом, включают поисковый запрос, если вы использовали сценарий для создания удержания на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="4bc16-180">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
