---
title: Использование сценария для добавления пользователей в удержание в случае core eDiscovery
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
description: Узнайте, как запустить сценарий для добавления почтовых ящиков & сайтов OneDrive для бизнеса в новое удержание, связанное с делом eDiscovery в Центре соответствия требованиям Microsoft 365.
ms.openlocfilehash: 278e8e051165eca906e9b454268068cbbe6aef05
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175578"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="cda50-103">Использование сценария для добавления пользователей в удержание в случае core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cda50-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="cda50-104">PowerShell & Центре безопасности и соответствия требованиям предоставляет рабочие процессы для автоматизации трудоемких задач, связанных с созданием дел eDiscovery и управлением ними.</span><span class="sxs-lookup"><span data-stu-id="cda50-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="cda50-105">В настоящее время применение основного дела eDiscovery в Центре безопасности & соответствия требованиям для применения большого количества местоположений контента хранителя на удержание требует времени и подготовки.</span><span class="sxs-lookup"><span data-stu-id="cda50-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="cda50-106">Например, перед созданием удержания необходимо собрать URL-адрес для каждого сайта OneDrive для бизнеса, который вы хотите разместить на удержании.</span><span class="sxs-lookup"><span data-stu-id="cda50-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="cda50-107">Затем для каждого пользователя, для которых необходимо наложить удержание, необходимо добавить к удержанию его почтовый ящик и сайт OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cda50-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="cda50-108">Для автоматизации этого процесса можно использовать сценарий, который используется в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cda50-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="cda50-109">Сценарий запрашивает имя домена "Мой сайт" вашей организации (например, в URL-адресе, имя существующего дела `contoso` eDiscovery, имя нового удержания, связанного с делом, список адресов электронной почты пользователей, которые нужно поместить на удержание, и поисковый запрос, который будет применяться при создании удержания на основе https://contoso-my.sharepoint.com) запроса.</span><span class="sxs-lookup"><span data-stu-id="cda50-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="cda50-110">Затем сценарий получает URL-адрес сайта OneDrive для бизнеса для каждого пользователя в списке, создает новое удержание, а затем добавляет почтовый ящик и сайт OneDrive для бизнеса для каждого пользователя в списке в удержание.</span><span class="sxs-lookup"><span data-stu-id="cda50-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="cda50-111">Скрипт также создает файлы журналов, содержащие сведения о новом удержании.</span><span class="sxs-lookup"><span data-stu-id="cda50-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="cda50-112">Чтобы это произошло, сделайте вот что:</span><span class="sxs-lookup"><span data-stu-id="cda50-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="cda50-113">Шаг 1. Установка командной консоли SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cda50-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="cda50-114">Шаг 2. Создание списка пользователей</span><span class="sxs-lookup"><span data-stu-id="cda50-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="cda50-115">Шаг 3. Запуск сценария для создания удержания и добавления пользователей</span><span class="sxs-lookup"><span data-stu-id="cda50-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="cda50-116">Перед добавлением пользователей в удержание</span><span class="sxs-lookup"><span data-stu-id="cda50-116">Before you add users to a hold</span></span>

- <span data-ttu-id="cda50-117">Для запуска сценария на шаге 3 необходимо быть членом группы ролей "Руководитель службы eDiscovery Manager" в Центре безопасности & соответствия требованиям и администратором SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cda50-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="cda50-118">Дополнительные сведения см. в центре безопасности и соответствия требованиям [Office 365 & назначить разрешения на & eDiscovery.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="cda50-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="cda50-119">К удержанию, связанному с делом eDiscover & y в Центре безопасности и соответствия требованиям, можно добавить не более 1000 почтовых ящиков и 100 сайтов.</span><span class="sxs-lookup"><span data-stu-id="cda50-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="cda50-120">Предположим, что у каждого пользователя, который вы хотите разместить на удержании, есть сайт OneDrive для бизнеса, вы можете добавить в удержание не более 100 пользователей с помощью сценария, написанного в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cda50-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="cda50-121">Не забудьте сохранить список пользователей, которые вы создали на шаге 2, и скрипт на шаге 3 в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="cda50-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="cda50-122">Это упростит запуск сценария.</span><span class="sxs-lookup"><span data-stu-id="cda50-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="cda50-123">Сценарий добавляет список пользователей в новое удержание, связанное с существующим делом.</span><span class="sxs-lookup"><span data-stu-id="cda50-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="cda50-124">Убедитесь, что перед запуском сценария создается дело, с помощью которое вы хотите связать удержание.</span><span class="sxs-lookup"><span data-stu-id="cda50-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="cda50-125">Сценарий в этой статье поддерживает современную проверку подлинности при подключении к PowerShell Центра & безопасности и sharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cda50-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="cda50-126">Вы можете использовать сценарий как есть, если вы — microsoft 365 или организация Microsoft 365 GCC.</span><span class="sxs-lookup"><span data-stu-id="cda50-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="cda50-127">Если вы — организация Office 365 Germany, Microsoft 365 GCC High или Microsoft 365 DoD, вам придется изменить сценарий, чтобы успешно запустить его.</span><span class="sxs-lookup"><span data-stu-id="cda50-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="cda50-128">В частности, необходимо изменить строку и использовать параметры `Connect-IPPSSession` *ConnectionUri* и *AzureADAuthorizationEndpointUri* (и соответствующие значения для типа организации) для подключения к PowerShell Центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cda50-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="cda50-129">Дополнительные сведения см. в примерах [в PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)Центра & безопасности.</span><span class="sxs-lookup"><span data-stu-id="cda50-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="cda50-130">Сценарий автоматически отключается от PowerShell центра & безопасности и sharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cda50-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="cda50-131">Сценарий включает минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="cda50-131">The script includes minimal error handling.</span></span> <span data-ttu-id="cda50-132">Его основная цель — быстро и легко разместить почтовый ящик и сайт OneDrive для бизнеса каждого пользователя на удержание.</span><span class="sxs-lookup"><span data-stu-id="cda50-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="cda50-p109">Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="cda50-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="cda50-138">Шаг 1. Установка командной консоли SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cda50-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="cda50-139">Первый шаг — установка оболочки управления SharePoint Online, если она еще не установлена на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cda50-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="cda50-140">Вам не нужно использовать оболочку в этой процедуре, но ее необходимо установить, так как она содержит необходимые порядок, необходимые для скрипта, который вы запустите в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="cda50-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="cda50-141">Эти необходимые условия позволяют сценарию взаимодействовать с SharePoint Online для получения URL-адресов сайтов OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cda50-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="cda50-142">Перейдите к разделу "Настройка Windows PowerShell [SharePoint Online"](https://go.microsoft.com/fwlink/p/?LinkID=286318) и выполните шаг 1 и шаг 2, чтобы установить на локальном компьютере оболочку управления SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cda50-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="cda50-143">Шаг 2. Создание списка пользователей</span><span class="sxs-lookup"><span data-stu-id="cda50-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="cda50-144">Сценарий в шаге 3 создаст удержание, связанное с делом eDiscovery, и добавит почтовые ящики и сайты OneDrive для бизнеса списка пользователей в удержание.</span><span class="sxs-lookup"><span data-stu-id="cda50-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="cda50-145">Вы можете просто ввести адреса электронной почты в текстовый файл или выполнить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файл (расположенный в той же папке, в которую вы сохраните сценарий на шаге 3).</span><span class="sxs-lookup"><span data-stu-id="cda50-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="cda50-146">Вот команда PowerShell (которую вы запустите с помощью удаленной powerShell, подключенной к организации Exchange Online), чтобы получить список адресов электронной почты для всех пользователей в организации и сохранить его в текстовый файл с именем HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="cda50-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="cda50-147">После запуска этой команды откройте текстовый файл и удалите заглавную папку с именем  `PrimarySmtpAddress` свойства.</span><span class="sxs-lookup"><span data-stu-id="cda50-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="cda50-148">Затем удалите все адреса электронной почты, кроме тех, для которых вы хотите добавить удержание, которое вы создадим на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="cda50-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="cda50-149">Убедитесь, что до или после списка адресов электронной почты нет пустых строк.</span><span class="sxs-lookup"><span data-stu-id="cda50-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="cda50-150">Шаг 3. Запуск сценария для создания удержания и добавления пользователей</span><span class="sxs-lookup"><span data-stu-id="cda50-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="cda50-151">При запуске скрипта на этом этапе вам будут предложены следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="cda50-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="cda50-152">Перед запуском сценария обязательно подготовьтесь к этим данным.</span><span class="sxs-lookup"><span data-stu-id="cda50-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="cda50-153">**Учетные данные пользователя:** Сценарий будет использовать ваши учетные данные для подключения к Центру безопасности & соответствия требованиям с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cda50-153">**Your user credentials:** The script will use your credentials to connect to Security & Compliance Center with PowerShell.</span></span> <span data-ttu-id="cda50-154">Они также будут использовать эти учетные данные для доступа к SharePoint Online, чтобы получить URL-адреса OneDrive для бизнеса для списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="cda50-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="cda50-155">**Имя домена SharePoint:** В сценарии вам будет предложено ввести это имя, чтобы подключиться к Центру администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cda50-155">**Name of your SharePoint domain:** The script prompts you to enter this name so it can connect to the SharePoint admin center.</span></span> <span data-ttu-id="cda50-156">В нем также используется доменное имя ДЛЯ URL-адресов OneDrive в организации.</span><span class="sxs-lookup"><span data-stu-id="cda50-156">It also uses the domain name for the OneDrive URLs in your organization.</span></span> <span data-ttu-id="cda50-157">Например, если URL-адрес вашего Центра администрирования и URL-адрес oneDrive — это, то вы введите, когда сценарий запросит у вас `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` доменное имя.</span><span class="sxs-lookup"><span data-stu-id="cda50-157">For example, if the URL for your admin center is `https://contoso-admin.sharepoint.com` and the URL for OneDrive is `https://contoso-my.sharepoint.com`, then you would enter `contoso` when the script prompts you for your domain name.</span></span>

- <span data-ttu-id="cda50-158">**Имя дела:** Имя существующего дела.</span><span class="sxs-lookup"><span data-stu-id="cda50-158">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="cda50-159">Сценарий создаст новое удержание, связанное с этим делом.</span><span class="sxs-lookup"><span data-stu-id="cda50-159">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="cda50-160">**Имя удержания:** Имя удержания, которое скрипт создает и связывает с указанным делом.</span><span class="sxs-lookup"><span data-stu-id="cda50-160">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="cda50-161">**Поиск запроса на удержание на основе запроса:** Можно создать удержание на основе запроса, чтобы на удержание помещалось только содержимое, которое соответствует указанным условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="cda50-161">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="cda50-162">Чтобы разместить все содержимое на удержании, просто **нажмите** ввод, когда вам будет предложено найти поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="cda50-162">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="cda50-163">**Включив удержание, или нет:** Вы можете включить удержание после его создания или создать удержание, не включив его.</span><span class="sxs-lookup"><span data-stu-id="cda50-163">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="cda50-164">Если сценарий не включит удержание, его можно включить позже в Центре безопасности & соответствия требованиям или с помощью следующих команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cda50-164">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="cda50-165">**Имя текстового файла** со списком пользователей — имя текстового файла из шага 2, который содержит список пользователей, добавляемого в удержание.</span><span class="sxs-lookup"><span data-stu-id="cda50-165">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="cda50-166">Если этот файл находится в той же папке, что и сценарий, просто введите имя файла (например, HoldUsers.txt).</span><span class="sxs-lookup"><span data-stu-id="cda50-166">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="cda50-167">Если текстовый файл находится в другой папке, введите полное имя пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="cda50-167">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="cda50-168">После того как вы соберите сведения, которые будет предложено выполнить сценарий, запустите сценарий, чтобы создать удержание и добавить в него пользователей.</span><span class="sxs-lookup"><span data-stu-id="cda50-168">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="cda50-169">Сохраните следующий текст в Windows PowerShell сценария, используя суффикс имени файла `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="cda50-169">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="cda50-170">Например, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="cda50-170">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="cda50-171">На локальном компьютере откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="cda50-171">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="cda50-172">Запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="cda50-172">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="cda50-173">Введите сведения, которые вам будет предложено ввести в сценарии.</span><span class="sxs-lookup"><span data-stu-id="cda50-173">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="cda50-174">Сценарий подключается к PowerShell Центра безопасности и & соответствия требованиям, а затем создает новое удержание в деле eDiscovery и добавляет почтовые ящики и OneDrive для бизнеса для пользователей в списке.</span><span class="sxs-lookup"><span data-stu-id="cda50-174">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="cda50-175">Чтобы просмотреть новое удержание, можно перейти к делу на странице **"EDiscovery"** в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cda50-175">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="cda50-176">После завершения работы скрипта он создает следующие файлы журнала и сохраняет их в папке, в которой находится сценарий.</span><span class="sxs-lookup"><span data-stu-id="cda50-176">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="cda50-177">**LocationsOnHold.txt:** Содержит список почтовых ящиков и сайтов OneDrive для бизнеса, которые сценарий успешно поместил на удержание.</span><span class="sxs-lookup"><span data-stu-id="cda50-177">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="cda50-178">**LocationsNotOnHold.txt:** Содержит список почтовых ящиков и сайтов OneDrive для бизнеса, которые сценарий не удерживал.</span><span class="sxs-lookup"><span data-stu-id="cda50-178">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="cda50-179">Если у пользователя есть почтовый ящик, но не сайт OneDrive для бизнеса, он будет включен в список сайтов OneDrive для бизнеса, не помещенных на удержание.</span><span class="sxs-lookup"><span data-stu-id="cda50-179">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="cda50-180">**GetCaseHoldPolicy.txt:** Содержит выходные данные для нового **удержания,** которое сценарий запустил после создания нового удержания.</span><span class="sxs-lookup"><span data-stu-id="cda50-180">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="cda50-181">Информация, возвращаемая этим cmdlet, включает список пользователей, чьи почтовые ящики и сайты OneDrive для бизнеса были помещены на удержание и включено ли удержание.</span><span class="sxs-lookup"><span data-stu-id="cda50-181">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="cda50-182">**GetCaseHoldRule.txt:** Содержит выходные данные для нового **удержания,** которое сценарий запустил после создания нового удержания.</span><span class="sxs-lookup"><span data-stu-id="cda50-182">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="cda50-183">Сведения, возвращаемые этим cmdlet, включают поисковый запрос, если вы использовали сценарий для создания удержания на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="cda50-183">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
