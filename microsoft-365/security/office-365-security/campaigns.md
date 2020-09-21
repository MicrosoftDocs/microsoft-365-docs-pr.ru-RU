---
title: Представления кампаний в плане Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Ознакомьтесь с представлениями кампаний в Office 365 Advanced Threat Protection.
ms.openlocfilehash: 60ec8ea1d2c164905e7b57f4b518ea3f80e7986c
ms.sourcegitcommit: dcbcd5ef278949c777059b0aa6db072e821f72dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "48173312"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="a629e-103">Представления кампаний в Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a629e-103">Campaign Views in Office 365 ATP</span></span>

<span data-ttu-id="a629e-104">Представления кампаний — это функция Advanced Threat protection (ATP), план 2 (например, Microsoft 365 в строку "е" или организациях с надстройкой "план ATP 2").</span><span class="sxs-lookup"><span data-stu-id="a629e-104">Campaign Views is a feature in Advanced Threat Protection (ATP) Plan 2 (for example Microsoft 365 E5 or organizations with an ATP Plan 2 add-on).</span></span> <span data-ttu-id="a629e-105">Представления кампаний в центре безопасности & соответствия требованиям определяют и классифицируют атаки фишинга в службе.</span><span class="sxs-lookup"><span data-stu-id="a629e-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="a629e-106">Представления кампаний помогают:</span><span class="sxs-lookup"><span data-stu-id="a629e-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="a629e-107">эффективно анализировать фишинговые атаки и отвечать на них;</span><span class="sxs-lookup"><span data-stu-id="a629e-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="a629e-108">точнее устанавливать область, затронутую атакой;</span><span class="sxs-lookup"><span data-stu-id="a629e-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="a629e-109">демонстрировать проблему лицам, ответственным за принятие решений.</span><span class="sxs-lookup"><span data-stu-id="a629e-109">Show value to decision makers.</span></span>

<span data-ttu-id="a629e-110">Представления кампаний позволяют быстрее и полнее получить общую картину атаки.</span><span class="sxs-lookup"><span data-stu-id="a629e-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="a629e-111">Что такое кампания?</span><span class="sxs-lookup"><span data-stu-id="a629e-111">What is a campaign?</span></span>

<span data-ttu-id="a629e-112">Кампания — это скоординированная атака по электронной почте, направленная против одной или нескольких организаций.</span><span class="sxs-lookup"><span data-stu-id="a629e-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="a629e-113">Атаки электронной почты, которые украсть учетные данные и данные компании — это большая и Лукративе отрасль.</span><span class="sxs-lookup"><span data-stu-id="a629e-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="a629e-114">Так как технологии увеличивают усилия для прекращения атак, злоумышленники могут изменить их методы, чтобы убедиться в успешном завершении работы.</span><span class="sxs-lookup"><span data-stu-id="a629e-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="a629e-115">Корпорация Майкрософт использует огромные объемы защиты от нежелательной почты, защиты от нежелательной почты и вредоносных программ во всей службе, чтобы облегчить идентификацию кампаний.</span><span class="sxs-lookup"><span data-stu-id="a629e-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="a629e-116">Мы анализируем и классифицируем информацию об атаках в зависимости от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="a629e-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="a629e-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="a629e-117">For example:</span></span>

- <span data-ttu-id="a629e-118">**Источник атаки**: исходные IP-адреса и домены электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="a629e-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="a629e-119">**Свойства сообщения**: содержимое, стиль и тон сообщений.</span><span class="sxs-lookup"><span data-stu-id="a629e-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="a629e-120">**Получатели сообщения**: способ связи получателей.</span><span class="sxs-lookup"><span data-stu-id="a629e-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="a629e-121">Например, домены получателей, задания получателей (Администраторы, руководители и т. д.), типы компаний (крупные, малые, общедоступные, частные и т. д.) и отрасли.</span><span class="sxs-lookup"><span data-stu-id="a629e-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="a629e-122">**Полезные данные для атак**: вредоносные ссылки, вложения или другие полезные данные в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="a629e-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="a629e-123">Кампания может быть коротким временем существования или может занимать несколько дней, недель или месяцев с активными и неактивными периодами.</span><span class="sxs-lookup"><span data-stu-id="a629e-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="a629e-124">Кампания может быть запущена для конкретной организации, или ваша организация может быть частью более крупной кампании в нескольких компаниях.</span><span class="sxs-lookup"><span data-stu-id="a629e-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="a629e-125">Представления кампаний в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a629e-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="a629e-126">Представления кампаний доступны в [центре безопасности & соответствия требованиям](https://protection.office.com) в кампаниях по **управлению угрозами** \> **Campaigns**или непосредственно в <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="a629e-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Обзор кампаний в Центре безопасности и соответствия требованиям](../../media/campaigns-overview.png)

<span data-ttu-id="a629e-128">Вы также можете перейти к представлениям кампании из:</span><span class="sxs-lookup"><span data-stu-id="a629e-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="a629e-129">**Управление** \> угрозами **Explorer** \> **View (Просмотр** \> ) **Кампании**</span><span class="sxs-lookup"><span data-stu-id="a629e-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="a629e-130">**Управление** \> угрозами **Explorer** \> **View (Просмотр** \> ) **Вся электронная почта** \> Вкладка " **кампания** "</span><span class="sxs-lookup"><span data-stu-id="a629e-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="a629e-131">**Управление** \> угрозами **Explorer** \> **View (Просмотр** \> ) **Фишинг** \> Вкладка " **кампания** "</span><span class="sxs-lookup"><span data-stu-id="a629e-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="a629e-132">**Управление** \> угрозами **Explorer** \> **View (Просмотр** \> ) **Вредоносные программы** \> Вкладка " **кампания** "</span><span class="sxs-lookup"><span data-stu-id="a629e-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="a629e-133">Для доступа к представлениям кампаний необходимо быть участником группы ролей " **Управление организацией**", " **администратор безопасности**" или " **читатель безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a629e-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a629e-134">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a629e-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="a629e-135">Обзор кампаний</span><span class="sxs-lookup"><span data-stu-id="a629e-135">Campaigns overview</span></span>

<span data-ttu-id="a629e-136">На странице Обзор отображаются сведения обо всех кампаниях.</span><span class="sxs-lookup"><span data-stu-id="a629e-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="a629e-137">На вкладке **кампания** по умолчанию в области **тип кампании** отображается гистограмма, на которой показано количество получателей в день.</span><span class="sxs-lookup"><span data-stu-id="a629e-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="a629e-138">По умолчанию на графике отображаются данные **фишинга** и **вредоносных программ** .</span><span class="sxs-lookup"><span data-stu-id="a629e-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="a629e-139">Если вы не видите данные кампании, попробуйте изменить диапазон дат или [фильтры](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="a629e-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="a629e-140">В оставшейся части страницы обзор отображаются следующие сведения на вкладке **кампания** :</span><span class="sxs-lookup"><span data-stu-id="a629e-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="a629e-141">**Название**</span><span class="sxs-lookup"><span data-stu-id="a629e-141">**Name**</span></span>

- <span data-ttu-id="a629e-142">**Образец темы**: строка темы одного из сообщений кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="a629e-143">Обратите внимание, что все сообщения в кампании не обязательно будут иметь одинаковые темы.</span><span class="sxs-lookup"><span data-stu-id="a629e-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="a629e-144">**Targeted**: процент, рассчитанный на: (число получателей кампании в организации)/(общее количество получателей в кампании для всех организаций в службе).</span><span class="sxs-lookup"><span data-stu-id="a629e-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="a629e-145">Это значение указывает степень направления кампании в Организации (более высокое значение) vs. также в других организациях в службе (меньшее значение).</span><span class="sxs-lookup"><span data-stu-id="a629e-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="a629e-146">**Тип**: это значение является **фишингом** или **вредоносной программой**.</span><span class="sxs-lookup"><span data-stu-id="a629e-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="a629e-147">**Подтип**: это значение содержит дополнительные сведения о кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="a629e-148">Например:</span><span class="sxs-lookup"><span data-stu-id="a629e-148">For example:</span></span>

  - <span data-ttu-id="a629e-149">**Фишинг**: если он доступен, фирменная символика будет поддельной для этой кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="a629e-150">Например,,,, `Microsoft` `365` `Unknown` `Outlook` , или `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="a629e-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="a629e-151">**Вредоносные программы**: например, `HTML/PHISH` или `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="a629e-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="a629e-152">Если это так, фирменная символика, которая будет поддельной для этой кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="a629e-153">Когда обнаружение определяется технологией ATP, в значение подтипа добавляется префикс **ATP** .</span><span class="sxs-lookup"><span data-stu-id="a629e-153">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="a629e-154">**Получатели**: количество пользователей, которые подверглись этой кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="a629e-155">**Папка "Входящие"**: количество пользователей, которые получали сообщения от этой кампании в папке "Входящие" (не доставляются в папку "Нежелательная почта").</span><span class="sxs-lookup"><span data-stu-id="a629e-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="a629e-156">**Выбрано**: количество пользователей, которые щелкают по URL-адресу или открыли вложение в сообщении фишинга.</span><span class="sxs-lookup"><span data-stu-id="a629e-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="a629e-157">**Нажмите кнопку частота**: процент, рассчитанный по "**выбранным**  /  **папкам" Входящие**".</span><span class="sxs-lookup"><span data-stu-id="a629e-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="a629e-158">Это значение является индикатором эффективности кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="a629e-159">Другими словами, если получатели смогли идентифицировать сообщение как фишинг, и если они не щелкают URL-адрес полезных данных.</span><span class="sxs-lookup"><span data-stu-id="a629e-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="a629e-160">Обратите внимание на то, что функция **"частота нажатий"** не используется в кампаниях</span><span class="sxs-lookup"><span data-stu-id="a629e-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="a629e-161">**Просмотрено**: количество пользователей, фактически выполненных на веб-сайте полезных данных.</span><span class="sxs-lookup"><span data-stu-id="a629e-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="a629e-162">Если **выбраны значения,** но безопасные ссылки блокировали доступ к веб-сайту, это значение будет равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a629e-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="a629e-163">На вкладке **Источник кампании** показаны источники сообщений на карте мира.</span><span class="sxs-lookup"><span data-stu-id="a629e-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="a629e-164">Фильтры и параметры</span><span class="sxs-lookup"><span data-stu-id="a629e-164">Filters and settings</span></span>

<span data-ttu-id="a629e-165">В верхней части страницы представления кампании есть несколько параметров фильтрации и запросов, которые помогут вам найти и изолировать конкретные кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Фильтры кампании](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="a629e-167">Наиболее простой способ фильтрации — Дата и время начала и Дата и время окончания.</span><span class="sxs-lookup"><span data-stu-id="a629e-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="a629e-168">Чтобы дополнительно отфильтровать представление, можно выполнить фильтрацию по одному свойству с несколькими значениями, нажав кнопку **тип кампании** , сделав выбор, а затем нажав кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="a629e-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="a629e-169">Доступные свойства кампании описаны в приведенном ниже списке.</span><span class="sxs-lookup"><span data-stu-id="a629e-169">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="a629e-170">Обычный</span><span class="sxs-lookup"><span data-stu-id="a629e-170">Basic</span></span>

  - <span data-ttu-id="a629e-171">**Тип кампании**: выбор **вредоносных программ** или **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="a629e-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="a629e-172">Очистка выбранных значений приводит к тому же результату, что и выбор обоих вариантов.</span><span class="sxs-lookup"><span data-stu-id="a629e-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="a629e-173">**Название кампании**</span><span class="sxs-lookup"><span data-stu-id="a629e-173">**Campaign name**</span></span>
  - <span data-ttu-id="a629e-174">**Подтип кампании**</span><span class="sxs-lookup"><span data-stu-id="a629e-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="a629e-175">**Sender**</span><span class="sxs-lookup"><span data-stu-id="a629e-175">**Sender**</span></span>
  - <span data-ttu-id="a629e-176">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="a629e-176">**Recipients**</span></span>
  - <span data-ttu-id="a629e-177">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="a629e-177">**Sender domain**</span></span>
  - <span data-ttu-id="a629e-178">**Subject**</span><span class="sxs-lookup"><span data-stu-id="a629e-178">**Subject**</span></span>
  - <span data-ttu-id="a629e-179">**Имя файла вложения**</span><span class="sxs-lookup"><span data-stu-id="a629e-179">**Attachment filename**</span></span>
  - <span data-ttu-id="a629e-180">**Семейство вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="a629e-180">**Malware family**</span></span>
  - <span data-ttu-id="a629e-181">**Действие доставки**</span><span class="sxs-lookup"><span data-stu-id="a629e-181">**Delivery action**</span></span>
  - <span data-ttu-id="a629e-182">**Технология обнаружения**</span><span class="sxs-lookup"><span data-stu-id="a629e-182">**Detection technology**</span></span>
  - <span data-ttu-id="a629e-183">**Tags**</span><span class="sxs-lookup"><span data-stu-id="a629e-183">**Tags**</span></span>
  - <span data-ttu-id="a629e-184">**Переопределение системы**</span><span class="sxs-lookup"><span data-stu-id="a629e-184">**System overrides**</span></span>

- <span data-ttu-id="a629e-185">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="a629e-185">Advanced</span></span>

  - <span data-ttu-id="a629e-186">**Идентификатор сообщения Интернета**: доступен в поле заголовка сообщения **с идентификатором** в заголовке сообщения.</span><span class="sxs-lookup"><span data-stu-id="a629e-186">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="a629e-187">Пример значения: `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="a629e-187">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="a629e-188">**Идентификатор сетевого сообщения**: значение GUID, которое доступно в поле заголовка **X – MS – Exchange – Organization – Network — Message — ID** в заголовке сообщения.</span><span class="sxs-lookup"><span data-stu-id="a629e-188">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="a629e-189">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="a629e-189">**Sender IP**</span></span>
  
  - <span data-ttu-id="a629e-190">**Вложение SHA256**: чтобы найти хэш-значение SHA256 файла в Windows, выполните следующую команду в командной строки: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="a629e-190">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="a629e-191">**ИДЕНТИФИКАТОР кластера**</span><span class="sxs-lookup"><span data-stu-id="a629e-191">**Cluster ID**</span></span>
  
  - <span data-ttu-id="a629e-192">**Идентификатор политики оповещений**</span><span class="sxs-lookup"><span data-stu-id="a629e-192">**Alert Policy ID**</span></span>

- <span data-ttu-id="a629e-193">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="a629e-193">URLs</span></span>

  - <span data-ttu-id="a629e-194">**Домен URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="a629e-194">**URL domain**</span></span>
  - <span data-ttu-id="a629e-195">**Домен и путь URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="a629e-195">**URL domain and path**</span></span>
  - <span data-ttu-id="a629e-196">**URL**</span><span class="sxs-lookup"><span data-stu-id="a629e-196">**URL**</span></span>
  - <span data-ttu-id="a629e-197">**Путь URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="a629e-197">**URL path**</span></span>
  - <span data-ttu-id="a629e-198">**Нажмите кнопку вредоносности**</span><span class="sxs-lookup"><span data-stu-id="a629e-198">**Click verdict**</span></span>

<span data-ttu-id="a629e-199">Для более расширенной фильтрации, включая фильтрацию по нескольким свойствам, можно нажать кнопку **Расширенный фильтр** , чтобы создать запрос.</span><span class="sxs-lookup"><span data-stu-id="a629e-199">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="a629e-200">Доступны те же свойства кампании, но со следующими расширениями:</span><span class="sxs-lookup"><span data-stu-id="a629e-200">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="a629e-201">Можно нажать кнопку **Добавить условие** , чтобы выбрать несколько условий.</span><span class="sxs-lookup"><span data-stu-id="a629e-201">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="a629e-202">Вы можете выбрать оператор **and** или **or** между условиями.</span><span class="sxs-lookup"><span data-stu-id="a629e-202">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="a629e-203">Вы можете выбрать элемент **Группа условий** в нижней части списка условий, чтобы сформировать сложные составные условия.</span><span class="sxs-lookup"><span data-stu-id="a629e-203">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="a629e-204">Когда все будет готово, нажмите кнопку **запрос** .</span><span class="sxs-lookup"><span data-stu-id="a629e-204">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="a629e-205">После создания базового или расширенного фильтра его можно сохранить с помощью команды **Сохранить запрос** или **Сохранить запрос как**.</span><span class="sxs-lookup"><span data-stu-id="a629e-205">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="a629e-206">Позже, когда вы вернетесь к представлениям кампании, вы можете загрузить сохраненный фильтр, щелкнув **сохраненные параметры запросов**.</span><span class="sxs-lookup"><span data-stu-id="a629e-206">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="a629e-207">Чтобы экспортировать диаграмму или список кампаний, нажмите кнопку **Экспорт** и выберите **Экспорт данных диаграммы** или **Экспорт списка кампаний**.</span><span class="sxs-lookup"><span data-stu-id="a629e-207">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="a629e-208">Если у вас есть подписка на Microsoft Defender ATP, вы можете щелкнуть **вдатп** , чтобы подключиться к сведениям о кампаниях и отключить их с помощью Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a629e-208">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="a629e-209">Дополнительную информацию можно найти [в статье интеграция Office 365 ATP с защитником Microsoft](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="a629e-209">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="a629e-210">Сведения о кампании</span><span class="sxs-lookup"><span data-stu-id="a629e-210">Campaign details</span></span>

<span data-ttu-id="a629e-211">Если щелкнуть название кампании, сведения о кампании отобразятся в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="a629e-211">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="a629e-212">Сведения о кампании</span><span class="sxs-lookup"><span data-stu-id="a629e-212">Campaign information</span></span>

<span data-ttu-id="a629e-213">В верхней части представления сведений о кампании доступны следующие сведения о кампании:</span><span class="sxs-lookup"><span data-stu-id="a629e-213">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="a629e-214">**ID**: уникальный идентификатор кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-214">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="a629e-215">**Начато** и **завершено**: Дата начала и Дата окончания кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-215">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="a629e-216">Обратите внимание, что эти даты могут расширяться позже дат фильтрации, выбранных на странице Обзор.</span><span class="sxs-lookup"><span data-stu-id="a629e-216">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="a629e-217">**Воздействие**: в этом разделе содержатся следующие данные для выбранного фильтра диапазона дат (или выбранного на временной шкале):</span><span class="sxs-lookup"><span data-stu-id="a629e-217">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="a629e-218">Общее количество получателей.</span><span class="sxs-lookup"><span data-stu-id="a629e-218">The total number of recipients.</span></span>
  - <span data-ttu-id="a629e-219">Количество сообщений, отправленных в папку "Входящие" (то есть доставленных в папку "Входящие", а не в папку нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="a629e-219">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="a629e-220">Количество пользователей, которые щелкают в полезных данных URL-адреса в phishing-сообщениях.</span><span class="sxs-lookup"><span data-stu-id="a629e-220">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="a629e-221">Хове многие пользователи посещали URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="a629e-221">Howe many users visited the URL.</span></span>

- <span data-ttu-id="a629e-222">**Targeted**: процент, рассчитанный на: (число получателей кампании в организации)/(общее количество получателей в кампании для всех организаций в службе).</span><span class="sxs-lookup"><span data-stu-id="a629e-222">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="a629e-223">Обратите внимание, что это значение рассчитывается на протяжении всего жизненного цикла кампании и не изменяется в зависимости от фильтров дат.</span><span class="sxs-lookup"><span data-stu-id="a629e-223">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="a629e-224">Интерактивная временная шкала действий кампании: временная шкала показывает действия за весь срок жизни кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-224">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="a629e-225">По умолчанию затененная область включает фильтр диапазона дат, выбранный в обзоре.</span><span class="sxs-lookup"><span data-stu-id="a629e-225">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="a629e-226">Можно щелкнуть и перетащить для выбора определенной начальной точки и конечной точки, которая изменит <u>данные, отображаемые в области **влияния** , и на оставшейся части страницы, как описано в следующих разделах</u>.</span><span class="sxs-lookup"><span data-stu-id="a629e-226">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="a629e-227">В строке заголовка можно щелкнуть значок " **загрузить** кампанию для скачивания кампании" ![ ](../../media/download-campaign-write-up-button.png) , чтобы загрузить сведения о кампании в документ Word (по умолчанию с именем CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="a629e-227">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="a629e-228">Обратите внимание на то, что загрузка содержит сведения по всему сроку действия кампании (а не только к выбранным датам фильтрации).</span><span class="sxs-lookup"><span data-stu-id="a629e-228">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Сведения о кампании](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="a629e-230">Ход кампании</span><span class="sxs-lookup"><span data-stu-id="a629e-230">Campaign flow</span></span>

<span data-ttu-id="a629e-231">В центре представления сведений о кампании важные сведения о кампании представлены в разделе " **потоки** " в горизонтальной схеме (которая называется схемой _Санкэй_ ).</span><span class="sxs-lookup"><span data-stu-id="a629e-231">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="a629e-232">Эти сведения помогут вам изучить элементы кампании и ее потенциальное влияние на вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="a629e-232">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="a629e-233">Сведения, отображаемые на схеме **Flow** , контролируются затененным диапазоном дат на временной шкале, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="a629e-233">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Сведения о кампании без переходов пользователей по URL-адресам](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="a629e-235">Если навести указатель мыши на горизонтальную полоску на схеме, будет показано количество связанных с ней сообщений (например, сообщений с определенного исходного IP-адреса, сообщения из исходного IP-адреса с использованием указанного домена отправителя и т. д.).</span><span class="sxs-lookup"><span data-stu-id="a629e-235">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="a629e-236">Схема содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="a629e-236">The diagram contains the following information:</span></span>

- <span data-ttu-id="a629e-237">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="a629e-237">**Sender IPs**</span></span>

- <span data-ttu-id="a629e-238">**Домены отправителей**</span><span class="sxs-lookup"><span data-stu-id="a629e-238">**Sender domains**</span></span>

- <span data-ttu-id="a629e-239">**Filter вердиктс**: значения вредоносности относятся к доступной антифишингу и фильтрации нежелательной почты вердиктс, как описано в [заголовках сообщений по защите от нежелательной почты](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="a629e-239">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="a629e-240">Доступные значения описаны в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="a629e-240">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="a629e-241">Значение</span><span class="sxs-lookup"><span data-stu-id="a629e-241">Value</span></span>|<span data-ttu-id="a629e-242">Вредоносности фильтра нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="a629e-242">Spam filter verdict</span></span>|<span data-ttu-id="a629e-243">Описание</span><span class="sxs-lookup"><span data-stu-id="a629e-243">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="a629e-244">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="a629e-244">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="a629e-245">Сообщение помечено как нежелательная почта и/или пропущенная фильтрация перед оценкой при фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a629e-245">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="a629e-246">Например, сообщение было помечено как нежелательная почта правилом обработки почты (также называемым правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="a629e-246">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span><br/><br/><span data-ttu-id="a629e-247">Сообщение пропустила фильтрацию нежелательной почты по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="a629e-247">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="a629e-248">Например, отправитель и получатель отображаются в одной организации.</span><span class="sxs-lookup"><span data-stu-id="a629e-248">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="a629e-249">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="a629e-249">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="a629e-250">Сообщение помечено как нежелательная почта перед оценкой с помощью фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a629e-250">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="a629e-251">Например, с помощью правила для почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="a629e-251">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="a629e-252">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="a629e-252">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="a629e-253">Сообщение помечено фильтром спама как спам.</span><span class="sxs-lookup"><span data-stu-id="a629e-253">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="a629e-254">**Не обнаружено**</span><span class="sxs-lookup"><span data-stu-id="a629e-254">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="a629e-255">При фильтрации нежелательной почты сообщение помечено как нежелательная почта.</span><span class="sxs-lookup"><span data-stu-id="a629e-255">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="a629e-256">**Снят**</span><span class="sxs-lookup"><span data-stu-id="a629e-256">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="a629e-257">Сообщение пропустило фильтрацию нежелательной почты, так как оно было выпущено из карантина.</span><span class="sxs-lookup"><span data-stu-id="a629e-257">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="a629e-258">**Разрешить клиентов**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a629e-258">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="a629e-259">Сообщение пропустила фильтрацию нежелательной почты из-за параметров политики защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a629e-259">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="a629e-260">Например, отправитель находится в списке разрешенных отправителей или разрешенных доменах.</span><span class="sxs-lookup"><span data-stu-id="a629e-260">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="a629e-261">**Блок клиента**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="a629e-261">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="a629e-262">Сообщение заблокировано фильтром нежелательной почты из-за параметров политики защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a629e-262">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="a629e-263">Например, отправитель находится в списке разрешенных отправителей или разрешенных доменах.</span><span class="sxs-lookup"><span data-stu-id="a629e-263">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="a629e-264">**Разрешение пользователя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a629e-264">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="a629e-265">Сообщение пропустило фильтрацию нежелательной почты, так как отправитель был помещен в список надежных отправителей пользователя.</span><span class="sxs-lookup"><span data-stu-id="a629e-265">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="a629e-266">**Пользовательская блокировка**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="a629e-266">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="a629e-267">Сообщение заблокировано фильтром нежелательной почты, так как отправитель находится в списке заблокированных отправителей пользователя.</span><span class="sxs-lookup"><span data-stu-id="a629e-267">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="a629e-268">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="a629e-268">**ZAP**</span></span>|<span data-ttu-id="a629e-269">н/д</span><span class="sxs-lookup"><span data-stu-id="a629e-269">n/a</span></span>|<span data-ttu-id="a629e-270">[Автоматическая очистка (ZAP)](zero-hour-auto-purge.md) . доставленное сообщение перемещено в папку "Нежелательная почта" или "карантин".</span><span class="sxs-lookup"><span data-stu-id="a629e-270">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="a629e-271">Вы настраиваете действие в политике защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a629e-271">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="a629e-272"><sup>\*</sup> Проверьте политики защиты от нежелательной почты, так как разрешенное сообщение было бы заблокировано службой.</span><span class="sxs-lookup"><span data-stu-id="a629e-272"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="a629e-273"><sup>\*\*</sup> Просмотрите политики защиты от нежелательной почты, так как эти сообщения должны быть помещены в карантин, а не доставлены.</span><span class="sxs-lookup"><span data-stu-id="a629e-273"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="a629e-274">**Места доставки**: вы, вероятно, захотите исследовать сообщения, которые были доставлены получателям (в папку "Входящие" или в папку "Нежелательная почта"), даже если пользователи не щелкают URL-адрес полезных данных в сообщении.</span><span class="sxs-lookup"><span data-stu-id="a629e-274">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="a629e-275">Вы также можете удалить помещенные в карантин сообщения из карантина.</span><span class="sxs-lookup"><span data-stu-id="a629e-275">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="a629e-276">Дополнительные сведения см. [в статье сообщения электронной почты, помещенные в карантин в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a629e-276">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="a629e-277">**Удалена папка**</span><span class="sxs-lookup"><span data-stu-id="a629e-277">**Deleted folder**</span></span>
  - <span data-ttu-id="a629e-278">**Утерян**</span><span class="sxs-lookup"><span data-stu-id="a629e-278">**Dropped**</span></span>
  - <span data-ttu-id="a629e-279">**Внешний**: получатель находится в локальной организации электронной почты в гибридных средах.</span><span class="sxs-lookup"><span data-stu-id="a629e-279">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="a629e-280">**Не удалось выполнить**</span><span class="sxs-lookup"><span data-stu-id="a629e-280">**Failed**</span></span>
  - <span data-ttu-id="a629e-281">**Пересылаются**</span><span class="sxs-lookup"><span data-stu-id="a629e-281">**Forwarded**</span></span>
  - <span data-ttu-id="a629e-282">**Входящие**</span><span class="sxs-lookup"><span data-stu-id="a629e-282">**Inbox**</span></span>
  - <span data-ttu-id="a629e-283">**Нежелательная почта**</span><span class="sxs-lookup"><span data-stu-id="a629e-283">**Junk folder**</span></span>
  - <span data-ttu-id="a629e-284">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="a629e-284">**Quarantine**</span></span>
  - <span data-ttu-id="a629e-285">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="a629e-285">**Unknown**</span></span>

- <span data-ttu-id="a629e-286">**URL-адреса**: эти значения описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="a629e-286">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="a629e-287">Во всех слоях, содержащих более 10 элементов, отображаются первые 10 элементов, а остальные элементы объединяются в **другие**.</span><span class="sxs-lookup"><span data-stu-id="a629e-287">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="a629e-288">Переходы по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="a629e-288">URL clicks</span></span>

<span data-ttu-id="a629e-289">При доставке фишингового сообщения в папку "Входящие" или "Нежелательная почта" получателя всегда существует вероятность того, что пользователь выполнит щелчок по URL-адресу полезных данных.</span><span class="sxs-lookup"><span data-stu-id="a629e-289">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="a629e-290">Не щелкая по URL-адресу, вы можете немало оценить успешность, но вам нужно определить, почему сообщение фишинга было даже доставлено в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="a629e-290">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="a629e-291">Если пользователь щелкнул URL-адрес полезных данных в phishing-сообщении, действия отображаются в области схемы **щелчков URL-адресов** в представлении сведения о кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-291">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="a629e-292">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="a629e-292">**Allowed**</span></span>

- <span data-ttu-id="a629e-293">**Блоккпаже**: получатель щелкает URL-адрес полезных данных, но его доступ к вредоносному веб-сайту заблокирован политиками [безопасных ссылок ATP](atp-safe-links.md) в Организации.</span><span class="sxs-lookup"><span data-stu-id="a629e-293">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="a629e-294">**Блоккпажеоверриде**: получатель находился на URL-адрес полезных данных в сообщении, безопасные ссылки ATP попытались остановить их, но могут переопределять блок.</span><span class="sxs-lookup"><span data-stu-id="a629e-294">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="a629e-295">Изучите [политики безопасных ссылок](set-up-atp-safe-links-policies.md) , чтобы узнать, почему пользователям разрешено переопределять безопасные ссылки вредоносности и продолжить работу с вредоносным веб-сайтом.</span><span class="sxs-lookup"><span data-stu-id="a629e-295">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="a629e-296">**Пендингдетонатионпаже**: безопасные вложения в Office 365 ATP находятся в процессе открытия и изучения URL-адреса полезных данных в среде виртуального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a629e-296">**PendingDetonationPage**: Safe Attachments in Office 365 ATP is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>

- <span data-ttu-id="a629e-297">**Пендингдетонатионпажеоверриде**: получателю разрешается переопределить процесс детонации полезных данных и открыть URL-адрес без ожидания результатов.</span><span class="sxs-lookup"><span data-stu-id="a629e-297">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="a629e-298">Вкладки</span><span class="sxs-lookup"><span data-stu-id="a629e-298">Tabs</span></span>

<span data-ttu-id="a629e-299">Вкладки в представлении сведения о кампании позволяют продолжить исследование кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-299">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="a629e-300">Сведения, отображаемые на вкладках, контролируются затененным диапазоном дат на временной шкале, как описано в разделе [сведения о кампании](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="a629e-300">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="a629e-301">**URL-адреса**: Если пользователи не щелкнули URL-адрес полезных данных в сообщении, этот раздел будет пустым.</span><span class="sxs-lookup"><span data-stu-id="a629e-301">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="a629e-302">Если пользователь мог щелкнуть URL-адрес, будут заполнены следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a629e-302">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="a629e-303">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a629e-303">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="a629e-304">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a629e-304">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="a629e-305">**Щелкните время**</span><span class="sxs-lookup"><span data-stu-id="a629e-305">**Click time**</span></span>
  - <span data-ttu-id="a629e-306">**Нажмите кнопку вредоносности**</span><span class="sxs-lookup"><span data-stu-id="a629e-306">**Click verdict**</span></span>

- <span data-ttu-id="a629e-307">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="a629e-307">**Sender IPs**</span></span>

  - <span data-ttu-id="a629e-308">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a629e-308">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="a629e-309">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="a629e-309">**Total count**</span></span>
  - <span data-ttu-id="a629e-310">**Папка "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="a629e-310">**Inboxed**</span></span>
  - <span data-ttu-id="a629e-311">**Нет папки "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="a629e-311">**Not Inboxed**</span></span>
  - <span data-ttu-id="a629e-312">**Переданная SPF**: отправитель прошел проверку подлинности с помощью [инфраструктуры политики отправителей (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="a629e-312">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="a629e-313">Отправитель, который не прошел проверку SPF, указывает, что отправитель, не прошедший проверку подлинности, или сообщение подделки законного отправителя.</span><span class="sxs-lookup"><span data-stu-id="a629e-313">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="a629e-314">**Отправители**</span><span class="sxs-lookup"><span data-stu-id="a629e-314">**Senders**</span></span>

  - <span data-ttu-id="a629e-315">**Отправитель**: фактический адрес отправителя в команде SMTP MAIL FROM, который не обязательно является адресом электронной почты, который пользователи видят в своих почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="a629e-315">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="a629e-316">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="a629e-316">**Total count**</span></span>
  - <span data-ttu-id="a629e-317">**Папка "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="a629e-317">**Inboxed**</span></span>
  - <span data-ttu-id="a629e-318">**Нет папки "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="a629e-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="a629e-319">**DKIM передан**: отправитель проходил проверку подлинности с помощью [ключей домена. определенная почта (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a629e-319">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="a629e-320">Отправитель, который не проходит проверку DKIM, указывает на отправителя, не прошедший проверку подлинности, или если сообщение поддается подделке законному отправителю.</span><span class="sxs-lookup"><span data-stu-id="a629e-320">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="a629e-321">**DMARC передано**: прошедший проверку подлинности отправителя проводилась проверкой [подлинности сообщений на основе домена, созданием отчетов и соответствием (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="a629e-321">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="a629e-322">Отправитель, который не проходит проверку DMARC, указывает на отправителя, не прошедший проверку подлинности, или если сообщение поддается подделке законному отправителю.</span><span class="sxs-lookup"><span data-stu-id="a629e-322">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="a629e-323">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="a629e-323">**Attachments**</span></span>

  - <span data-ttu-id="a629e-324">**Filename**</span><span class="sxs-lookup"><span data-stu-id="a629e-324">**Filename**</span></span>
  - <span data-ttu-id="a629e-325">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="a629e-325">**SHA256**</span></span>
  - <span data-ttu-id="a629e-326">**Семейство вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="a629e-326">**Malware family**</span></span>
  - <span data-ttu-id="a629e-327">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="a629e-327">**Total count**</span></span>

- <span data-ttu-id="a629e-328">**URL**</span><span class="sxs-lookup"><span data-stu-id="a629e-328">**URL**</span></span>

  - <span data-ttu-id="a629e-329">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a629e-329">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="a629e-330">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="a629e-330">**Total Count**</span></span>

<span data-ttu-id="a629e-331"><sup>\*</sup> Если щелкнуть это значение, в верхней части представления сведений о кампании откроется новое всплывающее окно с более подробными сведениями об указанном элементе (пользователь, URL-адрес и т. д.)</span><span class="sxs-lookup"><span data-stu-id="a629e-331"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="a629e-332">Чтобы вернуться в представление сведений о кампании, нажмите кнопку **Готово** в новом всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="a629e-332">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="a629e-333">Кнопки</span><span class="sxs-lookup"><span data-stu-id="a629e-333">Buttons</span></span>

<span data-ttu-id="a629e-334">Кнопки в представлении сведений о кампании позволяют использовать возможности обозревателя угроз для дальнейшего изучения кампании.</span><span class="sxs-lookup"><span data-stu-id="a629e-334">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="a629e-335">**Изучение кампании**: открывает новую вкладку поиска обозревателя угроз со значением **ID кампании** в качестве поискового фильтра.</span><span class="sxs-lookup"><span data-stu-id="a629e-335">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="a629e-336">**Просмотр сообщений, отправленных в папку "Входящие"**: открывает новую вкладку поиска угроз с помощью **идентификатора кампании** и **места доставки: "Входящие"** в качестве фильтра поиска.</span><span class="sxs-lookup"><span data-stu-id="a629e-336">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
