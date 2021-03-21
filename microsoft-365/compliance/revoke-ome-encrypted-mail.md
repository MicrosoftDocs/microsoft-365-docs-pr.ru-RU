---
title: Отзовет электронную почту, шифруемую с помощью предварительного шифрования сообщений
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Как администратор и отправитель сообщений можно отослать некоторые сообщения, зашифрованные с помощью шифрования расширенных сообщений Office 365.
ms.openlocfilehash: b49915b6ef72d366a4b2718319150d2d5b640b9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917201"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="d683c-103">Отзовет электронную почту, шифруемую с помощью предварительного шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="d683c-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="d683c-104">Отзыв электронной почты предлагается в рамках предварительного шифрования сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="d683c-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="d683c-105">Шифрование расширенных сообщений Office 365 включено в [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (некоммерческие цены на персонал), Office 365 Enterprise E5 (некоммерческие цены на персонал) и Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="d683c-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="d683c-106">Если в вашей организации есть подписка, не включаемая шифрование расширенных сообщений Office 365, ее можно приобрести с помощью надстройки microsoft 365 E5 Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (некоммерческие цены персонала) или надстройки Office 365 Advanced Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (некоммерческие цены персонала) или Office 365 SKUS.</span><span class="sxs-lookup"><span data-stu-id="d683c-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="d683c-107">Эта статья является частью более крупной серии статей о [шифровании сообщений Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="d683c-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="d683c-108">Если сообщение было зашифровано с помощью шифрования расширенных сообщений Office 365, а вы администратор Microsoft 365 или отправитель сообщения, вы можете отослать сообщение при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="d683c-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="d683c-109">Администраторы отзовет сообщения с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d683c-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="d683c-110">Отправитель отзовет сообщение, отправленное непосредственно из Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d683c-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="d683c-111">В этой статье описываются обстоятельства, при которых возможно отозов, и как это сделать.</span><span class="sxs-lookup"><span data-stu-id="d683c-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="d683c-112">Зашифрованные сообщения электронной почты, которые можно отоискить</span><span class="sxs-lookup"><span data-stu-id="d683c-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="d683c-113">Администраторы и отправители сообщений могут отослать зашифрованные сообщения, если получатель получил зашифрованную электронную почту на основе ссылок.</span><span class="sxs-lookup"><span data-stu-id="d683c-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="d683c-114">Если получатель получил родной inline-опыт в поддерживаемом клиенте Outlook, вы не можете отоискить сообщение.</span><span class="sxs-lookup"><span data-stu-id="d683c-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="d683c-115">Независимо от того, получает ли получатель доступ к ссылке или имеется ли он, зависит от типа удостоверения получателя: получатели учетных записей Office 365 и Microsoft (например, outlook.com пользователей) получают доступ в поддерживаемых клиентах Outlook.</span><span class="sxs-lookup"><span data-stu-id="d683c-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="d683c-116">Все другие типы получателей, такие как получатели Gmail и Yahoo, получают ссылку.</span><span class="sxs-lookup"><span data-stu-id="d683c-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="d683c-117">Администраторы и отправители сообщений могут отослать зашифрованные сообщения с помощью шифрования, примененного непосредственно из Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d683c-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="d683c-118">Например, сообщения, зашифрованные с помощью параметра Шифровать только.</span><span class="sxs-lookup"><span data-stu-id="d683c-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Снимок экрана, показывающий параметр Шифровать только в Outlook в Интернете.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="d683c-120">Опыт получателей для отозванных зашифрованных сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="d683c-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="d683c-121">После отзыва электронной почты получатель получает ошибку при доступе к зашифрованной электронной почте через портал шифрования сообщений Office 365: "Сообщение было отозвано отправильщиком".</span><span class="sxs-lookup"><span data-stu-id="d683c-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Снимок экрана, на который показан отозванный зашифрованный адрес электронной почты.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="d683c-123">Как отоскить зашифрованное сообщение, отправленное</span><span class="sxs-lookup"><span data-stu-id="d683c-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="d683c-124">Вы можете отоискить почту, отправленную одному получателю, использующему социальную учетную запись, например gmail.com или yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="d683c-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="d683c-125">Другими словами, вы можете отоискить сообщение электронной почты, отправленное одному получателю, который получил ссылку.</span><span class="sxs-lookup"><span data-stu-id="d683c-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="d683c-126">Нельзя отоискить почту, отправленную получателю, использующему учетную запись в Office 365 или Microsoft 365 или пользователю, использующему учетную запись Майкрософт, например outlook.com учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d683c-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="d683c-127">Чтобы отоискить отправленное зашифрованное сообщение, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="d683c-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="d683c-128">В Outlook в Интернете в папке **Отправлено** просматривайте сообщение, которое необходимо отооперить.</span><span class="sxs-lookup"><span data-stu-id="d683c-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="d683c-129">Если почта отменяется, в верхней части сообщения вы увидите ссылку "Удаление внешнего доступа".</span><span class="sxs-lookup"><span data-stu-id="d683c-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Снимок экрана, показывающий зашифрованную почту, которую необходимо отоискить в Outlook в Интернете.":::

2. <span data-ttu-id="d683c-131">Нажмите **кнопку Удалить внешний доступ** для отзова сообщения.</span><span class="sxs-lookup"><span data-stu-id="d683c-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="d683c-132">В сообщении показано, что его состояние отозвано.</span><span class="sxs-lookup"><span data-stu-id="d683c-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Снимок экрана, показывающий отозванное зашифрованное сообщение в Outlook в Интернете.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="d683c-134">Как отоскить зашифрованное сообщение в качестве администратора</span><span class="sxs-lookup"><span data-stu-id="d683c-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="d683c-135">Администраторы Microsoft 365 следуют этим общим шагам, чтобы отоиметь доступную зашифрованную электронную почту:</span><span class="sxs-lookup"><span data-stu-id="d683c-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="d683c-136">Получите ID сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d683c-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="d683c-137">Убедитесь, что вы можете отоокить сообщение.</span><span class="sxs-lookup"><span data-stu-id="d683c-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="d683c-138">Отзови почту.</span><span class="sxs-lookup"><span data-stu-id="d683c-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="d683c-139">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="d683c-139">Step 1.</span></span> <span data-ttu-id="d683c-140">Получение ID сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="d683c-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="d683c-141">Прежде чем отоискить зашифрованную почту, соберем код сообщения.</span><span class="sxs-lookup"><span data-stu-id="d683c-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="d683c-142">MessageId обычно имеет формат:</span><span class="sxs-lookup"><span data-stu-id="d683c-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="d683c-143">Существует несколько способов поиска ID сообщения электронной почты, отозоваемой.</span><span class="sxs-lookup"><span data-stu-id="d683c-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="d683c-144">В этом разделе описаны несколько вариантов, но вы можете использовать любой метод, который предоставляет ID.</span><span class="sxs-lookup"><span data-stu-id="d683c-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="d683c-145">Определение ID сообщения электронной почты, которое необходимо отоискить с помощью трассировки сообщений в Центре соответствия &amp; требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="d683c-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d683c-146">Поиск электронной почты отправителю или получателю с помощью [New Message Trace в центре & безопасности.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="d683c-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="d683c-147">После того, как вы найме электронной почты, выберите его, чтобы привести в итоге области сведений **о трассировке** сообщения.</span><span class="sxs-lookup"><span data-stu-id="d683c-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="d683c-148">**Разойдите дополнительные** сведения, чтобы найти ID сообщения.</span><span class="sxs-lookup"><span data-stu-id="d683c-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="d683c-149">Идентификация ID сообщения электронной почты, отозоваемой с помощью отчетов о шифровании сообщений Office в Центре соответствия &amp; требованиям безопасности</span><span class="sxs-lookup"><span data-stu-id="d683c-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d683c-150">В Центре соответствия &amp; требованиям безопасности перейдите к отчету о **шифровании сообщений.**</span><span class="sxs-lookup"><span data-stu-id="d683c-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="d683c-151">Сведения об этом отчете см. в обзоре отчетов о безопасности электронной почты [в Центре соответствия требованиям &amp; безопасности.](../security/office-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="d683c-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="d683c-152">Выберите **таблицу сведений** о представлении и определите сообщение, которое необходимо отоискить.</span><span class="sxs-lookup"><span data-stu-id="d683c-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="d683c-153">Дважды щелкните сообщение, чтобы просмотреть сведения, включаю в себя ID сообщения.</span><span class="sxs-lookup"><span data-stu-id="d683c-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="d683c-154">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="d683c-154">Step 2.</span></span> <span data-ttu-id="d683c-155">Убедитесь, что почта является отзывной</span><span class="sxs-lookup"><span data-stu-id="d683c-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="d683c-156">Чтобы проверить, можно ли отоискить сообщение, проверьте, отображается ли поле "Статус отзыва" в отчете шифрования в таблице Details в Центре соответствия требованиям  &amp; безопасности.</span><span class="sxs-lookup"><span data-stu-id="d683c-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="d683c-157">Чтобы проверить, можно ли отоискить определенное сообщение электронной почты с помощью Windows PowerShell, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="d683c-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="d683c-158">С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации запустите сеанс Windows PowerShell и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d683c-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="d683c-159">Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d683c-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d683c-160">Выполните Get-OMEMessageStatus следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d683c-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="d683c-161">Эта команда возвращает тему сообщения и является ли сообщение отзывным.</span><span class="sxs-lookup"><span data-stu-id="d683c-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="d683c-162">Пример.</span><span class="sxs-lookup"><span data-stu-id="d683c-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="d683c-163">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="d683c-163">Step 3.</span></span> <span data-ttu-id="d683c-164">Отоимка почты</span><span class="sxs-lookup"><span data-stu-id="d683c-164">Revoke the mail</span></span>

<span data-ttu-id="d683c-165">После того, как вы узнаете ID сообщения электронной почты, которое требуется отооскить, и убедились, что сообщение является отзывным, вы можете отоискить сообщение с помощью Центра соответствия требованиям безопасности &amp; или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d683c-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="d683c-166">Для отзова сообщения с помощью Центра соответствия &amp; требованиям безопасности</span><span class="sxs-lookup"><span data-stu-id="d683c-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d683c-167">С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации подключись к Центру & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d683c-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="d683c-168">В **отчете Шифрование** в таблице **Details** для сообщения выберите **сообщение Revoke**.</span><span class="sxs-lookup"><span data-stu-id="d683c-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="d683c-169">Для отзова электронной почты с помощью Windows PowerShell используйте Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="d683c-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="d683c-170">Использование учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации Подключись [к Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d683c-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d683c-171">Выполните Set-OMEMessageRevocation следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d683c-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="d683c-172">Чтобы проверить, было ли отозвано сообщение, выполните Get-OMEMessageStatus следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d683c-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="d683c-173">Если отзыв был успешным, этот комдлет возвращает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="d683c-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="d683c-174">Дополнительные сведения о шифровании расширенных сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="d683c-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="d683c-175">Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="d683c-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="d683c-176">Шифрование расширенных сообщений Office 365 — срок действия электронной почты</span><span class="sxs-lookup"><span data-stu-id="d683c-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="d683c-177">Описание политики сообщений и службы соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d683c-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)