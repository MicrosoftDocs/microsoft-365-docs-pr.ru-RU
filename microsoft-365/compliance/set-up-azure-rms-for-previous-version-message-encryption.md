---
title: Настройка Azure Rights Management для предыдущей версии шифрования сообщений
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: Предыдущая версия шифрования сообщений Office 365 зависит от службы управления правами Microsoft Azure (прежнее название — Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 879f4ec1db8a8cfe1fe3c8d3b1dd9e1fc68dd687
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165920"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="4338a-103">Настройка azure Rights Management для предыдущей версии шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="4338a-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="4338a-104">В этом разделе описываются действия, которые необходимо предпринять, чтобы активировать и настроить службу Azure Rights Management (RMS), включаемую в Azure Information Protection, для использования с предыдущей версией шифрования сообщений Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="4338a-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="4338a-105">Эта статья относится только к предыдущей версии OME</span><span class="sxs-lookup"><span data-stu-id="4338a-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="4338a-106">Если вы еще не перешли на новые возможности OME, но уже развернули OME, сведения в этой статье применимы к вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4338a-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="4338a-107">Корпорация Майкрософт рекомендует спланировать переход на новые возможности OME, как только это будет приемлемо для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4338a-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="4338a-108">Инструкции см. в настройках новых возможностей шифрования [сообщений Office 365.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="4338a-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="4338a-109">Дополнительные информацию о том, как новые возможности работают [](ome.md)в первую очередь, см. в этой теме.</span><span class="sxs-lookup"><span data-stu-id="4338a-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="4338a-110">Остальная часть этой статьи относится к поведению OME перед выпуском новых возможностей OME.</span><span class="sxs-lookup"><span data-stu-id="4338a-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="4338a-111">Необходимые условия для использования предыдущей версии шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="4338a-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="4338a-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="4338a-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="4338a-113">Шифрование сообщений Office 365 (OME), включая IRM, зависит от службы Azure Rights Management (Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="4338a-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="4338a-114">Azure RMS — это технология защиты, используемая Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="4338a-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="4338a-115">Чтобы использовать OME, ваша организация должна включить подписку exchange Online или Exchange Online Protection, которая, в свою очередь, включает подписку на Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="4338a-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="4338a-116">Если вы не знаете, что входит в подписку, см. описание службы Exchange Online для политики сообщений, восстановления [и соответствия требованиям.](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)</span><span class="sxs-lookup"><span data-stu-id="4338a-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="4338a-117">Если у вас есть служба Azure Rights Management, но она не настроена для Exchange Online или Exchange Online Protection, в этой статье описывается, как активировать службу Azure Rights Management, а затем описан лучший способ настроить OME для работы с Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="4338a-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="4338a-118">Если вы уже настроили OME для работы с azure Rights Management для Exchange Online или Exchange Online Protection, в зависимости от того, как вы настроили OME, вы можете сразу приступить к использованию OME и его новых возможностей.</span><span class="sxs-lookup"><span data-stu-id="4338a-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="4338a-119">В этой статье объясняется, как определить, правильно ли настроена настройка OME, что делать, если необходимо изменить настройку, и что произойдет, если вы решите не изменять настройку.</span><span class="sxs-lookup"><span data-stu-id="4338a-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="4338a-120">Например, чтобы использовать новые возможности, необходимо использовать Azure RMS с OME.</span><span class="sxs-lookup"><span data-stu-id="4338a-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="4338a-121">Новые возможности нельзя использовать с локальной службой active Directory RMS.</span><span class="sxs-lookup"><span data-stu-id="4338a-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="4338a-122">Активация azure Rights Management для предыдущей версии OME в Office 365</span><span class="sxs-lookup"><span data-stu-id="4338a-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="4338a-123">Необходимо активировать Службу управления правами Azure, чтобы пользователи в организации могли применять защиту информации к отправляемым ими сообщениям, а также открывать сообщения и файлы, защищенные службой управления правами Azure.</span><span class="sxs-lookup"><span data-stu-id="4338a-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="4338a-124">Инструкции см. в [инструкциях по активации службы управления правами Azure.](https://go.microsoft.com/fwlink/p/?LinkId=525775)</span><span class="sxs-lookup"><span data-stu-id="4338a-124">For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775).</span></span> <span data-ttu-id="4338a-125">Завершив активацию, вернись сюда и продолжите выполнение задач, которые данная статья.</span><span class="sxs-lookup"><span data-stu-id="4338a-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="4338a-126">Настройка предыдущей версии OME для использования Azure RMS путем импорта доверенных доменов публикации (TPD)</span><span class="sxs-lookup"><span data-stu-id="4338a-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="4338a-127">TPD — это XML-файл, содержащий сведения о параметрах управления правами организации.</span><span class="sxs-lookup"><span data-stu-id="4338a-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="4338a-128">Например, TPD содержит сведения о сертификате лицензирования сервера (SLC), используемом для подписи и шифрования сертификатов и лицензий, URL-адресах, используемых для лицензирования и публикации, и т. д.</span><span class="sxs-lookup"><span data-stu-id="4338a-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="4338a-129">Вы импортируете TPD в свою организацию с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4338a-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4338a-130">Ранее можно было импортировать TPD из службы управления правами Active Directory (AD RMS) в организацию.</span><span class="sxs-lookup"><span data-stu-id="4338a-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="4338a-131">Однако это не позволит вам использовать новые возможности OME и не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="4338a-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="4338a-132">Если в настоящее время ваша организация настроена таким образом, Корпорация Майкрософт рекомендует создать план перехода с локальной службы active Directory RMS на облачную службу Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="4338a-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="4338a-133">Дополнительные сведения см. в переходе [с AD RMS на Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="4338a-133">For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="4338a-134">Вы не сможете использовать новые возможности OME, пока не завершите миграцию в Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="4338a-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="4338a-135">**Импорт TPD из Azure RMS**</span><span class="sxs-lookup"><span data-stu-id="4338a-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="4338a-136">[Подключение к Exchange Online с помощью удаленной powerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4338a-136">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="4338a-137">Выберите URL-адрес общего доступа по ключам, соответствующий географическому расположению вашей организации:</span><span class="sxs-lookup"><span data-stu-id="4338a-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="4338a-138">**Location**</span><span class="sxs-lookup"><span data-stu-id="4338a-138">**Location**</span></span>|<span data-ttu-id="4338a-139">**URL-адрес расположения для общего доступа к ключам**</span><span class="sxs-lookup"><span data-stu-id="4338a-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4338a-140">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="4338a-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4338a-141">Европейский Союз</span><span class="sxs-lookup"><span data-stu-id="4338a-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4338a-142">Азия</span><span class="sxs-lookup"><span data-stu-id="4338a-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4338a-143">Южная Америка</span><span class="sxs-lookup"><span data-stu-id="4338a-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="4338a-144">Office 365 для государственных организаций (облако сообщества госучреждений)</span><span class="sxs-lookup"><span data-stu-id="4338a-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="4338a-145">Это расположение для общего доступа к ключам RMS зарезервировано для клиентов, которые приобрели Office 365 для государственных номеров.</span><span class="sxs-lookup"><span data-stu-id="4338a-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="4338a-146">Настройте расположение для общего доступа [](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) к ключам, задав для этого 24-й и 10-й разделы.</span><span class="sxs-lookup"><span data-stu-id="4338a-146">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="4338a-147">Например, чтобы настроить расположение общего доступа к ключам, если ваша организация расположена в Северной Америке:</span><span class="sxs-lookup"><span data-stu-id="4338a-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="4338a-148">[Запустителет Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) с переключателем -RMSOnline, чтобы импортировать TPD из azure Rights Management:</span><span class="sxs-lookup"><span data-stu-id="4338a-148">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="4338a-149">Где  *TPDName*  это имя, которое вы хотите использовать для TPD.</span><span class="sxs-lookup"><span data-stu-id="4338a-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="4338a-150">Например, "Contoso North American TPD".</span><span class="sxs-lookup"><span data-stu-id="4338a-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="4338a-151">Чтобы убедиться, что вы успешно настроили свою организацию для использования службы управления правами Azure, выполните с помощью переключателя -RMSOnline с помощью команды [Test-IRMConfiguration:](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4338a-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="4338a-152">Помимо прочего, этот cmdlet проверяет возможность подключения к службе управления правами Azure, скачивает TPD и проверяет его действительность.</span><span class="sxs-lookup"><span data-stu-id="4338a-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="4338a-153">Чтобы [отключить](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) доступ к шаблонам управления правами Azure в Outlook в Интернете и Outlook, выполните этот запуск следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4338a-153">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="4338a-154">Чтобы [](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) включить Службу управления правами Azure для облачной организации электронной почты и настроить ее на использование службы Azure Rights Management для шифрования сообщений Office 365, выполните этот запуск следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4338a-154">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="4338a-155">Чтобы убедиться, что вы успешно импортировали TPD и включили azure Rights Management, используйте Test-IRMConfiguration для проверки функций Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="4338a-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="4338a-156">Подробные сведения см. в примере 1 в [test-IRMConfiguration.](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4338a-156">For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="4338a-157">У меня установлена предыдущая версия OME с управлением правами Active Directory, а не Azure Information Protection, что мне делать?</span><span class="sxs-lookup"><span data-stu-id="4338a-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="4338a-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4338a-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="4338a-159">Вы можете продолжать использовать существующие правила потока почты шифрования сообщений Office 365 с управлением правами Active Directory, но не можете настроить или использовать новые возможности OME.</span><span class="sxs-lookup"><span data-stu-id="4338a-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="4338a-160">Вместо этого необходимо перейти на Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="4338a-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="4338a-161">Сведения о миграции и о том, что это означает для вашей организации, см. в сведениях о переходе с [AD RMS на Azure Information Protection.](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)</span><span class="sxs-lookup"><span data-stu-id="4338a-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="4338a-162">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4338a-162">Next steps</span></span>
<span data-ttu-id="4338a-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4338a-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="4338a-164">Если вы хотите включить новые возможности OME, по завершению настройки azure Rights Management, см. сведения о настройке новых возможностей шифрования сообщений [Office 365,](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities) построенных на основе Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="4338a-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)</span></span>
  
<span data-ttu-id="4338a-165">После того как вы настроите свою организацию для использования новых возможностей OME, вы можете определить правила потока почты для защиты сообщений электронной почты с помощью новых возможностей [OME.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="4338a-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4338a-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4338a-166">Related topics</span></span>
<span data-ttu-id="4338a-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="4338a-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="4338a-168">Шифрование в Office 365</span><span class="sxs-lookup"><span data-stu-id="4338a-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="4338a-169">Техническая справка по шифрованию в Office 365</span><span class="sxs-lookup"><span data-stu-id="4338a-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="4338a-170">Управление правами Azure</span><span class="sxs-lookup"><span data-stu-id="4338a-170">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
