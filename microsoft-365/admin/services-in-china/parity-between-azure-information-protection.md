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
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099682"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="cd10c-103">Поддержка Azure Information Protection для Office 365 под управлением 21Vianet</span><span class="sxs-lookup"><span data-stu-id="cd10c-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="cd10c-104">В этой статье освещаются различия между поддержкой Azure Information Protection (AIP) для Office 365 под управлением 21Vianet и коммерческих предложений, а также конкретные инструкции по настройке AIP для клиентов в Китае, включая установку локального сканера AIP и управление заданиями сканирования &mdash; контента.</span><span class="sxs-lookup"><span data-stu-id="cd10c-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="cd10c-105">Различия между AIP для Office 365 под управлением 21Vianet и коммерческими предложениями</span><span class="sxs-lookup"><span data-stu-id="cd10c-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="cd10c-106">Хотя наша цель — предоставить все коммерческие функции клиентам в Китае с нашим предложением AIP для Office 365 под управлением 21Vianet, мы хотим выделить некоторые отсутствующие функции.</span><span class="sxs-lookup"><span data-stu-id="cd10c-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="cd10c-107">В следующем списке содержатся существующие пробелы между AIP для Office 365 под управлением 21Vianet и нашими коммерческими предложениями с января 2021 г.:</span><span class="sxs-lookup"><span data-stu-id="cd10c-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="cd10c-108">Управление правами на управление правами на данные (IRM) поддерживается только для приложений Microsoft 365 для предприятий (сборка 11731.10000 или выше).</span><span class="sxs-lookup"><span data-stu-id="cd10c-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="cd10c-109">Office 2010, Office 2013 и другие версии Office 2016 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="cd10c-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="cd10c-110">Миграция служба управления правами Active Directory (AD RMS) на AIP в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="cd10c-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="cd10c-111">Совместное использование защищенных сообщений электронной почты с пользователями в коммерческом облаке поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cd10c-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="cd10c-112">Общий доступ к документам и вложениям электронной почты пользователям в коммерческом облаке в настоящее время не доступен.</span><span class="sxs-lookup"><span data-stu-id="cd10c-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="cd10c-113">К ним относятся пользователи Office 365 под управлением 21Vianet в коммерческом облаке, пользователи не из Office 365 под управлением 21Vianet в коммерческом облаке и пользователи с лицензией RMS для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="cd10c-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="cd10c-114">IRM с SharePoint (сайты и библиотеки, защищенные с помощью IRM) в настоящее время не доступен.</span><span class="sxs-lookup"><span data-stu-id="cd10c-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="cd10c-115">Расширение мобильного устройства для AD RMS в настоящее время не доступно.</span><span class="sxs-lookup"><span data-stu-id="cd10c-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="cd10c-116">Приложение ["Просмотр мобильных устройств"](/azure/information-protection/rms-client/mobile-app-faq) не поддерживается azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="cd10c-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="cd10c-117">Область AIP портала Azure недоступна для пользователей в Китае.</span><span class="sxs-lookup"><span data-stu-id="cd10c-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="cd10c-118">Вместо выполнения действий на портале, таких как установка локального сканера и управление заданиями сканирования контента, используйте команды [PowerShell.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="cd10c-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="cd10c-119">Настройка AIP для клиентов в Китае</span><span class="sxs-lookup"><span data-stu-id="cd10c-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="cd10c-120">Настройка AIP для клиентов в Китае:</span><span class="sxs-lookup"><span data-stu-id="cd10c-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="cd10c-121">[Включить управление правами для клиента.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="cd10c-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="cd10c-122">[Настройка шифрования DNS.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="cd10c-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="cd10c-123">[Установите и настройте клиент унифицированных меток AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="cd10c-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="cd10c-124">[Настройка приложений AIP в Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="cd10c-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="cd10c-125">[Установка локального сканера AIP и управление заданиями проверки содержимого.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="cd10c-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="cd10c-126">Шаг 1. Включить управление правами для клиента</span><span class="sxs-lookup"><span data-stu-id="cd10c-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="cd10c-127">Чтобы шифрование работало правильно, необходимо включить для клиента RMS.</span><span class="sxs-lookup"><span data-stu-id="cd10c-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="cd10c-128">Проверьте, включена ли RMS:</span><span class="sxs-lookup"><span data-stu-id="cd10c-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="cd10c-129">Запустите PowerShell от учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="cd10c-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="cd10c-130">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="cd10c-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="cd10c-131">Импорт модуля с помощью `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="cd10c-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="cd10c-132">Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="cd10c-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="cd10c-133">Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте `Enabled` состояние.</span><span class="sxs-lookup"><span data-stu-id="cd10c-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="cd10c-134">Если функциональным состоянием является `Disabled` , запустите `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="cd10c-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="cd10c-135">Шаг 2. Настройка шифрования DNS</span><span class="sxs-lookup"><span data-stu-id="cd10c-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="cd10c-136">Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к экземпляру службы в Китае и из нее подключаться к первой загрузке.</span><span class="sxs-lookup"><span data-stu-id="cd10c-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="cd10c-137">Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись DNS SRV с информацией об URL-адресе Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="cd10c-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="cd10c-138">Без DNS-записи SRV клиентские приложения по умолчанию попытаются подключиться к экземпляру общего облака и не будут работать.</span><span class="sxs-lookup"><span data-stu-id="cd10c-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="cd10c-139">Кроме того, предположим, что пользователи будут входить в систему с помощью имени пользователя, основанного на домене, владельцем клиента (например, ), а не ином пользователем `joe@contoso.cn` `onmschina` (например). `joe@contoso.onmschina.cn`</span><span class="sxs-lookup"><span data-stu-id="cd10c-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="cd10c-140">Доменное имя из имени пользователя используется для перенаправления DNS на правильный экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="cd10c-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="cd10c-141">Настройка шифрования DNS — Windows</span><span class="sxs-lookup"><span data-stu-id="cd10c-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="cd10c-142">Получите ИД RMS:</span><span class="sxs-lookup"><span data-stu-id="cd10c-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="cd10c-143">Запустите PowerShell от учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="cd10c-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="cd10c-144">Если модуль AIPService не установлен, запустите `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="cd10c-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="cd10c-145">Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="cd10c-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="cd10c-146">`(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ИД RMS.</span><span class="sxs-lookup"><span data-stu-id="cd10c-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="cd10c-147">Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="cd10c-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="cd10c-148">Служба = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="cd10c-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="cd10c-149">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="cd10c-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="cd10c-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="cd10c-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="cd10c-151">Target = `[GUID].rms.aadrm.cn` (где GUID — это ИД RMS)</span><span class="sxs-lookup"><span data-stu-id="cd10c-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="cd10c-152">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="cd10c-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="cd10c-153">Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="cd10c-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="cd10c-154">При этом в DNS будет добавлена запись, проверка которой может занять несколько минут после добавления значения в параметры DNS.</span><span class="sxs-lookup"><span data-stu-id="cd10c-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="cd10c-155">Войдите в Центр администрирования Microsoft 365 с соответствующими учетными данными глобального администратора и добавьте домен (например, `contoso.cn` ) для создания пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd10c-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="cd10c-156">В процессе проверки могут потребоваться дополнительные изменения DNS.</span><span class="sxs-lookup"><span data-stu-id="cd10c-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="cd10c-157">После проверки пользователи могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="cd10c-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="cd10c-158">Настройка шифрования DNS — Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="cd10c-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="cd10c-159">Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="cd10c-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="cd10c-160">Служба = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="cd10c-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="cd10c-161">Протокол = `_http`</span><span class="sxs-lookup"><span data-stu-id="cd10c-161">Protocol = `_http`</span></span>
- <span data-ttu-id="cd10c-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="cd10c-162">Name = `_tcp`</span></span>
- <span data-ttu-id="cd10c-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="cd10c-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="cd10c-164">Порт = `80`</span><span class="sxs-lookup"><span data-stu-id="cd10c-164">Port = `80`</span></span>
- <span data-ttu-id="cd10c-165">Приоритет, вес, секунды, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="cd10c-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="cd10c-166">Шаг 3. Установка и настройка клиента унифицированных меток AIP</span><span class="sxs-lookup"><span data-stu-id="cd10c-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="cd10c-167">Скачайте клиент унифицированных меток AIP из [Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="cd10c-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="cd10c-168">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="cd10c-168">For more information, see:</span></span>

- [<span data-ttu-id="cd10c-169">Документация по AIP</span><span class="sxs-lookup"><span data-stu-id="cd10c-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="cd10c-170">История версий AIP и политика поддержки</span><span class="sxs-lookup"><span data-stu-id="cd10c-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="cd10c-171">Требования к системе AIP</span><span class="sxs-lookup"><span data-stu-id="cd10c-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="cd10c-172">Краткое развертывание клиента AIP</span><span class="sxs-lookup"><span data-stu-id="cd10c-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="cd10c-173">Руководство администратора AIP</span><span class="sxs-lookup"><span data-stu-id="cd10c-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="cd10c-174">Руководство пользователя по AIP</span><span class="sxs-lookup"><span data-stu-id="cd10c-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="cd10c-175">Узнайте о метах конфиденциальности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd10c-175">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="cd10c-176">Шаг 4. Настройка приложений AIP в Windows</span><span class="sxs-lookup"><span data-stu-id="cd10c-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="cd10c-177">Приложениям AIP в Windows необходим следующий ключ реестра, чтобы указать им правильное независимое облако для Azure в Китае:</span><span class="sxs-lookup"><span data-stu-id="cd10c-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="cd10c-178">Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="cd10c-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="cd10c-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="cd10c-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="cd10c-180">Значение = `6` (по умолчанию = 0)</span><span class="sxs-lookup"><span data-stu-id="cd10c-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="cd10c-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="cd10c-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd10c-182">Убедитесь, что не удаляйте ключ реестра после удаления.</span><span class="sxs-lookup"><span data-stu-id="cd10c-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="cd10c-183">Если ключ пустой, неправильный или несуществующий, функция будет действовать как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака).</span><span class="sxs-lookup"><span data-stu-id="cd10c-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="cd10c-184">Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.</span><span class="sxs-lookup"><span data-stu-id="cd10c-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="cd10c-185">Шаг 5. Установка локального сканера AIP и управление заданиями сканирования контента</span><span class="sxs-lookup"><span data-stu-id="cd10c-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="cd10c-186">Установите локального сканерА AIP, чтобы проверить сетевые и контентные пакеты на конфиденциальные данные, а также применить метки классификации и защиты, настроенные в политике организации.</span><span class="sxs-lookup"><span data-stu-id="cd10c-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="cd10c-187">При установке сканера и управлении заданиями проверки содержимого используйте следующие cmdlets вместо интерфейса портала Azure, который используется коммерческими предложениями:</span><span class="sxs-lookup"><span data-stu-id="cd10c-187">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="cd10c-188">Командлет</span><span class="sxs-lookup"><span data-stu-id="cd10c-188">Cmdlet</span></span> | <span data-ttu-id="cd10c-189">Description</span><span class="sxs-lookup"><span data-stu-id="cd10c-189">Description</span></span> |
|--|--|
| [<span data-ttu-id="cd10c-190">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cd10c-190">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="cd10c-191">Добавляет новый репозиторий в задание проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="cd10c-191">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="cd10c-192">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cd10c-192">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="cd10c-193">Получает сведения о заданиях проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="cd10c-193">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="cd10c-194">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cd10c-194">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="cd10c-195">Получает сведения о репозиториях, определенных для задания сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="cd10c-195">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="cd10c-196">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cd10c-196">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="cd10c-197">Удаляет задание проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="cd10c-197">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="cd10c-198">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cd10c-198">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="cd10c-199">Удаляет репозиторий из задания сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="cd10c-199">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="cd10c-200">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cd10c-200">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="cd10c-201">Определяет параметры задания проверки содержимого.</span><span class="sxs-lookup"><span data-stu-id="cd10c-201">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="cd10c-202">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cd10c-202">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="cd10c-203">Определяет параметры существующего репозитория в заданиях сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="cd10c-203">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="cd10c-204">Дополнительные сведения см. в том, что такое унифицированный сканер меток [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) И управление заданиями проверки содержимого [с помощью только PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="cd10c-204">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
