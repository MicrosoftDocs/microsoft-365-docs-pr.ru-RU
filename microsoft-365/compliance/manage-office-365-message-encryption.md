---
title: Управление шифрованием сообщений Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: После завершения настройки шифрования сообщений Office 365 (OME) узнайте, как настроить развертывание несколькими способами.
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815436"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="871a0-103">Управление шифрованием сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="871a0-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="871a0-104">После завершения настройки шифрования сообщений Office 365 (OME) можно настроить конфигурацию развертывания несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="871a0-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="871a0-105">Например, можно настроить, следует ли включить одноветные  коды прохода, отобразить кнопку "Зашифровать" в Outlook в Интернете и многого другого.</span><span class="sxs-lookup"><span data-stu-id="871a0-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="871a0-106">В этой статье описано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="871a0-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="871a0-107">Управляйте тем, могут ли получатели учетных записей Google, Yahoo и Microsoft использовать эти учетные записи для входов на портал шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="871a0-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="871a0-108">При настройках новых возможностей шифрования сообщений Office 365 пользователи в организации могут отправлять сообщения получателям, которые находятся за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="871a0-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="871a0-109">Если получатель  использует социальный ИД, например учетную запись Google, учетную запись Yahoo или учетную запись Майкрософт, получатель может войти на портал OME с помощью социального ИД.</span><span class="sxs-lookup"><span data-stu-id="871a0-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="871a0-110">При этом можно разрешить получателям использовать социальные ID для входов на портал OME.</span><span class="sxs-lookup"><span data-stu-id="871a0-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="871a0-111">Управление возможностью получателей использовать социальные ID для входов на портал OME</span><span class="sxs-lookup"><span data-stu-id="871a0-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="871a0-112">[Подключение к Exchange Online с помощью удаленной powerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="871a0-112">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="871a0-113">Выполните Set-OMEConfiguration с параметром SocialIdSignIn следующим образом:</span><span class="sxs-lookup"><span data-stu-id="871a0-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="871a0-114">Например, чтобы отключить социальные ИД:</span><span class="sxs-lookup"><span data-stu-id="871a0-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="871a0-115">Чтобы включить социальные ИД:</span><span class="sxs-lookup"><span data-stu-id="871a0-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="871a0-116">Управление использованием разных кодов прохода для портала шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="871a0-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="871a0-117">Если получатель сообщения, зашифрованного с помощью OME, не использует Outlook, независимо от учетной записи, используемой получателем, получатель получает ограниченную ссылку на веб-представление, которая позволяет ему прочитать сообщение.</span><span class="sxs-lookup"><span data-stu-id="871a0-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="871a0-118">Эта ссылка включает одноветный код прохода.</span><span class="sxs-lookup"><span data-stu-id="871a0-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="871a0-119">Как администратор вы можете решить, могут ли получатели использовать однонаправленные коды для входов на портал OME.</span><span class="sxs-lookup"><span data-stu-id="871a0-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="871a0-120">Управление созданием OME одновейных кодов прохода</span><span class="sxs-lookup"><span data-stu-id="871a0-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="871a0-121">Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="871a0-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="871a0-122">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="871a0-122">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="871a0-123">Запустите Set-OMEConfiguration с параметром OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="871a0-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="871a0-124">Например, чтобы отключить разовые коды проходов:</span><span class="sxs-lookup"><span data-stu-id="871a0-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="871a0-125">Чтобы включить разовые коды прохода:</span><span class="sxs-lookup"><span data-stu-id="871a0-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="871a0-126">Управление отображением кнопки "Зашифровать" в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="871a0-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="871a0-127">Администратор может управлять отображением этой кнопки для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="871a0-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="871a0-128">Управление тем, отображается ли кнопка "Зашифровать" в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="871a0-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="871a0-129">Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="871a0-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="871a0-130">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="871a0-130">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="871a0-131">Запустите Set-IRMConfiguration с параметром -SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="871a0-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="871a0-132">Например, чтобы отключить кнопку **"Зашифровать":**</span><span class="sxs-lookup"><span data-stu-id="871a0-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="871a0-133">Чтобы включить **кнопку "Зашифровать":**</span><span class="sxs-lookup"><span data-stu-id="871a0-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="871a0-134">Включить расшифровку сообщений электронной почты на стороне службы для пользователей почтовых приложений iOS</span><span class="sxs-lookup"><span data-stu-id="871a0-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="871a0-135">Почтовое приложение iOS не может расшифровывать сообщения, защищенные с помощью шифрования сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="871a0-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="871a0-136">Как администратор Microsoft 365 вы можете применять расшифровку на стороне службы для сообщений, доставленных в почтовое приложение iOS.</span><span class="sxs-lookup"><span data-stu-id="871a0-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="871a0-137">При использовании расшифровки на стороне службы служба отправляет расшифрованную копию сообщения на устройство iOS.</span><span class="sxs-lookup"><span data-stu-id="871a0-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="871a0-138">На клиентских устройствах хранится расшифрованная копия сообщения.</span><span class="sxs-lookup"><span data-stu-id="871a0-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="871a0-139">В сообщении также сохраняются сведения о правах на использование, даже если почтовое приложение iOS не применяет клиентские права на использование к пользователю.</span><span class="sxs-lookup"><span data-stu-id="871a0-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="871a0-140">Пользователь может копировать или печатать сообщение, даже если у него изначально нет прав на это.</span><span class="sxs-lookup"><span data-stu-id="871a0-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="871a0-141">Однако если пользователь по пытается выполнить действие, которое требует на сервере почты Microsoft 365, например пересылать сообщение, сервер не позволит выполнить это действие, если пользователь изначально не имеет права на использование.</span><span class="sxs-lookup"><span data-stu-id="871a0-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="871a0-142">Тем не менее конечные пользователи могут обойти ограничение использования "Не пересылать", перена пересылая сообщение из другой учетной записи в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="871a0-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="871a0-143">Независимо от того, настроена ли расшифровка почты на стороне службы, вложения для зашифрованной и защищенной правами почты не могут просматриваться в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="871a0-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="871a0-144">Если вы не разрешаете отправлять расшифрованные сообщения пользователям почтового приложения iOS, пользователи получают сообщение о том, что у них нет прав на просмотр сообщения.</span><span class="sxs-lookup"><span data-stu-id="871a0-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="871a0-145">По умолчанию расшифровка сообщений электронной почты на стороне службы не включена.</span><span class="sxs-lookup"><span data-stu-id="871a0-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="871a0-146">Дополнительные сведения и сведения о клиенте см. в сообщении, зашифрованном на [iPhone или iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)</span><span class="sxs-lookup"><span data-stu-id="871a0-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="871a0-147">Управление возможностью просмотра сообщений, защищенных с помощью шифрования сообщений Office 365, для пользователей почтового приложения iOS</span><span class="sxs-lookup"><span data-stu-id="871a0-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="871a0-148">Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="871a0-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="871a0-149">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="871a0-149">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="871a0-150">Запустите Set-ActiveSyncOrganizations с параметром AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="871a0-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="871a0-151">Например, чтобы настроить службу для расшифровки сообщений, прежде чем они будут отправлены неподтвершенным приложениям, например почтовому приложению iOS:</span><span class="sxs-lookup"><span data-stu-id="871a0-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="871a0-152">Или, чтобы служба не отправлять расшифрованные сообщения в неподслужимые приложения:</span><span class="sxs-lookup"><span data-stu-id="871a0-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="871a0-153">Отдельные политики почтовых ящиков (OWA/ActiveSync) переопрепреют эти параметры (т. е. если для параметра -IRMEnabled задано false в соответствующей политике почтовых ящиков OWA или политике почтовых ящиков ActiveSync, эти конфигурации не будут применяться).</span><span class="sxs-lookup"><span data-stu-id="871a0-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="871a0-154">Включить расшифровку вложений электронной почты на стороне службы для почтовых клиентов веб-браузера</span><span class="sxs-lookup"><span data-stu-id="871a0-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="871a0-155">Обычно при использовании шифрования сообщений Office 365 вложения шифруются автоматически.</span><span class="sxs-lookup"><span data-stu-id="871a0-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="871a0-156">Как администратор вы можете применять расшифровку на стороне службы к вложениям электронной почты, скачиваемых пользователями из веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="871a0-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="871a0-157">При использовании расшифровки на стороне службы служба отправляет расшифрованную копию файла на устройство.</span><span class="sxs-lookup"><span data-stu-id="871a0-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="871a0-158">Сообщение по-прежнему зашифровано.</span><span class="sxs-lookup"><span data-stu-id="871a0-158">The message is still encrypted.</span></span> <span data-ttu-id="871a0-159">Вложение электронной почты также хранит сведения о правах на использование, даже если браузер не применяет к пользователю права на использование на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="871a0-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="871a0-160">Пользователь может копировать или печатать вложение электронной почты, даже если у него изначально нет прав на это.</span><span class="sxs-lookup"><span data-stu-id="871a0-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="871a0-161">Однако если пользователь попытается выполнить действие, которое требует от почтового сервера Microsoft 365, например пересылать вложение, сервер не позволит выполнить это действие, если пользователь изначально не имеет права на использование.</span><span class="sxs-lookup"><span data-stu-id="871a0-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="871a0-162">Независимо от того, настроена ли расшифровка вложений на стороне службы, пользователи не могут просматривать вложения для зашифрованной и защищенной правами почты в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="871a0-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="871a0-163">Если вы не разрешаете расшифровывать вложения электронной почты (это значение по умолчанию), пользователи получают сообщение о том, что у них нет прав на просмотр вложения.</span><span class="sxs-lookup"><span data-stu-id="871a0-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="871a0-164">Дополнительные сведения о том, как Microsoft 365 реализует шифрование для сообщений электронной почты и вложений с помощью параметра Encrypt-Only, см. в параметре "Только шифрование" для сообщений [электронной почты.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="871a0-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="871a0-165">Управление расшифровкой вложений электронной почты при загрузке из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="871a0-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="871a0-166">Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="871a0-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="871a0-167">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="871a0-167">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="871a0-168">Запустите Set-IRMConfiguration с параметром DecryptAttachmentForEncryptOnly:</span><span class="sxs-lookup"><span data-stu-id="871a0-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="871a0-169">Например, чтобы настроить службу для расшифровки вложений электронной почты, когда пользователь загружает их из веб-браузера:</span><span class="sxs-lookup"><span data-stu-id="871a0-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="871a0-170">Чтобы настроить службу на то, чтобы оставить зашифрованные вложения электронной почты после загрузки:</span><span class="sxs-lookup"><span data-stu-id="871a0-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="871a0-171">Убедитесь, что все внешние получатели используют портал OME для чтения зашифрованной почты</span><span class="sxs-lookup"><span data-stu-id="871a0-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="871a0-172">Вы можете использовать настраиваемые шаблоны фирменения, чтобы заставить получателей получать сообщения-оболочки, которые поосят их на чтение зашифрованной электронной почты на портале OME, а не с помощью Outlook или Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="871a0-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="871a0-173">Это может потребоваться, если вы хотите больше контролировать, как получатели используют почту, которая они получают.</span><span class="sxs-lookup"><span data-stu-id="871a0-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="871a0-174">Например, если внешние получатели просматривают электронную почту на веб-портале, вы можете установить дату окончания срока действия сообщения и отоискить сообщение.</span><span class="sxs-lookup"><span data-stu-id="871a0-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="871a0-175">Эти функции поддерживаются только на портале OME.</span><span class="sxs-lookup"><span data-stu-id="871a0-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="871a0-176">При создании правил потока почты можно использовать параметры "Шифровать" и "Не пересылать".</span><span class="sxs-lookup"><span data-stu-id="871a0-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="871a0-177">Использование пользовательского шаблона для принудительного использования всеми внешними получателями портала OME и зашифрованной электронной почты</span><span class="sxs-lookup"><span data-stu-id="871a0-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="871a0-178">Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="871a0-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="871a0-179">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="871a0-179">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="871a0-180">Запустите New-TransportRule управления:</span><span class="sxs-lookup"><span data-stu-id="871a0-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="871a0-181">где:</span><span class="sxs-lookup"><span data-stu-id="871a0-181">where:</span></span>

   - <span data-ttu-id="871a0-182">`mail flow rule name` это имя, которое вы хотите использовать для нового правила потока почты.</span><span class="sxs-lookup"><span data-stu-id="871a0-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="871a0-183">`option name` is either `Encrypt` or `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="871a0-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="871a0-184">`template name` это имя, которое вы предоставили пользовательскому шаблону фирменой настройки, например `OME Configuration` .</span><span class="sxs-lookup"><span data-stu-id="871a0-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="871a0-185">Чтобы зашифровать все внешние сообщения электронной почты с помощью шаблона "Конфигурация OME" и применить Encrypt-Only параметр:</span><span class="sxs-lookup"><span data-stu-id="871a0-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="871a0-186">Чтобы зашифровать все внешние сообщения электронной почты с помощью шаблона "Конфигурация OME" и применить параметр "Не переадружайте":</span><span class="sxs-lookup"><span data-stu-id="871a0-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="871a0-187">Настройка внешнего вида сообщений электронной почты и портала OME</span><span class="sxs-lookup"><span data-stu-id="871a0-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="871a0-188">Дополнительные сведения о настройке OME для организации см. в описании добавления фирменного параметра организации в [зашифрованные сообщения.](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="871a0-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="871a0-189">Отключение новых возможностей OME</span><span class="sxs-lookup"><span data-stu-id="871a0-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="871a0-190">Надеемся, что это не так, но при необходимости отключить новые возможности для OME очень просто.</span><span class="sxs-lookup"><span data-stu-id="871a0-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="871a0-191">Сначала необходимо удалить все созданные правила потока почты, которые используют новые возможности OME.</span><span class="sxs-lookup"><span data-stu-id="871a0-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="871a0-192">Сведения об удалении правил потока почты см. в под [управлением правил потока почты.](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="871a0-192">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="871a0-193">Затем выполните эти действия в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="871a0-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="871a0-194">Отключение новых возможностей OME</span><span class="sxs-lookup"><span data-stu-id="871a0-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="871a0-195">Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, Windows PowerShell сеанс и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="871a0-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="871a0-196">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="871a0-196">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="871a0-197">Если вы  включили кнопку "Зашифровать" в Outlook в Интернете, отключили ее, задав Set-IRMConfiguration с параметром SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="871a0-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="871a0-198">В противном случае пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="871a0-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="871a0-199">Отключив новые возможности OME, задав для параметра AzureRMSLicensingEnabled Set-IRMConfiguration параметру false:</span><span class="sxs-lookup"><span data-stu-id="871a0-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
