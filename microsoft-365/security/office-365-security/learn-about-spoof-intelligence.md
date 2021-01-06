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
description: Администраторы могут узнать об аналитике спуфинга в Exchange Online Protection (EOP), где можно разрешить или заблокировать определенных поддельных отправителей.
ms.openlocfilehash: 603aeb35241f9808561593afa69b3b9ce7193fb0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760534"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="a39ce-103">Настройка аналитики спуфинга в EOP</span><span class="sxs-lookup"><span data-stu-id="a39ce-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a39ce-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online входящие сообщения электронной почты автоматически защищаются от спуфинга с помощью EOP в октябре 2018 г.</span><span class="sxs-lookup"><span data-stu-id="a39ce-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="a39ce-105">EOP использует аналитику спуфинга как часть общей защиты организации от фишинга.</span><span class="sxs-lookup"><span data-stu-id="a39ce-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="a39ce-106">Дополнительные сведения см. в подмене защиты от [спуфинга в EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="a39ce-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="a39ce-107">Когда отправитель подменит адрес электронной почты, он представляется пользователем в одном из доменов организации или пользователем внешнего домена, который отправляет электронную почту в организацию.</span><span class="sxs-lookup"><span data-stu-id="a39ce-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="a39ce-108">Злоумышленники, которые подменяют отправителей для отправки спама или фишинговой электронной почты, должны быть заблокированы.</span><span class="sxs-lookup"><span data-stu-id="a39ce-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="a39ce-109">Однако существуют сценарии спуфинга законных отправителей.</span><span class="sxs-lookup"><span data-stu-id="a39ce-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="a39ce-110">Например:</span><span class="sxs-lookup"><span data-stu-id="a39ce-110">For example:</span></span>

- <span data-ttu-id="a39ce-111">Возможные сценарии спуфинга внутренних доменов:</span><span class="sxs-lookup"><span data-stu-id="a39ce-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="a39ce-112">Сторонние отправители используют ваш домен для массовой рассылки почты своим сотрудникам для опросов компании.</span><span class="sxs-lookup"><span data-stu-id="a39ce-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="a39ce-113">Внешняя компания создает и отправляет рекламные обновления или обновления продуктов от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="a39ce-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="a39ce-114">Помощник регулярно должен отправлять электронную почту другому сотруднику в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a39ce-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="a39ce-115">Внутреннее приложение отправляет уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="a39ce-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="a39ce-116">Возможные сценарии спуфинга внешних доменов:</span><span class="sxs-lookup"><span data-stu-id="a39ce-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="a39ce-117">Отправитель находится в списке рассылки (также известном как список обсуждений), а список рассылки передает электронную почту от исходного отправитель всем участникам в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="a39ce-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="a39ce-118">Внешняя компания отправляет электронную почту от имени другой компании (например, автоматический отчет или компания программного обеспечения как услуга).</span><span class="sxs-lookup"><span data-stu-id="a39ce-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="a39ce-119">Аналитика спуфинга, а именно стандартная (и единственная) политика аналитики спуфинга, помогает гарантировать, что поддельные сообщения, отправляемые законными отправителями, не будут перехвачены в фильтрах нежелательной почты EOP или внешних системах электронной почты, а ваши пользователи будут защищены от спама или фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="a39ce-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="a39ce-120">Вы можете управлять спуфингом в Центре безопасности и & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="a39ce-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a39ce-121">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a39ce-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a39ce-122">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a39ce-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a39ce-123">Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="a39ce-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="a39ce-124">Чтобы перейти непосредственно на страницу защиты **от фишинга,** используйте <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="a39ce-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="a39ce-125">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a39ce-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a39ce-126">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a39ce-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a39ce-127">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="a39ce-127">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a39ce-128">Чтобы изменить политику аналитики спуфинга или включить или отключить аналитику спуфингов, необходимо быть членом группы ролей "Управление организацией" или "Администратор **безопасности".** </span><span class="sxs-lookup"><span data-stu-id="a39ce-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a39ce-129">Для доступа только для чтения к политике аналитики спуфингов необходимо  быть членом группы ролей **"Глобальное** чтение" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="a39ce-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a39ce-130">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a39ce-130">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="a39ce-131">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="a39ce-131">**Notes**:</span></span>

  - <span data-ttu-id="a39ce-132">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a39ce-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a39ce-133">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a39ce-133">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="a39ce-134">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="a39ce-134">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a39ce-135">Рекомендуемые параметры для аналитики спуфинга см. в настройках политики защиты от фишинга по умолчанию [для EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="a39ce-135">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="a39ce-136">Использование Центра безопасности & соответствия требованиям для управления поддельными отправителями</span><span class="sxs-lookup"><span data-stu-id="a39ce-136">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="a39ce-137">Если у вас есть подписка на Microsoft 365 корпоративный E5 или вы отдельно приобрели надстройку Microsoft Defender для Office [](walkthrough-spoof-intelligence-insight.md)365, вы также можете управлять отправителями, которые спуфингят ваш домен, с помощью аналитики спуфинга.</span><span class="sxs-lookup"><span data-stu-id="a39ce-137">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="a39ce-138">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="a39ce-138">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a39ce-139">На странице **"Параметры борьбы с нежелательной** почтой" щелкните значок "Развернуть", чтобы ![ развернуть политику ](../../media/scc-expand-icon.png) **аналитики спуфингов.**</span><span class="sxs-lookup"><span data-stu-id="a39ce-139">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Выбор политики аналитики спуфинга](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="a39ce-141">Сделайте одно из следующих выбором:</span><span class="sxs-lookup"><span data-stu-id="a39ce-141">Make one of the following selections:</span></span>

   - <span data-ttu-id="a39ce-142">**Просмотр новых отправителей**</span><span class="sxs-lookup"><span data-stu-id="a39ce-142">**Review new senders**</span></span>
   - <span data-ttu-id="a39ce-143">**Показать отправителей, которые я уже просмотрел**</span><span class="sxs-lookup"><span data-stu-id="a39ce-143">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="a39ce-144">В **окле "Решите, разрешено** ли этим отправителям спуфинг пользователей" выберите одну из следующих вкладок:</span><span class="sxs-lookup"><span data-stu-id="a39ce-144">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="a39ce-145">**Ваши домены**: отправителей, спуфинг пользователей во внутренних доменах.</span><span class="sxs-lookup"><span data-stu-id="a39ce-145">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="a39ce-146">**Внешние домены**: отправителей, спуфинг пользователей во внешних доменах.</span><span class="sxs-lookup"><span data-stu-id="a39ce-146">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="a39ce-147">Щелкните ![ значок ](../../media/scc-expand-icon.png) "Развернуть" в **столбце "Разрешено спуфинг".**</span><span class="sxs-lookup"><span data-stu-id="a39ce-147">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="a39ce-148">Выберите  "Да", чтобы разрешить поддельный отправитель, или **"Нет",** чтобы пометить сообщение как подмену.</span><span class="sxs-lookup"><span data-stu-id="a39ce-148">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="a39ce-149">Это действие контролируется политикой защиты от фишинга по умолчанию или пользовательскими политиками защиты от фишинга (значение по умолчанию — Переместить сообщение в папку нежелательной **почты).**</span><span class="sxs-lookup"><span data-stu-id="a39ce-149">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="a39ce-150">Дополнительные сведения см. в [параметрах спуфинга в](set-up-anti-phishing-policies.md#spoof-settings)политиках защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="a39ce-150">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Screenshot showing the spoofed senders flyout, and whether the sender is allowed to spoof](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="a39ce-152">Столбцы и значения, которые вы видите, поясняется в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="a39ce-152">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="a39ce-153">**Поддельный пользователь:** учетная запись пользователя, подменяемая.</span><span class="sxs-lookup"><span data-stu-id="a39ce-153">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="a39ce-154">Это отправитель сообщения в адресе отправитель (также известный как адрес), который отображается `5322.From` в почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="a39ce-154">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="a39ce-155">SPF не проверяет правильность этого адреса.</span><span class="sxs-lookup"><span data-stu-id="a39ce-155">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="a39ce-156">На **вкладке "Ваши** домены" значение содержит один адрес электронной почты, или если исходный почтовый сервер подменит несколько учетных записей пользователей, он содержит несколько **.**</span><span class="sxs-lookup"><span data-stu-id="a39ce-156">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="a39ce-157">На **вкладке "Внешние домены"** значение содержит домен подмены пользователя, а не полный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a39ce-157">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="a39ce-158">**Инфраструктура отправки**: домен, найденный в обратном DNS-подыске (запись PTR) IP-адреса сервера электронной почты источника.</span><span class="sxs-lookup"><span data-stu-id="a39ce-158">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="a39ce-159">Если исходный IP-адрес не имеет записи PTR, инфраструктура отправки будет определена как \<source IP\> /24 (например, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="a39ce-159">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="a39ce-160">Дополнительные сведения об источниках сообщений и отправителей сообщений см. в [обзоре стандартов сообщений электронной почты.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="a39ce-160">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="a39ce-161">**# сообщений:** количество сообщений из инфраструктуры отправки в организацию, содержащих указанного подмены отправителей или отправителей за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="a39ce-161">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="a39ce-162">**# жалоб пользователей:** жалобы, подавные вашими пользователями в отношении этого отправитель в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="a39ce-162">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="a39ce-163">Жалобы обычно имеют форму отправки нежелательной почты в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a39ce-163">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="a39ce-164">**Результат проверки подлинности:** одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="a39ce-164">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="a39ce-165">**Passed**: отправитель прошел проверки подлинности электронной почты (SPF или DKIM).</span><span class="sxs-lookup"><span data-stu-id="a39ce-165">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="a39ce-166">**Failed**: The sender failed EOP sender authentication checks.</span><span class="sxs-lookup"><span data-stu-id="a39ce-166">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="a39ce-167">**Неизвестно:** результат этих проверок неизвестен.</span><span class="sxs-lookup"><span data-stu-id="a39ce-167">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="a39ce-168">**Выбор решения:** показывает, кто определил, разрешено ли отправляемой инфраструктуре спуфинг пользователя:</span><span class="sxs-lookup"><span data-stu-id="a39ce-168">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="a39ce-169">**Политика аналитики спуфинга** (автоматически)</span><span class="sxs-lookup"><span data-stu-id="a39ce-169">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="a39ce-170">**Администратор** (вручную)</span><span class="sxs-lookup"><span data-stu-id="a39ce-170">**Admin** (manual)</span></span>

   - <span data-ttu-id="a39ce-171">**Last seen**: the last date when a message was received from the sending infrastructure that contains the spoofed user.</span><span class="sxs-lookup"><span data-stu-id="a39ce-171">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="a39ce-172">**Разрешено спуфинг?**</span><span class="sxs-lookup"><span data-stu-id="a39ce-172">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="a39ce-173">**Да:** сообщения из комбинации подмены пользователя и инфраструктуры отправки разрешены и не рассматриваются как поддельные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a39ce-173">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="a39ce-174">**Нет:** сообщения из комбинации подмены пользователя и инфраструктуры отправки помечаются как поддельные.</span><span class="sxs-lookup"><span data-stu-id="a39ce-174">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="a39ce-175">Это действие контролируется политикой защиты от фишинга по умолчанию или пользовательскими политиками защиты от фишинга (значение по умолчанию — Переместить сообщение в папку нежелательной **почты).**</span><span class="sxs-lookup"><span data-stu-id="a39ce-175">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="a39ce-176">Дополнительные сведения см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="a39ce-176">See the next section for more information.</span></span>

     - <span data-ttu-id="a39ce-177">**Некоторые пользователи** **(только вкладка** "Ваши домены"): инфраструктура отправки спуфинга нескольких пользователей, где одни поддельные пользователи разрешены, а другие — нет.</span><span class="sxs-lookup"><span data-stu-id="a39ce-177">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="a39ce-178">Используйте **вкладку "Подробные** сведения", чтобы увидеть конкретные адреса.</span><span class="sxs-lookup"><span data-stu-id="a39ce-178">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="a39ce-179">В нижней части страницы нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a39ce-179">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="a39ce-180">Использование PowerShell для управления поддельными отправителями</span><span class="sxs-lookup"><span data-stu-id="a39ce-180">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="a39ce-181">Чтобы просмотреть разрешенных и заблокированных отправителей в аналитике спуфинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a39ce-181">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="a39ce-182">В этом примере возвращаются подробные сведения обо всех отправителей, которые могут подменить пользователей в ваших доменах.</span><span class="sxs-lookup"><span data-stu-id="a39ce-182">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="a39ce-183">Подробные сведения о синтаксисах и параметрах см. в описании [Get-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="a39ce-183">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="a39ce-184">Чтобы настроить разрешенных и заблокированных отправителей в аналитике спуфингов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a39ce-184">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="a39ce-185">Зафиксировать текущий список обнаруженных поддельных отправителей, записав выходные данные с помощью cmdlet **Get-PhishFilterPolicy** в CSV-файл:</span><span class="sxs-lookup"><span data-stu-id="a39ce-185">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="a39ce-186">Измените CSV-файл, чтобы добавить или изменить значения **SpoofedUser** (адрес электронной почты) и **AllowedToSpoof** (Да или Нет).</span><span class="sxs-lookup"><span data-stu-id="a39ce-186">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="a39ce-187">Сохраните файл, прочитайте его и сохраните его содержимое в качестве переменной с именем `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="a39ce-187">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="a39ce-188">Используйте `$UpdateSpoofedSenders` переменную для настройки политики аналитики спуфингов:</span><span class="sxs-lookup"><span data-stu-id="a39ce-188">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="a39ce-189">Подробные сведения о синтаксисах и параметрах см. в [описании Set-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="a39ce-189">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="a39ce-190">Использование Центра безопасности & соответствия требованиям для настройки аналитики спуфингов</span><span class="sxs-lookup"><span data-stu-id="a39ce-190">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="a39ce-191">Параметры конфигурации для аналитики спуфинга описаны в параметрах спуфинга в политиках защиты от [фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="a39ce-191">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="a39ce-192">Параметры аналитики спуфинга можно настроить в политике защиты от фишинга по умолчанию, а также в настраиваемых политиках.</span><span class="sxs-lookup"><span data-stu-id="a39ce-192">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="a39ce-193">Инструкции по подписке см. в одном из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="a39ce-193">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="a39ce-194">[Настройка политик защиты от фишинга в EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a39ce-194">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="a39ce-195">[Настройка политик защиты от фишинга в Microsoft Defender для Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a39ce-195">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a39ce-196">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="a39ce-196">How do you know these procedures worked?</span></span>

<span data-ttu-id="a39ce-197">Чтобы убедиться, что вы настроили аналитику спуфинг для отправителей, которым разрешено и запрещено спуфинг, и что вы настроили параметры аналитики спуфингов, с помощью любого из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a39ce-197">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="a39ce-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** select Show me \> **senders I already reviewed** \> select the Your **Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span><span class="sxs-lookup"><span data-stu-id="a39ce-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="a39ce-199">В PowerShell запустите следующие команды, чтобы просмотреть отправителей, которым разрешено и запрещено спуфинг:</span><span class="sxs-lookup"><span data-stu-id="a39ce-199">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="a39ce-200">В PowerShell запустите следующую команду, чтобы экспортировать список всех поддельных отправителей в CSV-файл:</span><span class="sxs-lookup"><span data-stu-id="a39ce-200">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="a39ce-201">В Центре безопасности & соответствия требованиям  перейдите в центр защиты от фишинга политики управления угрозами или \>  \>  **atP** и сделайте следующее:  </span><span class="sxs-lookup"><span data-stu-id="a39ce-201">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="a39ce-202">Выберите политику в списке.</span><span class="sxs-lookup"><span data-stu-id="a39ce-202">Select a policy from the list.</span></span> <span data-ttu-id="a39ce-203">Проверьте значения в разделе **"Подмена".**</span><span class="sxs-lookup"><span data-stu-id="a39ce-203">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="a39ce-204">Щелкните **политику по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="a39ce-204">Click **Default policy**.</span></span> <span data-ttu-id="a39ce-205">Проверьте значения в разделе **"Подмена".**</span><span class="sxs-lookup"><span data-stu-id="a39ce-205">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="a39ce-206">В Exchange Online PowerShell замените office 365 antiPhish Default или имя настраиваемой политики и запустите следующую команду, чтобы \<Name\> проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="a39ce-206">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="a39ce-207">Другие способы управления спуфингом и фишингом</span><span class="sxs-lookup"><span data-stu-id="a39ce-207">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="a39ce-208">Будьте внимательны к спуфингу и защите от фишинга.</span><span class="sxs-lookup"><span data-stu-id="a39ce-208">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="a39ce-209">Вот связанные способы проверки отправителей на спуфинг домена и предотвращения их повреждения в организации.</span><span class="sxs-lookup"><span data-stu-id="a39ce-209">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="a39ce-210">Проверьте отчет **о подмене почты.**</span><span class="sxs-lookup"><span data-stu-id="a39ce-210">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="a39ce-211">Этот отчет можно часто использовать для просмотра поддельных отправителей и управления ими.</span><span class="sxs-lookup"><span data-stu-id="a39ce-211">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="a39ce-212">Подробнее см. в отчете [об обнаружении подмены.](view-email-security-reports.md#spoof-detections-report)</span><span class="sxs-lookup"><span data-stu-id="a39ce-212">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="a39ce-213">Просмотрите конфигурацию SPF.</span><span class="sxs-lookup"><span data-stu-id="a39ce-213">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="a39ce-214">Для быстрого ознакомления с SPF и его быстрой настройки см. раздел [Настройка SPF в Microsoft 365, чтобы предотвратить подделку](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="a39ce-214">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="a39ce-215">Дополнительные сведения об использовании инфраструктуры политики отправителей в Office 365, рекомендации по устранению неполадок и инструкции для нестандартных, в том числе гибридных, развертываний см. в статье [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="a39ce-215">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="a39ce-216">Просмотрите конфигурацию почты DomainKeys Identified Mail (DKIM).</span><span class="sxs-lookup"><span data-stu-id="a39ce-216">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="a39ce-217">Помимо SPF и DMARC, следует использовать DKIM, чтобы предотвратить отправку злоумышленниками сообщений, которые выглядят так, как будто они приходят из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="a39ce-217">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="a39ce-218">DKIM позволяет добавлять цифровую подпись в заголовки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a39ce-218">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="a39ce-219">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="a39ce-219">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="a39ce-220">Просмотрите конфигурацию проверки подлинности, отчетности и соответствия сообщений на основе домена (DMARC).</span><span class="sxs-lookup"><span data-stu-id="a39ce-220">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="a39ce-221">Реализация DMARC в сочетании с SPF и DKIM обеспечивает дополнительную защиту от спуфинга и фишинга.</span><span class="sxs-lookup"><span data-stu-id="a39ce-221">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="a39ce-222">DMARC помогает получающим почтовым системам определить, что делать с сообщениями, отправленными из вашего домена, которые не прошли проверки SPF или DKIM.</span><span class="sxs-lookup"><span data-stu-id="a39ce-222">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="a39ce-223">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="a39ce-223">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
