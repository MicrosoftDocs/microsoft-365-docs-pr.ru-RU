---
title: Настройка новых возможностей шифрования сообщений
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Узнайте о новых возможностях шифрования сообщений Office 365, позволяющих защитить переписку с людьми внутри и за пределами вашей организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d6e37da7456cfbb0b7cbf8d986b54615aca60f0
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819189"
---
# <a name="set-up-new-message-encryption-capabilities"></a><span data-ttu-id="9985f-103">Настройка новых возможностей шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="9985f-103">Set up new Message Encryption capabilities</span></span>

<span data-ttu-id="9985f-104">Новые возможности шифрования сообщений в Office 365 (OME) позволяют организациям обмениваться защищенными сообщениями с кем угодно с любого устройства.</span><span class="sxs-lookup"><span data-stu-id="9985f-104">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="9985f-105">Пользователи могут обмениваться защищенными сообщениями с другими организациями Microsoft 365, а также с сотрудниками других организаций, использующих Outlook.com, Gmail и прочие почтовые службы.</span><span class="sxs-lookup"><span data-stu-id="9985f-105">Users can exchange protected messages with other Microsoft 365 organizations, as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="9985f-106">Чтобы убедиться, что новые возможности OME доступны в вашей организации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9985f-106">Follow the steps below to ensure that the new OME capabilities are available in your organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="9985f-107">Проверьте, активна ли служба Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="9985f-107">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="9985f-108">Новые возможности OME используют функции защиты в [службе управления правами Azure (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) — технологию, используемую службой [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) для защиты электронной почты и документов с помощью шифрования и управления доступом.</span><span class="sxs-lookup"><span data-stu-id="9985f-108">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="9985f-109">Единственное обязательное условие для использования новых возможностей OME — [служба управления правами Azure](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) должна быть активирована в клиенте вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9985f-109">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="9985f-110">Если это так, Microsoft 365 автоматически активирует новые возможности OME, а от вас не потребуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="9985f-110">If it is, Microsoft 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="9985f-111">Кроме того, служба Azure RMS автоматически активируется для большинства соответствующих планов. В этом случае от вас тоже не потребуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="9985f-111">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="9985f-112">Дополнительные сведения см. в статье [Активация службы управления правами Azure](https://docs.microsoft.com/azure/information-protection/activate-service).</span><span class="sxs-lookup"><span data-stu-id="9985f-112">See [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9985f-113">Если вы используете службу управления правами Active Directory (AD RMS) в Exchange Online, перед использованием новых возможностей OME необходимо [перейти на службу Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms).</span><span class="sxs-lookup"><span data-stu-id="9985f-113">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="9985f-114">Служба OME не совместима с AD RMS.</span><span class="sxs-lookup"><span data-stu-id="9985f-114">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="9985f-115">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="9985f-115">For more information, see:</span></span>

- <span data-ttu-id="9985f-116">[Какие подписки необходимо использовать для новых возможностей OME?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) Эта статья поможет вам убедиться, что ваш план подписки включает службу Azure Information Protection (которая включает функции Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="9985f-116">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="9985f-117">Сведения о приобретении соответствующей подписки см. в статье [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="9985f-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="9985f-118">Активация службы управления правами Azure вручную</span><span class="sxs-lookup"><span data-stu-id="9985f-118">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="9985f-119">Если вы отключили службу Azure RMS или по какой-либо причине она не была активирована автоматически, вы можете активировать ее вручную, используя одно из указанных ниже средств.</span><span class="sxs-lookup"><span data-stu-id="9985f-119">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="9985f-120">**Центр администрирования Microsoft 365**. Инструкции см. в статье [Активация службы управления правами Azure в Центре администрирования](https://docs.microsoft.com/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="9985f-120">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="9985f-121">**Портал Azure**. Инструкции см. в статье [Активация службы управления правами Azure на портале Azure](https://docs.microsoft.com/azure/information-protection/activate-azure).</span><span class="sxs-lookup"><span data-stu-id="9985f-121">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="9985f-122">Настройка управления ключом клиента для службы Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="9985f-122">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="9985f-123">Это действие не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="9985f-123">This is an optional step.</span></span> <span data-ttu-id="9985f-124">По умолчанию корпорации Майкрософт разрешено управлять корневым ключом для службы Azure Information Protection. Этот вариант рекомендуется для большинства организаций.</span><span class="sxs-lookup"><span data-stu-id="9985f-124">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most organizations.</span></span> <span data-ttu-id="9985f-125">В таком случае от вас не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="9985f-125">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="9985f-126">Существует множество причин, по которым вам может потребоваться создать собственный корневой ключ (BYOK), а также управлять им, например для обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9985f-126">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="9985f-127">В таком случае перед настройкой новых возможностей OME рекомендуется выполнить необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="9985f-127">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="9985f-128">Дополнительные сведения см. в статье [Планирование и реализация ключа клиента Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="9985f-128">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="9985f-129">Проверка новой конфигурации OME в Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="9985f-129">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="9985f-130">Вы можете убедиться, что клиент Microsoft 365 настроен для использования новых возможностей OME, с помощью [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9985f-130">You can verify that your Microsoft 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="9985f-131">[Подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) с помощью учетной записи с разрешениями глобального администратора в клиенте Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9985f-131">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Microsoft 365 tenant.</span></span>

2. <span data-ttu-id="9985f-132">Запустите командлет Get-IRMConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9985f-132">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="9985f-133">Для параметра AzureRMSLicensingEnabled должно быть задано значение $True, указывающее, что в клиенте настроены возможности OME.</span><span class="sxs-lookup"><span data-stu-id="9985f-133">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="9985f-134">В противном случае используйте командлет Set-IRMConfiguration, чтобы задать для параметра AzureRMSLicensingEnabled значение $True и включить OME.</span><span class="sxs-lookup"><span data-stu-id="9985f-134">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="9985f-135">Запустите командлет Test-IRMConfiguration, используя приведенный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9985f-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="9985f-136">**Пример**.</span><span class="sxs-lookup"><span data-stu-id="9985f-136">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="9985f-137">Указывать электронный адрес отправителя необязательно, но это позволит системе выполнить дополнительные проверки.</span><span class="sxs-lookup"><span data-stu-id="9985f-137">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="9985f-138">Используйте электронный адрес любого пользователя в клиенте Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9985f-138">Use the email address of any user in your Microsoft 365 tenant.</span></span>

     <span data-ttu-id="9985f-139">Результаты должны выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="9985f-139">Your results should be similar to:</span></span>

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - <span data-ttu-id="9985f-140">Название вашей организации заменит *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="9985f-140">Your organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="9985f-141">Заданные по умолчанию имена шаблонов могут отличаться от указанных выше.</span><span class="sxs-lookup"><span data-stu-id="9985f-141">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="9985f-142">Дополнительные сведения см. в статье [Настройка шаблонов для Azure Information Protection и управление ими](https://docs.microsoft.com/azure/information-protection/configure-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="9985f-142">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="9985f-143">Выполните командлет Remove-PSSession, чтобы отключиться от службы управления правами.</span><span class="sxs-lookup"><span data-stu-id="9985f-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="9985f-144">Дальнейшие действия: определение правил потока обработки почты для использования новых возможностей OME</span><span class="sxs-lookup"><span data-stu-id="9985f-144">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="9985f-145">Если правила потока обработки почты для шифрования почты в организации уже настроены, то для использования новых возможностей OME их необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="9985f-145">If there are previously configured mail flow rules to encrypt email in your organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="9985f-146">Для выполнения новых развертываний необходимо создать новые правила потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="9985f-146">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9985f-147">Если не обновить существующие правила потока обработки почты, пользователи будут и дальше получать зашифрованные сообщения с вложениями в формате HTML без новых возможностей OME.</span><span class="sxs-lookup"><span data-stu-id="9985f-147">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="9985f-148">Правила потока обработки почты определяют, при каких условиях нужно шифровать электронную почту, а также условия для отмены такого шифрования.</span><span class="sxs-lookup"><span data-stu-id="9985f-148">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="9985f-149">Если задать действие для правила, все сообщения, которые удовлетворяют его условиям, будут шифроваться при отправке.</span><span class="sxs-lookup"><span data-stu-id="9985f-149">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="9985f-150">Дополнительные сведения о создании правил потока обработки почты для OME см. в статье [Определение правил потока обработки почты для шифрования сообщений в Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="9985f-150">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="9985f-151">Чтобы обновить существующие правила и использовать новые возможности OME, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9985f-151">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="9985f-152">В Центре администрирования Microsoft 365 выберите пункты **Центры администрирования > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="9985f-152">In the Microsoft 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="9985f-153">В Центре администрирования Exchange выберите **Поток обработки почты > Правила**.</span><span class="sxs-lookup"><span data-stu-id="9985f-153">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="9985f-154">Повторите представленную ниже процедуру для каждого правила в разделе **Выполнить следующие действия**.</span><span class="sxs-lookup"><span data-stu-id="9985f-154">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="9985f-155">Выберите **Изменить безопасность сообщения**.</span><span class="sxs-lookup"><span data-stu-id="9985f-155">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="9985f-156">Выберите **Применить шифрование сообщений Office 365 и защиту с помощью прав**.</span><span class="sxs-lookup"><span data-stu-id="9985f-156">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="9985f-157">Выберите шаблон RMS из списка.</span><span class="sxs-lookup"><span data-stu-id="9985f-157">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="9985f-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9985f-158">Select **Save**.</span></span>
    - <span data-ttu-id="9985f-159">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9985f-159">Select **OK**.</span></span>
