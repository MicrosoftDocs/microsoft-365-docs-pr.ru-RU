---
title: Управление шифрованием сообщений Office 365
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
description: После завершения настройки шифрования сообщений Office 365 (OME) можно настроить конфигурацию развертывания несколькими способами. Например, вы можете включить одноразовые коды проходов, отобразить кнопку Защита в Outlook в Интернете и многое другое. Задачи, описанные в этой статье, описывают, как.
ms.openlocfilehash: 5e087211ec72c9cc37896a9a48cc01ce3c1a8d07
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090386"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="e2cf3-105">Управление шифрованием сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="e2cf3-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="e2cf3-106">После завершения настройки шифрования сообщений Office 365 (OME) можно настроить конфигурацию развертывания несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="e2cf3-107">Например, можно включить одноразовые коды проходов, отобразить кнопку **шифрования** в Outlook в Интернете и т. д.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-107">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="e2cf3-108">Задачи, описанные в этой статье, описывают, как.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="e2cf3-109">Управление тем, могут ли получатели учетной записи Google, Yahoo и Майкрософт использовать эти учетные записи для входа на портал Office 365 для шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="e2cf3-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="e2cf3-110">Когда вы настраиваете новые возможности шифрования сообщений Office 365, пользователи в организации могут отправлять сообщения получателям, находящимся за пресроком вашей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="e2cf3-111">Если получатель использует *социальные идентификаторы* , такие как учетная запись Google, учетная запись Yahoo или учетная запись Майкрософт, получатель может войти на портал OME с помощью социальных идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="e2cf3-112">При необходимости вы можете запретить получателям использовать социальные идентификаторы для входа на портал OME.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="e2cf3-113">Чтобы управлять тем, могут ли получатели использовать социальные идентификаторы для входа на портал OME</span><span class="sxs-lookup"><span data-stu-id="e2cf3-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="e2cf3-114">[Подключитесь к Exchange Online с помощью удаленной оболочки PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-114">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="e2cf3-115">Выполните командлет Set – OMEConfiguration с параметром СоЦиалидсигнин следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="e2cf3-116">Например, чтобы отключить социальные идентификаторы:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="e2cf3-117">Чтобы включить социальные идентификаторы:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="e2cf3-118">Управление использованием кодов одноразовых проходов для портала шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="e2cf3-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="e2cf3-119">Если получатель сообщения, зашифрованного с помощью OME, не использует Outlook независимо от учетной записи, используемой получателем, получатель получает ссылку на веб-просмотр в ограниченном времени, которая позволяет читать сообщение.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="e2cf3-120">Эта ссылка включает однократный код этапа.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="e2cf3-121">Как администратор вы можете определить, могут ли получатели использовать коды одноразовых проходов для входа на портал OME.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="e2cf3-122">Управление созданием одноразовых кодов этапа OME</span><span class="sxs-lookup"><span data-stu-id="e2cf3-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="e2cf3-123">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e2cf3-124">Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e2cf3-125">Выполните командлет Set – OMEConfiguration с параметром Отпенаблед:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="e2cf3-126">Например, чтобы отключить однократные коды прохода:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="e2cf3-127">Чтобы включить однократные коды прохода:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="e2cf3-128">Управление отображением кнопки шифрования в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="e2cf3-128">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="e2cf3-129">Как администратор, вы можете управлять тем, отображается ли эта кнопка для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-129">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="e2cf3-130">Управление отображением кнопки "шифровать" в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="e2cf3-130">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="e2cf3-131">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-131">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e2cf3-132">Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e2cf3-133">Выполните командлет Set – IRMConfiguration с параметром – Симплифиедклиентакцессенаблед:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-133">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="e2cf3-134">Например, чтобы отключить кнопку " **шифровать** ":</span><span class="sxs-lookup"><span data-stu-id="e2cf3-134">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="e2cf3-135">Чтобы включить кнопку " **шифровать** ":</span><span class="sxs-lookup"><span data-stu-id="e2cf3-135">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="e2cf3-136">Включение расшифровки сообщений электронной почты на стороне службы для пользователей почтового приложения для iOS</span><span class="sxs-lookup"><span data-stu-id="e2cf3-136">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="e2cf3-137">Почтовое приложение iOS не может расшифровывать сообщения, защищенные с помощью шифрования сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-137">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="e2cf3-138">Как администратор Office 365, вы можете применять расшифровку на стороне службы для сообщений, доставляемых в почтовое приложение iOS.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-138">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="e2cf3-139">Если вы решили использовать расшифровку на стороне службы, служба отправляет расшифрованную копию сообщения на устройство iOS.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-139">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="e2cf3-140">Клиентское устройство сохраняет расшифрованную копию сообщения.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-140">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="e2cf3-141">Кроме того, в сообщении хранятся сведения о правах на использование, даже если почтовое приложение iOS не применяет к пользователю права на использование на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-141">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="e2cf3-142">Пользователь может скопировать или напечатать сообщение, даже если у них изначально нет прав на это.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-142">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="e2cf3-143">Тем не менее, если пользователь попытается выполнить действие, требующее наличия почтового сервера Office 365, например переслать сообщение, сервер не разрешил действие, если пользователь изначально не имел право на использование.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-143">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="e2cf3-144">Тем не менее, конечные пользователи могут обойти ограничение использования "не пересылать", пересылая сообщение из другой учетной записи в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-144">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="e2cf3-145">Независимо от того, настроена ли расшифровка почты на стороне службы, вложения в зашифрованные и защищенные правами сообщения не могут быть просмотрены в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-145">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="e2cf3-146">Если вы решили не разрешать отправку расшифрованных сообщений пользователям почтовых приложений iOS, пользователи получат сообщение о том, что у них нет прав на просмотр сообщения.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-146">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="e2cf3-147">По умолчанию Расшифровка сообщений электронной почты на стороне службы не включена.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-147">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="e2cf3-148">Более подробную информацию и представление интерфейса взаимодействия с клиентом можно узнать в статье [Просмотр зашифрованных сообщений на iPhone или iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-148">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="e2cf3-149">Управление тем, могут ли пользователи почтового приложения iOS просматривать сообщения, защищенные с помощью шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="e2cf3-149">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="e2cf3-150">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-150">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e2cf3-151">Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-151">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e2cf3-152">Выполните командлет Set – Активесинкорганизатионс с параметром Алловрмссуппортфоруненлигхтенедаппс:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-152">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="e2cf3-153">Например, чтобы настроить службу для расшифровки сообщений перед их отправкой в приложения уненлигхтенед, такие как почтовое приложение для iOS:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-153">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="e2cf3-154">Или, чтобы настроить службу так, чтобы она не отправляла расшифрованные сообщения в приложения уненлигхтенед:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-154">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="e2cf3-155">Индивидуальные политики почтовых ящиков (OWA/ActiveSync) переопределяют эти параметры (например, если для параметра-IRMEnabled задано значение false в соответствующей политике почтовых ящиков OWA или политика почтовых ящиков ActiveSync, то эти конфигурации не применяются).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-155">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="e2cf3-156">Включение расшифровки вложений электронной почты на стороне службы для почтовых клиентов веб-браузеров</span><span class="sxs-lookup"><span data-stu-id="e2cf3-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="e2cf3-157">Как правило, при использовании шифрования сообщений Office 365 вложения автоматически шифруются.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="e2cf3-158">Как администратор Office 365, вы можете применять расшифровку на стороне службы для вложений электронной почты, которые пользователи скачивают из веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="e2cf3-159">При использовании расшифровки на стороне службы Служба отправляет расшифрованную копию файла на устройство.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="e2cf3-160">Сообщение все еще зашифровано.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-160">The message is still encrypted.</span></span> <span data-ttu-id="e2cf3-161">Вложение электронной почты также хранит сведения о правах на использование, несмотря на то, что браузер не применяет к пользователю права на использование на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="e2cf3-162">Пользователь может копировать или печатать вложение электронной почты, даже если у них изначально нет прав на это.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="e2cf3-163">Тем не менее, если пользователь попытается выполнить действие, требующее наличия почтового сервера Office 365, например переслать вложение, сервер не разрешил действие, если пользователь изначально не имел право на использование.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="e2cf3-164">Независимо от того, настроена ли расшифровка вложений на стороне службы, пользователи не могут просматривать вложения в зашифрованные сообщения и сообщения, защищенные правами, в почтовом приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="e2cf3-165">Если вы не разрешите расшифровывать вложенные сообщения электронной почты (по умолчанию), пользователи получат сообщение о том, что у них нет прав на просмотр вложения.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="e2cf3-166">Для получения дополнительных сведений о том, как Office 365 внедряет шифрование для сообщений электронной почты и вложений электронной почты с помощью параметра только шифрование, в разделе только [шифрование для сообщений](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="e2cf3-167">Чтобы управлять расшифровкой вложений электронной почты при загрузке из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="e2cf3-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="e2cf3-168">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e2cf3-169">Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e2cf3-170">Выполните командлет Set – IRMConfiguration с параметром Декриптаттачментфромпортал:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="e2cf3-171">Например, чтобы настроить службу для расшифровки вложений электронной почты, когда пользователь загрузит их из веб-браузера, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="e2cf3-172">Чтобы настроить службу для выхода из зашифрованных вложений электронной почты во время загрузки, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a><span data-ttu-id="e2cf3-173">Убедитесь, что все внешние получатели используют портал OME для чтения шифрованной почты — только расширенное шифрование сообщений в Office 365</span><span class="sxs-lookup"><span data-stu-id="e2cf3-173">Ensure all external recipients use the OME Portal to read encrypted mail — Office 365 Advanced Message Encryption only</span></span>

<span data-ttu-id="e2cf3-174">Если вы используете расширенное шифрование сообщений Office 365, вы можете использовать настраиваемые шаблоны фирменной символики, чтобы заставить получателей получать почтовую почту, которая направляет им возможность читать зашифрованную электронную почту на портале OME, а не использовать Outlook или Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-174">If you have Office 365 Advanced Message Encryption, you can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="e2cf3-175">Это может потребоваться, если вы хотите лучше контролировать, как получатели используют полученные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="e2cf3-176">Например, если внешние получатели просматривают электронную почту на веб-портале, вы можете задать дату истечения срока действия для электронной почты и отозвать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="e2cf3-177">Эти функции поддерживаются только на портале OME.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="e2cf3-178">При создании правил для почтового процесса можно использовать параметр шифрования и параметр "не пересылать".</span><span class="sxs-lookup"><span data-stu-id="e2cf3-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a><span data-ttu-id="e2cf3-179">Создание настраиваемого шаблона для принудительного использования портала OME всеми внешними получателями, а для шифрования электронной почты — ревокабле и истечения срока действия в течение 7 дней</span><span class="sxs-lookup"><span data-stu-id="e2cf3-179">Create a custom template to force all external recipients to use the OME Portal and for encrypted email to be revocable and expire in 7 days</span></span>

1. <span data-ttu-id="e2cf3-180">Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e2cf3-181">Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e2cf3-182">Запустите командлет New – OMEConfiguration:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-182">Run the New-OMEConfiguration cmdlet:</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   <span data-ttu-id="e2cf3-183">где `template name` — это имя, которое вы хотите использовать для шаблона настраиваемого фирменного стиля Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-183">where `template name` is the name you want to use for the Office 365 Message Encryption custom branding template.</span></span> <span data-ttu-id="e2cf3-184">For example,</span><span class="sxs-lookup"><span data-stu-id="e2cf3-184">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. <span data-ttu-id="e2cf3-185">Запустите командлет New – TransportRule:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-185">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="e2cf3-186">где:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-186">where:</span></span>

   - <span data-ttu-id="e2cf3-187">`mail flow rule name`— Это имя, которое вы хотите использовать для нового правила для почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-187">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="e2cf3-188">`option name`может иметь `Encrypt` значение `Do Not Forward`или.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-188">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="e2cf3-189">`template name`— Это имя, которое вы присвоили настраиваемому шаблону фирменной символики, например `One week expiration`.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-189">`template name` is the name you gave the custom branding template, for example `One week expiration`.</span></span>

   <span data-ttu-id="e2cf3-190">Чтобы зашифровать все внешние сообщения с помощью шаблона "срок действия одной недели" и применить параметр только шифрование:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-190">To encrypt all external email with the "One week expiration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   <span data-ttu-id="e2cf3-191">Чтобы зашифровать все внешние сообщения с помощью шаблона "срок действия одной недели" и применить параметр "не пересылать":</span><span class="sxs-lookup"><span data-stu-id="e2cf3-191">To encrypt all external email with the "One week expiration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="e2cf3-192">Настройка внешнего вида сообщений электронной почты и портала OME</span><span class="sxs-lookup"><span data-stu-id="e2cf3-192">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="e2cf3-193">Подробные сведения о том, как настроить OME для вашей организации, можно найти [в статье Добавление фирменной символики вашей организации в зашифрованные сообщения](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-193">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="e2cf3-194">Отключение новых возможностей для OME</span><span class="sxs-lookup"><span data-stu-id="e2cf3-194">Disable the new capabilities for OME</span></span>

<span data-ttu-id="e2cf3-195">Мы надеемся, что она не поступила, но если вам необходимо отключить новые возможности для OME, очень просто.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-195">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="e2cf3-196">Сначала необходимо удалить все созданные вами правила для процесса обработки почты, в которых используются новые возможности OME.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-196">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="e2cf3-197">Сведения об удалении правил для процесса обработки почты приведены в разделе [Управление правилами](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)обработки почты.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-197">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="e2cf3-198">Затем выполните указанные ниже действия в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-198">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="e2cf3-199">Отключение новых возможностей для OME</span><span class="sxs-lookup"><span data-stu-id="e2cf3-199">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="e2cf3-200">С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-200">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e2cf3-201">Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="e2cf3-201">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="e2cf3-202">Если вы включили кнопку **шифровать** в Outlook в Интернете, отключите ее, выполнив командлет Set-IRMConfiguration с параметром симплифиедклиентакцессенаблед.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-202">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="e2cf3-203">В противном случае пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="e2cf3-203">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="e2cf3-204">Отключите новые возможности для OME, выполнив командлет Set – IRMConfiguration с параметром Азурермслиценсинженаблед, равным false:</span><span class="sxs-lookup"><span data-stu-id="e2cf3-204">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
