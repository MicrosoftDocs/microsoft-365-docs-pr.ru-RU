---
title: Поддержка azure information Protection для Office 365, выполняемая 21Vianet
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
description: Дополнительные сведения о Azure Information Protection (AIP) для Office 365, выполняемой 21Vianet, и о настройке ее для клиентов в Китае.
monikerRange: o365-21vianet
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418036"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="8952b-103">Поддержка azure information Protection для Office 365, выполняемая 21Vianet</span><span class="sxs-lookup"><span data-stu-id="8952b-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="8952b-104">В этой статье освещаются различия между поддержкой Azure Information Protection (AIP) для Office 365, управляемой 21Vianet, и коммерческими предложениями, а также конкретные инструкции по настройке AIP для клиентов в Китае, включая установку локального сканера AIP и управление заданиями сканирования &mdash; контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="8952b-105">Различия между AIP для Office 365, выполняемым 21Vianet, и коммерческими предложениями</span><span class="sxs-lookup"><span data-stu-id="8952b-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="8952b-106">Хотя наша цель — предоставить все коммерческие функции и функции клиентам в Китае с помощью AIP для Office 365 с предложением 21Vianet, мы хотели бы выделить некоторые недостающие функции.</span><span class="sxs-lookup"><span data-stu-id="8952b-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="8952b-107">В следующем списке содержатся существующие пробелы между AIP для Office 365, выполняемым 21Vianet, и нашими коммерческими предложениями по январю 2021 г.:</span><span class="sxs-lookup"><span data-stu-id="8952b-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="8952b-108">Управление правами на информацию (IRM) поддерживается только для приложений Microsoft 365 для предприятия (сборка 11731.10000 или более).</span><span class="sxs-lookup"><span data-stu-id="8952b-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="8952b-109">Версии Office 2010, Office 2013 и других версий Office 2016 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8952b-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="8952b-110">Миграция служба управления правами Active Directory (AD RMS) в AIP в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="8952b-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="8952b-111">Поддерживается обмен защищенными электронными письмами с пользователями в коммерческом облаке.</span><span class="sxs-lookup"><span data-stu-id="8952b-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="8952b-112">Обмен документами и вложениями электронной почты с пользователями в коммерческом облаке в настоящее время не доступен.</span><span class="sxs-lookup"><span data-stu-id="8952b-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="8952b-113">Это включает Office 365, управляемый 21-ю пользователямиVianet в коммерческом облаке, не-Office 365, управляемый 21-ю пользователямиVianet в коммерческом облаке, и пользователей с лицензией RMS для физических лиц.</span><span class="sxs-lookup"><span data-stu-id="8952b-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="8952b-114">IRM с SharePoint (защищенные IRM-сайты и библиотеки) в настоящее время недоступны.</span><span class="sxs-lookup"><span data-stu-id="8952b-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="8952b-115">Расширение мобильного устройства для AD RMS в настоящее время не доступно.</span><span class="sxs-lookup"><span data-stu-id="8952b-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="8952b-116">Мобильный [зритель не](/azure/information-protection/rms-client/mobile-app-faq) поддерживается Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="8952b-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="8952b-117">Область AIP портала Azure недоступна для клиентов в Китае.</span><span class="sxs-lookup"><span data-stu-id="8952b-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="8952b-118">Используйте [команды PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) вместо выполнения действий на портале, например установки локального сканера и управления заданиями сканирования контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="8952b-119">Настройка AIP для клиентов в Китае</span><span class="sxs-lookup"><span data-stu-id="8952b-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="8952b-120">Настройка AIP для клиентов в Китае:</span><span class="sxs-lookup"><span data-stu-id="8952b-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="8952b-121">[Включить управление правами для клиента.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="8952b-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="8952b-122">[Настройка шифрования DNS.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="8952b-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="8952b-123">[Установка и настройка клиента единой маркировки AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="8952b-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="8952b-124">[Настройка приложений AIP в Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="8952b-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="8952b-125">[Установка локального сканера AIP и управление заданиями сканирования контента.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="8952b-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="8952b-126">Шаг 1. Включить управление правами для клиента</span><span class="sxs-lookup"><span data-stu-id="8952b-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="8952b-127">Чтобы шифрование работало правильно, необходимо включить RMS для клиента.</span><span class="sxs-lookup"><span data-stu-id="8952b-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="8952b-128">Проверьте, включен ли RMS:</span><span class="sxs-lookup"><span data-stu-id="8952b-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="8952b-129">Запустите PowerShell в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="8952b-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="8952b-130">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="8952b-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="8952b-131">Импорт модуля с помощью `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="8952b-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="8952b-132">Подключение к службе с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="8952b-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="8952b-133">Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте, является ли состояние `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="8952b-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="8952b-134">Если функциональное состояние , `Disabled` запустите `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="8952b-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="8952b-135">Шаг 2. Настройка шифрования DNS</span><span class="sxs-lookup"><span data-stu-id="8952b-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="8952b-136">Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к китайскому экземпляру службы и загрузке оттуда.</span><span class="sxs-lookup"><span data-stu-id="8952b-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="8952b-137">Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись SRV DNS с информацией о URL-адресе Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="8952b-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="8952b-138">Без записи SRV DNS клиентские приложения по умолчанию попытаются подключиться к общедоступным облачным экземплярам и сбой.</span><span class="sxs-lookup"><span data-stu-id="8952b-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="8952b-139">Кроме того, существует предположение, что пользователи будут входить в систему с иным имям пользователя, основанным на домене, владельцем клиента (например, ), а не имям `joe@contoso.cn` `onmschina` пользователя (например, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="8952b-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="8952b-140">Имя домена из имени пользователя используется для перенаправления DNS в правильный экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="8952b-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="8952b-141">Настройка шифрования DNS - Windows</span><span class="sxs-lookup"><span data-stu-id="8952b-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="8952b-142">Получите ID RMS:</span><span class="sxs-lookup"><span data-stu-id="8952b-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="8952b-143">Запустите PowerShell в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="8952b-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="8952b-144">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="8952b-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="8952b-145">Подключение к службе с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="8952b-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="8952b-146">`(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ID RMS.</span><span class="sxs-lookup"><span data-stu-id="8952b-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="8952b-147">Войдите в поставщик DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="8952b-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="8952b-148">Служба = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="8952b-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="8952b-149">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="8952b-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="8952b-150">Имя = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="8952b-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="8952b-151">Target = `[GUID].rms.aadrm.cn` (где GUID — это ID RMS)</span><span class="sxs-lookup"><span data-stu-id="8952b-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="8952b-152">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8952b-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="8952b-153">Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="8952b-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="8952b-154">Это добавит запись в DNS, для проверки которой может потребоваться несколько минут после добавления значения в параметры DNS.</span><span class="sxs-lookup"><span data-stu-id="8952b-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="8952b-155">Войдите в центр администрирования Microsoft 365 с соответствующими глобальными учетными данными администратора и добавьте домен (например, `contoso.cn` ) для создания пользователей.</span><span class="sxs-lookup"><span data-stu-id="8952b-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="8952b-156">В процессе проверки могут потребоваться дополнительные изменения DNS.</span><span class="sxs-lookup"><span data-stu-id="8952b-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="8952b-157">После проверки можно создать пользователей.</span><span class="sxs-lookup"><span data-stu-id="8952b-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="8952b-158">Настройка шифрования DNS - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="8952b-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="8952b-159">Войдите в поставщик DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="8952b-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="8952b-160">Служба = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="8952b-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="8952b-161">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="8952b-161">Protocol = `_http`</span></span>
- <span data-ttu-id="8952b-162">Имя = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="8952b-162">Name = `_tcp`</span></span>
- <span data-ttu-id="8952b-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="8952b-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="8952b-164">Порт = `80`</span><span class="sxs-lookup"><span data-stu-id="8952b-164">Port = `80`</span></span>
- <span data-ttu-id="8952b-165">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8952b-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="8952b-166">Шаг 3. Установка и настройка клиента единой маркировки AIP</span><span class="sxs-lookup"><span data-stu-id="8952b-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="8952b-167">Скачайте клиент единой метки AIP из [Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="8952b-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="8952b-168">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="8952b-168">For more information, see:</span></span>

- [<span data-ttu-id="8952b-169">Документация по AIP</span><span class="sxs-lookup"><span data-stu-id="8952b-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="8952b-170">История и политика поддержки версий AIP</span><span class="sxs-lookup"><span data-stu-id="8952b-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="8952b-171">Требования к системе AIP</span><span class="sxs-lookup"><span data-stu-id="8952b-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="8952b-172">AIP quickstart: Развертывание клиента AIP</span><span class="sxs-lookup"><span data-stu-id="8952b-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="8952b-173">Руководство администратора AIP</span><span class="sxs-lookup"><span data-stu-id="8952b-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="8952b-174">Руководство по пользователю AIP</span><span class="sxs-lookup"><span data-stu-id="8952b-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="8952b-175">Узнайте о метки конфиденциальности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8952b-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="8952b-176">Шаг 4. Настройка приложений AIP в Windows</span><span class="sxs-lookup"><span data-stu-id="8952b-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="8952b-177">Приложениям AIP в Windows необходим следующий ключ реестра, чтобы указать их на правильное суверенное облако для Azure China:</span><span class="sxs-lookup"><span data-stu-id="8952b-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="8952b-178">Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="8952b-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="8952b-179">Имя = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="8952b-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="8952b-180">Значение = `6` (по умолчанию = 0)</span><span class="sxs-lookup"><span data-stu-id="8952b-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="8952b-181">Тип = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="8952b-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8952b-182">Убедитесь, что не удаляйте ключ реестра после удаления.</span><span class="sxs-lookup"><span data-stu-id="8952b-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="8952b-183">Если ключ пустой, неправильный или несуществующий, функциональность будет вести себя как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака).</span><span class="sxs-lookup"><span data-stu-id="8952b-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="8952b-184">Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.</span><span class="sxs-lookup"><span data-stu-id="8952b-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="8952b-185">Шаг 5. Установка локального сканера AIP и управление заданиями сканирования контента</span><span class="sxs-lookup"><span data-stu-id="8952b-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="8952b-186">Установка локального сканера AIP для сканирования сетевых и контентных акций для конфиденциальных данных, а также применения меток классификации и защиты в зависимости от политики организации.</span><span class="sxs-lookup"><span data-stu-id="8952b-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="8952b-187">При создании и настройке приложений Azure AD для команды [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) в области  разрешений API запросов  показана таблица **API,** которая используется моей организацией вместо вкладки API Microsoft. Выберите **API, которые использует моя организация,** чтобы затем выбрать **службы управления** правами Azure.</span><span class="sxs-lookup"><span data-stu-id="8952b-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="8952b-188">При установке сканера и управлении заданиями сканирования контента используйте следующие cmdlets вместо интерфейса портала Azure, который используется коммерческими предложениями:</span><span class="sxs-lookup"><span data-stu-id="8952b-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="8952b-189">Командлет</span><span class="sxs-lookup"><span data-stu-id="8952b-189">Cmdlet</span></span> | <span data-ttu-id="8952b-190">Описание</span><span class="sxs-lookup"><span data-stu-id="8952b-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="8952b-191">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="8952b-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="8952b-192">Добавляет новый репозиторий в задание проверки контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="8952b-193">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="8952b-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="8952b-194">Получает сведения о работе по проверке контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="8952b-195">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="8952b-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="8952b-196">Получает сведения о репозиториях, определенных для задания сканирования контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="8952b-197">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="8952b-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="8952b-198">Удаляет задание сканирования контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="8952b-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="8952b-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="8952b-200">Удаляет репозиторий из задания проверки контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="8952b-201">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="8952b-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="8952b-202">Определяет параметры задания сканирования контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="8952b-203">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="8952b-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="8952b-204">Определяет параметры существующего репозитория в заданиях проверки контента.</span><span class="sxs-lookup"><span data-stu-id="8952b-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="8952b-205">При [установке сканера](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)используйте одно и то же имя кластера в команде [Install-AIPScanner,](/powershell/module/azureinformationprotection/install-aipscanner) чтобы связать несколько узлов сканера с тем же кластером.</span><span class="sxs-lookup"><span data-stu-id="8952b-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="8952b-206">Использование одного и того же кластера для нескольких узлов сканера позволяет нескольким сканерам работать вместе для выполнения сканирования.</span><span class="sxs-lookup"><span data-stu-id="8952b-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="8952b-207">Чтобы получить сведения о кластере, используйте комлет [Get-AIPScannerConfiguration.](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)</span><span class="sxs-lookup"><span data-stu-id="8952b-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="8952b-208">Дополнительные сведения см. в том, что такое сканер единой маркировки [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) и управление заданиями сканирования контента только [с помощью PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="8952b-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>