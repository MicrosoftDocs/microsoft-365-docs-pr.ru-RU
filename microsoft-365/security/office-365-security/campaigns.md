---
title: Представления кампаний в Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Ознакомьтесь с представлениями кампаний в Office 365 Advanced Threat Protection.
ms.openlocfilehash: 2d43b73a613ad6399a151a6bda39f236c7c913e8
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962764"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="33d42-103">Представления кампаний в Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="33d42-103">Campaign Views in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="33d42-104">Возможности, описанные в этой статье, в настоящее время доступны в предварительной версии и могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="33d42-104">The features described in this article are currently in preview and subject to change.</span></span>

<span data-ttu-id="33d42-105">Представления кампаний — это функция службы Advanced Threat Protection (ATP) в Центре безопасности и соответствия требованиям Office 365, которая определяет и классифицирует фишинговые атаки в службе.</span><span class="sxs-lookup"><span data-stu-id="33d42-105">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="33d42-106">Представления кампаний помогают:</span><span class="sxs-lookup"><span data-stu-id="33d42-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="33d42-107">эффективно анализировать фишинговые атаки и отвечать на них;</span><span class="sxs-lookup"><span data-stu-id="33d42-107">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="33d42-108">точнее устанавливать область, затронутую атакой;</span><span class="sxs-lookup"><span data-stu-id="33d42-108">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="33d42-109">демонстрировать проблему лицам, ответственным за принятие решений.</span><span class="sxs-lookup"><span data-stu-id="33d42-109">Show value to decision makers.</span></span>

<span data-ttu-id="33d42-110">Представления кампаний позволяют быстрее и полнее получить общую картину атаки.</span><span class="sxs-lookup"><span data-stu-id="33d42-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="33d42-111">Что такое кампания?</span><span class="sxs-lookup"><span data-stu-id="33d42-111">What is a ToolTip?</span></span>

<span data-ttu-id="33d42-112">Кампания — это скоординированная атака по электронной почте, направленная против одной или нескольких организаций.</span><span class="sxs-lookup"><span data-stu-id="33d42-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="33d42-113">На сегодняшний день атаки по электронной почте с целью украсть учетные данные и данные компании — это большой и прибыльный бизнес.</span><span class="sxs-lookup"><span data-stu-id="33d42-113">Today, email attacks that steal credentials and company data are a big and lucrative business.</span></span> <span data-ttu-id="33d42-114">По мере того, как совершенствуются технологии защиты от атак, злоумышленникам приходится менять свои методы, чтобы добиться продолжительного успеха.</span><span class="sxs-lookup"><span data-stu-id="33d42-114">As technologies increase in an effort to stop attacks, attackers are sophisticated enough to modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="33d42-115">Для выявления кампаний корпорация Майкрософт применяет во всех компонентах службы Office 365 во всем мире разнообразные данные и механизмы защиты от фишинга, спама и вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="33d42-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data and experience across the entire Office 365 service world-wide to identify campaigns.</span></span> <span data-ttu-id="33d42-116">Информация об атаке анализируется и систематизируется с учетом ряда факторов.</span><span class="sxs-lookup"><span data-stu-id="33d42-116">The attack information is analyzed and classified according to several factors.</span></span> <span data-ttu-id="33d42-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="33d42-117">For example:</span></span>

- <span data-ttu-id="33d42-118">**Источник атаки**: исходные адреса и домены электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="33d42-118">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="33d42-119">**Свойства сообщения атаки**: содержание, стиль и тон сообщений, выражающих атаку.</span><span class="sxs-lookup"><span data-stu-id="33d42-119">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="33d42-120">**Объекты атаки**: домены получателей, должности получателей (администраторы, руководители и т. д.), типы компаний (крупные, мелкие, государственные, частные и т. д.) и отрасли.</span><span class="sxs-lookup"><span data-stu-id="33d42-120">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="33d42-121">**Полезная нагрузка атаки**: вредоносные ссылки, вложения или другие данные.</span><span class="sxs-lookup"><span data-stu-id="33d42-121">**Attack payload**: Malicious links, attachments, or other payloads.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="33d42-122">Представления кампаний в Центре безопасности и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="33d42-122">Permissions in the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="33d42-123">Представления кампаний доступны в следующих разделах [Центра безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center):</span><span class="sxs-lookup"><span data-stu-id="33d42-123">Campaign Views is available in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) at the following locations:</span></span>

- <span data-ttu-id="33d42-124">**Управление угрозами** \> **Обозреватель** \> **Вид** \> **Фишинг** \> **Top campaign (предварительная версия)**</span><span class="sxs-lookup"><span data-stu-id="33d42-124">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Top campaign (Preview)**</span></span>

- <span data-ttu-id="33d42-125">**Управление угрозами** \> **Обозреватель** \> **Вид** \> **Вся почта** \> **Top campaign (предварительная версия)**</span><span class="sxs-lookup"><span data-stu-id="33d42-125">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Top campaign (Preview)**</span></span>

![Обзор кампаний в Центре безопасности и соответствия требованиям](../media/campaigns-overview.png)

> [!TIP]
> <span data-ttu-id="33d42-127">В настоящее время доступна только фильтрация по диапазону дат.</span><span class="sxs-lookup"><span data-stu-id="33d42-127">Currently, the only filtering that's available is the date range.</span></span> <span data-ttu-id="33d42-128">Если вы не видите данные кампаний, попробуйте изменить диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="33d42-128">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="33d42-129">На странице обзора приведена следующая информация о кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-129">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="33d42-130">**Название**</span><span class="sxs-lookup"><span data-stu-id="33d42-130">**Name**</span></span>

- <span data-ttu-id="33d42-131">**Образец темы**: строка темы одного из сообщений кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-131">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="33d42-132">Учтите, что не у _всех_ сообщений в кампании обязательно будет такая же строка темы.</span><span class="sxs-lookup"><span data-stu-id="33d42-132">Note that _all_ the messages in the campaign will not necessarily have this same subject line.</span></span>

- <span data-ttu-id="33d42-133">**Тип**: в настоящее время используется только тип **Фишинг**.</span><span class="sxs-lookup"><span data-stu-id="33d42-133">**Type**: Currently, this value will always be **Phish**.</span></span>

- <span data-ttu-id="33d42-134">**Подтип**: при наличии — бренд, который подвергается фишингу в этой кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-134">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="33d42-135">Если при обнаружении кампании используется технология ATP, перед подтипом ставится префикс **ATP-**.</span><span class="sxs-lookup"><span data-stu-id="33d42-135">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="33d42-136">**Получатели**: количество пользователей, которые подверглись этой кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-136">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="33d42-137">**Доставлено**: количество пользователей, в почтовые ящики которых пришли сообщения этой кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-137">**Delivered**: The number of users that received messages from this campaign into their Inbox.</span></span>

- <span data-ttu-id="33d42-138">**ID**: уникальный идентификатор кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-138">**ID**: A unique identifier for the campaign.</span></span>

<span data-ttu-id="33d42-139">Если щелкнуть название кампании, в всплывающем окне выводятся сведения о кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-139">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="33d42-140">Сведения о кампании</span><span class="sxs-lookup"><span data-stu-id="33d42-140">Campaign details</span></span>

<span data-ttu-id="33d42-141">В окне сведений о кампании представлена очень подробная информация о кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-141">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="33d42-142">Информация о кампании</span><span class="sxs-lookup"><span data-stu-id="33d42-142">Campaign information:</span></span>

  - <span data-ttu-id="33d42-143">**ID**: уникальный идентификатор кампании, указанный на экране обзора.</span><span class="sxs-lookup"><span data-stu-id="33d42-143">**ID**: The same unique identifier of the campaign from the overview screen.</span></span>

  - <span data-ttu-id="33d42-144">**Начало** и **Окончание**: выбранный диапазон данных.</span><span class="sxs-lookup"><span data-stu-id="33d42-144">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="33d42-145">**Влияние**: количество сообщений, отправленных в течение выбранного диапазона дат, сколько сообщений пришло в почтовые ящик и сколько пользователей перешло по URL-адресу, приведенному в фишинговом сообщении.</span><span class="sxs-lookup"><span data-stu-id="33d42-145">**Impact**: the number of messages sent in the date range you selected, how many were "inboxed" (that is, delivered to the Inbox), and how many users clicked on the URL payload in the phishing message.</span></span>

  - <span data-ttu-id="33d42-146">Временная шкала активности кампании: когда кампания была начата и закончена и изменение объема сообщений со временем.</span><span class="sxs-lookup"><span data-stu-id="33d42-146">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="33d42-147">Ход кампании</span><span class="sxs-lookup"><span data-stu-id="33d42-147">Campaign flow</span></span>

<span data-ttu-id="33d42-148">Важные сведения о кампании представлены на горизонтальной блок-схеме (так называемой схеме _Sankey_) в разделе **Поток**.</span><span class="sxs-lookup"><span data-stu-id="33d42-148">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="33d42-149">Эти сведения помогут вам изучить элементы кампании и ее потенциальное влияние на вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="33d42-149">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Сведения о кампании без переходов пользователей по URL-адресам](../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="33d42-151">Если навести указатель мыши на горизонтальную полоску на схеме, будет показано количество связанных с ней сообщений (например, сообщений с определенного исходного IP-адреса, сообщения из исходного IP-адреса с использованием указанного домена отправителя и т. д.).</span><span class="sxs-lookup"><span data-stu-id="33d42-151">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="33d42-152">Схема содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="33d42-152">The entry contains the following information:</span></span>

- <span data-ttu-id="33d42-153">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="33d42-153">**Sender IPs**</span></span>

- <span data-ttu-id="33d42-154">**Домены отправителей**</span><span class="sxs-lookup"><span data-stu-id="33d42-154">**Sender domains**</span></span>

- <span data-ttu-id="33d42-155">**Выводы по фильтрам**: эти значения относятся к выводам по доступным фильтрам против фишинга и спама, описанным в статье [Заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="33d42-155">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="33d42-156">Большой интерес здесь представляют значения **Разрешение клиента**, которые показывают, что настройка, заданная в организации, разрешила пропустить сообщение, которое иначе было бы заблокировано службой (например, домен в списке "Разрешенные отправители").</span><span class="sxs-lookup"><span data-stu-id="33d42-156">Of great interest here are the values **Tenant Allow**, which means a configured setting in the organization allowed a message through that would have been otherwise blocked by the service (for example, a domain in the Allowed Senders list).</span></span>

  - <span data-ttu-id="33d42-157">**Блокировка клиента**: это значение показывает, что настройка в вашей организации (например, запись в списке [Заблокированные отправители](create-block-sender-lists-in-office-365.md)) позволила как обнаружить сообщение, так и определить, куда оно было доставлено.</span><span class="sxs-lookup"><span data-stu-id="33d42-157">**Tenant Block**: This value indicates that a setting in your organization (for example, a domain entry in the [Blocked Senders list](create-block-sender-lists-in-office-365.md)) both detected the message and determined where it was delivered.</span></span> <span data-ttu-id="33d42-158">Для сообщений, которые не были помещены в карантин, проверьте настройки заблокированных отправителей, чтобы определить, почему сообщение было доставлено.</span><span class="sxs-lookup"><span data-stu-id="33d42-158">For messages that weren't quarantined, review your blocked senders settings to determine why the message was delivered.</span></span>

  - <span data-ttu-id="33d42-159">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="33d42-159">**Detected app**</span></span>

  - <span data-ttu-id="33d42-160">**Разрешение клиента**</span><span class="sxs-lookup"><span data-stu-id="33d42-160">**Tenant Allow**</span></span>

- <span data-ttu-id="33d42-161">**Места доставки**: скорее всего, вы захотите исследовать сообщения, которые действительно были доставлены получателям (в папку "Входящие" или в папку "Нежелательная почта"), даже если пользователи не переходили по URL-адресам, указанным в сообщении.</span><span class="sxs-lookup"><span data-stu-id="33d42-161">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="33d42-162">Вы также можете удалять сообщения из [карантина сообщений электронной почты в Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="33d42-162">You can also remove the quarantined messages from [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="33d42-163">**Нежелательная почта**</span><span class="sxs-lookup"><span data-stu-id="33d42-163">**Junk folder**</span></span>

  - <span data-ttu-id="33d42-164">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="33d42-164">**Quarantine**</span></span>

  - <span data-ttu-id="33d42-165">**Входящие**</span><span class="sxs-lookup"><span data-stu-id="33d42-165">**Inbox**</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="33d42-166">Переходы по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="33d42-166">URL clicks</span></span>

<span data-ttu-id="33d42-167">Всегда есть вероятность, что пользователь предпримет действия с сообщениями, доставленными в его папку "Входящие" или "Нежелательная почта" (то есть щелкнет вредоносный URL-адрес в сообщении).</span><span class="sxs-lookup"><span data-stu-id="33d42-167">There's always the chance that messages delivered to the recipient's Inbox or Junk Email folder can be acted upon by the user (that is, user will click on the malicious URL in the message).</span></span> <span data-ttu-id="33d42-168">Если пользователь ничего не делал, это уже небольшой успех, но вам определенно нужно установить, почему вообще вредоносное сообщение попало в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="33d42-168">If they haven't, that's a small measure of success, although you certainly need to determine why the harmful message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="33d42-169">Если пользователь щелкнул вредоносный URL-адрес, действия отображаются в области **Переходы по URL-адресу** на схеме.</span><span class="sxs-lookup"><span data-stu-id="33d42-169">If a user has clicked on the malicious URL, the actions are displayed in the **URL clicks** area of the diagram.</span></span>

![Сведения о кампании с переходами пользователей по URL-адресам](../media/campaign-details-with-recipient-actions.png)

- <span data-ttu-id="33d42-171">**Блокировка безопасных ссылок**: это значение показывает, что получатель щелкнул URL-адрес в сообщении, но он был заблокирован политиками [Безопасные ссылки ATP](atp-safe-links.md) вашей организации.</span><span class="sxs-lookup"><span data-stu-id="33d42-171">**Safe Links Block**: This value indicates the recipient clicked on the payload URL in the message, but it was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="33d42-172">**Отмена блокировки безопасных ссылок**: это значение также указывает, что получатель щелкнул URL-адрес в сообщении, политики «Безопасные ссылки ATP» попытались остановить его, но им было разрешено отменить блокировку.</span><span class="sxs-lookup"><span data-stu-id="33d42-172">**Safe Links Block Override**: This value also indicates the recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="33d42-173">Необходимо изучить ваши политики [Безопасные ссылки](set-up-atp-safe-links-policies.md) и узнать, почему пользователям разрешено отменять выводы "Безопасных ссылок" и переходить по вредоносным URL-адресам.</span><span class="sxs-lookup"><span data-stu-id="33d42-173">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and click on malicious URLs.</span></span>

### <a name="tabs"></a><span data-ttu-id="33d42-174">Вкладки</span><span class="sxs-lookup"><span data-stu-id="33d42-174">Tabs</span></span>

<span data-ttu-id="33d42-175">Представление сведений о кампании содержит несколько вкладок, с помощью которых можно более подробно изучить кампанию.</span><span class="sxs-lookup"><span data-stu-id="33d42-175">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="33d42-176">**Переходы по URL-адресу**: если пользователь не перешел по URL-адресу в фишинговом сообщении, этот раздел будет пустым.</span><span class="sxs-lookup"><span data-stu-id="33d42-176">**URL Clicks**: If the payload URL in the phishing message wasn't clicked, this section will be blank.</span></span> <span data-ttu-id="33d42-177">Если пользователь мог перейти по URL-адресу,</span><span class="sxs-lookup"><span data-stu-id="33d42-177">If a user was able to click on the URL, you</span></span>

  - <span data-ttu-id="33d42-178">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33d42-178">User</span></span>

  - <span data-ttu-id="33d42-179">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33d42-179">URL</span></span>

  - <span data-ttu-id="33d42-180">**Время перехода**</span><span class="sxs-lookup"><span data-stu-id="33d42-180">**Click Time**</span></span>

  - <span data-ttu-id="33d42-181">**Действие перехода**</span><span class="sxs-lookup"><span data-stu-id="33d42-181">Click **Action**.</span></span>

- <span data-ttu-id="33d42-182">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="33d42-182">**Sender IPs**</span></span>

  - <span data-ttu-id="33d42-183">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33d42-183">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="33d42-184">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="33d42-184">**Total Count**</span></span>

  - <span data-ttu-id="33d42-185">**Полученное количество**</span><span class="sxs-lookup"><span data-stu-id="33d42-185">**Inboxed Count**</span></span>

  - <span data-ttu-id="33d42-186">**Заблокированное количество**</span><span class="sxs-lookup"><span data-stu-id="33d42-186">**Blocked Count**</span></span>

  - <span data-ttu-id="33d42-187">**Прошли SPF**</span><span class="sxs-lookup"><span data-stu-id="33d42-187">**SPF Passed**</span></span>

- <span data-ttu-id="33d42-188">**Отправители**</span><span class="sxs-lookup"><span data-stu-id="33d42-188">**Senders**</span></span>

  - <span data-ttu-id="33d42-189">**Отправитель**</span><span class="sxs-lookup"><span data-stu-id="33d42-189">**Sender**</span></span>

  - <span data-ttu-id="33d42-190">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="33d42-190">**Total Count**</span></span>

  - <span data-ttu-id="33d42-191">**Полученное количество**</span><span class="sxs-lookup"><span data-stu-id="33d42-191">**Inboxed Count**</span></span>

  - <span data-ttu-id="33d42-192">**Заблокированное количество**</span><span class="sxs-lookup"><span data-stu-id="33d42-192">**Blocked Count**</span></span>

  - <span data-ttu-id="33d42-193">**Прошли DKIM**</span><span class="sxs-lookup"><span data-stu-id="33d42-193">**DKIM Passed**</span></span>

  - <span data-ttu-id="33d42-194">**Прошли DMARC**</span><span class="sxs-lookup"><span data-stu-id="33d42-194">**DMARC Passed**</span></span>

- <span data-ttu-id="33d42-195">**Полезная нагрузка**</span><span class="sxs-lookup"><span data-stu-id="33d42-195">**Payloads**</span></span>

  - <span data-ttu-id="33d42-196">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="33d42-196">URL</span></span>

  - <span data-ttu-id="33d42-197">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="33d42-197">**Total Count**</span></span>

<span data-ttu-id="33d42-198"><sup>\*</sup> Если щелкнуть это значение, в верхней части представления сведений о кампании откроется новое всплывающее окно с более подробными сведениями об указанном элементе (пользователь, URL-адрес и т. д.)</span><span class="sxs-lookup"><span data-stu-id="33d42-198"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="33d42-199">Чтобы вернуться в представление сведений о кампании, нажмите кнопку **Готово** в новом всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="33d42-199">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="33d42-200">Кнопки</span><span class="sxs-lookup"><span data-stu-id="33d42-200">Buttons</span></span>

<span data-ttu-id="33d42-201">Кнопки в представлении сведений о кампании позволяют использовать возможности обозревателя угроз для дальнейшего изучения кампании.</span><span class="sxs-lookup"><span data-stu-id="33d42-201">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="33d42-202">**Изучение кампании**: открывает новую вкладку поиска обозревателя угроз со значением **ID кампании** в качестве поискового фильтра.</span><span class="sxs-lookup"><span data-stu-id="33d42-202">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="33d42-203">**Изучение входящих сообщений**: открывает новую вкладку поиска обозревателя угроз с **ID кампании** и **Место доставки: Входящие** в качестве поискового фильтра.</span><span class="sxs-lookup"><span data-stu-id="33d42-203">**Explore Inbox messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
