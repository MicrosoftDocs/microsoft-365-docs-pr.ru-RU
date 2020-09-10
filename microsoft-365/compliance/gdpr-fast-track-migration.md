---
title: GDPR
description: 'Технические рекомендации Майкрософт: НАБОР ИНСТРУМЕНТОВ МИГРАЦИИ С ПОМОЩЬЮ FASTTRACK ДЛЯ ОТПРАВКИ ЗАПРОСОВ НА УДАЛЕНИЕ'
keywords: Миграция с помощью FastTrack, Microsoft 365 для образования, документация по Microsoft 365, GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 162a64535f82f24411121ed81e36078511eb8eba
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416915"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="e87bf-104">Набор инструментов миграции с помощью FastTrack для отправки запросов на удаление</span><span class="sxs-lookup"><span data-stu-id="e87bf-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="e87bf-105">Назначение набора инструментов</span><span class="sxs-lookup"><span data-stu-id="e87bf-105">Toolset purpose</span></span>

<span data-ttu-id="e87bf-p101">Если вы клиент, участвующий в миграции с помощью FastTrack, удаление учетной записи пользователя не приведет к удалению копии данных, хранящейся у специалистов Microsoft FastTrack. Эти данные хранятся исключительно для целей завершения миграции. Если в процессе миграции вам потребуется, чтобы специалисты Microsoft FastTrack удалили имеющуюся у них копию данных, отправьте соответствующий запрос с помощью этого набора инструментов. В обычных обстоятельствах Microsoft FastTrack удаляет все копии данных по завершении миграции организации.</span><span class="sxs-lookup"><span data-stu-id="e87bf-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="e87bf-109">Поддерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="e87bf-109">Supported platforms</span></span>
<span data-ttu-id="e87bf-p102">Корпорация Майкрософт поддерживает первоначальный выпуск этого набора инструментов для платформы Windows и консоли PowerShell. Кроме того, этот набор инструментов поддерживает указанные ниже известные платформы.</span><span class="sxs-lookup"><span data-stu-id="e87bf-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="e87bf-112">***Таблица 1. Платформы, поддерживаемые набором инструментов***</span><span class="sxs-lookup"><span data-stu-id="e87bf-112">***Table 1 — Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="e87bf-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="e87bf-113">**Windows 7**</span></span>|<span data-ttu-id="e87bf-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="e87bf-114">**Windows 8**</span></span>|<span data-ttu-id="e87bf-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="e87bf-115">**Windows 10**</span></span>|<span data-ttu-id="e87bf-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="e87bf-116">**Windows Server 2012**</span></span>|<span data-ttu-id="e87bf-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="e87bf-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="e87bf-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="e87bf-118">PS 5.0</span></span>|<span data-ttu-id="e87bf-119">Не</span><span class="sxs-lookup"><span data-stu-id="e87bf-119">Not</span></span><br/><span data-ttu-id="e87bf-120">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-120">Supported</span></span>|<span data-ttu-id="e87bf-121">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-121">Supported</span></span>|<span data-ttu-id="e87bf-122">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-122">Supported</span></span>|<span data-ttu-id="e87bf-123">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-123">Supported</span></span>|<span data-ttu-id="e87bf-124">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-124">Supported</span></span>|
|<span data-ttu-id="e87bf-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="e87bf-125">PS 5.1</span></span>|<span data-ttu-id="e87bf-126">Не</span><span class="sxs-lookup"><span data-stu-id="e87bf-126">Not</span></span><br/><span data-ttu-id="e87bf-127">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-127">Supported</span></span>|<span data-ttu-id="e87bf-128">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-128">Supported</span></span>|<span data-ttu-id="e87bf-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-129">Supported</span></span>|<span data-ttu-id="e87bf-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-130">Supported</span></span>|<span data-ttu-id="e87bf-131">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="e87bf-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="e87bf-132">Получение набора инструментов</span><span class="sxs-lookup"><span data-stu-id="e87bf-132">Obtaining the toolset</span></span>

<span data-ttu-id="e87bf-p103">Этот набор инструментов доступен в коллекции PowerShell в консольном приложении PowerShell. Чтобы найти и загрузить этот модуль командлета, сначала откройте PowerShell в режиме администратора, чтобы получить соответствующие разрешения для установки модуля. Если ранее вы не использовали PowerShell, в поле поиска на панели задач Windows введите PowerShell. Чтобы запустить Windows PowerShell, щелкните консольное приложение правой кнопкой мыши, выберите **Запуск от имени администратора** и нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="e87bf-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell: запуск от имени администратора](../media/fasttrack-powershell_image.png)

![PowerShell: предоставление разрешения на внесение изменений приложению](../media/fasttrack-run-powershell_image.png)

<span data-ttu-id="e87bf-p104">Теперь, когда вы открыли консоль, вам потребуется настроить разрешения для выполнения скрипта. Чтобы разрешить выполнение скрипта, введите следующую команду: Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope: Process</span><span class="sxs-lookup"><span data-stu-id="e87bf-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope: Process’</span></span>

<span data-ttu-id="e87bf-141">Вам будет предложено подтвердить это действие, так как администратор может изменять область по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="e87bf-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="e87bf-142">***Настройка политики выполнения***</span><span class="sxs-lookup"><span data-stu-id="e87bf-142">***Set Execution Policy***</span></span>

![Изменение политики выполнения в PowerShell](../media/powershell-set-execution-policy_image.png)

<span data-ttu-id="e87bf-144">Теперь, когда для консоли настроено разрешение на выполнение скрипта, установите необходимый модуль, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e87bf-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="e87bf-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery</span><span class="sxs-lookup"><span data-stu-id="e87bf-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="e87bf-146">Компоненты, необходимые для работы модуля</span><span class="sxs-lookup"><span data-stu-id="e87bf-146">Prerequisites for module</span></span>
<span data-ttu-id="e87bf-p105">Для успешной работы этого модуля вам может потребоваться установить зависимые модули (если они еще не установлены). Возможно, вам придется перезапустить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e87bf-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="e87bf-149">Чтобы отправить запрос субъекта данных, вам сначала потребуется выполнить вход, используя свои учетные данные Office 365. Введя соответствующие учетные данные, вы подтвердите свой статус глобального администратора и сможете собирать информацию о клиенте.</span><span class="sxs-lookup"><span data-stu-id="e87bf-149">In order to submit a DSR, you must first log in using your Office 365 credentials — entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="e87bf-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span><span class="sxs-lookup"><span data-stu-id="e87bf-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="e87bf-151">После успешного входа в систему учетные данные и ключ будут сохранены для использования с модулями FastTrack до конца текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e87bf-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="e87bf-152">Если вам необходимо подключиться к облачной среде, отличной от коммерческой, нужно добавить к команде *Log in* параметр *-Environment* с указанием одной из допустимых сред:</span><span class="sxs-lookup"><span data-stu-id="e87bf-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>
- <span data-ttu-id="e87bf-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="e87bf-153">AzureCloud</span></span>
- <span data-ttu-id="e87bf-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="e87bf-154">AzureChinaCloud</span></span>
- <span data-ttu-id="e87bf-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="e87bf-155">AzureGermanCloud</span></span>
- <span data-ttu-id="e87bf-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="e87bf-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="e87bf-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <облачная среда\>**</span><span class="sxs-lookup"><span data-stu-id="e87bf-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="e87bf-158">Чтобы отправить запрос субъекта данных, выполните следующую команду: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: ЭлектронныйАдресСубъектаДанных@МояКомпания.com</span><span class="sxs-lookup"><span data-stu-id="e87bf-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="e87bf-p106">При успешном выполнении командлета он возвратит объект идентификатора транзакции. Сохраните этот идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="e87bf-p106">On success — the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="e87bf-161">Проверка состояния транзакции запроса</span><span class="sxs-lookup"><span data-stu-id="e87bf-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="e87bf-162">Запустите следующую функцию, используя ранее полученный идентификатор транзакции: Get-FastTrackGdprDsrRequest -TransactionID: "ИдентификаторВашейТранзакции"</span><span class="sxs-lookup"><span data-stu-id="e87bf-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="e87bf-163">Коды состояния транзакции</span><span class="sxs-lookup"><span data-stu-id="e87bf-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="e87bf-164">**Транзакция**</span><span class="sxs-lookup"><span data-stu-id="e87bf-164">**Transaction**</span></span> |<span data-ttu-id="e87bf-165">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="e87bf-165">**Status**</span></span>|
|<span data-ttu-id="e87bf-166">**Создана**</span><span class="sxs-lookup"><span data-stu-id="e87bf-166">**Created**</span></span> |<span data-ttu-id="e87bf-167">Запрос создан</span><span class="sxs-lookup"><span data-stu-id="e87bf-167">Request has been created</span></span>|
|<span data-ttu-id="e87bf-168">**Не удалось выполнить**</span><span class="sxs-lookup"><span data-stu-id="e87bf-168">**Failed**</span></span>|<span data-ttu-id="e87bf-169">Не удалось создать запрос. Отправьте запрос еще раз или обратитесь в службу поддержки</span><span class="sxs-lookup"><span data-stu-id="e87bf-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="e87bf-170">**Выполнена**</span><span class="sxs-lookup"><span data-stu-id="e87bf-170">**Completed**</span></span>|<span data-ttu-id="e87bf-171">Запрос был выполнен и очищен</span><span class="sxs-lookup"><span data-stu-id="e87bf-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="e87bf-172">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e87bf-172">Learn more</span></span>
[<span data-ttu-id="e87bf-173">Центр управления безопасностью (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="e87bf-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview
)
