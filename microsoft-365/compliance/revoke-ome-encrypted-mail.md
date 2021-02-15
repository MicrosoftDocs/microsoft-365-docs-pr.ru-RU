---
title: Отодвигать сообщения электронной почты, зашифрованные с помощью advanced Message Encryption
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
description: Администратор и отправитель сообщений могут отослать определенные сообщения, зашифрованные с помощью office 365 Advanced Message Encryption.
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105144"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="62b58-103">Отодвигать сообщения электронной почты, зашифрованные с помощью advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="62b58-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="62b58-104">Отзыв электронной почты предлагается в рамках службы office 365 Advanced Message Encryption.</span><span class="sxs-lookup"><span data-stu-id="62b58-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="62b58-105">Office 365 Advanced Message Encryption входит в [состав Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/home)корпоративный E5, Office 365 E5, Microsoft 365 E5 (цены для некоммерческих сотрудников), Office 365 корпоративный E5 (цены для некоммерческих сотрудников) и Office 365 для образования A5.</span><span class="sxs-lookup"><span data-stu-id="62b58-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="62b58-106">Если у вашей организации есть подписка, не включаемая в расширенный шифрование сообщений Office 365, вы можете приобрести ее с помощью надстройки SKU соответствия требованиям Microsoft 365 E5 для Microsoft 365 E3, Microsoft 365 E3 (цены для некоммерческих сотрудников) или надстройки Office 365 Advanced Compliance SKU для Microsoft 365 E3, Microsoft 365 E3 (цены для некоммерческих сотрудников) или SKU Office 365.</span><span class="sxs-lookup"><span data-stu-id="62b58-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="62b58-107">Эта статья входит в большую серию статей о шифровании сообщений [Office 365.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="62b58-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="62b58-108">Если сообщение было зашифровано с помощью office 365 Advanced Message Encryption и вы администратор Microsoft 365 или вы отправитель сообщения, вы можете отослать сообщение при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="62b58-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="62b58-109">Администраторы отозовют сообщения с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62b58-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="62b58-110">Отправитель отзовет сообщение, отправленное непосредственно из Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="62b58-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="62b58-111">В этой статье описываются условия, при которых отзыв возможен, и описывается, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="62b58-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="62b58-112">Зашифрованные сообщения электронной почты, которые можно отооскить</span><span class="sxs-lookup"><span data-stu-id="62b58-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="62b58-113">Администраторы и отправители сообщений могут отослать зашифрованные сообщения, если получатель получил сообщение электронной почты с фирменным шифрованием на основе ссылок.</span><span class="sxs-lookup"><span data-stu-id="62b58-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="62b58-114">Если получатель получил опыт работы с текстом в поддерживаемом клиенте Outlook, вы не сможете отоискить сообщение.</span><span class="sxs-lookup"><span data-stu-id="62b58-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="62b58-115">Тип удостоверения получателя зависит от типа удостоверения получателя: получатели учетных записей Office 365 и Майкрософт (например, outlook.com пользователей) получают возможность работы в поддерживаемых клиентах Outlook.</span><span class="sxs-lookup"><span data-stu-id="62b58-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="62b58-116">Все другие типы получателей, такие как Gmail и Yahoo, получают ссылки на основе ссылок.</span><span class="sxs-lookup"><span data-stu-id="62b58-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="62b58-117">Администраторы и отправители сообщений могут отослать сообщения, зашифрованные с помощью шифрования, примененного непосредственно из Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="62b58-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="62b58-118">Например, сообщения, зашифрованные с помощью параметра "Только шифрование".</span><span class="sxs-lookup"><span data-stu-id="62b58-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Снимок экрана с параметром &quot;Только шифрование&quot; в Outlook в Интернете.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="62b58-120">Опыт получателей для отозванных зашифрованных сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="62b58-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="62b58-121">После отзыва сообщения электронной почты получатель получает сообщение об ошибке при доступе к зашифрованному сообщению на портале шифрования сообщений Office 365: "Сообщение было отозвано отправиком".</span><span class="sxs-lookup"><span data-stu-id="62b58-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Снимок экрана: отозванное зашифрованное сообщение электронной почты.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="62b58-123">Как отоискить отправленное зашифрованное сообщение</span><span class="sxs-lookup"><span data-stu-id="62b58-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="62b58-124">Вы можете отоискить почту, отправленную одному получателю, использующему учетную запись социальных сетей, например gmail.com или yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="62b58-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="62b58-125">Другими словами, вы можете отоскить сообщение электронной почты, отправленное одному получателю, который получил ссылку.</span><span class="sxs-lookup"><span data-stu-id="62b58-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="62b58-126">Вы не можете отоискить почту, отправленную получателю, использующему учетную запись для работы или учебного заведения из Office 365 или Microsoft 365, или пользователя, который использует учетную запись Майкрософт, например учетную запись outlook.com учетной записи.</span><span class="sxs-lookup"><span data-stu-id="62b58-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="62b58-127">Чтобы отоискать отправленное зашифрованное сообщение, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="62b58-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="62b58-128">В Outlook в Интернете  в папке "Отправлено" перейдите к сообщению, которое нужно отоискить.</span><span class="sxs-lookup"><span data-stu-id="62b58-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="62b58-129">Если сообщение отозвано, в верхней части сообщения будет отобрана ссылка "Удалить внешний доступ".</span><span class="sxs-lookup"><span data-stu-id="62b58-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot showing encrypted mail that you want to revoke in Outlook on the web.":::

2. <span data-ttu-id="62b58-131">Нажмите **кнопку "Удалить внешний доступ",** чтобы отоискать сообщение.</span><span class="sxs-lookup"><span data-stu-id="62b58-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="62b58-132">Сообщение показывает, что его состояние отозвано.</span><span class="sxs-lookup"><span data-stu-id="62b58-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Снимок экрана: отозванное зашифрованное сообщение в Outlook в Интернете.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="62b58-134">Как отоискить зашифрованное сообщение от администратора</span><span class="sxs-lookup"><span data-stu-id="62b58-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="62b58-135">Администраторы Microsoft 365 выполните следующие общие действия, чтобы отоискить доступную зашифрованную электронную почту:</span><span class="sxs-lookup"><span data-stu-id="62b58-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="62b58-136">Получите ИД сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62b58-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="62b58-137">Убедитесь, что вы можете отоскить сообщение.</span><span class="sxs-lookup"><span data-stu-id="62b58-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="62b58-138">Отозовет сообщение.</span><span class="sxs-lookup"><span data-stu-id="62b58-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="62b58-139">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="62b58-139">Step 1.</span></span> <span data-ttu-id="62b58-140">Получение ИД сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="62b58-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="62b58-141">Прежде чем отоскить зашифрованное сообщение, соберем его код.</span><span class="sxs-lookup"><span data-stu-id="62b58-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="62b58-142">MessageId обычно имеет формат:</span><span class="sxs-lookup"><span data-stu-id="62b58-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="62b58-143">Существует несколько способов найти ИД сообщения электронной почты, которое требуется отоискить.</span><span class="sxs-lookup"><span data-stu-id="62b58-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="62b58-144">В этом разделе описывается несколько параметров, но можно использовать любой метод, который предоставляет ИД.</span><span class="sxs-lookup"><span data-stu-id="62b58-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="62b58-145">Идентификация ИД сообщения, отозоваемого с помощью трассировки сообщений, в Центре соответствия &amp; требованиям безопасности</span><span class="sxs-lookup"><span data-stu-id="62b58-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="62b58-146">Поиск электронной почты по отправителю или получателю с помощью новой трассировки сообщений в Центре [& соответствия требованиям.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="62b58-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="62b58-147">После того как вы нашли сообщение электронной почты, выберите его, чтобы отследить его в области **сведений о трассировке** сообщений.</span><span class="sxs-lookup"><span data-stu-id="62b58-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="62b58-148">**Разойдите дополнительные** сведения, чтобы найти ИД сообщения.</span><span class="sxs-lookup"><span data-stu-id="62b58-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="62b58-149">Определение ИД сообщения, которое требуется отооскить, с помощью отчетов шифрования сообщений Office в Центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="62b58-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="62b58-150">В Центре соответствия &amp; требованиям безопасности перейдите к отчету о шифровании **сообщений.**</span><span class="sxs-lookup"><span data-stu-id="62b58-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="62b58-151">Сведения об этом отчете см. в отчете о безопасности электронной [почты в Центре соответствия &amp; требованиям безопасности.](../security/office-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="62b58-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="62b58-152">Выберите **таблицу сведений о** представлении и определите сообщение, которое нужно отоискить.</span><span class="sxs-lookup"><span data-stu-id="62b58-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="62b58-153">Дважды щелкните сообщение, чтобы просмотреть сведения с ИД сообщения.</span><span class="sxs-lookup"><span data-stu-id="62b58-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="62b58-154">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="62b58-154">Step 2.</span></span> <span data-ttu-id="62b58-155">Убедитесь, что сообщение отозвано</span><span class="sxs-lookup"><span data-stu-id="62b58-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="62b58-156">Чтобы проверить возможность отзыва сообщения, проверьте, отображается ли поле "Состояние отзыва" в отчете  "Шифрование" в таблице "Сведения" в Центре соответствия &amp; требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="62b58-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="62b58-157">Чтобы убедиться, что вы можете отоискить определенное сообщение электронной почты с помощью Windows PowerShell, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="62b58-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="62b58-158">Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, Windows PowerShell сеанс и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="62b58-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="62b58-159">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="62b58-159">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="62b58-160">Выполните Get-OMEMessageStatus следующим образом:</span><span class="sxs-lookup"><span data-stu-id="62b58-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="62b58-161">Эта команда возвращает тему сообщения и сообщает, можно ли отозвано сообщение.</span><span class="sxs-lookup"><span data-stu-id="62b58-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="62b58-162">Пример.</span><span class="sxs-lookup"><span data-stu-id="62b58-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="62b58-163">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="62b58-163">Step 3.</span></span> <span data-ttu-id="62b58-164">Отоискить почту</span><span class="sxs-lookup"><span data-stu-id="62b58-164">Revoke the mail</span></span>

<span data-ttu-id="62b58-165">После того как вы знаете ИД сообщения, которое вы хотите отооскить, и убедились, что сообщение отзывается, вы можете отоискить сообщение с помощью Центра соответствия требованиям безопасности или &amp; Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62b58-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="62b58-166">Как отоискить сообщение с помощью Центра соответствия &amp; требованиям безопасности</span><span class="sxs-lookup"><span data-stu-id="62b58-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="62b58-167">Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите ее к Центру безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="62b58-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="62b58-168">В **отчете Encryption**  (Шифрование) в таблице сведений для сообщения выберите **"Отоскить сообщение".**</span><span class="sxs-lookup"><span data-stu-id="62b58-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="62b58-169">Чтобы отоискить сообщение электронной почты с помощью Windows PowerShell, используйте Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="62b58-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="62b58-170">Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, подключите к [Exchange Online PowerShell.](https://aka.ms/exopowershell)</span><span class="sxs-lookup"><span data-stu-id="62b58-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="62b58-171">Выполните Set-OMEMessageRevocation следующим образом:</span><span class="sxs-lookup"><span data-stu-id="62b58-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="62b58-172">Чтобы проверить, отозвано ли сообщение электронной почты, выполните Get-OMEMessageStatus следующим образом:</span><span class="sxs-lookup"><span data-stu-id="62b58-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="62b58-173">В случае успешного отзыва он возвращает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="62b58-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="62b58-174">Дополнительные сведения о службе Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="62b58-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="62b58-175">Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="62b58-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="62b58-176">Office 365 Advanced Message Encryption — срок действия электронной почты</span><span class="sxs-lookup"><span data-stu-id="62b58-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="62b58-177">Описание политики сообщений и службы соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="62b58-177">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
