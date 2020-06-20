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
description: После завершения настройки шифрования сообщений Office 365 (OME) Узнайте, как настроить развертывание несколькими способами.
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815436"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="e20f8-103">Управление шифрованием сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="e20f8-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="e20f8-104">После завершения настройки шифрования сообщений Office 365 (OME) можно настроить конфигурацию развертывания несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="e20f8-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="e20f8-105">Например, можно включить одноразовые коды проходов, отобразить кнопку **шифрования** в Outlook в Интернете и т. д.</span><span class="sxs-lookup"><span data-stu-id="e20f8-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="e20f8-106">Задачи, описанные в этой статье, описывают, как.</span><span class="sxs-lookup"><span data-stu-id="e20f8-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="e20f8-107">Управление тем, могут ли получатели учетной записи Google, Yahoo и Майкрософт использовать эти учетные записи для входа на портал Office 365 для шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="e20f8-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="e20f8-108">Когда вы настраиваете новые возможности шифрования сообщений Office 365, пользователи в организации могут отправлять сообщения получателям, находящимся за пресроком вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e20f8-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="e20f8-109">Если получатель использует *социальные идентификаторы* , такие как учетная запись Google, учетная запись Yahoo или учетная запись Майкрософт, получатель может войти на портал OME с помощью социальных идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="e20f8-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="e20f8-110">При необходимости вы можете запретить получателям использовать социальные идентификаторы для входа на портал OME.</span><span class="sxs-lookup"><span data-stu-id="e20f8-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="e20f8-111">Чтобы управлять тем, могут ли получатели использовать социальные идентификаторы для входа на портал OME</span><span class="sxs-lookup"><span data-stu-id="e20f8-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="e20f8-112">[Подключитесь к Exchange Online с помощью удаленной оболочки PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e20f8-112">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="e20f8-113">Выполните командлет Set – OMEConfiguration с параметром СоЦиалидсигнин следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e20f8-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="e20f8-114">Например, чтобы отключить социальные идентификаторы:</span><span class="sxs-lookup"><span data-stu-id="e20f8-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="e20f8-115">Чтобы включить социальные идентификаторы:</span><span class="sxs-lookup"><span data-stu-id="e20f8-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="e20f8-116">Управление использованием кодов одноразовых проходов для портала шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="e20f8-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="e20f8-117">Если получатель сообщения, зашифрованного с помощью OME, не использует Outlook независимо от учетной записи, используемой получателем, получатель получает ссылку на веб-просмотр в ограниченном времени, которая позволяет читать сообщение.</span><span class="sxs-lookup"><span data-stu-id="e20f8-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="e20f8-118">Эта ссылка включает однократный код этапа.</span><span class="sxs-lookup"><span data-stu-id="e20f8-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="e20f8-119">Как администратор вы можете определить, могут ли получатели использовать коды одноразовых проходов для входа на портал OME.</span><span class="sxs-lookup"><span data-stu-id="e20f8-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="e20f8-120">Управление созданием одноразовых кодов этапа OME</span><span class="sxs-lookup"><span data-stu-id="e20f8-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="e20f8-121">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в Организации, а также запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e20f8-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e20f8-122">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e20f8-122">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e20f8-123">Выполните командлет Set – OMEConfiguration с параметром Отпенаблед:</span><span class="sxs-lookup"><span data-stu-id="e20f8-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="e20f8-124">Например, чтобы отключить однократные коды прохода:</span><span class="sxs-lookup"><span data-stu-id="e20f8-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="e20f8-125">Чтобы включить однократные коды прохода:</span><span class="sxs-lookup"><span data-stu-id="e20f8-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="e20f8-126">Управление отображением кнопки шифрования в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="e20f8-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="e20f8-127">Как администратор, вы можете управлять тем, отображается ли эта кнопка для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e20f8-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="e20f8-128">Управление отображением кнопки "шифровать" в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="e20f8-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="e20f8-129">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в Организации, а также запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e20f8-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e20f8-130">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e20f8-130">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e20f8-131">Выполните командлет Set – IRMConfiguration с параметром – Симплифиедклиентакцессенаблед:</span><span class="sxs-lookup"><span data-stu-id="e20f8-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="e20f8-132">Например, чтобы отключить кнопку " **шифровать** ":</span><span class="sxs-lookup"><span data-stu-id="e20f8-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="e20f8-133">Чтобы включить кнопку " **шифровать** ":</span><span class="sxs-lookup"><span data-stu-id="e20f8-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="e20f8-134">Включение расшифровки сообщений электронной почты на стороне службы для пользователей почтового приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="e20f8-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="e20f8-135">Почтовое приложение iOS не может расшифровывать сообщения, защищенные с помощью шифрования сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="e20f8-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="e20f8-136">Как администратор Microsoft 365, вы можете применять расшифровку на стороне службы для сообщений, доставляемых в почтовое приложение iOS.</span><span class="sxs-lookup"><span data-stu-id="e20f8-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="e20f8-137">Если вы решили использовать расшифровку на стороне службы, служба отправляет расшифрованную копию сообщения на устройство iOS.</span><span class="sxs-lookup"><span data-stu-id="e20f8-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="e20f8-138">Клиентское устройство сохраняет расшифрованную копию сообщения.</span><span class="sxs-lookup"><span data-stu-id="e20f8-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="e20f8-139">Кроме того, в сообщении хранятся сведения о правах на использование, даже если почтовое приложение iOS не применяет к пользователю права на использование на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="e20f8-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="e20f8-140">Пользователь может скопировать или напечатать сообщение, даже если у них изначально нет прав на это.</span><span class="sxs-lookup"><span data-stu-id="e20f8-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="e20f8-141">Тем не менее, если пользователь попытается выполнить действие, требующее наличия почтового сервера Microsoft 365, например переслать сообщение, сервер не будет разрешать действие, если пользователь изначально не имел право на использование.</span><span class="sxs-lookup"><span data-stu-id="e20f8-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="e20f8-142">Тем не менее, конечные пользователи могут обойти ограничение использования "не пересылать", пересылая сообщение из другой учетной записи в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="e20f8-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="e20f8-143">Независимо от того, настроена ли расшифровка почты на стороне службы, вложения в зашифрованные и защищенные правами сообщения не могут быть просмотрены в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="e20f8-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="e20f8-144">Если вы решили не разрешать отправку расшифрованных сообщений пользователям почтовых приложений iOS, пользователи получат сообщение о том, что у них нет прав на просмотр сообщения.</span><span class="sxs-lookup"><span data-stu-id="e20f8-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="e20f8-145">По умолчанию Расшифровка сообщений электронной почты на стороне службы не включена.</span><span class="sxs-lookup"><span data-stu-id="e20f8-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="e20f8-146">Более подробную информацию и представление интерфейса взаимодействия с клиентом можно узнать в статье [Просмотр зашифрованных сообщений на iPhone или iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="e20f8-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="e20f8-147">Управление тем, могут ли пользователи почтового приложения iOS просматривать сообщения, защищенные с помощью шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="e20f8-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="e20f8-148">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в Организации, а также запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e20f8-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e20f8-149">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e20f8-149">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e20f8-150">Выполните командлет Set – Активесинкорганизатионс с параметром Алловрмссуппортфоруненлигхтенедаппс:</span><span class="sxs-lookup"><span data-stu-id="e20f8-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="e20f8-151">Например, чтобы настроить службу для расшифровки сообщений перед их отправкой в приложения уненлигхтенед, такие как почтовое приложение для iOS:</span><span class="sxs-lookup"><span data-stu-id="e20f8-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="e20f8-152">Или, чтобы настроить службу так, чтобы она не отправляла расшифрованные сообщения в приложения уненлигхтенед:</span><span class="sxs-lookup"><span data-stu-id="e20f8-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="e20f8-153">Индивидуальные политики почтовых ящиков (OWA/ActiveSync) переопределяют эти параметры (например, если для параметра-IRMEnabled задано значение false в соответствующей политике почтовых ящиков OWA или политика почтовых ящиков ActiveSync, то эти конфигурации не применяются).</span><span class="sxs-lookup"><span data-stu-id="e20f8-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="e20f8-154">Включение расшифровки вложений электронной почты на стороне службы для почтовых клиентов веб-браузеров</span><span class="sxs-lookup"><span data-stu-id="e20f8-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="e20f8-155">Как правило, при использовании шифрования сообщений Office 365 вложения автоматически шифруются.</span><span class="sxs-lookup"><span data-stu-id="e20f8-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="e20f8-156">Как администратор вы можете применять расшифровку на стороне службы для вложений электронной почты, которые пользователи скачивают из веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="e20f8-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="e20f8-157">При использовании расшифровки на стороне службы Служба отправляет расшифрованную копию файла на устройство.</span><span class="sxs-lookup"><span data-stu-id="e20f8-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="e20f8-158">Сообщение все еще зашифровано.</span><span class="sxs-lookup"><span data-stu-id="e20f8-158">The message is still encrypted.</span></span> <span data-ttu-id="e20f8-159">Вложение электронной почты также хранит сведения о правах на использование, несмотря на то, что браузер не применяет к пользователю права на использование на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="e20f8-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="e20f8-160">Пользователь может копировать или печатать вложение электронной почты, даже если у них изначально нет прав на это.</span><span class="sxs-lookup"><span data-stu-id="e20f8-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="e20f8-161">Тем не менее, если пользователь попытается выполнить действие, требующее наличия почтового сервера Microsoft 365, например переслать вложение, сервер не разрешил действие, если пользователь изначально не имел право на использование.</span><span class="sxs-lookup"><span data-stu-id="e20f8-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="e20f8-162">Независимо от того, настроена ли расшифровка вложений на стороне службы, пользователи не могут просматривать вложения в зашифрованные сообщения и сообщения, защищенные правами, в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="e20f8-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="e20f8-163">Если вы не разрешите расшифровывать вложенные сообщения электронной почты (по умолчанию), пользователи получат сообщение о том, что у них нет прав на просмотр вложения.</span><span class="sxs-lookup"><span data-stu-id="e20f8-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="e20f8-164">Для получения дополнительных сведений о том, как Microsoft 365 внедряет шифрование для сообщений электронной почты и вложений электронной почты с помощью параметра только шифрование, обратитесь к разделу [параметр только шифрование для сообщений](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e20f8-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="e20f8-165">Чтобы управлять расшифровкой вложений электронной почты при загрузке из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="e20f8-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="e20f8-166">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в Организации, а также запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e20f8-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e20f8-167">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e20f8-167">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e20f8-168">Выполните командлет Set – IRMConfiguration с параметром Декриптаттачментфоренкриптонли:</span><span class="sxs-lookup"><span data-stu-id="e20f8-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="e20f8-169">Например, чтобы настроить службу для расшифровки вложений электронной почты, когда пользователь загрузит их из веб-браузера, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e20f8-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="e20f8-170">Чтобы настроить службу для выхода из зашифрованных вложений электронной почты во время загрузки, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e20f8-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="e20f8-171">Убедитесь, что все внешние получатели используют портал OME для чтения зашифрованных сообщений</span><span class="sxs-lookup"><span data-stu-id="e20f8-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="e20f8-172">Вы можете использовать настраиваемые шаблоны фирменного стиля, чтобы заставить получателей получать почтовую почту, которая направляет им возможность читать зашифрованную электронную почту на портале OME, а не использовать Outlook или Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e20f8-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="e20f8-173">Это может потребоваться, если вы хотите лучше контролировать, как получатели используют полученные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e20f8-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="e20f8-174">Например, если внешние получатели просматривают электронную почту на веб-портале, вы можете задать дату истечения срока действия для электронной почты и отозвать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="e20f8-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="e20f8-175">Эти функции поддерживаются только на портале OME.</span><span class="sxs-lookup"><span data-stu-id="e20f8-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="e20f8-176">При создании правил для почтового процесса можно использовать параметр шифрования и параметр "не пересылать".</span><span class="sxs-lookup"><span data-stu-id="e20f8-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="e20f8-177">Использование настраиваемого шаблона для принудительного использования портала OME и шифрования электронной почты всеми внешними получателями</span><span class="sxs-lookup"><span data-stu-id="e20f8-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="e20f8-178">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в Организации, а также запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e20f8-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e20f8-179">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e20f8-179">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e20f8-180">Запустите командлет New – TransportRule:</span><span class="sxs-lookup"><span data-stu-id="e20f8-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="e20f8-181">где:</span><span class="sxs-lookup"><span data-stu-id="e20f8-181">where:</span></span>

   - <span data-ttu-id="e20f8-182">`mail flow rule name`— Это имя, которое вы хотите использовать для нового правила для почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="e20f8-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="e20f8-183">`option name`может иметь значение `Encrypt` или `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="e20f8-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="e20f8-184">`template name`— Это имя, которое вы присвоили настраиваемому шаблону фирменной символики, например `OME Configuration` .</span><span class="sxs-lookup"><span data-stu-id="e20f8-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="e20f8-185">Чтобы зашифровать все внешние сообщения электронной почты с помощью шаблона "Конфигурация OME" и применить параметр "только шифрование":</span><span class="sxs-lookup"><span data-stu-id="e20f8-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="e20f8-186">Чтобы зашифровать все внешние сообщения электронной почты с помощью шаблона "Конфигурация OME" и применить параметр "не пересылать":</span><span class="sxs-lookup"><span data-stu-id="e20f8-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="e20f8-187">Настройка внешнего вида сообщений электронной почты и портала OME</span><span class="sxs-lookup"><span data-stu-id="e20f8-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="e20f8-188">Подробные сведения о том, как настроить OME для вашей организации, можно найти [в статье Добавление фирменной символики вашей организации в зашифрованные сообщения](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e20f8-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="e20f8-189">Отключение новых возможностей для OME</span><span class="sxs-lookup"><span data-stu-id="e20f8-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="e20f8-190">Мы надеемся, что она не поступила, но если вам необходимо отключить новые возможности для OME, очень просто.</span><span class="sxs-lookup"><span data-stu-id="e20f8-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="e20f8-191">Сначала необходимо удалить все созданные вами правила для процесса обработки почты, в которых используются новые возможности OME.</span><span class="sxs-lookup"><span data-stu-id="e20f8-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="e20f8-192">Сведения об удалении правил для процесса обработки почты приведены в разделе [Управление правилами](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)обработки почты.</span><span class="sxs-lookup"><span data-stu-id="e20f8-192">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="e20f8-193">Затем выполните указанные ниже действия в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e20f8-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="e20f8-194">Отключение новых возможностей для OME</span><span class="sxs-lookup"><span data-stu-id="e20f8-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="e20f8-195">С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в Организации запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e20f8-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e20f8-196">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e20f8-196">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e20f8-197">Если вы включили кнопку **шифровать** в Outlook в Интернете, отключите ее, выполнив командлет Set-IRMConfiguration с параметром симплифиедклиентакцессенаблед.</span><span class="sxs-lookup"><span data-stu-id="e20f8-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="e20f8-198">В противном случае пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="e20f8-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="e20f8-199">Отключите новые возможности для OME, выполнив командлет Set – IRMConfiguration с параметром Азурермслиценсинженаблед, равным false:</span><span class="sxs-lookup"><span data-stu-id="e20f8-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
