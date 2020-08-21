---
title: Настройка аналитики спуфинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Администраторы могут узнать об аналитике подделок в Exchange Online Protection (EOP), где можно разрешить или заблокировать определенных поддельных отправителей.
ms.openlocfilehash: 66cfc419c3e2f3a5dd8ad45cdb9fe651b613679b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826581"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="89cb9-103">Настройка аналитики спуфинга в EOP</span><span class="sxs-lookup"><span data-stu-id="89cb9-103">Configure spoof intelligence in EOP</span></span>

<span data-ttu-id="89cb9-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online входящие сообщения электронной почты автоматически защищены от спуфинга, используя почту EOP с октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="89cb9-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="89cb9-105">EOP использует аналитику спуфинга в рамках общей защиты от фишинга в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="89cb9-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="89cb9-106">Дополнительные сведения см. в статье ["Защита от спуфинга" в EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="89cb9-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="89cb9-107">Когда отправитель подделывает электронный адрес, он является пользователем одного из доменов вашей организации или пользователем внешнего домена, который отправляет электронную почту в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="89cb9-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="89cb9-108">Злоумышленники, которые спуфинга отправляют нежелательную почту или фишинговые сообщения, должны блокироваться.</span><span class="sxs-lookup"><span data-stu-id="89cb9-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="89cb9-109">Но в некоторых случаях надежные отправители подделывающиеся отправители являются спуффикацией.</span><span class="sxs-lookup"><span data-stu-id="89cb9-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="89cb9-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="89cb9-110">For example:</span></span>

- <span data-ttu-id="89cb9-111">Законных сценариев для подделывания внутренних доменов:</span><span class="sxs-lookup"><span data-stu-id="89cb9-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="89cb9-112">Сторонние отправители используют ваш домен для массовой рассылки для ваших сотрудников на опросы компании.</span><span class="sxs-lookup"><span data-stu-id="89cb9-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="89cb9-113">Внешняя компания создает и отправляет обновления рекламы или продукта от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="89cb9-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="89cb9-114">Помощнику необходимо регулярно отправлять электронную почту другому пользователю в организации.</span><span class="sxs-lookup"><span data-stu-id="89cb9-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="89cb9-115">Внутреннее приложение отправляет уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="89cb9-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="89cb9-116">Законные сценарии для подделывания внешних доменов:</span><span class="sxs-lookup"><span data-stu-id="89cb9-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="89cb9-117">Отправитель находится в списке рассылки (также называемом списком обсуждений), и список рассылки ретранслирует сообщения электронной почты от исходного отправителя всем участникам списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="89cb9-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="89cb9-118">Внешняя компания отправляет электронную почту от имени другой компании (например, автоматический отчет или компанию с использованием программного обеспечения как услуги).</span><span class="sxs-lookup"><span data-stu-id="89cb9-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="89cb9-119">Иными данными о подделке и, в частности, политику анализа спуфинга по умолчанию (и только) спуфинга, помогает предотвратить попадание поддельных писем в фильтрах нежелательной почты EOP или внешних почтовых системах, не защищая ваших пользователей от спама или фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="89cb9-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="89cb9-120">Вы можете управлять аналитикой подделок в Центре безопасности & соответствия требованиям или PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; отдельный PowerShell EOP для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="89cb9-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="89cb9-121">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="89cb9-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="89cb9-122">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="89cb9-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="89cb9-123">Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="89cb9-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="89cb9-124">Чтобы перейти непосредственно на страницу **"Защита от фишинга"** используйте <https://protection.office.com/antiphishing> этот код.</span><span class="sxs-lookup"><span data-stu-id="89cb9-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="89cb9-125">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="89cb9-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="89cb9-126">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="89cb9-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="89cb9-127">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="89cb9-127">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="89cb9-128">Чтобы изменить политику аналитики подделок или включить или отключить аналитику спуфинга, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="89cb9-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="89cb9-129">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="89cb9-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="89cb9-130">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="89cb9-130">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="89cb9-131">Чтобы получить доступ к политике аналитики спуфинга только для чтения, вы должны быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="89cb9-131">For read-only access to the spoof intelligence policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="89cb9-132">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="89cb9-132">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="89cb9-133">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="89cb9-133">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="89cb9-134">Рекомендуемые параметры для аналитики спуфинга см. в [статье о параметрах политики защиты от фишинга EOP по умолчанию.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="89cb9-134">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="89cb9-135">Использование Центра безопасности & безопасности для управления поддельных отправителями</span><span class="sxs-lookup"><span data-stu-id="89cb9-135">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="89cb9-136">Если у вас есть подписка на Microsoft 365 корпоративный E5 или надстройка Office 365 Advanced Threat Protection (Office 365 ATP), вы также можете управлять отправителями, которые подделывают ваш домен, с [помощью аналитики защиты от](walkthrough-spoof-intelligence-insight.md)подделок.</span><span class="sxs-lookup"><span data-stu-id="89cb9-136">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased an Office 365 Advanced Threat Protection (Office 365 ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="89cb9-137">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="89cb9-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="89cb9-138">На странице параметров **защиты от нежелательной почты** щелкните ![ значок "Развернуть", ](../../media/scc-expand-icon.png) чтобы развернуть **политику аналитики подделок.**</span><span class="sxs-lookup"><span data-stu-id="89cb9-138">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Выбор политики аналитики подделок](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="89cb9-140">Выберите один из приведенных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="89cb9-140">Make one of the following selections:</span></span>

   - <span data-ttu-id="89cb9-141">**Просмотр новых отправителей**</span><span class="sxs-lookup"><span data-stu-id="89cb9-141">**Review new senders**</span></span>
   - <span data-ttu-id="89cb9-142">**Показать мне отправителей, которых я уже проверил**</span><span class="sxs-lookup"><span data-stu-id="89cb9-142">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="89cb9-143">В разделе **"Решите, могут ли эти отправители** подделывать ся подвижущего элемента" пользователей, выберите одну из следующих вкладок:</span><span class="sxs-lookup"><span data-stu-id="89cb9-143">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="89cb9-144">**Ваши домены:** отправители спуфинга во внутренних доменах.</span><span class="sxs-lookup"><span data-stu-id="89cb9-144">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="89cb9-145">**Внешние домены:** отправители, спуфинга пользователей во внешних доменах.</span><span class="sxs-lookup"><span data-stu-id="89cb9-145">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="89cb9-146">Щелкните ![ значок ](../../media/scc-expand-icon.png) «Развернуть» в **столбце "Разрешено спуфинг?".**</span><span class="sxs-lookup"><span data-stu-id="89cb9-146">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="89cb9-147">Выберите **"Да",** чтобы разрешить поддельному отправителю или **выберите "Нет",** чтобы отметить сообщение как поддельное.</span><span class="sxs-lookup"><span data-stu-id="89cb9-147">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="89cb9-148">Действием управляет стандартная политика защиты от фишинга или настраиваемые политики защиты от фишинга ATP (значение по умолчанию — **"Переместить сообщение в папку нежелательной почты").**</span><span class="sxs-lookup"><span data-stu-id="89cb9-148">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="89cb9-149">Дополнительные сведения см. в статье ["Параметры подделки" в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="89cb9-149">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Снимок экрана: всплывающие элементы отправителя и то, разрешено ли спуфинг отправителю подмену](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="89cb9-151">Представленные столбцы и значения поясняются в приведенном ниже списке.</span><span class="sxs-lookup"><span data-stu-id="89cb9-151">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="89cb9-152">**Поддельный пользователь**— поддельная учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="89cb9-152">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="89cb9-153">Это отправитель сообщения в адресе отправителя (также называемом `5322.From` адресом), который отображается в почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="89cb9-153">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="89cb9-154">Этот адрес не проверяется с помощью инфраструктуры политики отправителей.</span><span class="sxs-lookup"><span data-stu-id="89cb9-154">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="89cb9-155">На **вкладке "Домены"** значение содержит один электронный адрес, или если исходный почтовый сервер подделывает несколько учетных записей пользователей, оно **содержит более одной.**</span><span class="sxs-lookup"><span data-stu-id="89cb9-155">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="89cb9-156">На **вкладке "Внешние** домены" значение содержит домен поддельного пользователя, а не полный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="89cb9-156">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="89cb9-157">**Инфраструктура отправки**— домен, обнаруженный в обратном поиске DNS (запись PTR) IP-адреса исходного почтового сервера электронной почты или IP-адрес, если у исходного сервера нет записи PTR.</span><span class="sxs-lookup"><span data-stu-id="89cb9-157">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="89cb9-158">Дополнительные сведения об источниках сообщений и отправителях сообщений см. в [обзоре стандартов сообщений электронной почты.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="89cb9-158">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="89cb9-159">**Количество сообщений:** количество сообщений из инфраструктуры отправки в вашу организацию, содержащих указанных поддельных отправителей или отправителей за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="89cb9-159">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="89cb9-160">**# of user complaints**: Complaints file by your users against the this sender within the last 30 days.</span><span class="sxs-lookup"><span data-stu-id="89cb9-160">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="89cb9-161">Жалобы обычно представлены в виде отправки спама корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="89cb9-161">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="89cb9-162">**Результат проверки**подлинности: одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="89cb9-162">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="89cb9-163">**Пассивный:** отправитель прошел проверку подлинности электронной почты отправителя (SPF или DKIM).</span><span class="sxs-lookup"><span data-stu-id="89cb9-163">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="89cb9-164">**Ошибка:** отправитель не прошел проверку подлинности отправителя в EOP.</span><span class="sxs-lookup"><span data-stu-id="89cb9-164">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="89cb9-165">**Неизвестно:** результат этих проверок неизвестен.</span><span class="sxs-lookup"><span data-stu-id="89cb9-165">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="89cb9-166">**Решение, установленное:** отображает, кто выявил, разрешена ли инфраструктура отправки подделки пользователя:</span><span class="sxs-lookup"><span data-stu-id="89cb9-166">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="89cb9-167">**Spoof intelligence policy** (automatic)</span><span class="sxs-lookup"><span data-stu-id="89cb9-167">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="89cb9-168">**Администратор** (вручную)</span><span class="sxs-lookup"><span data-stu-id="89cb9-168">**Admin** (manual)</span></span>

   - <span data-ttu-id="89cb9-169">**Last seen:** Дата последнего получения сообщения от отправляющих инфраструктуры, содержащей поддельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="89cb9-169">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="89cb9-170">**Разрешено спуфилинг?** Значения, которые отображаются здесь:</span><span class="sxs-lookup"><span data-stu-id="89cb9-170">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="89cb9-171">**Да.** Сообщения из комбинации поддельных пользователей и инфраструктуры отправки разрешены и не считаются поддельной электронной почтой.</span><span class="sxs-lookup"><span data-stu-id="89cb9-171">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="89cb9-172">**Нет:** сообщения от сочетания поддельного пользователя и инфраструктуры отправки помечаются как поддельные.</span><span class="sxs-lookup"><span data-stu-id="89cb9-172">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="89cb9-173">Действием управляет стандартная политика защиты от фишинга или настраиваемые политики защиты от фишинга ATP (значение по умолчанию — **"Переместить сообщение в папку нежелательной почты").**</span><span class="sxs-lookup"><span data-stu-id="89cb9-173">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="89cb9-174">Дополнительные сведения см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="89cb9-174">See the next section for more information.</span></span>

     - <span data-ttu-id="89cb9-175">**Some users** **(your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others not.</span><span class="sxs-lookup"><span data-stu-id="89cb9-175">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="89cb9-176">Используйте **вкладку "Подробные** сведения" для просмотра определенных адресов.</span><span class="sxs-lookup"><span data-stu-id="89cb9-176">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="89cb9-177">В нижней части страницы нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="89cb9-177">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="89cb9-178">Управление поддельных отправителями с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="89cb9-178">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="89cb9-179">Чтобы просмотреть разрешенных и заблокированных отправителей в аналитике спуфинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="89cb9-179">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="89cb9-180">В этом примере возвращаются подробные сведения обо всех отправителях, которым разрешено подделывать пользователей в ваших доменах.</span><span class="sxs-lookup"><span data-stu-id="89cb9-180">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="89cb9-181">Дополнительные сведения о синтаксисе и параметрах см. в [статье О Get-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="89cb9-181">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="89cb9-182">Чтобы настроить разрешенных и заблокированных отправителей для аналитики спуфинга, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="89cb9-182">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="89cb9-183">Чтобы записать текущий список обнаруженных поддельных отправителей, записав выходные **данные командлета Get-PhishFilterPolicy** в CSV-файл:</span><span class="sxs-lookup"><span data-stu-id="89cb9-183">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="89cb9-184">Измените CSV-файл, чтобы добавить или изменить **значения SpoofedUser** (электронный адрес) **и AllowedToSpoof** (Да или Нет).</span><span class="sxs-lookup"><span data-stu-id="89cb9-184">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="89cb9-185">Сохраните файл, прочтите файл и сохраните его содержимое в виде переменной с именем `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="89cb9-185">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="89cb9-186">Используйте `$UpdateSpoofedSenders` переменную для настройки политики аналитики подделок:</span><span class="sxs-lookup"><span data-stu-id="89cb9-186">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="89cb9-187">Дополнительные сведения о синтаксисе и параметрах [см. в статье О Set-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="89cb9-187">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="89cb9-188">Использование Центра безопасности & для настройки аналитики спуфинга</span><span class="sxs-lookup"><span data-stu-id="89cb9-188">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="89cb9-189">Параметры конфигурации для аналитики подделок описаны в параметрах [подделок в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="89cb9-189">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="89cb9-190">Вы можете настроить параметры аналитики подделок в политике защиты от фишинга по умолчанию, а также в настраиваемых политиках.</span><span class="sxs-lookup"><span data-stu-id="89cb9-190">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="89cb9-191">Инструкции по подписке см. в одной из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="89cb9-191">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="89cb9-192">[Настройте политики защиты от фишинга в EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="89cb9-192">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="89cb9-193">[Настройка политик защиты от фишинга в ATP в Microsoft 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="89cb9-193">[Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="89cb9-194">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="89cb9-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="89cb9-195">Чтобы убедиться, что вы настроили аналитику спуфинга с отправителями, которым разрешено спуфинг, а также настроили параметры аналитики спуфинга, используйте любой из следующих шагов:</span><span class="sxs-lookup"><span data-stu-id="89cb9-195">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="89cb9-196">В Центре безопасности & выберите "Защита от нежелательной почты" **разверните** "Показать отправителей, подделавших ся подделки", выбрав \> **Policy** \> **Anti-spam** \> **Spoof intelligence policy** \> **Show me senders I already reviewed** \> вкладку **"Домены"** или **"Внешние домены" и** проверьте значение отправителя, к которому можно подменить **подделку?**</span><span class="sxs-lookup"><span data-stu-id="89cb9-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="89cb9-197">В PowerShell выполните следующие команды, чтобы просмотреть отправителей, которым разрешено использовать спуфинг:</span><span class="sxs-lookup"><span data-stu-id="89cb9-197">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="89cb9-198">В PowerShell выполните следующую команду, чтобы экспортировать список всех поддельных отправителей в CSV-файл:</span><span class="sxs-lookup"><span data-stu-id="89cb9-198">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="89cb9-199">В Центре безопасности & **Threat management** выберите защиту от фишинга политики управления угрозами или защиту от \> **Policy** \> **Anti-phishing** **фишинга ATP.** Выполните одно из следующих действий:  </span><span class="sxs-lookup"><span data-stu-id="89cb9-199">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="89cb9-200">Выберите политику из списка.</span><span class="sxs-lookup"><span data-stu-id="89cb9-200">Select a policy from the list.</span></span> <span data-ttu-id="89cb9-201">В появившемся всплывающем окне проверьте значения в разделе **"Подделка".**</span><span class="sxs-lookup"><span data-stu-id="89cb9-201">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="89cb9-202">Щелкните **"Политика по умолчанию".**</span><span class="sxs-lookup"><span data-stu-id="89cb9-202">Click **Default policy**.</span></span> <span data-ttu-id="89cb9-203">В появившемся всплывающем окне проверьте значения в разделе **"Подделка".**</span><span class="sxs-lookup"><span data-stu-id="89cb9-203">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="89cb9-204">В Exchange Online PowerShell замените параметры по умолчанию для антифишинговых данных Office 365 или именем \<Name\> настраиваемой политики и выполните следующую команду для проверки параметров:</span><span class="sxs-lookup"><span data-stu-id="89cb9-204">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="89cb9-205">Другие способы управления спуфикацией и фишингом</span><span class="sxs-lookup"><span data-stu-id="89cb9-205">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="89cb9-206">Будйте диффужны для спуфинга и защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="89cb9-206">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="89cb9-207">Ниже приведены связанные способы проверить отправителей, подделывающие ваш домен, и предотвратить повреждение вашей организации.</span><span class="sxs-lookup"><span data-stu-id="89cb9-207">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="89cb9-208">Проверьте отчет **о поддельной почте.**</span><span class="sxs-lookup"><span data-stu-id="89cb9-208">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="89cb9-209">Этот отчет часто используется для просмотра поддельных отправителей и управления ими.</span><span class="sxs-lookup"><span data-stu-id="89cb9-209">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="89cb9-210">Дополнительные сведения см. в [отчете об обнаружении подделок.](view-email-security-reports.md#spoof-detections-report)</span><span class="sxs-lookup"><span data-stu-id="89cb9-210">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="89cb9-211">Проверьте конфигурацию инфраструктуры политики отправителей (SPF).</span><span class="sxs-lookup"><span data-stu-id="89cb9-211">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="89cb9-212">Для быстрого ознакомления с SPF и его быстрой настройки см. раздел [Настройка SPF в Microsoft 365, чтобы предотвратить подделку](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="89cb9-212">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="89cb9-213">Дополнительные сведения об использовании инфраструктуры политики отправителей в Office 365, рекомендации по устранению неполадок и инструкции для нестандартных, в том числе гибридных, развертываний см. в статье [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="89cb9-213">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="89cb9-214">Просмотрите конфигурацию DomainKeys Identified Mail (DKIM).</span><span class="sxs-lookup"><span data-stu-id="89cb9-214">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="89cb9-215">Используйте DKIM вместе с инфраструктурой политики f и DMARC, чтобы предотвратить отправку сообщений, поступающих в ваш домен, а также в том случае, если злоумышленники поступают из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="89cb9-215">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="89cb9-216">DKIM позволяет добавлять цифровую подпись в заголовки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="89cb9-216">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="89cb9-217">Дополнительные сведения см. в [статье, посвященной DKIM, для проверки исходящей электронной почты, отправляемой с личного домена в Office 365.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="89cb9-217">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="89cb9-218">Проверьте конфигурацию протокола DMARC с доменными сообщениями, отчетов и проверки подлинности сообщений на основе домена.</span><span class="sxs-lookup"><span data-stu-id="89cb9-218">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="89cb9-219">Реализация DMARC в сочетании с SPF и DKIM обеспечивает дополнительную защиту от спуфинга и фишинга.</span><span class="sxs-lookup"><span data-stu-id="89cb9-219">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="89cb9-220">DMARC помогает получающим почтовым системам определить, что делать с сообщениями, отправленными из вашего домена, которые не прошли проверки SPF или DKIM.</span><span class="sxs-lookup"><span data-stu-id="89cb9-220">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="89cb9-221">Дополнительные сведения см. в статье [Использование DMARC для проверки электронной почты в Office 365.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="89cb9-221">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
