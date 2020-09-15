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
ms.openlocfilehash: 10a983297640ac4b65aaf181ef35ac19918e74fe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547394"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="41641-104">Набор инструментов миграции с помощью FastTrack для отправки запросов на удаление</span><span class="sxs-lookup"><span data-stu-id="41641-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="41641-105">Назначение набора инструментов</span><span class="sxs-lookup"><span data-stu-id="41641-105">Toolset purpose</span></span>

<span data-ttu-id="41641-p101">Если вы клиент, участвующий в миграции с помощью FastTrack, удаление учетной записи пользователя не приведет к удалению копии данных, хранящейся у специалистов Microsoft FastTrack. Эти данные хранятся исключительно для целей завершения миграции. Если в процессе миграции вам потребуется, чтобы специалисты Microsoft FastTrack удалили имеющуюся у них копию данных, отправьте соответствующий запрос с помощью этого набора инструментов. В обычных обстоятельствах Microsoft FastTrack удаляет все копии данных по завершении миграции организации.</span><span class="sxs-lookup"><span data-stu-id="41641-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="41641-109">Поддерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="41641-109">Supported platforms</span></span>

<span data-ttu-id="41641-p102">Корпорация Майкрософт поддерживает первоначальный выпуск этого набора инструментов для платформы Windows и консоли PowerShell. Кроме того, этот набор инструментов поддерживает указанные ниже известные платформы.</span><span class="sxs-lookup"><span data-stu-id="41641-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>

<span data-ttu-id="41641-112">***Таблица 1. Платформы, поддерживаемые набором инструментов***</span><span class="sxs-lookup"><span data-stu-id="41641-112">***Table 1 — Platforms supported by this toolset***</span></span>

****

|<span data-ttu-id="41641-113">Версия PowerShell</span><span class="sxs-lookup"><span data-stu-id="41641-113">PowerShell version</span></span>|<span data-ttu-id="41641-114">Windows 7</span><span class="sxs-lookup"><span data-stu-id="41641-114">Windows 7</span></span>|<span data-ttu-id="41641-115">Windows 8</span><span class="sxs-lookup"><span data-stu-id="41641-115">Windows 8</span></span>|<span data-ttu-id="41641-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="41641-116">Windows 10</span></span>|<span data-ttu-id="41641-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="41641-117">Windows Server 2012</span></span>|<span data-ttu-id="41641-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="41641-118">Windows Server 2016</span></span>|
|:---:|:---:|:---:|:---:|:---:|:---:|
|<span data-ttu-id="41641-119">5.0</span><span class="sxs-lookup"><span data-stu-id="41641-119">5.0</span></span>|<span data-ttu-id="41641-120">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-120">Not Supported</span></span>|<span data-ttu-id="41641-121">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-121">Supported</span></span>|<span data-ttu-id="41641-122">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-122">Supported</span></span>|<span data-ttu-id="41641-123">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-123">Supported</span></span>|<span data-ttu-id="41641-124">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-124">Supported</span></span>|
|<span data-ttu-id="41641-125">5.1</span><span class="sxs-lookup"><span data-stu-id="41641-125">5.1</span></span>|<span data-ttu-id="41641-126">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-126">Not Supported</span></span>|<span data-ttu-id="41641-127">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-127">Supported</span></span>|<span data-ttu-id="41641-128">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-128">Supported</span></span>|<span data-ttu-id="41641-129">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-129">Supported</span></span>|<span data-ttu-id="41641-130">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="41641-130">Supported</span></span>|
|

### <a name="obtaining-the-toolset"></a><span data-ttu-id="41641-131">Получение набора инструментов</span><span class="sxs-lookup"><span data-stu-id="41641-131">Obtaining the toolset</span></span>

<span data-ttu-id="41641-p103">Этот набор инструментов доступен в коллекции PowerShell в консольном приложении PowerShell. Чтобы найти и загрузить этот модуль командлета, сначала откройте PowerShell в режиме администратора, чтобы получить соответствующие разрешения для установки модуля. Если ранее вы не использовали PowerShell, в поле поиска на панели задач Windows введите PowerShell. Чтобы запустить Windows PowerShell, щелкните консольное приложение правой кнопкой мыши, выберите **Запуск от имени администратора** и нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="41641-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell: запуск от имени администратора](../media/fasttrack-powershell_image.png)

![PowerShell: предоставление разрешения на внесение изменений приложению](../media/fasttrack-run-powershell_image.png)

<span data-ttu-id="41641-138">Теперь, когда консоль открыта, необходимо задать разрешения для выполнения сценария.</span><span class="sxs-lookup"><span data-stu-id="41641-138">Now that the console is open, you need to set permissions for script execution.</span></span> <span data-ttu-id="41641-139">Чтобы разрешить запуск сценариев, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41641-139">Type the following command to allow the scripts to run:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

<span data-ttu-id="41641-140">Вам будет предложено подтвердить это действие, так как администратор может изменять область по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="41641-140">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="41641-141">***Настройка политики выполнения***</span><span class="sxs-lookup"><span data-stu-id="41641-141">***Set Execution Policy***</span></span>

![Изменение политики выполнения в PowerShell](../media/powershell-set-execution-policy_image.png)

<span data-ttu-id="41641-143">Теперь, когда для консоли настроено разрешение на выполнение скрипта, установите необходимый модуль, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41641-143">Now that the console is set to allow the script, run this next command to install the module:</span></span>

```powershell
Install-Module -Name Microsoft.FastTrack -Repository PSGallery -WarningAction SilentlyContinue -Force
```

### <a name="prerequisites-for-module"></a><span data-ttu-id="41641-144">Компоненты, необходимые для работы модуля</span><span class="sxs-lookup"><span data-stu-id="41641-144">Prerequisites for module</span></span>

<span data-ttu-id="41641-p105">Для успешной работы этого модуля вам может потребоваться установить зависимые модули (если они еще не установлены). Возможно, вам придется перезапустить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41641-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>

<span data-ttu-id="41641-147">Прежде чем отправить DSR, необходимо выполнить вход с помощью учетных данных Office 365.</span><span class="sxs-lookup"><span data-stu-id="41641-147">In order to submit a DSR, you must first log in using your Office 365 credentials.</span></span> <span data-ttu-id="41641-148">Ввод соответствующих учетных данных позволит подтвердить статус глобального администратора и собрать сведения о клиенте.</span><span class="sxs-lookup"><span data-stu-id="41641-148">Entering the proper credentials will validate your global administrator status and collect tenant information.</span></span>

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM>
```

<span data-ttu-id="41641-149">После успешного входа в систему учетные данные и ключ будут сохранены для использования с модулями FastTrack до конца текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41641-149">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="41641-150">Если вам необходимо подключиться к облачной среде, отличной от коммерческой, нужно добавить к команде *Log in* параметр *-Environment* с указанием одной из допустимых сред:</span><span class="sxs-lookup"><span data-stu-id="41641-150">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>

- <span data-ttu-id="41641-151">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="41641-151">AzureCloud</span></span>
- <span data-ttu-id="41641-152">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="41641-152">AzureChinaCloud</span></span>
- <span data-ttu-id="41641-153">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="41641-153">AzureGermanCloud</span></span>
- <span data-ttu-id="41641-154">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="41641-154">AzureUSGovernmentCloud</span></span>

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM> -Environment <cloud environment>
```

<span data-ttu-id="41641-155">Чтобы отправить запрос DSR, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41641-155">To submit a DSR request, run the following command:</span></span>

```powershell
Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail SubjectUserEmail@mycompany.com
```

<span data-ttu-id="41641-156">В случае успеха командлет возвращает объект идентификатора транзакции.</span><span class="sxs-lookup"><span data-stu-id="41641-156">On success, the cmdlet will return a Transaction ID object.</span></span> <span data-ttu-id="41641-157">Просьба сохранить идентификатора транзакции.</span><span class="sxs-lookup"><span data-stu-id="41641-157">Please retain the Transaction ID.</span></span>

#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="41641-158">Проверка состояния транзакции запроса</span><span class="sxs-lookup"><span data-stu-id="41641-158">Checking the status of a request transaction</span></span>

<span data-ttu-id="41641-159">Запустите следующую функцию, используя ранее полученный идентификатор транзакции:</span><span class="sxs-lookup"><span data-stu-id="41641-159">Run the following function using the previously obtained Transaction ID:</span></span>

```powershell
Get-FastTrackGdprDsrRequest -TransactionID "YourTransactionID"
```

#### <a name="transaction-status-codes"></a><span data-ttu-id="41641-160">Коды состояния транзакции</span><span class="sxs-lookup"><span data-stu-id="41641-160">Transaction Status Codes</span></span>

|<span data-ttu-id="41641-161">Транзакция</span><span class="sxs-lookup"><span data-stu-id="41641-161">Transaction</span></span>|<span data-ttu-id="41641-162">Статус</span><span class="sxs-lookup"><span data-stu-id="41641-162">Status</span></span>|
|---|---|
|<span data-ttu-id="41641-163">**Создано**</span><span class="sxs-lookup"><span data-stu-id="41641-163">**Created**</span></span>|<span data-ttu-id="41641-164">Запрос создан.</span><span class="sxs-lookup"><span data-stu-id="41641-164">Request has been created.</span></span>|
|<span data-ttu-id="41641-165">**Не удалось выполнить**</span><span class="sxs-lookup"><span data-stu-id="41641-165">**Failed**</span></span>|<span data-ttu-id="41641-166">Не удалось создать запрос. Отправьте запрос еще раз или обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="41641-166">Request failed to create, please resubmit, or contact support.</span></span>|
|<span data-ttu-id="41641-167">**Выполнено**</span><span class="sxs-lookup"><span data-stu-id="41641-167">**Completed**</span></span>|<span data-ttu-id="41641-168">Запрос был выполнен и очищен.</span><span class="sxs-lookup"><span data-stu-id="41641-168">Request has been completed and sanitized.</span></span>|
|

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->

## <a name="learn-more"></a><span data-ttu-id="41641-169">Подробнее</span><span class="sxs-lookup"><span data-stu-id="41641-169">Learn more</span></span>

[<span data-ttu-id="41641-170">Центр управления безопасностью (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="41641-170">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
