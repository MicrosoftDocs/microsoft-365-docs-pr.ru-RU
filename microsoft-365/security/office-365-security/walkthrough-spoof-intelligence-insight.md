---
title: Управление поддельными отправителями с помощью политики подмены сведений и анализа подмены сведений
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как использовать политику подмены сведений и представление о подмене сведений, чтобы разрешить или заблокировать обнаруженных поддельных отправителей.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0e5c83bc50197e30c12f8f7aeedc83930d7ff5e
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793212"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a><span data-ttu-id="c3859-103">Управление поддельными отправителями с помощью политики подмены сведений и анализа подмены сведений в EOP</span><span class="sxs-lookup"><span data-stu-id="c3859-103">Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3859-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c3859-104">**Applies to**</span></span>
- [<span data-ttu-id="c3859-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c3859-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c3859-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3859-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="c3859-107">В этой статье описывается старый опыт управления подменой отправитель, который заменяется.</span><span class="sxs-lookup"><span data-stu-id="c3859-107">This article describes the older spoofed sender management experience that's being replaced.</span></span> <span data-ttu-id="c3859-108">Дополнительные сведения о новом опыте см. в дополнительных сведениях [об аналитике Spoof в EOP](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="c3859-108">For more information about the new experience, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span></span>

<span data-ttu-id="c3859-109">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков входящие сообщения электронной почты автоматически защищены от подмены EOP с октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="c3859-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="c3859-110">EOP использует **spoof intelligence** как часть общей защиты организации от фишинга.</span><span class="sxs-lookup"><span data-stu-id="c3859-110">EOP uses **spoof intelligence** as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="c3859-111">Дополнительные сведения см. в дополнительных сведениях в области защиты от подмены в [EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c3859-111">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="c3859-112">Политика разведки по умолчанию (и **только)** позволяет убедиться, что подмена электронной почты, отправленная законными отправителями, не будет впадать в фильтры нежелательной почты EOP, защищая пользователей от нежелательной почты или фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="c3859-112">The default (and only) **spoof intelligence policy** helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters while protecting your users from spam or phishing attacks.</span></span> <span data-ttu-id="c3859-113">Кроме того, с помощью аналитики **Spoof** можно быстро определить, какие внешние отправители законно отправляют вам неавентированные сообщения электронной почты (сообщения из доменов, которые не проходят проверки SPF, DKIM или DMARC).</span><span class="sxs-lookup"><span data-stu-id="c3859-113">You can also use the **Spoof intelligence insight** to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="c3859-114">Вы можете управлять спуф-аналитикой в Центре обеспечения безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без Exchange Online почтовых ящиков).</span><span class="sxs-lookup"><span data-stu-id="c3859-114">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3859-115">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c3859-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3859-116">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c3859-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span>
  - <span data-ttu-id="c3859-117">Чтобы перейти непосредственно на страницу параметры **"Анти-нежелательной** почты" для политики подмены сведений, используйте <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="c3859-117">To go directly to the **Anti-spam settings** page for the spoof intelligence policy, use <https://protection.office.com/antispam>.</span></span>
  - <span data-ttu-id="c3859-118">Чтобы перейти непосредственно на страницу панели **мониторинга** безопасности, чтобы получить представление о подмене сведений, используйте <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="c3859-118">To go directly to the **Security dashboard** page for the spoof intelligence insight, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

- <span data-ttu-id="c3859-119">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3859-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c3859-120">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3859-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c3859-121">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="c3859-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c3859-122">Чтобы изменить политику подмены сведений или включить или отключить подмену сведений, необходимо быть членом группы ролей администратора организации или **администратора** безопасности. </span><span class="sxs-lookup"><span data-stu-id="c3859-122">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c3859-123">Для доступа только для чтения к политике подмены сведений необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="c3859-123">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c3859-124">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="c3859-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="c3859-125">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="c3859-125">**Notes**:</span></span>

  - <span data-ttu-id="c3859-126">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3859-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c3859-127">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c3859-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="c3859-128">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="c3859-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="c3859-129">Параметры spoof intelligence описаны в [параметрах Spoof в политиках защиты от фишинга.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="c3859-129">The options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="c3859-130">Вы можете включить, отключить и настроить параметры подмены сведений в политиках защиты от фишинга.</span><span class="sxs-lookup"><span data-stu-id="c3859-130">You can enable, disable, and configure the spoof intelligence settings in anti-phishing policies.</span></span> <span data-ttu-id="c3859-131">Инструкции по подписке см. в одном из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="c3859-131">For instructions based on your subscription, see one of the following topics:</span></span>

  - <span data-ttu-id="c3859-132">[Настройка политик защиты от фишинга в EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="c3859-132">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>
  - <span data-ttu-id="c3859-133">[Настройка политик защиты от фишинга в Microsoft Defender для](configure-atp-anti-phishing-policies.md)Office 365.</span><span class="sxs-lookup"><span data-stu-id="c3859-133">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="c3859-134">Рекомендуемые параметры для подмены сведений см. в рекомендациях EOP по борьбе [с фишинговыми политиками.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="c3859-134">For our recommended settings for spoof intelligence, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

## <a name="manage-spoofed-senders"></a><span data-ttu-id="c3859-135">Управление поддельными отправителями</span><span class="sxs-lookup"><span data-stu-id="c3859-135">Manage spoofed senders</span></span>

<span data-ttu-id="c3859-136">Существует два способа разрешить и заблокировать поддельных отправителей:</span><span class="sxs-lookup"><span data-stu-id="c3859-136">There are two ways to allow and block spoofed senders:</span></span>

- [<span data-ttu-id="c3859-137">Использование политики подмены сведений</span><span class="sxs-lookup"><span data-stu-id="c3859-137">Use the spoof intelligence policy</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [<span data-ttu-id="c3859-138">Используйте представление о подмене сведений</span><span class="sxs-lookup"><span data-stu-id="c3859-138">Use the spoof intelligence insight</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a><span data-ttu-id="c3859-139">Управление поддельными отправителями в политике подмены сведений</span><span class="sxs-lookup"><span data-stu-id="c3859-139">Manage spoofed senders in the spoof intelligence policy</span></span>

1. <span data-ttu-id="c3859-140">В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.</span><span class="sxs-lookup"><span data-stu-id="c3859-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c3859-141">На странице **Параметры для борьбы со спамом** нажмите кнопку ![ Расширение значка, ](../../media/scc-expand-icon.png) чтобы расширить политику **разведки Spoof**.</span><span class="sxs-lookup"><span data-stu-id="c3859-141">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Выберите политику подмены сведений](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="c3859-143">Сделайте один из следующих выборов:</span><span class="sxs-lookup"><span data-stu-id="c3859-143">Make one of the following selections:</span></span>

   - <span data-ttu-id="c3859-144">**Просмотр новых отправителей**</span><span class="sxs-lookup"><span data-stu-id="c3859-144">**Review new senders**</span></span>
   - <span data-ttu-id="c3859-145">**Покажи мне отправителей, которые я уже просмотрел**</span><span class="sxs-lookup"><span data-stu-id="c3859-145">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="c3859-146">В поле **Решить, разрешено** ли этим отправителям подмену вылетов пользователей, которые появляются, выберите одну из следующих вкладок:</span><span class="sxs-lookup"><span data-stu-id="c3859-146">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="c3859-147">**Домены.** Отправители, которые подменяют пользователей во внутренних доменах.</span><span class="sxs-lookup"><span data-stu-id="c3859-147">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="c3859-148">**Внешние домены.** Отправители спуфинг пользователей во внешних доменах.</span><span class="sxs-lookup"><span data-stu-id="c3859-148">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="c3859-149">Щелкните ![ значок Расширение ](../../media/scc-expand-icon.png) в **столбце Разрешено подмены?**</span><span class="sxs-lookup"><span data-stu-id="c3859-149">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="c3859-150">Выберите **Да,** чтобы разрешить подмену отправитель, или выберите **Нет,** чтобы пометить сообщение как поддельный.</span><span class="sxs-lookup"><span data-stu-id="c3859-150">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="c3859-151">Действие контролируется политикой защиты от фишинга по умолчанию или настраиваемой политикой защиты от фишинга (по умолчанию значение **Move message to Junk Email folder).**</span><span class="sxs-lookup"><span data-stu-id="c3859-151">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="c3859-152">Дополнительные сведения см. в статье [Параметры фишинга в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="c3859-152">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Снимок экрана, показывающий вылет поддельных отправителей и разрешено ли подмене отправителям](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="c3859-154">Столбцы и значения, которые вы видите, объясняются в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="c3859-154">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="c3859-155">**Spoofed user:** The user account that's being spoofed.</span><span class="sxs-lookup"><span data-stu-id="c3859-155">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="c3859-156">Это отправитель сообщений в адресе From (также известном как адрес), который отображается `5322.From` в клиентах электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c3859-156">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="c3859-157">Подлинность этого адреса не проверяется SPF.</span><span class="sxs-lookup"><span data-stu-id="c3859-157">The validity of this address is not checked by SPF.</span></span>
     - <span data-ttu-id="c3859-158">На **вкладке Your Domains** значение содержит один адрес электронной почты, или если исходный сервер электронной почты подменит несколько учетных записей пользователей, он содержит несколько **.**</span><span class="sxs-lookup"><span data-stu-id="c3859-158">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>
     - <span data-ttu-id="c3859-159">На **вкладке Внешние домены** значение содержит домен подмены пользователя, а не полный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c3859-159">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="c3859-160">**Отправка** инфраструктуры. Домен, найденный в обратном DNS-сервере (запись PTR) IP-адреса сервера электронной почты источника.</span><span class="sxs-lookup"><span data-stu-id="c3859-160">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="c3859-161">Если исходный IP-адрес не имеет записи PTR, инфраструктура отправки определена как \<source IP\> /24 (например, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="c3859-161">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="c3859-162">Дополнительные сведения об источниках сообщений и отправителей сообщений см. [в обзоре стандартов сообщений электронной почты.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="c3859-162">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="c3859-163">**# сообщений.** Количество сообщений из инфраструктуры отправки в организацию, содержащих указанный поддельный отправитель или отправитель в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c3859-163">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="c3859-164">**# жалоб пользователей.** Жалобы, поданных пользователями на этого отправитель в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c3859-164">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="c3859-165">Жалобы обычно в виде нежелательной отправки в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c3859-165">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="c3859-166">**Результат проверки подлинности:** одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c3859-166">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="c3859-167">**Пройдено.** Отправитель прошел проверки проверки подлинности электронной почты отправитель (SPF или DKIM).</span><span class="sxs-lookup"><span data-stu-id="c3859-167">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="c3859-168">**Failed:** The sender failed EOP sender authentication checks.</span><span class="sxs-lookup"><span data-stu-id="c3859-168">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="c3859-169">**Неизвестно.** Результат этих проверок неизвестен.</span><span class="sxs-lookup"><span data-stu-id="c3859-169">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="c3859-170">**Решение,** запредельное: показывает, кто определяет, разрешено ли инфраструктуре отправки подменить пользователя:</span><span class="sxs-lookup"><span data-stu-id="c3859-170">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="c3859-171">**Политика разведки spoof** (автоматическая)</span><span class="sxs-lookup"><span data-stu-id="c3859-171">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="c3859-172">**Администратор** (вручную)</span><span class="sxs-lookup"><span data-stu-id="c3859-172">**Admin** (manual)</span></span>

   - <span data-ttu-id="c3859-173">**Последний просмотр:** последняя дата, когда сообщение было получено из инфраструктуры отправки, содержавшей подмену пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3859-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="c3859-174">**Разрешено подмену?**: Значения, которые вы видите здесь:</span><span class="sxs-lookup"><span data-stu-id="c3859-174">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="c3859-175">**Да.** Сообщения из сочетания подмены пользователя и инфраструктуры отправки разрешены и не рассматриваются как поддельные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c3859-175">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="c3859-176">**Нет.** Сообщения из сочетания подмены пользователя и инфраструктуры отправки помечены как поддельные.</span><span class="sxs-lookup"><span data-stu-id="c3859-176">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="c3859-177">Действие контролируется политикой защиты от фишинга по умолчанию или настраиваемой политикой защиты от фишинга (по умолчанию значение **Move message to Junk Email folder).**</span><span class="sxs-lookup"><span data-stu-id="c3859-177">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="c3859-178">Дополнительные сведения см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="c3859-178">See the next section for more information.</span></span>

     - <span data-ttu-id="c3859-179">**Некоторые пользователи** **(только** вкладка Домены): инфраструктура отправки подмены нескольких пользователей, где некоторые подмены пользователей разрешены, а другие нет.</span><span class="sxs-lookup"><span data-stu-id="c3859-179">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="c3859-180">Используйте **вкладку Подробные,** чтобы увидеть конкретные адреса.</span><span class="sxs-lookup"><span data-stu-id="c3859-180">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="c3859-181">В нижней части страницы нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c3859-181">At the bottom of the page, click **Save**.</span></span>

#### <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="c3859-182">Использование PowerShell для управления поддельными отправителями</span><span class="sxs-lookup"><span data-stu-id="c3859-182">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="c3859-183">Чтобы просмотреть разрешенных и заблокированных отправителей в спуф-аналитике, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c3859-183">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="c3859-184">В этом примере возвращаются подробные сведения обо всех отправителей, которые могут подменять пользователей в доменах.</span><span class="sxs-lookup"><span data-stu-id="c3859-184">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="c3859-185">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-PhishFilterPolicy.](/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="c3859-185">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="c3859-186">Чтобы настроить разрешенных и заблокированных отправителей в спуф-аналитике, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c3859-186">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="c3859-187">Захват текущего списка обнаруженных поддельных отправителей, написав вывод **командлета Get-PhishFilterPolicy** в CSV-файл, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c3859-187">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file by running the following command:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="c3859-188">Измените CSV-файл, чтобы добавить или изменить следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c3859-188">Edit the CSV file to add or modify the following values:</span></span>
   - <span data-ttu-id="c3859-189">**Отправитель** (домен в записи PTR сервера источника или IP/24-адрес)</span><span class="sxs-lookup"><span data-stu-id="c3859-189">**Sender** (domain in source server's PTR record or IP/24 address)</span></span>
   - <span data-ttu-id="c3859-190">**SpoofedUser**: Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c3859-190">**SpoofedUser**: One of the following values:</span></span>
     - <span data-ttu-id="c3859-191">Адрес электронной почты внутреннего пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3859-191">The internal user's email address.</span></span>
     - <span data-ttu-id="c3859-192">Домен электронной почты внешнего пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3859-192">The external user's email domain.</span></span>
     - <span data-ttu-id="c3859-193">Пустое значение, которое указывает, что вы хотите заблокировать или разрешить любые и все поддельные сообщения от указанного отправитель, независимо от подмены адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c3859-193">A blank value that indicates you want to block or allow any and all spoofed messages from the specified **Sender**, regardless of the spoofed email address.</span></span>
   - <span data-ttu-id="c3859-194">**AllowedToSpoof** (Да или Нет)</span><span class="sxs-lookup"><span data-stu-id="c3859-194">**AllowedToSpoof** (Yes or No)</span></span>
   - <span data-ttu-id="c3859-195">**SpoofType** (внутренняя или внешняя)</span><span class="sxs-lookup"><span data-stu-id="c3859-195">**SpoofType** (Internal or External)</span></span>

   <span data-ttu-id="c3859-196">Сохраните файл, прочитайте файл и сохраните содержимое в качестве переменной с именем, запуская `$UpdateSpoofedSenders` следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c3859-196">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders` by running the following command:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="c3859-197">Используйте `$UpdateSpoofedSenders` переменную для настройки политики подмены сведений, выполив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c3859-197">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy by running the following command:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="c3859-198">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-PhishFilterPolicy.](/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="c3859-198">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a><span data-ttu-id="c3859-199">Управление поддельными отправителями в анализе подмены сведений</span><span class="sxs-lookup"><span data-stu-id="c3859-199">Manage spoofed senders in the spoof intelligence insight</span></span>

1. <span data-ttu-id="c3859-200">В Центре & безопасности перейдите на панель **мониторинга** управления \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c3859-200">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard**.</span></span>

2. <span data-ttu-id="c3859-201">В **строке Insights** посмотрите один из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="c3859-201">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="c3859-202">**Вероятно, поддельные** домены в течение последних семи дней. Это представление указывает на то, что включена разведка подмены (она включена по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c3859-202">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="c3859-203">**Включить защиту от** подмены. Это представление указывает на отключение подмены сведений, а щелкнув по проницательности, вы сможете включить подмену сведений.</span><span class="sxs-lookup"><span data-stu-id="c3859-203">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="c3859-204">Сведения на панели мониторинга показывают такие сведения:</span><span class="sxs-lookup"><span data-stu-id="c3859-204">The insight on the dashboard shows you information like this:</span></span>

   ![Снимок экрана сведения о подмене сведений](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="c3859-206">Это представление имеет два режима:</span><span class="sxs-lookup"><span data-stu-id="c3859-206">This insight has two modes:</span></span>

   - <span data-ttu-id="c3859-207">**Режим Insight.** Если включена возможность подмены сведений, показано, сколько сообщений за последние семь дней были под влиянием наших возможностей подмены.</span><span class="sxs-lookup"><span data-stu-id="c3859-207">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="c3859-208">**Что делать,** если режим : Если подмена сведений отключена, то анализ показывает, сколько сообщений было бы повлияло на наши возможности подмены разведки за последние семь дней. </span><span class="sxs-lookup"><span data-stu-id="c3859-208">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="c3859-209">В любом случае подменные домены, отображаемые в проницательности, разделены на две **категории:** подозрительные домены и **неподозрительные домены.**</span><span class="sxs-lookup"><span data-stu-id="c3859-209">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="c3859-210">**Подозрительные домены:**</span><span class="sxs-lookup"><span data-stu-id="c3859-210">**Suspicious domains**:</span></span>
     - <span data-ttu-id="c3859-211">**Высоковероятная** подмена. Основываясь на исторических шаблонах отправки и оценке репутации доменов, мы уверены, что домены подмены, и сообщения из этих доменов, скорее всего, будут вредоносными.</span><span class="sxs-lookup"><span data-stu-id="c3859-211">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>
     - <span data-ttu-id="c3859-212">**Умеренное** подмена доверия. Основываясь на исторических шаблонах отправки и оценке репутации доменов, мы умеренно уверены, что домены являются спуфингом и что сообщения, отправленные из этих доменов, являются законными.</span><span class="sxs-lookup"><span data-stu-id="c3859-212">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="c3859-213">False positives are more likely in this category than high-confidence spoof.</span><span class="sxs-lookup"><span data-stu-id="c3859-213">False positives are more likely in this category than high-confidence spoof.</span></span>
   - <span data-ttu-id="c3859-214">**Не подозрительные домены:** домен не удалось явной проверки подлинности электронной почты [проверяет SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="c3859-214">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="c3859-215">Однако домен прошел неявную проверку подлинности электронной почты[(композитная проверка подлинности).](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="c3859-215">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="c3859-216">В результате в сообщении не было принято никаких действий по борьбе с подменой.</span><span class="sxs-lookup"><span data-stu-id="c3859-216">As a result, no anti-spoofing action was taken on the message.</span></span>

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a><span data-ttu-id="c3859-217">Просмотр подробных сведений о подозрительных и неназвинных доменах</span><span class="sxs-lookup"><span data-stu-id="c3859-217">View detailed information about suspicious and nonsuspicious domains</span></span>

1. <span data-ttu-id="c3859-218">На странице Spoof intelligence insight **щелкните** подозрительные домены или **неподозрительные** домены, чтобы перейти на страницу **аналитики Spoof.**</span><span class="sxs-lookup"><span data-stu-id="c3859-218">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="c3859-219">На **странице Spoof Intelligence содержатся** следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="c3859-219">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="c3859-220">**Поддельный домен:** домен подмены пользователя, отображаемого в поле **From** в клиентах электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c3859-220">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="c3859-221">Этот адрес также известен как `5322.From` адрес.</span><span class="sxs-lookup"><span data-stu-id="c3859-221">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="c3859-222">**Инфраструктура.** Также известная как _инфраструктура отправки._</span><span class="sxs-lookup"><span data-stu-id="c3859-222">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="c3859-223">Домен, найденный в обратной DNS-записи IP-адреса сервера электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c3859-223">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="c3859-224">Если исходный IP-адрес не имеет записи PTR, инфраструктура отправки определена как \<source IP\> /24 (например, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="c3859-224">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="c3859-225">**Количество сообщений:** количество сообщений из инфраструктуры отправки в организацию, содержащих указанный поддельный домен в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="c3859-225">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="c3859-226">**Последний просмотр:** последняя дата, когда сообщение было получено из инфраструктуры отправки, содержавшей поддельный домен.</span><span class="sxs-lookup"><span data-stu-id="c3859-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="c3859-227">**Тип Spoof.** Это значение **является внешним.**</span><span class="sxs-lookup"><span data-stu-id="c3859-227">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="c3859-228">**Разрешено подмену?**: Значения, которые вы видите здесь:</span><span class="sxs-lookup"><span data-stu-id="c3859-228">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="c3859-229">**Да.** Сообщения из сочетания подмены домена пользователя и инфраструктуры отправки разрешены и не рассматриваются как поддельные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c3859-229">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="c3859-230">**Нет.** Сообщения из сочетания подмены домена пользователя и инфраструктуры отправки помечены как поддельные.</span><span class="sxs-lookup"><span data-stu-id="c3859-230">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="c3859-231">Действие контролируется политикой защиты от фишинга по умолчанию или настраиваемой политикой защиты от фишинга (по умолчанию значение **Move message to Junk Email folder).**</span><span class="sxs-lookup"><span data-stu-id="c3859-231">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

2. <span data-ttu-id="c3859-232">Выберите элемент в списке, чтобы просмотреть сведения о паре инфраструктуры домена и отправки в вылете.</span><span class="sxs-lookup"><span data-stu-id="c3859-232">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="c3859-233">Эти сведения включают в себя следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="c3859-233">The information includes:</span></span>
   - <span data-ttu-id="c3859-234">Почему мы это поймали.</span><span class="sxs-lookup"><span data-stu-id="c3859-234">Why we caught this.</span></span>
   - <span data-ttu-id="c3859-235">Что нужно сделать.</span><span class="sxs-lookup"><span data-stu-id="c3859-235">What you need to do.</span></span>
   - <span data-ttu-id="c3859-236">Сводка домена.</span><span class="sxs-lookup"><span data-stu-id="c3859-236">A domain summary.</span></span>
   - <span data-ttu-id="c3859-237">WhoIs данные о отправителье.</span><span class="sxs-lookup"><span data-stu-id="c3859-237">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="c3859-238">Аналогичные сообщения, которые мы видели в вашем клиенте от того же отправителя.</span><span class="sxs-lookup"><span data-stu-id="c3859-238">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="c3859-239">Здесь вы также можете добавить или удалить пару инфраструктуры  домена или отправки из списка разрешенных для подмены отправитель разрешить.</span><span class="sxs-lookup"><span data-stu-id="c3859-239">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="c3859-240">Просто установите соответствующим образом перегиб.</span><span class="sxs-lookup"><span data-stu-id="c3859-240">Simply set the toggle accordingly.</span></span>

   ![Снимок экрана домена в области сведении Spoof](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c3859-242">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="c3859-242">How do you know these procedures worked?</span></span>

<span data-ttu-id="c3859-243">Чтобы убедиться, что вы настроили подмену сведений с отправителями, которым разрешено и не разрешено подмену, используйте любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c3859-243">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, use any of the following steps:</span></span>

- <span data-ttu-id="c3859-244">В Центре & безопасности перейдите к  политике управления угрозами, чтобы расширить политику \>  \>  \> Spoof intelligence select Show me senders I already reviewed select the Your  \>  \> **Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span><span class="sxs-lookup"><span data-stu-id="c3859-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="c3859-245">В PowerShell запустите следующие команды, чтобы просмотреть отправителей, которым разрешено и не разрешено подмену:</span><span class="sxs-lookup"><span data-stu-id="c3859-245">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="c3859-246">В PowerShell запустите следующую команду, чтобы экспортировать список всех поддельных отправителей в CSV-файл:</span><span class="sxs-lookup"><span data-stu-id="c3859-246">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
