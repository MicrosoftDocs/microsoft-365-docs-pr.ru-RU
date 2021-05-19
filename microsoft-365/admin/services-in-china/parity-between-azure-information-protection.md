---
title: Поддержка azure information Protection для Office 365 21Vianet
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
description: Дополнительные сведения о Azure Information Protection (AIP) для Office 365 21Vianet и настройке ее для клиентов в Китае.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535846"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="aeedc-103">Поддержка azure information Protection для Office 365 21Vianet</span><span class="sxs-lookup"><span data-stu-id="aeedc-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="aeedc-104">В этой статье освещаются различия между поддержкой Azure Information Protection (AIP) для Office 365 21Vianet и коммерческими предложениями, а также конкретные инструкции по настройке AIP для клиентов в Китае, включая установку локального сканера AIP и управление заданиями сканирования &mdash; контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="aeedc-105">Различия между AIP для Office 365 21Vianet и коммерческими предложениями</span><span class="sxs-lookup"><span data-stu-id="aeedc-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="aeedc-106">Хотя наша цель заключается в том, чтобы предоставить все коммерческие функции и функции клиентам в Китае с нашим AIP для Office 365 21Vianet предложение, есть некоторые отсутствующие функции, которые мы хотели бы выделить.</span><span class="sxs-lookup"><span data-stu-id="aeedc-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="aeedc-107">Следующий список включает существующие пробелы между AIP для Office 365 21Vianet и нашими коммерческими предложениями по январь 2021 г.:</span><span class="sxs-lookup"><span data-stu-id="aeedc-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="aeedc-108">Управление правами на информацию (IRM) поддерживается только для Приложения Microsoft 365 для предприятий (сборка 11731.10000 или выше).</span><span class="sxs-lookup"><span data-stu-id="aeedc-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="aeedc-109">Office 2010, Office 2013 г. и другие версии Office 2016 г. не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="aeedc-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="aeedc-110">Миграция службы Active Directory Rights Management (AD RMS) в AIP в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="aeedc-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="aeedc-111">Поддерживается обмен защищенными электронными письмами с пользователями в коммерческом облаке.</span><span class="sxs-lookup"><span data-stu-id="aeedc-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="aeedc-112">Обмен документами и вложениями электронной почты с пользователями в коммерческом облаке в настоящее время не доступен.</span><span class="sxs-lookup"><span data-stu-id="aeedc-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="aeedc-113">Это включает Office 365 21Vianet пользователей в коммерческом облаке, не Office 365 управляемых пользователями 21Vianet в коммерческом облаке, и пользователей с лицензией RMS для физических лиц.</span><span class="sxs-lookup"><span data-stu-id="aeedc-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="aeedc-114">IRM с SharePoint (защищенные IRM-сайты и библиотеки) в настоящее время недоступны.</span><span class="sxs-lookup"><span data-stu-id="aeedc-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="aeedc-115">Расширение мобильного устройства для AD RMS в настоящее время не доступно.</span><span class="sxs-lookup"><span data-stu-id="aeedc-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="aeedc-116">Мобильный [зритель не](/azure/information-protection/rms-client/mobile-app-faq) поддерживается Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="aeedc-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="aeedc-117">Область AIP портала Azure недоступна для клиентов в Китае.</span><span class="sxs-lookup"><span data-stu-id="aeedc-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="aeedc-118">Используйте [команды PowerShell вместо](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) выполнения действий на портале, таких как управление заданиями сканирования контента и выполнение их.</span><span class="sxs-lookup"><span data-stu-id="aeedc-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="aeedc-119">Настройка AIP для клиентов в Китае</span><span class="sxs-lookup"><span data-stu-id="aeedc-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="aeedc-120">Настройка AIP для клиентов в Китае:</span><span class="sxs-lookup"><span data-stu-id="aeedc-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="aeedc-121">[Включить управление правами для клиента.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="aeedc-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="aeedc-122">[Добавьте главу службы синхронизации защиты информации Майкрософт.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)</span><span class="sxs-lookup"><span data-stu-id="aeedc-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="aeedc-123">[Настройка шифрования DNS.](#step-3-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="aeedc-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="aeedc-124">[Установка и настройка клиента единой маркировки AIP.](#step-4-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="aeedc-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="aeedc-125">[Настройка приложений AIP на Windows](#step-5-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="aeedc-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="aeedc-126">[Установка локального сканера AIP и управление заданиями сканирования контента.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="aeedc-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="aeedc-127">Шаг 1. Включить управление правами для клиента</span><span class="sxs-lookup"><span data-stu-id="aeedc-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="aeedc-128">Чтобы шифрование работало правильно, необходимо включить RMS для клиента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="aeedc-129">Проверьте, включен ли RMS:</span><span class="sxs-lookup"><span data-stu-id="aeedc-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="aeedc-130">Запустите PowerShell в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="aeedc-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="aeedc-131">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="aeedc-132">Импорт модуля с помощью `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="aeedc-133">Подключение службе с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="aeedc-134">Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте, является ли состояние `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="aeedc-135">Если функциональное состояние , `Disabled` запустите `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="aeedc-136">Шаг 2. Добавление основного директора службы синхронизации microsoft Information Protection Service</span><span class="sxs-lookup"><span data-stu-id="aeedc-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="aeedc-137">Руководитель **службы синхронизации** защиты информации Майкрософт по умолчанию не доступен в клиентах Azure China и необходим для azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="aeedc-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="aeedc-138">Создайте эту главу службы вручную с помощью [командалета New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) и ID приложения для службы синхронизации защиты информации `870c4f2e-85b6-4d43-bdda-6ed9a579b725` Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aeedc-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="aeedc-139">После добавления основного владельца службы добавьте соответствующие разрешения, необходимые для службы.</span><span class="sxs-lookup"><span data-stu-id="aeedc-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="aeedc-140">Шаг 3. Настройка шифрования DNS</span><span class="sxs-lookup"><span data-stu-id="aeedc-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="aeedc-141">Чтобы шифрование работало правильно, Office клиентские приложения должны подключиться к китайскому экземпляру службы и загрузчику оттуда.</span><span class="sxs-lookup"><span data-stu-id="aeedc-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="aeedc-142">Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись SRV DNS с информацией о URL-адресе Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="aeedc-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="aeedc-143">Без записи SRV DNS клиентские приложения по умолчанию попытаются подключиться к общедоступным облачным экземплярам и сбой.</span><span class="sxs-lookup"><span data-stu-id="aeedc-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="aeedc-144">Кроме того, существует предположение, что пользователи будут входить в систему с иным имям пользователя, основанным на домене, владельцем клиента (например, ), а не имям `joe@contoso.cn` `onmschina` пользователя (например, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="aeedc-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="aeedc-145">Имя домена из имени пользователя используется для перенаправления DNS в правильный экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="aeedc-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="aeedc-146">Настройка шифрования DNS - Windows</span><span class="sxs-lookup"><span data-stu-id="aeedc-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="aeedc-147">Получите ID RMS:</span><span class="sxs-lookup"><span data-stu-id="aeedc-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="aeedc-148">Запустите PowerShell в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="aeedc-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="aeedc-149">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="aeedc-150">Подключение службе с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="aeedc-151">`(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ID RMS.</span><span class="sxs-lookup"><span data-stu-id="aeedc-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="aeedc-152">Войдите в поставщик DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="aeedc-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="aeedc-153">Служба = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="aeedc-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="aeedc-154">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="aeedc-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="aeedc-155">Имя = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="aeedc-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="aeedc-156">Target = `[GUID].rms.aadrm.cn` (где GUID — это ID RMS)</span><span class="sxs-lookup"><span data-stu-id="aeedc-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="aeedc-157">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="aeedc-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="aeedc-158">Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="aeedc-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="aeedc-159">Это добавит запись в DNS, для проверки которой может потребоваться несколько минут после добавления значения в параметры DNS.</span><span class="sxs-lookup"><span data-stu-id="aeedc-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="aeedc-160">Войдите в центр администрирования Microsoft 365 с соответствующими глобальными учетными данными администратора и добавьте домен (например, `contoso.cn` ) для создания пользователя.</span><span class="sxs-lookup"><span data-stu-id="aeedc-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="aeedc-161">В процессе проверки могут потребоваться дополнительные изменения DNS.</span><span class="sxs-lookup"><span data-stu-id="aeedc-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="aeedc-162">После проверки можно создать пользователей.</span><span class="sxs-lookup"><span data-stu-id="aeedc-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="aeedc-163">Настройка шифрования DNS - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="aeedc-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="aeedc-164">Войдите в поставщик DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="aeedc-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="aeedc-165">Служба = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="aeedc-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="aeedc-166">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="aeedc-166">Protocol = `_http`</span></span>
- <span data-ttu-id="aeedc-167">Имя = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="aeedc-167">Name = `_tcp`</span></span>
- <span data-ttu-id="aeedc-168">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="aeedc-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="aeedc-169">Порт = `80`</span><span class="sxs-lookup"><span data-stu-id="aeedc-169">Port = `80`</span></span>
- <span data-ttu-id="aeedc-170">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="aeedc-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="aeedc-171">Шаг 4. Установка и настройка клиента единой маркировки AIP</span><span class="sxs-lookup"><span data-stu-id="aeedc-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="aeedc-172">Скачайте и установите клиент единой метки AIP из [Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="aeedc-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="aeedc-173">Дополнительные сведения см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="aeedc-173">For more information, see:</span></span>

- [<span data-ttu-id="aeedc-174">Документация по AIP</span><span class="sxs-lookup"><span data-stu-id="aeedc-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="aeedc-175">История и политика поддержки версий AIP</span><span class="sxs-lookup"><span data-stu-id="aeedc-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="aeedc-176">Требования к системе AIP</span><span class="sxs-lookup"><span data-stu-id="aeedc-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="aeedc-177">AIP quickstart: Развертывание клиента AIP</span><span class="sxs-lookup"><span data-stu-id="aeedc-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="aeedc-178">Руководство администратора AIP</span><span class="sxs-lookup"><span data-stu-id="aeedc-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="aeedc-179">Руководство по пользователю AIP</span><span class="sxs-lookup"><span data-stu-id="aeedc-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="aeedc-180">Узнайте о Microsoft 365 меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="aeedc-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="aeedc-181">Шаг 5. Настройка приложений AIP на Windows</span><span class="sxs-lookup"><span data-stu-id="aeedc-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="aeedc-182">Приложениям AIP на Windows нужен следующий ключ реестра, чтобы указать их на правильное суверенное облако для Azure China:</span><span class="sxs-lookup"><span data-stu-id="aeedc-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="aeedc-183">Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="aeedc-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="aeedc-184">Имя = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="aeedc-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="aeedc-185">Значение = `6` (по умолчанию = 0)</span><span class="sxs-lookup"><span data-stu-id="aeedc-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="aeedc-186">Тип = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="aeedc-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aeedc-187">Убедитесь, что не удаляйте ключ реестра после удаления.</span><span class="sxs-lookup"><span data-stu-id="aeedc-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="aeedc-188">Если ключ пустой, неправильный или несуществующий, функциональность будет вести себя как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака).</span><span class="sxs-lookup"><span data-stu-id="aeedc-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="aeedc-189">Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.</span><span class="sxs-lookup"><span data-stu-id="aeedc-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="aeedc-190">Шаг 6. Установка локального сканера AIP и управление заданиями сканирования контента</span><span class="sxs-lookup"><span data-stu-id="aeedc-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="aeedc-191">Установка локального сканера AIP для сканирования сетевых и контентных акций для конфиденциальных данных, а также применения меток классификации и защиты в зависимости от политики организации.</span><span class="sxs-lookup"><span data-stu-id="aeedc-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="aeedc-192">При настройке и управлении заданиями проверки контента используйте следующую процедуру вместо интерфейса портала [Azure,](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) который используется коммерческими предложениями.</span><span class="sxs-lookup"><span data-stu-id="aeedc-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="aeedc-193">Дополнительные сведения см. в том, что такое сканер единой маркировки [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) и управление заданиями сканирования контента только [с помощью PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="aeedc-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="aeedc-194">**Установка и настройка сканера:**</span><span class="sxs-lookup"><span data-stu-id="aeedc-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="aeedc-195">Вопишитесь на компьютер Windows Server, который будет запускать сканер.</span><span class="sxs-lookup"><span data-stu-id="aeedc-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="aeedc-196">Используйте учетную запись с правами локального администратора и с разрешениями на запись в SQL Server базу данных.</span><span class="sxs-lookup"><span data-stu-id="aeedc-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="aeedc-197">Начните с закрытия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeedc-197">Start with PowerShell closed.</span></span> <span data-ttu-id="aeedc-198">Если вы ранее установили клиент AIP и сканер, убедитесь, что служба **AIPScanner** остановлена.</span><span class="sxs-lookup"><span data-stu-id="aeedc-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="aeedc-199">Откройте сеанс Windows PowerShell с помощью **параметра Run в качестве администратора.**</span><span class="sxs-lookup"><span data-stu-id="aeedc-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="aeedc-200">Запустите комлет [Install-AIPScanner,](/powershell/module/azureinformationprotection/Install-AIPScanner) указав SQL Server экземпляр, на котором можно создать базу данных для сканера защиты информации Azure, а также значимое имя кластера сканера.</span><span class="sxs-lookup"><span data-stu-id="aeedc-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="aeedc-201">Одно и то же имя кластера можно использовать в команде [Install-AIPScanner,](/powershell/module/azureinformationprotection/install-aipscanner) чтобы связать несколько узлов сканера с тем же кластером.</span><span class="sxs-lookup"><span data-stu-id="aeedc-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="aeedc-202">Использование одного и того же кластера для нескольких узлов сканера позволяет нескольким сканерам работать вместе для выполнения сканирования.</span><span class="sxs-lookup"><span data-stu-id="aeedc-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="aeedc-203">Убедитесь, что служба теперь установлена с помощью **служб**  >  **административных инструментов.**</span><span class="sxs-lookup"><span data-stu-id="aeedc-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="aeedc-204">Установленная служба называется **сканером защиты информации Azure** и настроена на запуск с помощью созданной учетной записи службы сканера.</span><span class="sxs-lookup"><span data-stu-id="aeedc-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="aeedc-205">Получите маркер Azure для использования с помощью сканера.</span><span class="sxs-lookup"><span data-stu-id="aeedc-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="aeedc-206">Маркер Azure AD позволяет сканеру выполнить проверку подлинности в службе защиты информации Azure, что позволяет сканеру работать без интерактивной работы.</span><span class="sxs-lookup"><span data-stu-id="aeedc-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="aeedc-207">Откройте портал Azure и создайте приложение Azure AD, чтобы указать маркер доступа для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="aeedc-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="aeedc-208">Дополнительные сведения см. в [материалах How to label files non-interactively for Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)</span><span class="sxs-lookup"><span data-stu-id="aeedc-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="aeedc-209">При создании и настройке приложений Azure AD для команды [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) в области  разрешений API запросов  показана таблица **API,** которая используется моей организацией вместо вкладки API Microsoft. Выберите **API, которые использует моя организация,** чтобы затем выбрать **службы управления** правами Azure.</span><span class="sxs-lookup"><span data-stu-id="aeedc-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="aeedc-210">С компьютера Windows Server, если учетной записи службы  сканера был предоставлен журнал на локальном праве для установки, войдите в эту учетную запись и запустите сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeedc-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="aeedc-211">Если учетная запись службы  сканера не может быть предоставлена журналу локально правильно для установки, используйте параметр *OnBehalfOf* с [помощью Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication)как описано в описании Как метить файлы неавтериализно для [Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)</span><span class="sxs-lookup"><span data-stu-id="aeedc-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="aeedc-212">Запустите [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication)указав значения, скопированные из приложения Azure AD:</span><span class="sxs-lookup"><span data-stu-id="aeedc-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="aeedc-213">Пример.</span><span class="sxs-lookup"><span data-stu-id="aeedc-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="aeedc-214">Теперь у сканера есть маркер для проверки подлинности в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="aeedc-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="aeedc-215">Этот маркер действителен в течение одного года, двух лет или никогда в соответствии с конфигурацией секрета клиента веб-приложения **и API** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="aeedc-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="aeedc-216">По истечении срока действия маркера необходимо повторить эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="aeedc-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="aeedc-217">Запустите [комлет Set-AIPScannerConfiguration,](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) чтобы настроить работу сканера в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="aeedc-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="aeedc-218">Запуск:</span><span class="sxs-lookup"><span data-stu-id="aeedc-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="aeedc-219">Запустите [комлет Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) для создания задания проверки контента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aeedc-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="aeedc-220">Единственным требуемого параметра в **комлете Set-AIPScannerContentScanJob** является **Enforce**.</span><span class="sxs-lookup"><span data-stu-id="aeedc-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="aeedc-221">Однако в настоящее время может потребоваться определить другие параметры для задания проверки контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="aeedc-222">Пример.</span><span class="sxs-lookup"><span data-stu-id="aeedc-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="aeedc-223">Синтаксис выше настраивает следующие параметры при продолжении настройки:</span><span class="sxs-lookup"><span data-stu-id="aeedc-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="aeedc-224">Сохраняет планирование запуска сканера в *ручном режиме*</span><span class="sxs-lookup"><span data-stu-id="aeedc-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="aeedc-225">Задает типы сведений, которые будут обнаружены на основе политики маркировки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="aeedc-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="aeedc-226">Не *применяет* политику маркировки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="aeedc-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="aeedc-227">Автоматически маркируется файлы на основе контента с помощью метки по умолчанию, определенной для политики маркировки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="aeedc-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="aeedc-228">Не *допускается* повторное перенаверение файлов</span><span class="sxs-lookup"><span data-stu-id="aeedc-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="aeedc-229">Сохраняет сведения о файлах при сканировании и автоматической маркировке, включая изменение даты, последние изменения *и* *изменение значений*</span><span class="sxs-lookup"><span data-stu-id="aeedc-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="aeedc-230">Задает сканер, чтобы исключить файлы .msg и .tmp при запуске</span><span class="sxs-lookup"><span data-stu-id="aeedc-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="aeedc-231">Устанавливает владельца по умолчанию для учетной записи, используемой при запуске сканера</span><span class="sxs-lookup"><span data-stu-id="aeedc-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="aeedc-232">Чтобы определить репозитории, которые необходимо сканировать в заданиях проверки контента, используйте код [Add-AIPScannerRepository.](/powershell/module/azureinformationprotection/add-aipscannerrepository)</span><span class="sxs-lookup"><span data-stu-id="aeedc-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="aeedc-233">Например, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="aeedc-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="aeedc-234">Используйте один из следующих синтаксисов в зависимости от типа репозитория, который вы добавляете:</span><span class="sxs-lookup"><span data-stu-id="aeedc-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="aeedc-235">Для сетевой доли используйте `\\Server\Folder` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="aeedc-236">Для библиотеки SharePoint используйте `http://sharepoint.contoso.com/Shared%20Documents/Folder` .</span><span class="sxs-lookup"><span data-stu-id="aeedc-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="aeedc-237">Для локального пути: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="aeedc-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="aeedc-238">Для пути UNC: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="aeedc-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="aeedc-239">Поддиадры не поддерживаются, а расположения WebDav не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="aeedc-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="aeedc-240">Чтобы изменить репозиторий позже, используйте вместо него кодлет [Set-AIPScannerRepository.](/powershell/module/azureinformationprotection/set-aipscannerrepository)</span><span class="sxs-lookup"><span data-stu-id="aeedc-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="aeedc-241">Продолжить следующие действия по мере необходимости:</span><span class="sxs-lookup"><span data-stu-id="aeedc-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="aeedc-242">Запуск цикла обнаружения и просмотр отчетов для сканера</span><span class="sxs-lookup"><span data-stu-id="aeedc-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="aeedc-243">Использование PowerShell для настройки сканера для применения классификации и защиты</span><span class="sxs-lookup"><span data-stu-id="aeedc-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="aeedc-244">Используйте PowerShell для настройки политики DLP с помощью сканера</span><span class="sxs-lookup"><span data-stu-id="aeedc-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="aeedc-245">В следующей таблице перечислены cmdlets PowerShell, которые необходимы для установки сканера и управления заданиями сканирования контента:</span><span class="sxs-lookup"><span data-stu-id="aeedc-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="aeedc-246">Командлет</span><span class="sxs-lookup"><span data-stu-id="aeedc-246">Cmdlet</span></span> | <span data-ttu-id="aeedc-247">Описание</span><span class="sxs-lookup"><span data-stu-id="aeedc-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="aeedc-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="aeedc-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="aeedc-249">Добавляет новый репозиторий в задание проверки контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="aeedc-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="aeedc-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="aeedc-251">Возвращает сведения о кластере.</span><span class="sxs-lookup"><span data-stu-id="aeedc-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="aeedc-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="aeedc-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="aeedc-253">Получает сведения о работе по проверке контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="aeedc-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="aeedc-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="aeedc-255">Получает сведения о репозиториях, определенных для задания сканирования контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="aeedc-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="aeedc-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="aeedc-257">Удаляет задание сканирования контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="aeedc-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="aeedc-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="aeedc-259">Удаляет репозиторий из задания проверки контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="aeedc-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="aeedc-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="aeedc-261">Определяет параметры задания сканирования контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="aeedc-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="aeedc-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="aeedc-263">Определяет параметры существующего репозитория в заданиях проверки контента.</span><span class="sxs-lookup"><span data-stu-id="aeedc-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="aeedc-264">Дополнительные сведения см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="aeedc-264">For more information, see:</span></span>

- [<span data-ttu-id="aeedc-265">Что такое сканер единой маркировки Azure Information Protection?</span><span class="sxs-lookup"><span data-stu-id="aeedc-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="aeedc-266">Настройка и установка единого сканера маркировки Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="aeedc-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="aeedc-267">[Управление заданиями сканирования контента только с помощью PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="aeedc-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
