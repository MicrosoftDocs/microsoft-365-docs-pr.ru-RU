---
title: Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Администратор Office 365 может отозвать определенные сообщения электронной почты, зашифрованные с помощью расширенного шифрования сообщений Office 365.
ms.openlocfilehash: d3d449c969b2fa5d21042779ebad11e3807d1d3e
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112523"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="6c139-103">Отзыв электронных писем, зашифрованных с помощью расширенного шифрования сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="6c139-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="6c139-104">Отзыв электронной почты предлагается как часть расширенного шифрования сообщения Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c139-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="6c139-105">Расширенное шифрование сообщений Office 365 включено в [microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365, Microsoft 365, Microsoft (ценообразование для сотрудников), Office 365 Enterprise и Office 365 образование A5.</span><span class="sxs-lookup"><span data-stu-id="6c139-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="6c139-106">Если в вашей организации есть подписка, не включающая в себя приложение Office 365 Advanced Message Encryption, вы можете приобрести его с помощью надстройки Microsoft 365 с поддержкой соответствия требованиям для Microsoft 365 E3, Microsoft 365 E3 (ценообразование для некоммерческих сотрудников) или Office 365 Advanced Надстройка SKU для обеспечения соответствия требованиям для Microsoft 365 E3, Microsoft 365 E3 (ценообразование для некоммерческих сотрудников) или SKU Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c139-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="6c139-107">Эта статья входит в набор статей, посвященных [шифрованию сообщений Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="6c139-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="6c139-108">Если сообщение было зашифровано с помощью расширенного шифрования сообщений Office 365 и вы являетесь администратором Office 365, вы можете отозвать сообщение при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="6c139-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="6c139-109">В этой статье описываются обстоятельства, при которых возможны случаи отзыва, и способы их выполнения.</span><span class="sxs-lookup"><span data-stu-id="6c139-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="6c139-110">Зашифрованные сообщения электронной почты, которые можно отозвать</span><span class="sxs-lookup"><span data-stu-id="6c139-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="6c139-111">Вы можете отозвать зашифрованные сообщения, если получатель получил зашифрованную электронную почту на основе ссылок.</span><span class="sxs-lookup"><span data-stu-id="6c139-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="6c139-112">Если получатель получил собственный встроенный интерфейс в поддерживаемом клиенте Outlook, эти сообщения не могут быть отозваны.</span><span class="sxs-lookup"><span data-stu-id="6c139-112">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="6c139-113">Сведения о том, получает ли получатель доступ на основе ссылок или встроенные возможности, зависят от типа удостоверения получателя: получатели Office 365 и учетной записи Майкрософт (например, пользователи outlook.com) получают встроенные возможности в поддерживаемых клиентах Outlook.</span><span class="sxs-lookup"><span data-stu-id="6c139-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="6c139-114">Все другие типы получателей, например получатели Gmail, получают интерфейс, основанный на ссылке.</span><span class="sxs-lookup"><span data-stu-id="6c139-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="6c139-115">Получатель отзыва о отозванных зашифрованных сообщениях</span><span class="sxs-lookup"><span data-stu-id="6c139-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="6c139-116">После того как сообщение было отозвано, получатель получает сообщение об ошибке при доступе к зашифрованной электронной почте через портал шифрования сообщений Office 365: "сообщение было отозвано отправителем".</span><span class="sxs-lookup"><span data-stu-id="6c139-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Снимок экрана, на котором показан отозванный зашифрованный адрес электронной почты.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="6c139-118">Отзыв зашифрованного сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="6c139-118">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="6c139-119">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="6c139-119">Step 1.</span></span> <span data-ttu-id="6c139-120">Получение идентификатора сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="6c139-120">Obtain the Message ID of the email</span></span>

<span data-ttu-id="6c139-121">Прежде чем отозвать зашифрованную почту, вы собираетесь получить идентификатор сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6c139-121">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="6c139-122">MessageId обычно имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="6c139-122">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="6c139-123">Существует несколько способов поиска идентификатора сообщения электронной почты, которое нужно отозвать.</span><span class="sxs-lookup"><span data-stu-id="6c139-123">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="6c139-124">В этом разделе описывается несколько вариантов, но вы можете использовать любой метод, который предоставляет идентификатор.</span><span class="sxs-lookup"><span data-stu-id="6c139-124">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="6c139-125">Определение идентификатора сообщения электронной почты, которое нужно отозвать, с помощью трассировки сообщений в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="6c139-125">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="6c139-126">Поиск почты по отправителям или получателям с помощью [новой трассировки сообщений в центре безопасности Office 365 & соответствия требованиям](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="6c139-126">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="6c139-127">После того как вы нашли сообщение, выберите его, чтобы открыть область **сведений трассировки сообщений** .</span><span class="sxs-lookup"><span data-stu-id="6c139-127">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="6c139-128">Разверните **Дополнительные сведения** , чтобы узнать идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="6c139-128">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="6c139-129">Определение идентификатора сообщения электронной почты, которое вы хотите отозвать, с помощью отчетов о шифровании сообщений Office в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="6c139-129">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="6c139-130">В центре безопасности &amp; и соответствия требованиям перейдите к **отчету шифрование сообщений**.</span><span class="sxs-lookup"><span data-stu-id="6c139-130">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="6c139-131">Сведения об этом отчете приведены в статье [Просмотр отчетов о безопасности электронной почты в &amp; центре безопасности и соответствия требованиям](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="6c139-131">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="6c139-132">Выберите таблицу **Просмотр сведений** и определите сообщение, которое нужно отозвать.</span><span class="sxs-lookup"><span data-stu-id="6c139-132">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="6c139-133">Дважды щелкните сообщение, чтобы просмотреть сведения, содержащие идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="6c139-133">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="6c139-134">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="6c139-134">Step 2.</span></span> <span data-ttu-id="6c139-135">Проверка подлинности почты ревокабле</span><span class="sxs-lookup"><span data-stu-id="6c139-135">Verify that the mail is revocable</span></span>

<span data-ttu-id="6c139-136">Чтобы проверить, можно ли отозвать сообщение, проверьте, отображается ли поле состояние отзыва в отчете о шифровании в таблице **сведений** в центре соответствия требованиям безопасности &amp; .</span><span class="sxs-lookup"><span data-stu-id="6c139-136">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="6c139-137">Чтобы проверить, можно ли отозвать конкретное сообщение электронной почты с помощью Windows PowerShell, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6c139-137">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="6c139-138">С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6c139-138">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="6c139-139">Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="6c139-139">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="6c139-140">Выполните командлет Get – Омемессажестатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6c139-140">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="6c139-141">Возвращает тему сообщения и о том, является ли сообщение ревокабле.</span><span class="sxs-lookup"><span data-stu-id="6c139-141">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="6c139-142">For example,</span><span class="sxs-lookup"><span data-stu-id="6c139-142">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="6c139-143">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="6c139-143">Step 3.</span></span> <span data-ttu-id="6c139-144">Отзыв почты</span><span class="sxs-lookup"><span data-stu-id="6c139-144">Revoke the mail</span></span>

<span data-ttu-id="6c139-145">Зная идентификатор сообщения, которое вы хотите отозвать, и убедитесь, что оно ревокабле, вы можете отозвать электронную почту с помощью центра безопасности &amp; или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c139-145">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="6c139-146">Отзыв сообщения с помощью центра безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="6c139-146">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="6c139-147">Чтобы отозвать электронную почту в центре безопасности &amp; и соответствия требованиям, в отчете шифрование в таблице **сведения** сообщения нажмите кнопку **отозвать сообщение**.</span><span class="sxs-lookup"><span data-stu-id="6c139-147">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="6c139-148">Отозвать электронную почту с помощью Windows PowerShell можно с помощью командлета Set – Омемессажеревокатион.</span><span class="sxs-lookup"><span data-stu-id="6c139-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="6c139-149">[Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="6c139-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="6c139-150">Выполните командлет Set – Омемессажеревокатион следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6c139-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="6c139-151">Чтобы проверить, было ли отозвано сообщение электронной почты, выполните командлет Get – Омемессажестатус следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6c139-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="6c139-152">Если отзыв был выполнен успешно, командлет возвращает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="6c139-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="6c139-153">Дополнительные сведения о расширенном шифровании сообщений в Office 365</span><span class="sxs-lookup"><span data-stu-id="6c139-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="6c139-154">Расширенное шифрование сообщений Office 365</span><span class="sxs-lookup"><span data-stu-id="6c139-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="6c139-155">Расширенное шифрование сообщения Office 365 — истечение срока действия электронной почты</span><span class="sxs-lookup"><span data-stu-id="6c139-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="6c139-156">Описание политики сообщений и службы соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="6c139-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
