---
title: Отзыв сообщений, зашифрованных с помощью расширенного шифрования сообщений
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
description: Администратор и отправитель сообщения могут отозвать определенные сообщения электронной почты, которые были зашифрованы с помощью расширенного шифрования сообщений Office 365.
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868960"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="4154d-103">Отзыв сообщений, зашифрованных с помощью расширенного шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="4154d-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="4154d-104">Отзыв электронной почты предлагается как часть расширенного шифрования сообщения Office 365.</span><span class="sxs-lookup"><span data-stu-id="4154d-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="4154d-105">Расширенное шифрование сообщений Office 365 включено в [microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365, Microsoft 365, Microsoft (ценообразование для сотрудников), Office 365 Enterprise и Office 365 образование A5.</span><span class="sxs-lookup"><span data-stu-id="4154d-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="4154d-106">Если в вашей организации есть подписка, не включающая в себя приложение Office 365 Advanced Message Encryption, вы можете приобрести его с помощью надстройки Microsoft 365 для обеспечения соответствия требованиям для Microsoft 365 E3, Microsoft 365 E3 (ценообразование для некоммерческих сотрудников) или надстройки Office 365 для расширенного соответствия требованиям для Microsoft 365 E3, Microsoft 365 E3 (ценообразование для некоммерческих сотрудников) или SKU Office 365</span><span class="sxs-lookup"><span data-stu-id="4154d-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="4154d-107">Эта статья входит в набор статей, посвященных [шифрованию сообщений Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="4154d-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="4154d-108">Если сообщение было зашифровано с помощью расширенного шифрования сообщения Office 365 и вы являетесь администратором Microsoft 365 или вы Отправитель этого сообщения, вы можете отозвать сообщение при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="4154d-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="4154d-109">Администраторы отзывают сообщения с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4154d-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="4154d-110">Отправитель отзывает сообщение, отправленное непосредственно из Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4154d-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="4154d-111">В этой статье описываются обстоятельства, при которых возможны случаи отзыва, и способы их выполнения.</span><span class="sxs-lookup"><span data-stu-id="4154d-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="4154d-112">Зашифрованные сообщения электронной почты, которые можно отозвать</span><span class="sxs-lookup"><span data-stu-id="4154d-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="4154d-113">Администраторы и отправители сообщений могут отзывать зашифрованные сообщения электронной почты, если получатель получил зашифрованную электронную почту на основе ссылок.</span><span class="sxs-lookup"><span data-stu-id="4154d-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="4154d-114">Если получатель получил собственный встроенный интерфейс в поддерживаемом клиенте Outlook, вы не можете отозвать сообщение.</span><span class="sxs-lookup"><span data-stu-id="4154d-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="4154d-115">Сведения о том, получает ли получатель доступ на основе ссылок или встроенные возможности, зависят от типа удостоверения получателя: получатели Office 365 и учетной записи Майкрософт (например, пользователи outlook.com) получают встроенные возможности в поддерживаемых клиентах Outlook.</span><span class="sxs-lookup"><span data-stu-id="4154d-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="4154d-116">Все другие типы получателей, такие как получатели Gmail и Yahoo, получают интерфейс, основанный на ссылке.</span><span class="sxs-lookup"><span data-stu-id="4154d-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="4154d-117">Администраторы и отправители сообщений могут отозвать сообщения, зашифрованные с помощью шифрования, непосредственно из Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4154d-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="4154d-118">Например, сообщения, зашифрованные с помощью параметра "только шифровать".</span><span class="sxs-lookup"><span data-stu-id="4154d-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Снимок экрана: параметр &quot;только шифрование&quot; в Outlook в Интернете.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="4154d-120">Получатель отзыва о отозванных зашифрованных сообщениях</span><span class="sxs-lookup"><span data-stu-id="4154d-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="4154d-121">После того как сообщение было отозвано, получатель получает сообщение об ошибке при доступе к зашифрованной электронной почте через портал шифрования сообщений Office 365: "сообщение было отозвано отправителем".</span><span class="sxs-lookup"><span data-stu-id="4154d-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Снимок экрана, на котором показан отозванный зашифрованный адрес электронной почты.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="4154d-123">Отзыв зашифрованного сообщения, которое вы отправили</span><span class="sxs-lookup"><span data-stu-id="4154d-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="4154d-124">Чтобы отозвать отправленное зашифрованное сообщение, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4154d-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="4154d-125">В Outlook в Интернете, в папке **Отправленные** , перейдите к сообщению, которое нужно отозвать.</span><span class="sxs-lookup"><span data-stu-id="4154d-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="4154d-126">Если почта ревокабле, вы увидите ссылку "Удаление внешнего доступа" в верхней части сообщения.</span><span class="sxs-lookup"><span data-stu-id="4154d-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Снимок экрана: параметр &quot;только шифрование&quot; в Outlook в Интернете.":::

2. <span data-ttu-id="4154d-128">Чтобы отозвать сообщение, нажмите кнопку **Удалить внешний доступ** .</span><span class="sxs-lookup"><span data-stu-id="4154d-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="4154d-129">Сообщение показывает, что его состояние отозвано.</span><span class="sxs-lookup"><span data-stu-id="4154d-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Снимок экрана: параметр &quot;только шифрование&quot; в Outlook в Интернете.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="4154d-131">Отзыв зашифрованного сообщения от имени администратора</span><span class="sxs-lookup"><span data-stu-id="4154d-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="4154d-132">Для отзыва подходящего зашифрованного сообщения администратору Microsoft 365 выполните следующие общие действия:</span><span class="sxs-lookup"><span data-stu-id="4154d-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="4154d-133">Получение идентификатора сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4154d-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="4154d-134">Убедитесь, что вы можете отозвать сообщение.</span><span class="sxs-lookup"><span data-stu-id="4154d-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="4154d-135">Отзыв почты.</span><span class="sxs-lookup"><span data-stu-id="4154d-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="4154d-136">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="4154d-136">Step 1.</span></span> <span data-ttu-id="4154d-137">Получение идентификатора сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="4154d-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="4154d-138">Прежде чем отозвать зашифрованную почту, соберите идентификатор сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4154d-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="4154d-139">MessageId обычно имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="4154d-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="4154d-140">Существует несколько способов поиска идентификатора сообщения электронной почты, которое нужно отозвать.</span><span class="sxs-lookup"><span data-stu-id="4154d-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="4154d-141">В этом разделе описывается несколько вариантов, но вы можете использовать любой метод, который предоставляет идентификатор.</span><span class="sxs-lookup"><span data-stu-id="4154d-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="4154d-142">Определение идентификатора сообщения электронной почты, которое нужно отозвать, с помощью трассировки сообщений в центре безопасности и &amp; соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4154d-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="4154d-143">Поиск почты по отправителям или получателям с помощью [новой трассировки сообщений в центре безопасности & соответствия требованиям](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="4154d-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="4154d-144">После того как вы нашли сообщение, выберите его, чтобы открыть область **сведений трассировки сообщений** .</span><span class="sxs-lookup"><span data-stu-id="4154d-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="4154d-145">Разверните **Дополнительные сведения** , чтобы узнать идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="4154d-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="4154d-146">Определение идентификатора сообщения электронной почты, которое вы хотите отозвать, с помощью отчетов о шифровании сообщений Office в центре безопасности и &amp; соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4154d-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="4154d-147">В центре безопасности &amp; и соответствия требованиям перейдите к **отчету шифрование сообщений**.</span><span class="sxs-lookup"><span data-stu-id="4154d-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="4154d-148">Сведения об этом отчете приведены в статье [Просмотр отчетов о безопасности электронной почты в &amp; центре безопасности и соответствия требованиям](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="4154d-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="4154d-149">Выберите таблицу **Просмотр сведений** и определите сообщение, которое нужно отозвать.</span><span class="sxs-lookup"><span data-stu-id="4154d-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="4154d-150">Дважды щелкните сообщение, чтобы просмотреть сведения, содержащие идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="4154d-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="4154d-151">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="4154d-151">Step 2.</span></span> <span data-ttu-id="4154d-152">Проверка подлинности почты ревокабле</span><span class="sxs-lookup"><span data-stu-id="4154d-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="4154d-153">Чтобы проверить, можно ли отозвать сообщение, проверьте, отображается ли поле состояние отзыва в отчете о шифровании в таблице **сведений** в &amp; центре соответствия требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="4154d-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="4154d-154">Чтобы проверить, можно ли отозвать конкретное сообщение электронной почты с помощью Windows PowerShell, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4154d-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="4154d-155">С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в Организации запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4154d-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="4154d-156">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="4154d-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="4154d-157">Выполните командлет Get – Омемессажестатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4154d-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="4154d-158">Эта команда возвращает тему сообщения и о том, является ли сообщение ревокабле.</span><span class="sxs-lookup"><span data-stu-id="4154d-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="4154d-159">Пример.</span><span class="sxs-lookup"><span data-stu-id="4154d-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="4154d-160">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="4154d-160">Step 3.</span></span> <span data-ttu-id="4154d-161">Отзыв почты</span><span class="sxs-lookup"><span data-stu-id="4154d-161">Revoke the mail</span></span>

<span data-ttu-id="4154d-162">Зная идентификатор сообщения, которое вы хотите отозвать, и убедитесь, что оно ревокабле, вы можете отозвать электронную почту с помощью &amp; центра безопасности или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4154d-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="4154d-163">Отзыв сообщения с помощью центра безопасности и &amp; соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4154d-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="4154d-164">С помощью рабочей или учебной учетной записи, имеющей разрешения глобального администратора в Организации, подключитесь к центру безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4154d-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="4154d-165">В **отчете шифрования**в таблице **сведения** для сообщения выберите **отзыв сообщения**.</span><span class="sxs-lookup"><span data-stu-id="4154d-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="4154d-166">Чтобы отозвать сообщение электронной почты с помощью Windows PowerShell, используйте командлет Set – Омемессажеревокатион.</span><span class="sxs-lookup"><span data-stu-id="4154d-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="4154d-167">С помощью рабочей или учебной учетной записи, имеющей разрешения глобального администратора в Организации, [подключитесь к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="4154d-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="4154d-168">Выполните командлет Set – Омемессажеревокатион следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4154d-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="4154d-169">Чтобы проверить, было ли отозвано сообщение электронной почты, выполните командлет Get – Омемессажестатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4154d-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="4154d-170">Если отзыв был выполнен успешно, командлет возвращает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="4154d-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="4154d-171">Дополнительные сведения о расширенном шифровании сообщений в Office 365</span><span class="sxs-lookup"><span data-stu-id="4154d-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="4154d-172">Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="4154d-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="4154d-173">Расширенное шифрование сообщения Office 365 — истечение срока действия электронной почты</span><span class="sxs-lookup"><span data-stu-id="4154d-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="4154d-174">Описание политики сообщений и службы соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4154d-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
