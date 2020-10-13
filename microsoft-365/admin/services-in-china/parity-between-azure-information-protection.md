---
title: Четность между службой Azure Information Protection для Office 365 под управлением 21Vianet и коммерческих услуг
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
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
description: Узнайте больше о службе Azure Information Protection для Office 365 под управлением 21Vianet и о том, как настроить его для клиентов в Китае.
monikerRange: o365-21vianet
ms.openlocfilehash: ca30811e77f686b92b8cdd13d624182eb0d3039e
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445583"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="5de29-103">Четность между службой Azure Information Protection для Office 365 под управлением 21Vianet и коммерческих услуг</span><span class="sxs-lookup"><span data-stu-id="5de29-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="5de29-104">Несмотря на то, что наша цель состоит в том, чтобы предоставить клиентам в Китае все коммерческие функции и функции с помощью Azure Information Protection для Office 365, предоставляемого компанией 21Vianet, есть некоторые функции, которые мы хотели бы выделить.</span><span class="sxs-lookup"><span data-stu-id="5de29-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="5de29-105">В приведенном ниже списке перечислены существующие промежутки между службой Azure Information Protection для Office 365 под управлением 21Vianet и наших коммерческих услуг на 2019 июля:</span><span class="sxs-lookup"><span data-stu-id="5de29-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="5de29-106">Управление правами на доступ к данным (IRM) поддерживается только для приложений Microsoft 365 для предприятий (сборка 11731,10000 или более поздняя).</span><span class="sxs-lookup"><span data-stu-id="5de29-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="5de29-107">Office 2010, Office 2013 и другие версии Office 2016 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5de29-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="5de29-108">Миграция из службы управления правами Active Directory (AD RMS) в Azure Information Protection в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="5de29-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="5de29-109">Поддерживается общий доступ к защищенным сообщениям электронной почты для пользователей в коммерческом облаке.</span><span class="sxs-lookup"><span data-stu-id="5de29-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="5de29-110">Общий доступ к документам и вложениям электронной почты для пользователей в коммерческом облаке в настоящее время недоступен.</span><span class="sxs-lookup"><span data-stu-id="5de29-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="5de29-111">Это включает Office 365 под управлением 21Vianet в коммерческом облаке, а не в Office 365, который управляется пользователями 21Vianet в коммерческом облаке, и пользователями с лицензией RMS для индивидуальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5de29-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="5de29-112">IRM с SharePoint (сайты и библиотеки, защищенные службой управления правами), в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="5de29-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="5de29-113">В настоящее время соединитель управления правами недоступен.</span><span class="sxs-lookup"><span data-stu-id="5de29-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="5de29-114">Расширение мобильных устройств для AD RMS в настоящее время недоступно.</span><span class="sxs-lookup"><span data-stu-id="5de29-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="5de29-115">Настройка Azure Information Protection для клиентов в Китае</span><span class="sxs-lookup"><span data-stu-id="5de29-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="5de29-116">Включение управления правами для клиента</span><span class="sxs-lookup"><span data-stu-id="5de29-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="5de29-117">Для правильной работы шифрования необходимо включить службу управления правами для клиента.</span><span class="sxs-lookup"><span data-stu-id="5de29-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="5de29-118">Проверьте, включена ли служба управления правами:</span><span class="sxs-lookup"><span data-stu-id="5de29-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="5de29-119">Запустите PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="5de29-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="5de29-120">Если модуль Аипсервице не установлен, запустите его  `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="5de29-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="5de29-121">Импортируйте модуль с помощью `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="5de29-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="5de29-122">Подключаться к службе с помощью  `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="5de29-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="5de29-123">Запустите  `(Get-AipServiceConfiguration).FunctionalState`   и проверьте, есть ли состояние  `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="5de29-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="5de29-124">Если функциональное состояние —  `Disabled` , запустите  `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="5de29-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="5de29-125">Конфигурация DNS для шифрования (Windows)</span><span class="sxs-lookup"><span data-stu-id="5de29-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="5de29-126">Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к экземпляру службы Китая и выполнять начальную загрузку.</span><span class="sxs-lookup"><span data-stu-id="5de29-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="5de29-127">Чтобы перенаправить клиентские приложения на правильный экземпляр службы, администратор клиента должен настроить запись DNS SRV со сведениями об URL-адресе Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="5de29-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="5de29-128">При отсутствии DNS-записи SRV клиентское приложение попытается подключиться к экземпляру общедоступного облака по умолчанию и завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="5de29-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="5de29-129">Кроме того, предполагается, что пользователи выполняют вход с именем пользователя, основанным на домене, принадлежащем клиенту (например, `joe@contoso.cn` ), а не `onmschina` именем пользователя (например, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="5de29-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="5de29-130">Имя домена из имени пользователя используется для перенаправления DNS на соответствующий экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="5de29-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="5de29-131">Получение идентификатора службы управления правами:</span><span class="sxs-lookup"><span data-stu-id="5de29-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="5de29-132">Запустите PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="5de29-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="5de29-133">Если модуль Аипсервице не установлен, запустите его  `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="5de29-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="5de29-134">Подключаться к службе с помощью  `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="5de29-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="5de29-135">Запустите  `(Get-AipServiceConfiguration).RightsManagementServiceId`   , чтобы получить идентификатор службы управления правами.</span><span class="sxs-lookup"><span data-stu-id="5de29-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="5de29-136">Выполните вход в систему поставщика DNS, перейдите к параметрам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="5de29-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="5de29-137">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="5de29-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="5de29-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="5de29-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="5de29-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="5de29-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="5de29-140">Target =  `[GUID].rms.aadrm.cn`   (где GUID — идентификатор RMS)</span><span class="sxs-lookup"><span data-stu-id="5de29-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="5de29-141">Priority, Weight, seconds, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="5de29-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="5de29-142">Свяжите личный домен с клиентом на [портале Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="5de29-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="5de29-143">Это приведет к добавлению записи в DNS, что может занять несколько минут, чтобы проверить его после добавления значения в параметры DNS.</span><span class="sxs-lookup"><span data-stu-id="5de29-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="5de29-144">Войдите в центр администрирования Microsoft 365, используя соответствующие учетные данные глобального администратора, и добавьте домен (например, `contoso.cn` ) для создания пользователя.</span><span class="sxs-lookup"><span data-stu-id="5de29-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="5de29-145">В процессе проверки могут потребоваться дополнительные изменения DNS.</span><span class="sxs-lookup"><span data-stu-id="5de29-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="5de29-146">После завершения проверки пользователи могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="5de29-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="5de29-147">Конфигурация DNS для шифрования (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="5de29-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="5de29-148">Выполните вход в систему поставщика DNS, перейдите к параметрам DNS для домена и добавьте новую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="5de29-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="5de29-149">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="5de29-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="5de29-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="5de29-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="5de29-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="5de29-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="5de29-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="5de29-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="5de29-153">Порт = `80`</span><span class="sxs-lookup"><span data-stu-id="5de29-153">Port = `80`</span></span>
  - <span data-ttu-id="5de29-154">Priority, Weight, seconds, TTL = значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="5de29-154">Priority, Weight, Seconds, TTL = default values</span></span>
