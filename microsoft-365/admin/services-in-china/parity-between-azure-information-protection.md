---
title: Поддержка Azure Information Protection для Office 365 под управлением 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988048"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="56d3a-103">Поддержка Azure Information Protection для Office 365 под управлением 21Vianet</span><span class="sxs-lookup"><span data-stu-id="56d3a-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="56d3a-104">В этой статье освещаются различия между поддержкой Azure Information Protection (AIP) для Office 365 под управлением 21Vianet и коммерческих предложений, а также конкретные инструкции по настройке AIP для клиентов в Китае, включая установку локального сканера AIP и управление заданиями сканирования &mdash; контента.</span><span class="sxs-lookup"><span data-stu-id="56d3a-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="56d3a-105">Различия между AIP для Office 365 под управлением 21Vianet и коммерческими предложениями</span><span class="sxs-lookup"><span data-stu-id="56d3a-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="56d3a-106">Хотя наша цель — предоставить все коммерческие функции клиентам в Китае с нашим предложением AIP для Office 365 под управлением 21Vianet, мы хотим выделить некоторые отсутствующие функции.</span><span class="sxs-lookup"><span data-stu-id="56d3a-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="56d3a-107">В следующем списке содержатся существующие пробелы между AIP для Office 365 под управлением 21Vianet и нашими коммерческими предложениями с января 2021 г.:</span><span class="sxs-lookup"><span data-stu-id="56d3a-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="56d3a-108">Управление правами на управление правами на данные (IRM) поддерживается только для приложений Microsoft 365 для предприятий (сборка 11731.10000 или выше).</span><span class="sxs-lookup"><span data-stu-id="56d3a-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="56d3a-109">Office 2010, Office 2013 и другие версии Office 2016 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="56d3a-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="56d3a-110">Миграция служба управления правами Active Directory (AD RMS) на AIP в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="56d3a-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="56d3a-111">Совместное использование защищенных сообщений электронной почты с пользователями в коммерческом облаке поддерживается.</span><span class="sxs-lookup"><span data-stu-id="56d3a-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="56d3a-112">Общий доступ к документам и вложениям электронной почты пользователям в коммерческом облаке в настоящее время не доступен.</span><span class="sxs-lookup"><span data-stu-id="56d3a-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="56d3a-113">К ним относятся пользователи Office 365 под управлением 21Vianet в коммерческом облаке, пользователи не из Office 365, управляемые пользователями 21Vianet в коммерческом облаке, а также пользователи с лицензией RMS для физических лиц.</span><span class="sxs-lookup"><span data-stu-id="56d3a-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="56d3a-114">IRM с SharePoint (сайты и библиотеки, защищенные с помощью IRM) в настоящее время не доступен.</span><span class="sxs-lookup"><span data-stu-id="56d3a-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="56d3a-115">Расширение мобильного устройства для AD RMS в настоящее время не доступно.</span><span class="sxs-lookup"><span data-stu-id="56d3a-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="56d3a-116">Приложение ["Просмотр мобильных устройств"](/azure/information-protection/rms-client/mobile-app-faq) не поддерживается azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="56d3a-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="56d3a-117">Настройка AIP для клиентов в Китае</span><span class="sxs-lookup"><span data-stu-id="56d3a-117">Configure AIP for customers in China</span></span>

<span data-ttu-id="56d3a-118">Чтобы настроить AIP для клиентов в Китае:</span><span class="sxs-lookup"><span data-stu-id="56d3a-118">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="56d3a-119">[Включить управление правами для клиента.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="56d3a-119">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="56d3a-120">[Настройка шифрования DNS.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="56d3a-120">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="56d3a-121">[Установите и настройте клиент унифицированных меток AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="56d3a-121">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="56d3a-122">[Настройка приложений AIP в Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="56d3a-122">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="56d3a-123">[Установка локального сканера AIP и управление заданиями проверки содержимого.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="56d3a-123">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="56d3a-124">Шаг 1. Включить управление правами для клиента</span><span class="sxs-lookup"><span data-stu-id="56d3a-124">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="56d3a-125">Чтобы шифрование работало правильно, необходимо включить для клиента RMS.</span><span class="sxs-lookup"><span data-stu-id="56d3a-125">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="56d3a-126">Проверьте, включена ли RMS:</span><span class="sxs-lookup"><span data-stu-id="56d3a-126">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="56d3a-127">Запустите PowerShell от учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="56d3a-127">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="56d3a-128">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="56d3a-128">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="56d3a-129">Импорт модуля с помощью `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="56d3a-129">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="56d3a-130">Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="56d3a-130">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="56d3a-131">Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте `Enabled` состояние.</span><span class="sxs-lookup"><span data-stu-id="56d3a-131">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="56d3a-132">Если функциональным состоянием является `Disabled` , запустите `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="56d3a-132">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="56d3a-133">Шаг 2. Настройка шифрования DNS</span><span class="sxs-lookup"><span data-stu-id="56d3a-133">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="56d3a-134">Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к экземпляру службы в Китае и из нее подключаться к первой загрузке.</span><span class="sxs-lookup"><span data-stu-id="56d3a-134">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="56d3a-135">Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись DNS SRV с информацией об URL-адресе Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="56d3a-135">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="56d3a-136">Без DNS-записи SRV клиентские приложения по умолчанию попытаются подключиться к экземпляру общего облака и не будут работать.</span><span class="sxs-lookup"><span data-stu-id="56d3a-136">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="56d3a-137">Кроме того, предположим, что пользователи будут входить с помощью имени пользователя, основанного на домене, владельцем клиента (например, ), а не ином пользователем `joe@contoso.cn` `onmschina` (например). `joe@contoso.onmschina.cn`</span><span class="sxs-lookup"><span data-stu-id="56d3a-137">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="56d3a-138">Доменное имя из имени пользователя используется для перенаправления DNS на правильный экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="56d3a-138">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="56d3a-139">Настройка шифрования DNS — Windows</span><span class="sxs-lookup"><span data-stu-id="56d3a-139">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="56d3a-140">Получите ИД RMS:</span><span class="sxs-lookup"><span data-stu-id="56d3a-140">Get the RMS ID:</span></span>

    1. <span data-ttu-id="56d3a-141">Запустите PowerShell от учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="56d3a-141">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="56d3a-142">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="56d3a-142">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="56d3a-143">Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="56d3a-143">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="56d3a-144">`(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ИД RMS.</span><span class="sxs-lookup"><span data-stu-id="56d3a-144">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="56d3a-145">Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="56d3a-145">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="56d3a-146">Служба = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="56d3a-146">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="56d3a-147">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="56d3a-147">Protocol = `_http`</span></span>
    - <span data-ttu-id="56d3a-148">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="56d3a-148">Name = `_tcp`</span></span>
    - <span data-ttu-id="56d3a-149">Target = `[GUID].rms.aadrm.cn` (где GUID — это ИД RMS)</span><span class="sxs-lookup"><span data-stu-id="56d3a-149">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="56d3a-150">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="56d3a-150">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="56d3a-151">Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="56d3a-151">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="56d3a-152">При этом в DNS будет добавлена запись, проверка которой может занять несколько минут после добавления значения в параметры DNS.</span><span class="sxs-lookup"><span data-stu-id="56d3a-152">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="56d3a-153">Войдите в Центр администрирования Microsoft 365 с соответствующими учетными данными глобального администратора и добавьте домен (например, `contoso.cn` ) для создания пользователя.</span><span class="sxs-lookup"><span data-stu-id="56d3a-153">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="56d3a-154">В процессе проверки могут потребоваться дополнительные изменения DNS.</span><span class="sxs-lookup"><span data-stu-id="56d3a-154">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="56d3a-155">После проверки можно создать пользователей.</span><span class="sxs-lookup"><span data-stu-id="56d3a-155">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="56d3a-156">Настройка шифрования DNS — Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="56d3a-156">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="56d3a-157">Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="56d3a-157">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="56d3a-158">Служба = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="56d3a-158">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="56d3a-159">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="56d3a-159">Protocol = `_http`</span></span>
- <span data-ttu-id="56d3a-160">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="56d3a-160">Name = `_tcp`</span></span>
- <span data-ttu-id="56d3a-161">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="56d3a-161">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="56d3a-162">Порт = `80`</span><span class="sxs-lookup"><span data-stu-id="56d3a-162">Port = `80`</span></span>
- <span data-ttu-id="56d3a-163">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="56d3a-163">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="56d3a-164">Шаг 3. Установка и настройка клиента унифицированных меток AIP</span><span class="sxs-lookup"><span data-stu-id="56d3a-164">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="56d3a-165">Скачайте клиент унифицированных меток AIP из [Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="56d3a-165">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="56d3a-166">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="56d3a-166">For more information, see:</span></span>

- [<span data-ttu-id="56d3a-167">Документация по AIP</span><span class="sxs-lookup"><span data-stu-id="56d3a-167">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="56d3a-168">История версий AIP и политика поддержки</span><span class="sxs-lookup"><span data-stu-id="56d3a-168">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="56d3a-169">Требования к системе AIP</span><span class="sxs-lookup"><span data-stu-id="56d3a-169">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="56d3a-170">Краткое развертывание клиента AIP</span><span class="sxs-lookup"><span data-stu-id="56d3a-170">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="56d3a-171">Руководство администратора AIP</span><span class="sxs-lookup"><span data-stu-id="56d3a-171">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="56d3a-172">Руководство пользователя по AIP</span><span class="sxs-lookup"><span data-stu-id="56d3a-172">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="56d3a-173">Узнайте о метах конфиденциальности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56d3a-173">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="56d3a-174">Шаг 4. Настройка приложений AIP в Windows</span><span class="sxs-lookup"><span data-stu-id="56d3a-174">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="56d3a-175">Приложениям AIP в Windows необходим следующий ключ реестра, чтобы указать им правильное независимое облако для Azure в Китае:</span><span class="sxs-lookup"><span data-stu-id="56d3a-175">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="56d3a-176">Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="56d3a-176">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="56d3a-177">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="56d3a-177">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="56d3a-178">Значение = `6` (по умолчанию = 0)</span><span class="sxs-lookup"><span data-stu-id="56d3a-178">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="56d3a-179">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="56d3a-179">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56d3a-180">Убедитесь, что не удаляйте ключ реестра после удаления.</span><span class="sxs-lookup"><span data-stu-id="56d3a-180">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="56d3a-181">Если ключ пустой, неправильный или несуществующий, функция будет действовать как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака).</span><span class="sxs-lookup"><span data-stu-id="56d3a-181">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="56d3a-182">Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.</span><span class="sxs-lookup"><span data-stu-id="56d3a-182">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="56d3a-183">Шаг 5. Установка локального сканера AIP и управление заданиями сканирования контента</span><span class="sxs-lookup"><span data-stu-id="56d3a-183">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="56d3a-184">Установите локального сканера AIP для сканирования сетевых и контентных сетей на конфиденциальные данные, а также примените метки классификации и защиты в зависимости от политики организации.</span><span class="sxs-lookup"><span data-stu-id="56d3a-184">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="56d3a-185">При установке сканера и управлении заданиями проверки содержимого используйте вместо интерфейса портала Azure, используемого коммерческими предложениями, следующие:</span><span class="sxs-lookup"><span data-stu-id="56d3a-185">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="56d3a-186">Командлет</span><span class="sxs-lookup"><span data-stu-id="56d3a-186">Cmdlet</span></span> | <span data-ttu-id="56d3a-187">Описание</span><span class="sxs-lookup"><span data-stu-id="56d3a-187">Description</span></span> |
|--|--|
| [<span data-ttu-id="56d3a-188">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="56d3a-188">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="56d3a-189">Добавляет новый репозиторий в задание проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="56d3a-189">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="56d3a-190">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="56d3a-190">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="56d3a-191">Получает сведения о вашем задание проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="56d3a-191">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="56d3a-192">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="56d3a-192">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="56d3a-193">Получает сведения о репозиториях, определенных для задания сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="56d3a-193">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="56d3a-194">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="56d3a-194">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="56d3a-195">Удаляет задание проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="56d3a-195">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="56d3a-196">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="56d3a-196">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="56d3a-197">Удаляет репозиторий из задания сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="56d3a-197">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="56d3a-198">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="56d3a-198">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="56d3a-199">Определяет параметры задания проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="56d3a-199">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="56d3a-200">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="56d3a-200">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="56d3a-201">Определяет параметры существующего репозитория в заданиях сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="56d3a-201">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="56d3a-202">Дополнительные сведения см. в том, что такое унифицированный сканер меток [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) И управление заданиями проверки содержимого [с помощью только PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="56d3a-202">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>