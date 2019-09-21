---
title: Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Администратор Office 365 может отозвать определенные сообщения электронной почты, зашифрованные с помощью расширенного шифрования сообщений Office 365.
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090784"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="d6b6d-103">Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="d6b6d-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="d6b6d-104">Отзыв электронной почты предлагается как часть расширенного шифрования сообщения Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="d6b6d-105">Расширенное шифрование сообщений Office 365 в определенных подписках доступно на основе шифрования сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="d6b6d-106">Расширенное шифрование сообщений включено в [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise и Office 365 образования A5.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="d6b6d-107">Если в вашей организации есть подписка на Office 365, которая не включает расширенное шифрование сообщений Office 365, вы можете приобрести дополнительное шифрование сообщений в качестве надстройки с соответствием требованиям к расширенному набору для обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="d6b6d-108">Эта статья входит в набор статей, посвященных [шифрованию сообщений Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="d6b6d-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="d6b6d-109">Если сообщение было зашифровано с помощью расширенного шифрования сообщений Office 365 и вы являетесь администратором Office 365, вы можете отозвать сообщение при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-109">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="d6b6d-110">В этой статье описываются обстоятельства, при которых возможны случаи отзыва, и способы их выполнения.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-110">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="d6b6d-111">Зашифрованные сообщения электронной почты, которые можно отозвать</span><span class="sxs-lookup"><span data-stu-id="d6b6d-111">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="d6b6d-112">Вы можете отозвать зашифрованные сообщения, если получатель получил зашифрованную электронную почту на основе ссылок.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-112">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="d6b6d-113">Если получатель получил собственный встроенный интерфейс в поддерживаемом клиенте Outlook, эти сообщения не могут быть отозваны.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-113">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="d6b6d-114">Сведения о том, получает ли получатель доступ на основе ссылок или встроенные возможности, зависят от типа удостоверения получателя: получатели Office 365 и учетной записи Майкрософт (например, пользователи outlook.com) получают встроенные возможности в поддерживаемых клиентах Outlook.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-114">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="d6b6d-115">Все другие типы получателей, например получатели Gmail, получают интерфейс, основанный на ссылке.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-115">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="d6b6d-116">Получатель отзыва о отозванных зашифрованных сообщениях</span><span class="sxs-lookup"><span data-stu-id="d6b6d-116">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="d6b6d-117">После того как сообщение было отозвано, получатель получает сообщение об ошибке при доступе к зашифрованной электронной почте через портал шифрования сообщений Office 365: "сообщение было отозвано отправителем".</span><span class="sxs-lookup"><span data-stu-id="d6b6d-117">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Снимок экрана, на котором показан отозванный зашифрованный адрес электронной почты.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="d6b6d-119">Отзыв зашифрованного сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="d6b6d-119">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="d6b6d-120">Действие 1.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-120">Step 1.</span></span> <span data-ttu-id="d6b6d-121">Получение идентификатора сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="d6b6d-121">Obtain the Message ID of the email</span></span>

<span data-ttu-id="d6b6d-122">Прежде чем отозвать зашифрованную почту, вы собираетесь получить идентификатор сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-122">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="d6b6d-123">MessageId обычно имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d6b6d-123">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="d6b6d-124">Существует несколько способов поиска идентификатора сообщения электронной почты, которое нужно отозвать.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-124">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="d6b6d-125">В этом разделе описывается несколько вариантов, но вы можете использовать любой метод, который предоставляет идентификатор.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-125">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="d6b6d-126">Определение идентификатора сообщения электронной почты, которое нужно отозвать, с помощью трассировки сообщений в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d6b6d-126">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d6b6d-127">Поиск почты по отправителям или получателям с помощью [новой трассировки сообщений в центре безопасности Office 365 & соответствия требованиям](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="d6b6d-127">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="d6b6d-128">После того как вы нашли сообщение, выберите его, чтобы открыть область **сведений трассировки сообщений** .</span><span class="sxs-lookup"><span data-stu-id="d6b6d-128">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="d6b6d-129">Разверните **Дополнительные сведения** , чтобы узнать идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-129">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="d6b6d-130">Определение идентификатора сообщения электронной почты, которое вы хотите отозвать, с помощью отчетов о шифровании сообщений Office в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d6b6d-130">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d6b6d-131">В центре безопасности &amp; и соответствия требованиям перейдите к **отчету шифрование сообщений**.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-131">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="d6b6d-132">Сведения об этом отчете приведены в статье [Просмотр отчетов о безопасности электронной почты в &amp; центре безопасности и соответствия требованиям](view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="d6b6d-132">For information on this report, see [View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md).</span></span>

2. <span data-ttu-id="d6b6d-133">Выберите таблицу **Просмотр сведений** и определите сообщение, которое нужно отозвать.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="d6b6d-134">Дважды щелкните сообщение, чтобы просмотреть сведения, содержащие идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="d6b6d-135">Действие 2.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-135">Step 2.</span></span> <span data-ttu-id="d6b6d-136">Проверка подлинности почты ревокабле</span><span class="sxs-lookup"><span data-stu-id="d6b6d-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="d6b6d-137">Чтобы проверить, можно ли отозвать сообщение, проверьте, отображается ли поле состояние отзыва в отчете о шифровании в таблице **сведений** в центре соответствия требованиям безопасности &amp; .</span><span class="sxs-lookup"><span data-stu-id="d6b6d-137">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="d6b6d-138">Чтобы проверить, можно ли отозвать конкретное сообщение электронной почты с помощью Windows PowerShell, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-138">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="d6b6d-139">С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="d6b6d-140">Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="d6b6d-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d6b6d-141">Выполните командлет Get – Омемессажестатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d6b6d-141">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="d6b6d-142">Возвращает тему сообщения и о том, является ли сообщение ревокабле.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="d6b6d-143">For example,</span><span class="sxs-lookup"><span data-stu-id="d6b6d-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="d6b6d-144">Действие 3.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-144">Step 3.</span></span> <span data-ttu-id="d6b6d-145">Отзыв почты</span><span class="sxs-lookup"><span data-stu-id="d6b6d-145">Revoke the mail</span></span>

<span data-ttu-id="d6b6d-146">Зная идентификатор сообщения, которое вы хотите отозвать, и убедитесь, что оно ревокабле, вы можете отозвать электронную почту с помощью центра безопасности &amp; или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="d6b6d-147">Отзыв сообщения с помощью центра безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d6b6d-147">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="d6b6d-148">Чтобы отозвать электронную почту в центре безопасности &amp; и соответствия требованиям, в отчете шифрование в таблице **сведения** сообщения нажмите кнопку **отозвать сообщение**.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-148">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="d6b6d-149">Отозвать электронную почту с помощью Windows PowerShell можно с помощью командлета Set – Омемессажеревокатион.</span><span class="sxs-lookup"><span data-stu-id="d6b6d-149">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="d6b6d-150">[Подключитесь к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="d6b6d-150">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d6b6d-151">Выполните командлет Set – Омемессажеревокатион следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d6b6d-151">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="d6b6d-152">Чтобы проверить, было ли отозвано сообщение электронной почты, выполните командлет Get – Омемессажестатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d6b6d-152">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="d6b6d-153">Если отзыв был выполнен успешно, командлет возвращает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="d6b6d-153">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="d6b6d-154">Дополнительные сведения о расширенном шифровании сообщений в Office 365</span><span class="sxs-lookup"><span data-stu-id="d6b6d-154">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="d6b6d-155">Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="d6b6d-155">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="d6b6d-156">Расширенное шифрование сообщения Office 365 — истечение срока действия электронной почты</span><span class="sxs-lookup"><span data-stu-id="d6b6d-156">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="d6b6d-157">Описание политики сообщений и службы соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d6b6d-157">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
