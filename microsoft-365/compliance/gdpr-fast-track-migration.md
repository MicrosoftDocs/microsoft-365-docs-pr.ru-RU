---
title: GDPR
description: 'Технические рекомендации Майкрософт: НАБОР ИНСТРУМЕНТОВ МИГРАЦИИ С ПОМОЩЬЮ FASTTRACK ДЛЯ ОТПРАВКИ ЗАПРОСОВ НА УДАЛЕНИЕ'
keywords: Миграция с помощью FastTrack, Microsoft 365 для образования, документация по Microsoft 365, GDPR
author: MohitKumar
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: mohitku
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: ae4c088ce16b2b415ffa79a6fadd3f1c2a0426c7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286824"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="7732e-104">Набор инструментов миграции с помощью FastTrack для отправки запросов на удаление</span><span class="sxs-lookup"><span data-stu-id="7732e-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="7732e-105">Назначение набора инструментов</span><span class="sxs-lookup"><span data-stu-id="7732e-105">Toolset purpose</span></span>

<span data-ttu-id="7732e-p101">Если вы клиент, участвующий в миграции с помощью FastTrack, удаление учетной записи пользователя Office 365 не приведет к удалению копии данных, хранящихся в группе Microsoft FastTrack. Эти данные хранятся исключительно для целей завершения миграции. Если в процессе миграции вам потребуется, чтобы группа Microsoft FastTrack удалила имеющуюся у них копию данных, отправьте соответствующий запрос с помощью этого набора инструментов. В обычных обстоятельствах группа Microsoft FastTrack удаляет все имеющиеся у нее копии данных по завершении миграции.</span><span class="sxs-lookup"><span data-stu-id="7732e-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the Office 365 user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If, during the migration, you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this toolset. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span> 

### <a name="supported-platforms"></a><span data-ttu-id="7732e-109">Поддерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="7732e-109">Supported platforms</span></span>
<span data-ttu-id="7732e-p102">Корпорация Майкрософт поддерживает первоначальный выпуск этого набора инструментов для платформы Windows и консоли PowerShell. Кроме того, этот набор инструментов поддерживает указанные ниже известные платформы.</span><span class="sxs-lookup"><span data-stu-id="7732e-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="7732e-112">***Таблица 1. Платформы, поддерживаемые набором инструментов***</span><span class="sxs-lookup"><span data-stu-id="7732e-112">***Table 1 - Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="7732e-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="7732e-113">**Windows 7**</span></span>|<span data-ttu-id="7732e-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="7732e-114">**Windows 8**</span></span>|<span data-ttu-id="7732e-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="7732e-115">**Windows 10**</span></span>|<span data-ttu-id="7732e-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="7732e-116">**Windows Server 2012**</span></span>|<span data-ttu-id="7732e-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="7732e-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="7732e-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="7732e-118">PS 5.0</span></span>|<span data-ttu-id="7732e-119">Не</span><span class="sxs-lookup"><span data-stu-id="7732e-119">Not</span></span><br/><span data-ttu-id="7732e-120">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-120">Supported</span></span>|<span data-ttu-id="7732e-121">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-121">Supported</span></span>|<span data-ttu-id="7732e-122">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-122">Supported</span></span>|<span data-ttu-id="7732e-123">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-123">Supported</span></span>|<span data-ttu-id="7732e-124">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-124">Supported</span></span>|
|<span data-ttu-id="7732e-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="7732e-125">PS 5.1</span></span>|<span data-ttu-id="7732e-126">Не</span><span class="sxs-lookup"><span data-stu-id="7732e-126">Not</span></span><br/><span data-ttu-id="7732e-127">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-127">Supported</span></span>|<span data-ttu-id="7732e-128">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-128">Supported</span></span>|<span data-ttu-id="7732e-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-129">Supported</span></span>|<span data-ttu-id="7732e-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-130">Supported</span></span>|<span data-ttu-id="7732e-131">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7732e-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="7732e-132">Получение набора инструментов</span><span class="sxs-lookup"><span data-stu-id="7732e-132">Obtaining the toolset</span></span>

<span data-ttu-id="7732e-p103">Этот набор инструментов доступен в коллекции PowerShell в консольном приложении PowerShell. Чтобы найти и загрузить этот модуль командлета, сначала откройте PowerShell в режиме администратора, чтобы получить соответствующие разрешения для установки модуля. Если ранее вы не использовали PowerShell, в поле поиска на панели задач Windows введите PowerShell. Чтобы запустить Windows PowerShell, щелкните консольное приложение правой кнопкой мыши, выберите **Запуск от имени администратора** и нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="7732e-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell: запуск от имени администратора](media/fasttrack-powershell_image.png)

![PowerShell: предоставление разрешения на внесение изменений приложению](media/fasttrack-run-powershell_image.png)

<span data-ttu-id="7732e-p104">Теперь, когда вы открыли консоль, вам потребуется настроить разрешения для выполнения скрипта. Чтобы разрешить выполнение скрипта, введите следующую команду: Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process</span><span class="sxs-lookup"><span data-stu-id="7732e-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process’</span></span>

<span data-ttu-id="7732e-141">Вам будет предложено подтвердить это действие, так как администратор может изменять область по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="7732e-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion..</span></span>

<span data-ttu-id="7732e-142">***Настройка политики выполнения***</span><span class="sxs-lookup"><span data-stu-id="7732e-142">***Set Execution Policy***</span></span>

![Изменение политики выполнения в PowerShell](media/powershell-set-execution-policy_image.png)

<span data-ttu-id="7732e-144">Теперь, когда для консоли настроено разрешение на выполнение скрипта, установите необходимый модуль, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7732e-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="7732e-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery</span><span class="sxs-lookup"><span data-stu-id="7732e-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="7732e-146">Компоненты, необходимые для работы модуля</span><span class="sxs-lookup"><span data-stu-id="7732e-146">Prerequisites for module</span></span>
<span data-ttu-id="7732e-p105">Для успешной работы этого модуля вам может потребоваться установить зависимые модули (если они еще не установлены). Возможно, вам придется перезапустить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7732e-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="7732e-149">Чтобы отправить запрос субъекта данных, вам сначала потребуется выполнить вход, используя свои учетные данные Office 365. Введя соответствующие учетные данные, вы подтвердите свой статус глобального администратора и сможете собирать информацию о клиенте.</span><span class="sxs-lookup"><span data-stu-id="7732e-149">In order to submit a DSR, you must first login using your Office 365 credentials – entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="7732e-150">**Login-FastTrackAccount -ApiKey: \<ключ API, предоставленный FastTrack MVM\>**</span><span class="sxs-lookup"><span data-stu-id="7732e-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="7732e-151">После успешного входа в систему учетные данные и ключ будут сохранены для использования с модулями FastTrack до конца текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7732e-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="7732e-152">Если вам необходимо подключиться к облачной среде, отличной от коммерческой, то потребуется добавить к команде *Login* параметр *-Environment* с указанием одной из допустимых сред:</span><span class="sxs-lookup"><span data-stu-id="7732e-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will needed to be added to *Login* command with one of the following valid environments:</span></span>
- <span data-ttu-id="7732e-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="7732e-153">AzureCloud</span></span>
- <span data-ttu-id="7732e-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="7732e-154">AzureChinaCloud</span></span>
- <span data-ttu-id="7732e-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="7732e-155">AzureGermanCloud</span></span>
- <span data-ttu-id="7732e-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="7732e-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="7732e-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <облачная среда\>**</span><span class="sxs-lookup"><span data-stu-id="7732e-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="7732e-158">Чтобы отправить запрос субъекта данных, выполните следующую команду: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: ЭлектронныйАдресСубъектаДанных@МояКомпания.com</span><span class="sxs-lookup"><span data-stu-id="7732e-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="7732e-p106">При успешном выполнении командлета он возвратит объект идентификатора транзакции. Сохраните этот идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="7732e-p106">On success – the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="7732e-161">Проверка состояния транзакции запроса</span><span class="sxs-lookup"><span data-stu-id="7732e-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="7732e-162">Запустите следующую функцию, используя ранее полученный идентификатор транзакции: Get-FastTrackGdprDsrRequest -TransactionID: "ИдентификаторВашейТранзакции"</span><span class="sxs-lookup"><span data-stu-id="7732e-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="7732e-163">Коды состояния транзакции</span><span class="sxs-lookup"><span data-stu-id="7732e-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="7732e-164">**Транзакция**</span><span class="sxs-lookup"><span data-stu-id="7732e-164">**Transaction**</span></span> |<span data-ttu-id="7732e-165">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="7732e-165">**Status**</span></span>|
|<span data-ttu-id="7732e-166">**Создана**</span><span class="sxs-lookup"><span data-stu-id="7732e-166">**Created**</span></span> |<span data-ttu-id="7732e-167">Запрос создан</span><span class="sxs-lookup"><span data-stu-id="7732e-167">Request has been created</span></span>|
|<span data-ttu-id="7732e-168">**Не удалось выполнить**</span><span class="sxs-lookup"><span data-stu-id="7732e-168">**Failed**</span></span>|<span data-ttu-id="7732e-169">Не удалось создать запрос. Отправьте запрос еще раз или обратитесь в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="7732e-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="7732e-170">**Выполнена**</span><span class="sxs-lookup"><span data-stu-id="7732e-170">**Completed**</span></span>|<span data-ttu-id="7732e-171">Запрос был выполнен и очищен</span><span class="sxs-lookup"><span data-stu-id="7732e-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="7732e-172">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7732e-172">Learn more</span></span>
[<span data-ttu-id="7732e-173">Центр управления безопасностью (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7732e-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)