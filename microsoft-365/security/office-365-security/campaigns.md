---
title: Представления кампаний в Office 365 ATP
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 40eab14dff8d0c51a35bfbc7a04365a5a025e207
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637332"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="4ea42-103">Представления кампаний в Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4ea42-103">Campaign Views in Office 365 ATP</span></span>

<span data-ttu-id="4ea42-104">Представления кампаний — это функция службы Advanced Threat Protection (ATP) в Центре безопасности и соответствия требованиям Office 365, которая определяет и классифицирует фишинговые атаки в службе.</span><span class="sxs-lookup"><span data-stu-id="4ea42-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="4ea42-105">Представления кампаний помогают:</span><span class="sxs-lookup"><span data-stu-id="4ea42-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="4ea42-106">эффективно анализировать фишинговые атаки и отвечать на них;</span><span class="sxs-lookup"><span data-stu-id="4ea42-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="4ea42-107">точнее устанавливать область, затронутую атакой;</span><span class="sxs-lookup"><span data-stu-id="4ea42-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="4ea42-108">демонстрировать проблему лицам, ответственным за принятие решений.</span><span class="sxs-lookup"><span data-stu-id="4ea42-108">Show value to decision makers.</span></span>

<span data-ttu-id="4ea42-109">Представления кампаний позволяют быстрее и полнее получить общую картину атаки.</span><span class="sxs-lookup"><span data-stu-id="4ea42-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="4ea42-110">Что такое кампания?</span><span class="sxs-lookup"><span data-stu-id="4ea42-110">What is a campaign?</span></span>

<span data-ttu-id="4ea42-111">Кампания — это скоординированная атака по электронной почте, направленная против одной или нескольких организаций.</span><span class="sxs-lookup"><span data-stu-id="4ea42-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="4ea42-112">Атаки электронной почты, которые украсть учетные данные и данные компании, являются большой и лукративеной промышленности.</span><span class="sxs-lookup"><span data-stu-id="4ea42-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="4ea42-113">Так как технологии увеличивают усилия для прекращения атак, злоумышленники могут изменить их методы, чтобы убедиться в успешном завершении работы.</span><span class="sxs-lookup"><span data-stu-id="4ea42-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="4ea42-114">Корпорация Майкрософт использует огромные объемы данных защиты от нежелательной почты и вредоносных программ во всей службе Office 365 для определения кампаний.</span><span class="sxs-lookup"><span data-stu-id="4ea42-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire Office 365 service to help identify campaigns.</span></span> <span data-ttu-id="4ea42-115">Мы анализируем и классифицируем информацию об атаках в зависимости от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="4ea42-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="4ea42-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="4ea42-116">For example:</span></span>

- <span data-ttu-id="4ea42-117">**Источник атаки**: исходные адреса и домены электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="4ea42-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="4ea42-118">**Свойства сообщения атаки**: содержание, стиль и тон сообщений, выражающих атаку.</span><span class="sxs-lookup"><span data-stu-id="4ea42-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="4ea42-119">**Объекты атаки**: домены получателей, должности получателей (администраторы, руководители и т. д.), типы компаний (крупные, мелкие, государственные, частные и т. д.) и отрасли.</span><span class="sxs-lookup"><span data-stu-id="4ea42-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="4ea42-120">**Полезные данные для атак**: вредоносные ссылки, вложения или другие полезные данные в сообщениях о атаках.</span><span class="sxs-lookup"><span data-stu-id="4ea42-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="4ea42-121">Кампания может быть коротким временем существования или может занимать несколько дней, недель или месяцев с активными и неактивными периодами.</span><span class="sxs-lookup"><span data-stu-id="4ea42-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="4ea42-122">Кампания может быть запущена для конкретной организации, или ваша организация может быть частью более крупной кампании в нескольких компаниях.</span><span class="sxs-lookup"><span data-stu-id="4ea42-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="4ea42-123">Представления кампаний в Центре безопасности и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="4ea42-123">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="4ea42-124">Представления кампаний доступны в [центре безопасности & соответствия требованиям](https://protection.office.com) в \> **кампаниях**по **управлению угрозами** .</span><span class="sxs-lookup"><span data-stu-id="4ea42-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![Обзор кампаний в Центре безопасности и соответствия требованиям](../../media/campaigns-overview.png)

<span data-ttu-id="4ea42-126">Вы также можете перейти к представлению кампании из:</span><span class="sxs-lookup"><span data-stu-id="4ea42-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="4ea42-127">\> **Просмотр** **кампаний** в \> **обозревателе** \> **управления угрозами**</span><span class="sxs-lookup"><span data-stu-id="4ea42-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="4ea42-128">\> **Обозреватель** \> **View** \> **Threat management** \> управления угрозой Просмотреть всю **кампанию** **по электронной почте**</span><span class="sxs-lookup"><span data-stu-id="4ea42-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="4ea42-129">Если вы не видите данные кампаний, попробуйте изменить диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="4ea42-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="4ea42-130">На странице обзора приведена следующая информация о кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="4ea42-131">**Название**</span><span class="sxs-lookup"><span data-stu-id="4ea42-131">**Name**</span></span>

- <span data-ttu-id="4ea42-132">**Образец темы**: строка темы одного из сообщений кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="4ea42-133">Обратите внимание, что все сообщения в кампании не обязательно будут иметь одинаковые темы.</span><span class="sxs-lookup"><span data-stu-id="4ea42-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="4ea42-134">**Тип**: в настоящее время это значение всегда является **ложным**.</span><span class="sxs-lookup"><span data-stu-id="4ea42-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="4ea42-135">**Подтип**: при наличии — бренд, который подвергается фишингу в этой кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="4ea42-136">Когда обнаружение определяется технологией ATP, в значение подтипа добавляется префикс **ATP** .</span><span class="sxs-lookup"><span data-stu-id="4ea42-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="4ea42-137">**Получатели**: количество пользователей, которые подверглись этой кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="4ea42-138">**Папка "Входящие"**: количество пользователей, которые получали сообщения от этой кампании в папке "Входящие" (не доставляются в Нежелательная почта).</span><span class="sxs-lookup"><span data-stu-id="4ea42-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="4ea42-139">**Выбрано**: количество пользователей, которые щелкают по URL-адресу в сообщении фишинга.</span><span class="sxs-lookup"><span data-stu-id="4ea42-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="4ea42-140">**Нажмите кнопку частота**: процент, рассчитанный по "**выбранным** / **папкам" Входящие**".</span><span class="sxs-lookup"><span data-stu-id="4ea42-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="4ea42-141">Это значение является индикатором эффективности кампании и того, могут ли получатели определить сообщение как фишинг и не щелкать URL-адрес полезных данных.</span><span class="sxs-lookup"><span data-stu-id="4ea42-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="4ea42-142">**Просмотрено**: количество пользователей, фактически выполненных на веб-сайте полезных данных.</span><span class="sxs-lookup"><span data-stu-id="4ea42-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="4ea42-143">Если **выбраны значения,** но безопасные ссылки блокировали доступ к веб-сайту, это значение будет равно нулю.</span><span class="sxs-lookup"><span data-stu-id="4ea42-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="4ea42-144">Если щелкнуть название кампании, в всплывающем окне выводятся сведения о кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="4ea42-145">Сведения о кампании</span><span class="sxs-lookup"><span data-stu-id="4ea42-145">Campaign details</span></span>

<span data-ttu-id="4ea42-146">В окне сведений о кампании представлена очень подробная информация о кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="4ea42-147">Информация о кампании</span><span class="sxs-lookup"><span data-stu-id="4ea42-147">Campaign information:</span></span>

  - <span data-ttu-id="4ea42-148">**ID**: уникальный идентификатор кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="4ea42-149">**Начало** и **Окончание**: выбранный диапазон данных.</span><span class="sxs-lookup"><span data-stu-id="4ea42-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="4ea42-150">**Влияние**: следующие данные для выбранного фильтра диапазона дат:</span><span class="sxs-lookup"><span data-stu-id="4ea42-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="4ea42-151">Общее количество получателей.</span><span class="sxs-lookup"><span data-stu-id="4ea42-151">The total number of recipients.</span></span>

    - <span data-ttu-id="4ea42-152">Количество сообщений, отправленных в папку "Входящие" (то есть доставленных в папку "Входящие", а не на Нежелательная почта).</span><span class="sxs-lookup"><span data-stu-id="4ea42-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="4ea42-153">Количество пользователей, которые щелкают в полезных данных URL-адреса в phishing-сообщениях.</span><span class="sxs-lookup"><span data-stu-id="4ea42-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="4ea42-154">Хове многие пользователи посещали URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="4ea42-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="4ea42-155">Временная шкала активности кампании: когда кампания была начата и закончена и изменение объема сообщений со временем.</span><span class="sxs-lookup"><span data-stu-id="4ea42-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="4ea42-156">Ход кампании</span><span class="sxs-lookup"><span data-stu-id="4ea42-156">Campaign flow</span></span>

<span data-ttu-id="4ea42-157">Важные сведения о кампании представлены на горизонтальной блок-схеме (так называемой схеме _Sankey_) в разделе **Поток**.</span><span class="sxs-lookup"><span data-stu-id="4ea42-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="4ea42-158">Эти сведения помогут вам изучить элементы кампании и ее потенциальное влияние на вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="4ea42-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Сведения о кампании без переходов пользователей по URL-адресам](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="4ea42-160">Если навести указатель мыши на горизонтальную полоску на схеме, будет показано количество связанных с ней сообщений (например, сообщений с определенного исходного IP-адреса, сообщения из исходного IP-адреса с использованием указанного домена отправителя и т. д.).</span><span class="sxs-lookup"><span data-stu-id="4ea42-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="4ea42-161">Схема содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="4ea42-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="4ea42-162">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="4ea42-162">**Sender IPs**</span></span>

- <span data-ttu-id="4ea42-163">**Домены отправителей**</span><span class="sxs-lookup"><span data-stu-id="4ea42-163">**Sender domains**</span></span>

- <span data-ttu-id="4ea42-164">**Filter вердиктс**: значения здесь относятся к доступной антифишингу и фильтрации нежелательной почты вердиктс, как описано в [заголовках сообщений по защите от нежелательной почты](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="4ea42-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="4ea42-165">Доступные значения описаны в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="4ea42-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="4ea42-166">Значение</span><span class="sxs-lookup"><span data-stu-id="4ea42-166">Value</span></span>|<span data-ttu-id="4ea42-167">Вредоносности фильтра нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="4ea42-167">Spam filter verdict</span></span>|<span data-ttu-id="4ea42-168">Description</span><span class="sxs-lookup"><span data-stu-id="4ea42-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="4ea42-169">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="4ea42-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="4ea42-170">Сообщение помечено как нежелательная или пропущенная фильтрация перед оценкой при фильтрации нежелательной почты (например, с помощью правила для обработки нежелательной почты, которое также называется правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="4ea42-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="4ea42-171">Сообщение пропустила фильтрацию нежелательной почты по другим причинам (например, отправитель и получатель отображаются в одной и той же организации).</span><span class="sxs-lookup"><span data-stu-id="4ea42-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="4ea42-172">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="4ea42-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="4ea42-173">Сообщение было помечено как спам, прежде чем оно будет оценено при фильтрации нежелательной почты (например, с помощью правила для процесса обработки почты).</span><span class="sxs-lookup"><span data-stu-id="4ea42-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="4ea42-174">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="4ea42-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="4ea42-175">Сообщение помечено как нежелательная почта при фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="4ea42-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="4ea42-176">**Не обнаружено**</span><span class="sxs-lookup"><span data-stu-id="4ea42-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="4ea42-177">При фильтрации нежелательной почты сообщение помечено как нежелательная почта.</span><span class="sxs-lookup"><span data-stu-id="4ea42-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="4ea42-178">**Снят**</span><span class="sxs-lookup"><span data-stu-id="4ea42-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="4ea42-179">Сообщение пропустило фильтрацию нежелательной почты, так как оно было выпущено из карантина.</span><span class="sxs-lookup"><span data-stu-id="4ea42-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="4ea42-180">**Разрешить клиентов**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ea42-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="4ea42-181">Сообщение пропустило фильтрацию нежелательной почты из-за параметров политики защиты от нежелательной почты (например, отправитель находится в списке разрешенных отправителей или список разрешенных доменов).</span><span class="sxs-lookup"><span data-stu-id="4ea42-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="4ea42-182">**Блок клиента**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ea42-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="4ea42-183">Сообщение заблокировано фильтром нежелательной почты из-за параметров политики защиты от нежелательной почты (например, отправитель находится в списке разрешенных отправителей или список разрешенных доменов).</span><span class="sxs-lookup"><span data-stu-id="4ea42-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="4ea42-184">**Разрешение пользователя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ea42-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="4ea42-185">Сообщение пропустило фильтрацию нежелательной почты, так как отправитель был в списке надежных отправителей пользователя в Outlook.</span><span class="sxs-lookup"><span data-stu-id="4ea42-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="4ea42-186">**Пользовательская блокировка**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ea42-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="4ea42-187">Сообщение заблокировано фильтром нежелательной почты, так как отправитель находится в списке заблокированных отправителей пользователя в Outlook.</span><span class="sxs-lookup"><span data-stu-id="4ea42-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="4ea42-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="4ea42-188">**ZAP**</span></span>|<span data-ttu-id="4ea42-189">н/д</span><span class="sxs-lookup"><span data-stu-id="4ea42-189">n/a</span></span>|<span data-ttu-id="4ea42-190">В соответствии с настройками политики защиты от нежелательной почты в почтовом сообщении (перемещено в папку "Нежелательная почта" или "помещено в карантин") было принято [нулевое автоматическое удаление (ZAP)](zero-hour-auto-purge.md) .</span><span class="sxs-lookup"><span data-stu-id="4ea42-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="4ea42-191"><sup>\*</sup>Проверьте политики защиты от нежелательной почты, так как разрешенное сообщение было бы заблокировано службой.</span><span class="sxs-lookup"><span data-stu-id="4ea42-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="4ea42-192"><sup>\*\*</sup>Просмотрите политики защиты от нежелательной почты, так как эти сообщения должны быть помещены в карантин, а не доставлены.</span><span class="sxs-lookup"><span data-stu-id="4ea42-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="4ea42-193">**Места доставки**: скорее всего, вы захотите исследовать сообщения, которые действительно были доставлены получателям (в папку "Входящие" или в папку "Нежелательная почта"), даже если пользователи не переходили по URL-адресам, указанным в сообщении.</span><span class="sxs-lookup"><span data-stu-id="4ea42-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="4ea42-194">Вы также можете удалить помещенные в карантин сообщения из карантина.</span><span class="sxs-lookup"><span data-stu-id="4ea42-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="4ea42-195">Дополнительные сведения см в разделе [карантин сообщений электронной почты в Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="4ea42-195">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="4ea42-196">**Удалена папка**</span><span class="sxs-lookup"><span data-stu-id="4ea42-196">**Deleted folder**</span></span>

  - <span data-ttu-id="4ea42-197">**Утерян**</span><span class="sxs-lookup"><span data-stu-id="4ea42-197">**Dropped**</span></span>

  - <span data-ttu-id="4ea42-198">**Внешний**: получатель находится в вашей локальной организации электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4ea42-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="4ea42-199">**Не удалось выполнить**</span><span class="sxs-lookup"><span data-stu-id="4ea42-199">**Failed**</span></span>

  - <span data-ttu-id="4ea42-200">**Пересылаются**</span><span class="sxs-lookup"><span data-stu-id="4ea42-200">**Forwarded**</span></span>

  - <span data-ttu-id="4ea42-201">**Входящие**</span><span class="sxs-lookup"><span data-stu-id="4ea42-201">**Inbox**</span></span>

  - <span data-ttu-id="4ea42-202">**Нежелательная почта**</span><span class="sxs-lookup"><span data-stu-id="4ea42-202">**Junk folder**</span></span>

  - <span data-ttu-id="4ea42-203">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="4ea42-203">**Quarantine**</span></span>

  - <span data-ttu-id="4ea42-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="4ea42-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="4ea42-205">Во всех слоях, содержащих более 10 элементов, отображаются первые 10 элементов, а остальные элементы объединяются в **другие**.</span><span class="sxs-lookup"><span data-stu-id="4ea42-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="4ea42-206">Переходы по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="4ea42-206">URL clicks</span></span>

<span data-ttu-id="4ea42-207">При доставке фишингового сообщения получателю (в папку "Входящие" или в папку "Нежелательная почта") всегда существует вероятность того, что пользователь выполнит щелчок URL-адреса полезных данных.</span><span class="sxs-lookup"><span data-stu-id="4ea42-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="4ea42-208">Не щелкая URL-адрес в доставленном сообщении — это незначительная мера успеха, но вам необходимо определить, почему сообщение фишинга было доставлено в свой почтовый ящик в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="4ea42-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="4ea42-209">Если пользователь щелкнул URL-адрес полезных данных в phishing-сообщении, действия отображаются в области схемы **щелчков URL-адресов** в представлении сведения о кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="4ea42-210">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="4ea42-210">**Allowed**</span></span>

- <span data-ttu-id="4ea42-211">**Блоккпаже**: получатель щелкает URL-адрес полезных данных, но его доступ к вредоносному веб-сайту заблокирован политиками [безопасных ссылок ATP](atp-safe-links.md) в Организации.</span><span class="sxs-lookup"><span data-stu-id="4ea42-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="4ea42-212">**Блоккпажеоверриде**: получатель находился на URL-адрес полезных данных в сообщении, безопасные ссылки ATP попытались остановить их, но могут переопределять блок.</span><span class="sxs-lookup"><span data-stu-id="4ea42-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="4ea42-213">Необходимо изучить [политики безопасных ссылок](set-up-atp-safe-links-policies.md) , чтобы узнать, почему пользователям разрешено переопределять безопасные ссылки вредоносности и продолжить работу с вредоносным веб-сайтом.</span><span class="sxs-lookup"><span data-stu-id="4ea42-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="4ea42-214">**Пендингдетонатионпаже**: безопасные вложения ATP — это процесс открытия URL-адреса полезных данных в среде виртуального компьютера и просмотра того, что происходит.</span><span class="sxs-lookup"><span data-stu-id="4ea42-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="4ea42-215">**Пендингдетонатионпажеоверриде**: получателю разрешается переопределить процесс детонации полезных данных и открыть URL-адрес без ожидания результатов.</span><span class="sxs-lookup"><span data-stu-id="4ea42-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="4ea42-216">Вкладки</span><span class="sxs-lookup"><span data-stu-id="4ea42-216">Tabs</span></span>

<span data-ttu-id="4ea42-217">Представление сведений о кампании содержит несколько вкладок, с помощью которых можно более подробно изучить кампанию.</span><span class="sxs-lookup"><span data-stu-id="4ea42-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="4ea42-218">**URL-адреса**: Если пользователи не щелкнули URL-адрес полезных данных в phishing-сообщении, этот раздел будет пустым.</span><span class="sxs-lookup"><span data-stu-id="4ea42-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="4ea42-219">Если пользователь мог щелкнуть URL-адрес, будут заполнены следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4ea42-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="4ea42-220">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ea42-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="4ea42-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ea42-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="4ea42-222">**Время перехода**</span><span class="sxs-lookup"><span data-stu-id="4ea42-222">**Click Time**</span></span>

  - <span data-ttu-id="4ea42-223">**Действие перехода**</span><span class="sxs-lookup"><span data-stu-id="4ea42-223">**Click Action**</span></span>

- <span data-ttu-id="4ea42-224">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="4ea42-224">**Sender IPs**</span></span>

  - <span data-ttu-id="4ea42-225">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ea42-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="4ea42-226">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="4ea42-226">**Total Count**</span></span>

  - <span data-ttu-id="4ea42-227">**Полученное количество**</span><span class="sxs-lookup"><span data-stu-id="4ea42-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="4ea42-228">**Заблокированное количество**</span><span class="sxs-lookup"><span data-stu-id="4ea42-228">**Blocked Count**</span></span>

  - <span data-ttu-id="4ea42-229">**Переданная SPF**: отправитель прошел проверку подлинности с помощью [инфраструктуры политики отправителей (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="4ea42-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="4ea42-230">Отправитель, не передающий проверку SPF, указывает на то, что отправитель не прошел проверку подлинности или что сообщение поддается подделке законному отправителю.</span><span class="sxs-lookup"><span data-stu-id="4ea42-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="4ea42-231">**Отправители**</span><span class="sxs-lookup"><span data-stu-id="4ea42-231">**Senders**</span></span>

  - <span data-ttu-id="4ea42-232">**Отправитель**: фактический адрес отправителя в команде SMTP MAIL FROM, который не обязательно является адресом электронной почты, который пользователи видят в своих почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="4ea42-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="4ea42-233">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="4ea42-233">**Total Count**</span></span>

  - <span data-ttu-id="4ea42-234">**Папка "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="4ea42-234">**Inboxed**</span></span>

  - <span data-ttu-id="4ea42-235">**Нет папки "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="4ea42-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="4ea42-236">**DKIM передан**: отправитель проходил проверку подлинности с помощью [ключей домена. определенная почта (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="4ea42-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="4ea42-237">Отправитель, который не проходит проверку DKIM, указывает, что отправитель не прошел проверку подлинности или что сообщение поддается подделке законному отправителю.</span><span class="sxs-lookup"><span data-stu-id="4ea42-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="4ea42-238">**DMARC передано**: прошедший проверку подлинности отправителя проводилась проверкой [подлинности сообщений на основе домена, созданием отчетов и соответствием (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="4ea42-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="4ea42-239">Отправитель, который не проходит проверку DMARC, указывает, что отправитель не прошел проверку подлинности или что сообщение поддается подделке законному отправителю.</span><span class="sxs-lookup"><span data-stu-id="4ea42-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="4ea42-240">**Полезная нагрузка**</span><span class="sxs-lookup"><span data-stu-id="4ea42-240">**Payloads**</span></span>

  - <span data-ttu-id="4ea42-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ea42-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="4ea42-242">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="4ea42-242">**Total Count**</span></span>

<span data-ttu-id="4ea42-243"><sup>\*</sup> Если щелкнуть это значение, в верхней части представления сведений о кампании откроется новое всплывающее окно с более подробными сведениями об указанном элементе (пользователь, URL-адрес и т. д.)</span><span class="sxs-lookup"><span data-stu-id="4ea42-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="4ea42-244">Чтобы вернуться в представление сведений о кампании, нажмите кнопку **Готово** в новом всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="4ea42-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="4ea42-245">Кнопки</span><span class="sxs-lookup"><span data-stu-id="4ea42-245">Buttons</span></span>

<span data-ttu-id="4ea42-246">Кнопки в представлении сведений о кампании позволяют использовать возможности обозревателя угроз для дальнейшего изучения кампании.</span><span class="sxs-lookup"><span data-stu-id="4ea42-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="4ea42-247">**Изучение кампании**: открывает новую вкладку поиска обозревателя угроз со значением **ID кампании** в качестве поискового фильтра.</span><span class="sxs-lookup"><span data-stu-id="4ea42-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="4ea42-248">**Просмотр сообщений, отправленных в папку "Входящие"**: открывает новую вкладку поиска угроз с помощью **идентификатора кампании** и **места доставки: "Входящие"** в качестве фильтра поиска.</span><span class="sxs-lookup"><span data-stu-id="4ea42-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
