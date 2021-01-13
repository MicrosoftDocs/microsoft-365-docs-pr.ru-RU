---
title: Четность между Azure Information Protection для Office 365 под управлением 21Vianet и коммерческими предложениями
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Узнайте больше об Azure Information Protection (AIP) для Office 365 под управлением 21Vianet и ее настройке для клиентов в Китае.
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840305"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="97242-103">Четность между Azure Information Protection для Office 365 под управлением 21Vianet и коммерческими предложениями</span><span class="sxs-lookup"><span data-stu-id="97242-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="97242-104">Хотя наша цель — предоставить все коммерческие функции клиентам в Китае с помощью нашей службы Azure Information Protection (AIP) для Office 365 под управлением 21Vianet, мы хотим выделить некоторые отсутствующие функции.</span><span class="sxs-lookup"><span data-stu-id="97242-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="97242-105">В следующем списке содержатся существующие пробелы между Azure Information Protection для Office 365 под управлением 21Vianet и нашими коммерческими предложениями с января 2021 г.:</span><span class="sxs-lookup"><span data-stu-id="97242-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="97242-106">Управление правами на управление правами на данные (IRM) поддерживается только для приложений Microsoft 365 для предприятий (сборка 11731.10000 или выше).</span><span class="sxs-lookup"><span data-stu-id="97242-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="97242-107">Office 2010, Office 2013 и другие версии Office 2016 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="97242-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="97242-108">Миграция служба управления правами Active Directory (AD RMS) в Azure Information Protection в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="97242-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="97242-109">Общий доступ к защищенным электронным письмам пользователям в коммерческом облаке поддерживается.</span><span class="sxs-lookup"><span data-stu-id="97242-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="97242-110">Общий доступ к документам и вложениям электронной почты пользователям в коммерческом облаке в настоящее время не доступен.</span><span class="sxs-lookup"><span data-stu-id="97242-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="97242-111">К ним относятся пользователи Office 365 под управлением 21Vianet в коммерческом облаке, пользователи не из Office 365, управляемые пользователями 21Vianet в коммерческом облаке, а также пользователи с лицензией RMS для физических лиц.</span><span class="sxs-lookup"><span data-stu-id="97242-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="97242-112">IRM с SharePoint (сайты и библиотеки, защищенные с помощью IRM) в настоящее время не доступен.</span><span class="sxs-lookup"><span data-stu-id="97242-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="97242-113">Расширение мобильного устройства для AD RMS в настоящее время не доступно.</span><span class="sxs-lookup"><span data-stu-id="97242-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="97242-114">Приложение ["Просмотр мобильных устройств"](/azure/information-protection/rms-client/mobile-app-faq) не поддерживается azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="97242-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="97242-115">Настройка Azure Information Protection для клиентов в Китае</span><span class="sxs-lookup"><span data-stu-id="97242-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="97242-116">Включить управление правами для клиента</span><span class="sxs-lookup"><span data-stu-id="97242-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="97242-117">Чтобы шифрование работало правильно, необходимо включить для клиента RMS.</span><span class="sxs-lookup"><span data-stu-id="97242-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="97242-118">Проверьте, включена ли RMS:</span><span class="sxs-lookup"><span data-stu-id="97242-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="97242-119">Запустите PowerShell от учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="97242-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="97242-120">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="97242-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="97242-121">Импорт модуля с помощью `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="97242-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="97242-122">Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="97242-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="97242-123">Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте `Enabled` состояние.</span><span class="sxs-lookup"><span data-stu-id="97242-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="97242-124">Если это функциональное `Disabled` состояние, запустите `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="97242-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="97242-125">Конфигурация DNS для шифрования (Windows)</span><span class="sxs-lookup"><span data-stu-id="97242-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="97242-126">Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к экземпляру службы в Китае и из нее подключаться к первой загрузке.</span><span class="sxs-lookup"><span data-stu-id="97242-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="97242-127">Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись DNS SRV с информацией об URL-адресе Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="97242-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="97242-128">Без DNS-записи SRV клиентские приложения по умолчанию попытаются подключиться к экземпляру общего облака и не будут работать.</span><span class="sxs-lookup"><span data-stu-id="97242-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="97242-129">Кроме того, предположим, что пользователи будут входить с помощью имени пользователя, основанного на домене, владельцем клиента (например, ), а не ином пользователем `joe@contoso.cn` `onmschina` (например). `joe@contoso.onmschina.cn`</span><span class="sxs-lookup"><span data-stu-id="97242-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="97242-130">Доменное имя из имени пользователя используется для перенаправления DNS на правильный экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="97242-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="97242-131">Получите ИД RMS:</span><span class="sxs-lookup"><span data-stu-id="97242-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="97242-132">Запустите PowerShell от учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="97242-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="97242-133">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="97242-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="97242-134">Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="97242-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="97242-135">`(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ИД RMS.</span><span class="sxs-lookup"><span data-stu-id="97242-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="97242-136">Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="97242-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="97242-137">Служба = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="97242-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="97242-138">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="97242-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="97242-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="97242-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="97242-140">Target = `[GUID].rms.aadrm.cn` (где GUID — это ИД RMS)</span><span class="sxs-lookup"><span data-stu-id="97242-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="97242-141">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="97242-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="97242-142">Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="97242-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="97242-143">Это добавит запись в DNS, проверка которой может занять несколько минут после добавления значения в параметры DNS.</span><span class="sxs-lookup"><span data-stu-id="97242-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="97242-144">Войдите в Центр администрирования Microsoft 365 с соответствующими учетными данными глобального администратора и добавьте домен (например, `contoso.cn` ) для создания пользователя.</span><span class="sxs-lookup"><span data-stu-id="97242-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="97242-145">В процессе проверки могут потребоваться дополнительные изменения DNS.</span><span class="sxs-lookup"><span data-stu-id="97242-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="97242-146">После проверки пользователи могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="97242-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="97242-147">Конфигурация DNS для шифрования (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="97242-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="97242-148">Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="97242-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="97242-149">Служба = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="97242-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="97242-150">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="97242-150">Protocol = `_http`</span></span>
- <span data-ttu-id="97242-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="97242-151">Name = `_tcp`</span></span>
- <span data-ttu-id="97242-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="97242-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="97242-153">Порт = `80`</span><span class="sxs-lookup"><span data-stu-id="97242-153">Port = `80`</span></span>
- <span data-ttu-id="97242-154">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="97242-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="97242-155">Конфигурация клиента AIP</span><span class="sxs-lookup"><span data-stu-id="97242-155">AIP client configuration</span></span>

<span data-ttu-id="97242-156">Унифицированный клиент AIP можно скачать в [Центре загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="97242-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="97242-157">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="97242-157">For more information, see:</span></span>

- [<span data-ttu-id="97242-158">Документация по Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="97242-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="97242-159">История версий AIP и политика поддержки</span><span class="sxs-lookup"><span data-stu-id="97242-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="97242-160">Требования к системе AIP</span><span class="sxs-lookup"><span data-stu-id="97242-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="97242-161">Краткое развертывание клиента AIP</span><span class="sxs-lookup"><span data-stu-id="97242-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="97242-162">Руководство администратора AIP</span><span class="sxs-lookup"><span data-stu-id="97242-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="97242-163">Руководство пользователя по AIP</span><span class="sxs-lookup"><span data-stu-id="97242-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="97242-164">Узнайте о метах конфиденциальности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="97242-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="97242-165">Конфигурация приложений AIP (только для клиента унифицированных меток)</span><span class="sxs-lookup"><span data-stu-id="97242-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="97242-166">Для решения унифицированных меток приложениям AIP в Windows необходим следующий ключ реестра, чтобы указать им правильное независимое облако для Azure в Китае:</span><span class="sxs-lookup"><span data-stu-id="97242-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="97242-167">Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="97242-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="97242-168">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="97242-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="97242-169">Значение = `6` (по умолчанию = 0)</span><span class="sxs-lookup"><span data-stu-id="97242-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="97242-170">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="97242-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97242-171">Убедитесь, что не удаляйте ключ реестра после удаления.</span><span class="sxs-lookup"><span data-stu-id="97242-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="97242-172">Если ключ пустой, неправильный или несуществующий, функция будет действовать как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака).</span><span class="sxs-lookup"><span data-stu-id="97242-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="97242-173">Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.</span><span class="sxs-lookup"><span data-stu-id="97242-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="97242-174">Управление заданиями проверки контента Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="97242-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="97242-175">Чтобы управлять заданиями сканирования контента Azure Information Protection на сервере сканера Azure в Китае, используйте вместо портала Azure следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="97242-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="97242-176">Командлет</span><span class="sxs-lookup"><span data-stu-id="97242-176">Cmdlet</span></span> | <span data-ttu-id="97242-177">Описание</span><span class="sxs-lookup"><span data-stu-id="97242-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="97242-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="97242-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="97242-179">Добавляет новый репозиторий в задание проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="97242-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="97242-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="97242-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="97242-181">Получает сведения о вашем задание проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="97242-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="97242-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="97242-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="97242-183">Получает сведения о репозиториях, определенных для задания сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="97242-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="97242-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="97242-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="97242-185">Удаляет задание проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="97242-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="97242-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="97242-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="97242-187">Удаляет репозиторий из задания сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="97242-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="97242-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="97242-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="97242-189">Определяет параметры задания проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="97242-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="97242-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="97242-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="97242-191">Определяет параметры существующего репозитория в заданиях сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="97242-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="97242-192">Дополнительные сведения см. в под [управление заданиями проверки содержимого только с помощью PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="97242-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>