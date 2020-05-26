---
title: Настройка аналитики спуфинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут ознакомиться со сведениями об управлении подменой в Exchange Online Protection (EOP), где можно разрешить или запретить использование определенных поддельных отправителей.
ms.openlocfilehash: 638f130c448f14bf7214afc705b5650311866fce
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351943"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="28ba2-103">Настройка логики подделки в EOP</span><span class="sxs-lookup"><span data-stu-id="28ba2-103">Configure spoof intelligence in EOP</span></span>

<span data-ttu-id="28ba2-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или в автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online сообщения входящей электронной почты автоматически защищаются от подмены EOP в течение октября 2018.</span><span class="sxs-lookup"><span data-stu-id="28ba2-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="28ba2-105">В EOP используется Аналитика подмены в рамках общей защиты Организации от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28ba2-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="28ba2-106">Дополнительную информацию можно узнать [в статье Защита от спуфинга в EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="28ba2-107">Когда отправитель подбирает адрес электронной почты, он отображается как пользователь в одном из доменов вашей организации или пользователь во внешнем домене, который отправляет электронную почту в организацию.</span><span class="sxs-lookup"><span data-stu-id="28ba2-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="28ba2-108">Злоумышленники, которые подделывать отправители для отправки нежелательной почты или фишинга, должны быть заблокированы.</span><span class="sxs-lookup"><span data-stu-id="28ba2-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="28ba2-109">Но существуют сценарии, в которых легальные отправители являются подложными.</span><span class="sxs-lookup"><span data-stu-id="28ba2-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="28ba2-110">Например:</span><span class="sxs-lookup"><span data-stu-id="28ba2-110">For example:</span></span>

- <span data-ttu-id="28ba2-111">Допустимые сценарии подмены внутренних доменов:</span><span class="sxs-lookup"><span data-stu-id="28ba2-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="28ba2-112">Сторонние отправители используют свой домен для отправки массовых писем своим сотрудникам для опросов компании.</span><span class="sxs-lookup"><span data-stu-id="28ba2-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>

  - <span data-ttu-id="28ba2-113">Внешняя компания создает и отправляет рекламу или обновления продуктов от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="28ba2-113">An external company generates and sends advertising or product updates on your behalf.</span></span>

  - <span data-ttu-id="28ba2-114">Помощнику часто требуется отправлять электронную почту другому человеку в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="28ba2-114">An assistant regularly needs to send email for another person within your organization.</span></span>

  - <span data-ttu-id="28ba2-115">Внутреннее приложение отправляет уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="28ba2-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="28ba2-116">Допустимые сценарии для подмены внешних доменов:</span><span class="sxs-lookup"><span data-stu-id="28ba2-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="28ba2-117">Отправитель находится в списке рассылки (который также называется списком обсуждений), а список рассылки ретранслирует электронную почту от исходного отправителя всем участникам списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="28ba2-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>

  - <span data-ttu-id="28ba2-118">Внешняя компания отправляет электронную почту от имени другой компании (например, автоматизированный отчет или компания, которая является компанией-службой).</span><span class="sxs-lookup"><span data-stu-id="28ba2-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="28ba2-119">Аналитика подделки, а именно политика подделки по умолчанию (и только), позволяет убедиться, что поддельное сообщение электронной почты, отправленное законными отправителями, не будет обнаруживаться в фильтрах нежелательной почты EOP или внешних почтовых системах, защищая пользователей от нежелательных или фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="28ba2-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="28ba2-120">Управлять подделкой можно в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="28ba2-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="28ba2-121">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="28ba2-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="28ba2-122">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="28ba2-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="28ba2-123">Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="28ba2-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="28ba2-124">Чтобы перейти непосредственно на страницу **защиты от фишинга** , используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="28ba2-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="28ba2-125">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28ba2-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="28ba2-126">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="28ba2-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="28ba2-127">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="28ba2-127">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="28ba2-128">Чтобы изменить политику контроля подделки или включить или отключить аналитику подделки, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="28ba2-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="28ba2-129">Для доступа только для чтения к политике подделки необходимо быть членом группы ролей " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="28ba2-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="28ba2-130">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-130">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="28ba2-131">Рекомендуемые параметры службы [EOP по умолчанию можно найти в разделе Параметры политики защиты от фишинга по умолчанию](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="28ba2-131">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="28ba2-132">Использование центра безопасности & соответствия требованиям для управления поддельными отправителями</span><span class="sxs-lookup"><span data-stu-id="28ba2-132">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="28ba2-133">Если у вас есть подписка на Microsoft 365 корпоративный, или у вас есть отдельно приобретенная надстройка Office 365 Advanced Threat protection (Office 365 ATP), вы также можете управлять отправителями, которые поднимаются подмене домена, с помощью функции " [подделка сведений](walkthrough-spoof-intelligence-insight.md)".</span><span class="sxs-lookup"><span data-stu-id="28ba2-133">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased an Office 365 Advanced Threat Protection (Office 365 ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="28ba2-134">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="28ba2-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="28ba2-135">На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть **политику анализа подделки**.</span><span class="sxs-lookup"><span data-stu-id="28ba2-135">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Выбор политики анализа подделки](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="28ba2-137">Сделайте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="28ba2-137">Make one of the following selections:</span></span>

   - <span data-ttu-id="28ba2-138">**Обзор новых отправителей**</span><span class="sxs-lookup"><span data-stu-id="28ba2-138">**Review new senders**</span></span>
   - <span data-ttu-id="28ba2-139">**Показать уже просмотренные мной отправители**</span><span class="sxs-lookup"><span data-stu-id="28ba2-139">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="28ba2-140">Выберите одну из следующих вкладок, если в появившемся всплывающем меню **Разрешить отправителям подмену ваших пользователей** .</span><span class="sxs-lookup"><span data-stu-id="28ba2-140">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="28ba2-141">**Домены**: отправители, которые подделывать пользователей во внутренних доменах.</span><span class="sxs-lookup"><span data-stu-id="28ba2-141">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="28ba2-142">**Внешние домены**: отправители подделывать пользователей во внешних доменах.</span><span class="sxs-lookup"><span data-stu-id="28ba2-142">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="28ba2-143">Нажмите ![ значок развернуть ](../../media/scc-expand-icon.png) в столбце **разрешено подменить?** .</span><span class="sxs-lookup"><span data-stu-id="28ba2-143">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="28ba2-144">Нажмите кнопку **Да** , чтобы разрешить поддельный отправитель, или кнопку **нет** , чтобы пометить сообщение как поддельное.</span><span class="sxs-lookup"><span data-stu-id="28ba2-144">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="28ba2-145">Действие управляется стандартной политикой защиты от фишинга или настраиваемыми политиками защиты от фишинга ATP (значение по умолчанию — **переместить сообщение в папку "Нежелательная почта**").</span><span class="sxs-lookup"><span data-stu-id="28ba2-145">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="28ba2-146">Дополнительные сведения см в разделе [Параметры подделки в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="28ba2-146">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Снимок экрана с всплывающим меню поддельных отправителей, а также от того, разрешено ли отправителю подменить](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="28ba2-148">Столбцы и значения, которые вы видите, объясняются в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="28ba2-148">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="28ba2-149">**Поддельный пользователь**: учетная запись пользователя, которая подделана.</span><span class="sxs-lookup"><span data-stu-id="28ba2-149">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="28ba2-150">Это отправитель сообщения в адресе отправителя (также называемый `5322.From` адресом), который отображается в почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="28ba2-150">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="28ba2-151">Срок действия этого адреса не проверяется с помощью SPF.</span><span class="sxs-lookup"><span data-stu-id="28ba2-151">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="28ba2-152">На вкладке **домены** , значение содержит один адрес электронной почты, или если исходный почтовый сервер подменяет несколько учетных записей пользователей, он содержит **более одной**учетной записи.</span><span class="sxs-lookup"><span data-stu-id="28ba2-152">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="28ba2-153">На вкладке **внешние домены** значение содержит домен поддельного пользователя, а не полный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="28ba2-153">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="28ba2-154">**Инфраструктура отправки**: домен, найденный в обратном поиске DNS (запись PTR) для IP-адреса исходного почтового сервера, или IP-адрес, если у источника нет записи PTR.</span><span class="sxs-lookup"><span data-stu-id="28ba2-154">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="28ba2-155">Для получения дополнительных сведений об источниках сообщений и отправителях сообщений ознакомьтесь [с обзором стандартов сообщений электронной почты](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="28ba2-155">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="28ba2-156">количество **сообщений**: количество сообщений от инфраструктуры отправки к Организации, которые содержат поддельный отправитель или отправители за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="28ba2-156">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="28ba2-157">**число жалоб пользователей**: жалобы, зафиксированные пользователями от этого отправителя за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="28ba2-157">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="28ba2-158">Жалобы, как правило, представлены в виде нежелательных отправок корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="28ba2-158">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="28ba2-159">**Результат проверки подлинности**: одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="28ba2-159">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="28ba2-160">**Передано**: отправитель прошел проверку проверки подлинности электронной почты отправителя (SPF или DKIM).</span><span class="sxs-lookup"><span data-stu-id="28ba2-160">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="28ba2-161">**Сбой**: отправитель не прошел проверку подлинности EOP отправителя.</span><span class="sxs-lookup"><span data-stu-id="28ba2-161">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="28ba2-162">**Unknown**: результат этих проверок неизвестен.</span><span class="sxs-lookup"><span data-stu-id="28ba2-162">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="28ba2-163">**Набор решений**: показывает, кто определил, может ли инфраструктура-отправитель подменить пользователя:</span><span class="sxs-lookup"><span data-stu-id="28ba2-163">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="28ba2-164">**Политика анализа подделки** (автоматическая)</span><span class="sxs-lookup"><span data-stu-id="28ba2-164">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="28ba2-165">**Администратор** (вручную)</span><span class="sxs-lookup"><span data-stu-id="28ba2-165">**Admin** (manual)</span></span>

   - <span data-ttu-id="28ba2-166">**Последнее обнаружение**: Последняя Дата получения сообщения от инфраструктуры отправки, которая содержит поддельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="28ba2-166">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="28ba2-167">**Разрешено спуфинг?**: отображаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="28ba2-167">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="28ba2-168">**Да**: сообщения из сочетания поддельного пользователя и инфраструктуры отправки разрешены и не считаются поддельными.</span><span class="sxs-lookup"><span data-stu-id="28ba2-168">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="28ba2-169">**Нет**: сообщения из сочетания поддельной инфраструктуры пользователя и отправляющей инфраструктуры помечаются как подложные.</span><span class="sxs-lookup"><span data-stu-id="28ba2-169">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="28ba2-170">Действие управляется стандартной политикой защиты от фишинга или настраиваемыми политиками защиты от фишинга ATP (значение по умолчанию — **переместить сообщение в папку "Нежелательная почта**").</span><span class="sxs-lookup"><span data-stu-id="28ba2-170">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="28ba2-171">Более подробную информацию можно найти в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="28ba2-171">See the next section for more information.</span></span>

     - <span data-ttu-id="28ba2-172">**Некоторые пользователи** (только на вкладке "**домены** "): преднаправленная инфраструктура подмена нескольких пользователей, в которой разрешено использование некоторых поддельных пользователей, а другие — нет.</span><span class="sxs-lookup"><span data-stu-id="28ba2-172">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="28ba2-173">Используйте вкладку **подробные сведения** , чтобы просмотреть конкретные адреса.</span><span class="sxs-lookup"><span data-stu-id="28ba2-173">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="28ba2-174">В нижней части страницы нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28ba2-174">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="28ba2-175">Использование PowerShell для управления поддельными отправителями</span><span class="sxs-lookup"><span data-stu-id="28ba2-175">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="28ba2-176">Чтобы просмотреть разрешенных и заблокированных отправителей в аналитике подделки, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28ba2-176">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="28ba2-177">В этом примере возвращаются подробные сведения обо всех отправителях, которым разрешено подделывать пользователей в ваших доменах.</span><span class="sxs-lookup"><span data-stu-id="28ba2-177">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="28ba2-178">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="28ba2-178">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="28ba2-179">Чтобы настроить разрешенных и заблокированных отправителей в аналитике подделки, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="28ba2-179">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="28ba2-180">Запишите текущий список обнаруженных поддельных отправителей, записав выходные данные командлета **Get-PhishFilterPolicy** в CSV-файл:</span><span class="sxs-lookup"><span data-stu-id="28ba2-180">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="28ba2-181">Измените CSV-файл, чтобы добавить или изменить параметры **спуфедусер** (адрес электронной почты) и **алловедтоспуф** (да или нет).</span><span class="sxs-lookup"><span data-stu-id="28ba2-181">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="28ba2-182">Сохраните файл, прочтите файл и сохраните его как переменную с именем `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="28ba2-182">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="28ba2-183">Используйте `$UpdateSpoofedSenders` переменную для настройки политики анализа подделки:</span><span class="sxs-lookup"><span data-stu-id="28ba2-183">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="28ba2-184">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="28ba2-184">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="28ba2-185">Использование центра безопасности & соответствия требованиям для настройки аналитики подделки</span><span class="sxs-lookup"><span data-stu-id="28ba2-185">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="28ba2-186">Параметры конфигурации для аналитики подделки описаны в разделе [Параметры подделки в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="28ba2-186">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="28ba2-187">Вы можете настроить параметры аналитики подделки в политике защиты от фишинга по умолчанию, а также в настраиваемых политиках.</span><span class="sxs-lookup"><span data-stu-id="28ba2-187">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="28ba2-188">Инструкции, основанные на вашей подписке, представлены в одном из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="28ba2-188">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="28ba2-189">[Настройка политик защиты от фишинга в EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-189">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="28ba2-190">[Настройка политик защиты от фишинга ATP в Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-190">[Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="28ba2-191">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="28ba2-191">How do you know these procedures worked?</span></span>

<span data-ttu-id="28ba2-192">Чтобы убедиться, что вы настроили логику подделки с отправителями, которым разрешено и не разрешено подменить, и что вы настроили параметры аналитики подделки, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="28ba2-192">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="28ba2-193">В центре безопасности & соответствия требованиям выберите политику **управления угрозой** \> **Policy** \> **Защита от нежелательной почты** \> . развернуть **поддельный** \> — **Показать отправители я уже просмотрен** \> выберите вкладку **домены** или **внешние домены** и убедитесь, что **разрешено спуфинг?** значение для отправителя.</span><span class="sxs-lookup"><span data-stu-id="28ba2-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="28ba2-194">В PowerShell выполните следующие команды, чтобы просмотреть отправители, которые разрешено и не разрешено подменить:</span><span class="sxs-lookup"><span data-stu-id="28ba2-194">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="28ba2-195">В PowerShell выполните следующую команду, чтобы экспортировать список поддельных отправителей в CSV-файл:</span><span class="sxs-lookup"><span data-stu-id="28ba2-195">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="28ba2-196">В центре безопасности & соответствия требованиям перейдите в раздел Защита от угроз для политики **управления угрозами** или с антифишингом \> **Policy** \> **Anti-phishing** **ATP**и выполните одно из указанных ниже действий.  </span><span class="sxs-lookup"><span data-stu-id="28ba2-196">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="28ba2-197">Выберите политику из списка.</span><span class="sxs-lookup"><span data-stu-id="28ba2-197">Select a policy from the list.</span></span> <span data-ttu-id="28ba2-198">В появившемся всплывающем меню проверьте значения в разделе **подделка** .</span><span class="sxs-lookup"><span data-stu-id="28ba2-198">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="28ba2-199">Щелкните **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="28ba2-199">Click **Default policy**.</span></span> <span data-ttu-id="28ba2-200">В появившемся всплывающем меню проверьте значения в разделе **подделка** .</span><span class="sxs-lookup"><span data-stu-id="28ba2-200">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="28ba2-201">В Exchange Online PowerShell замените \< имя \> на Office365 по умолчанию антифишингом или именем настраиваемой политики и выполните следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="28ba2-201">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="28ba2-202">Другие способы управления подменой и фишингом</span><span class="sxs-lookup"><span data-stu-id="28ba2-202">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="28ba2-203">Будьте более тщательно обменялись подменой и защита от фишинга.</span><span class="sxs-lookup"><span data-stu-id="28ba2-203">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="28ba2-204">Ниже приведены способы проверки отправителя на подмену домена и помощь в предотвращении повреждения вашей организации:</span><span class="sxs-lookup"><span data-stu-id="28ba2-204">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="28ba2-205">Просмотрите **отчет о поддельных почтовых сообщениях**.</span><span class="sxs-lookup"><span data-stu-id="28ba2-205">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="28ba2-206">Этот отчет часто можно использовать для просмотра поддельных отправителей и помощи в управлении ими.</span><span class="sxs-lookup"><span data-stu-id="28ba2-206">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="28ba2-207">Для получения дополнительных сведений обратитесь к [отчету Обнаружение поддельных поддельных](view-email-security-reports.md#spoof-detections-report)сведений.</span><span class="sxs-lookup"><span data-stu-id="28ba2-207">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="28ba2-208">Проверьте конфигурацию инфраструктуры политики отправителей (SPF).</span><span class="sxs-lookup"><span data-stu-id="28ba2-208">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="28ba2-209">Для быстрого ознакомления с SPF и его быстрой настройки см. раздел [Настройка SPF в Microsoft 365, чтобы предотвратить подделку](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-209">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="28ba2-210">Дополнительные сведения об использовании инфраструктуры политики отправителей в Office 365, рекомендации по устранению неполадок и инструкции для нестандартных, в том числе гибридных, развертываний см. в статье [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-210">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="28ba2-211">Проверьте конфигурацию электронной почты DomainKeys identified mail (DKIM).</span><span class="sxs-lookup"><span data-stu-id="28ba2-211">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="28ba2-212">Следует использовать DKIM в дополнение к SPF и DMARC, чтобы предотвратить отправку злоумышленниками сообщений, которые выглядят так, как они поступают из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="28ba2-212">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="28ba2-213">DKIM позволяет добавлять цифровую подпись в заголовки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="28ba2-213">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="28ba2-214">Сведения о том, [как использовать DKIM для проверки исходящей электронной почты, отправленной из личного домена в Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-214">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="28ba2-215">Изучите конфигурацию проверки подлинности сообщений, отчетов и соответствия (DMARC) на основе домена.</span><span class="sxs-lookup"><span data-stu-id="28ba2-215">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="28ba2-216">Реализация DMARC в сочетании с SPF и DKIM обеспечивает дополнительную защиту от спуфинга и фишинга.</span><span class="sxs-lookup"><span data-stu-id="28ba2-216">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="28ba2-217">DMARC помогает получающим почтовым системам определить, что делать с сообщениями, отправленными из вашего домена, которые не прошли проверки SPF или DKIM.</span><span class="sxs-lookup"><span data-stu-id="28ba2-217">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="28ba2-218">Для получения дополнительных сведений обратитесь к разделу [Использование DMARC для проверки электронной почты в Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-218">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
