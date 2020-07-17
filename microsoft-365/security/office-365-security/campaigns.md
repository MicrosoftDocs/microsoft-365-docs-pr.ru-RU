---
title: Представления кампании в ATP
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
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039481"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="213fd-103">Представления кампании в ATP</span><span class="sxs-lookup"><span data-stu-id="213fd-103">Campaign Views in ATP</span></span>

<span data-ttu-id="213fd-104">Представления кампаний — это функция Advanced Threat protection (ATP) в центре безопасности & соответствия требованиям, которая определяет и распределяет фишинговые атаки в службе.</span><span class="sxs-lookup"><span data-stu-id="213fd-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="213fd-105">Представления кампаний помогают:</span><span class="sxs-lookup"><span data-stu-id="213fd-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="213fd-106">эффективно анализировать фишинговые атаки и отвечать на них;</span><span class="sxs-lookup"><span data-stu-id="213fd-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="213fd-107">точнее устанавливать область, затронутую атакой;</span><span class="sxs-lookup"><span data-stu-id="213fd-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="213fd-108">демонстрировать проблему лицам, ответственным за принятие решений.</span><span class="sxs-lookup"><span data-stu-id="213fd-108">Show value to decision makers.</span></span>

<span data-ttu-id="213fd-109">Представления кампаний позволяют быстрее и полнее получить общую картину атаки.</span><span class="sxs-lookup"><span data-stu-id="213fd-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="213fd-110">Что такое кампания?</span><span class="sxs-lookup"><span data-stu-id="213fd-110">What is a campaign?</span></span>

<span data-ttu-id="213fd-111">Кампания — это скоординированная атака по электронной почте, направленная против одной или нескольких организаций.</span><span class="sxs-lookup"><span data-stu-id="213fd-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="213fd-112">Атаки электронной почты, которые украсть учетные данные и данные компании, являются большой и лукративеной промышленности.</span><span class="sxs-lookup"><span data-stu-id="213fd-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="213fd-113">Так как технологии увеличивают усилия для прекращения атак, злоумышленники могут изменить их методы, чтобы убедиться в успешном завершении работы.</span><span class="sxs-lookup"><span data-stu-id="213fd-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="213fd-114">Корпорация Майкрософт использует огромные объемы защиты от нежелательной почты, защиты от нежелательной почты и вредоносных программ во всей службе, чтобы облегчить идентификацию кампаний.</span><span class="sxs-lookup"><span data-stu-id="213fd-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="213fd-115">Мы анализируем и классифицируем информацию об атаках в зависимости от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="213fd-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="213fd-116">Например,</span><span class="sxs-lookup"><span data-stu-id="213fd-116">For example:</span></span>

- <span data-ttu-id="213fd-117">**Источник атаки**: исходные IP-адреса и домены электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="213fd-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="213fd-118">**Свойства сообщения о атаке**: содержимое, стиль и тон сообщений.</span><span class="sxs-lookup"><span data-stu-id="213fd-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="213fd-119">**Объекты атаки**: домены получателей, должности получателей (администраторы, руководители и т. д.), типы компаний (крупные, мелкие, государственные, частные и т. д.) и отрасли.</span><span class="sxs-lookup"><span data-stu-id="213fd-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="213fd-120">**Полезные данные для атак**: вредоносные ссылки, вложения или другие полезные данные в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="213fd-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="213fd-121">Кампания может быть коротким временем существования или может занимать несколько дней, недель или месяцев с активными и неактивными периодами.</span><span class="sxs-lookup"><span data-stu-id="213fd-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="213fd-122">Кампания может быть запущена для конкретной организации, или ваша организация может быть частью более крупной кампании в нескольких компаниях.</span><span class="sxs-lookup"><span data-stu-id="213fd-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="213fd-123">Представления кампании центр безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="213fd-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="213fd-124">Представления кампаний доступны в [центре безопасности & соответствия требованиям](https://protection.office.com) в кампаниях по **управлению угрозами** \> **Campaigns**или непосредственно в <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="213fd-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Обзор кампаний в Центре безопасности и соответствия требованиям](../../media/campaigns-overview.png)

<span data-ttu-id="213fd-126">Вы также можете перейти к представлениям кампании из:</span><span class="sxs-lookup"><span data-stu-id="213fd-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="213fd-127">**Управление** \> угрозами **Explorer** \> **View (Просмотр** \> ) **Кампании**</span><span class="sxs-lookup"><span data-stu-id="213fd-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="213fd-128">**Управление** \> угрозами **Explorer** \> **View (Просмотр** \> ) **Вся электронная почта** \> Вкладка " **кампания** "</span><span class="sxs-lookup"><span data-stu-id="213fd-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="213fd-129">**Управление** \> угрозами **Explorer** \> **View (Просмотр** \> ) **Фишинг** \> Вкладка " **кампания** "</span><span class="sxs-lookup"><span data-stu-id="213fd-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="213fd-130">**Управление** \> угрозами **Explorer** \> **View (Просмотр** \> ) **Вредоносные программы** \> Вкладка " **кампания** "</span><span class="sxs-lookup"><span data-stu-id="213fd-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="213fd-131">Для доступа к представлениям кампаний необходимо быть участником группы ролей " **Управление организацией**", " **администратор безопасности**" или " **читатель безопасности** " в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="213fd-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="213fd-132">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="213fd-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="213fd-133">Обзор кампаний</span><span class="sxs-lookup"><span data-stu-id="213fd-133">Campaigns overview</span></span>

<span data-ttu-id="213fd-134">На странице Обзор отображаются сведения обо всех кампаниях.</span><span class="sxs-lookup"><span data-stu-id="213fd-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="213fd-135">На вкладке **кампания** по умолчанию в области **тип кампании** отображается гистограмма, на которой показано количество получателей в день.</span><span class="sxs-lookup"><span data-stu-id="213fd-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="213fd-136">По умолчанию на графике отображаются данные **фишинга** и **вредоносных программ** .</span><span class="sxs-lookup"><span data-stu-id="213fd-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="213fd-137">Если вы не видите данные кампании, попробуйте изменить диапазон дат или [фильтры](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="213fd-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="213fd-138">В оставшейся части страницы обзор отображаются следующие сведения на вкладке **кампания** :</span><span class="sxs-lookup"><span data-stu-id="213fd-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="213fd-139">**Название**</span><span class="sxs-lookup"><span data-stu-id="213fd-139">**Name**</span></span>

- <span data-ttu-id="213fd-140">**Образец темы**: строка темы одного из сообщений кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="213fd-141">Обратите внимание, что все сообщения в кампании не обязательно будут иметь одинаковые темы.</span><span class="sxs-lookup"><span data-stu-id="213fd-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="213fd-142">**Targeted**: процент, рассчитанный на: (число получателей кампании в организации)/(общее количество получателей в кампании для всех организаций в службе).</span><span class="sxs-lookup"><span data-stu-id="213fd-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="213fd-143">Это значение указывает степень, на которую кампания направлена в Организации (более высокое значение) и направлена в других организациях в службе (более низкое значение).</span><span class="sxs-lookup"><span data-stu-id="213fd-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="213fd-144">**Тип**: это значение является **фишингом** или **вредоносной программой**.</span><span class="sxs-lookup"><span data-stu-id="213fd-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="213fd-145">**Подтип**: это значение содержит дополнительные сведения о кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="213fd-146">Например,</span><span class="sxs-lookup"><span data-stu-id="213fd-146">For example:</span></span>

  - <span data-ttu-id="213fd-147">**Фишинг**: если он доступен, фирменная символика будет поддельной для этой кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="213fd-148">Например,,,, `Microsoft` `365` `Unknown` `Outlook` , или `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="213fd-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="213fd-149">**Вредоносные программы**: например, `HTML/PHISH` или `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="213fd-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="213fd-150">Если это так, фирменная символика, которая будет поддельной для этой кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="213fd-151">Когда обнаружение определяется технологией ATP, в значение подтипа добавляется префикс **ATP** .</span><span class="sxs-lookup"><span data-stu-id="213fd-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="213fd-152">**Получатели**: количество пользователей, которые подверглись этой кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="213fd-153">**Папка "Входящие"**: количество пользователей, которые получали сообщения от этой кампании в папке "Входящие" (не доставляются в папку "Нежелательная почта").</span><span class="sxs-lookup"><span data-stu-id="213fd-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="213fd-154">**Выбрано**: количество пользователей, которые щелкают по URL-адресу или открыли вложение в сообщении фишинга.</span><span class="sxs-lookup"><span data-stu-id="213fd-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="213fd-155">**Нажмите кнопку частота**: процент, рассчитанный по "**выбранным**  /  **папкам" Входящие**".</span><span class="sxs-lookup"><span data-stu-id="213fd-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="213fd-156">Это значение является индикатором эффективности кампании и того, могут ли получатели определить сообщение как фишинг и не щелкать URL-адрес полезных данных.</span><span class="sxs-lookup"><span data-stu-id="213fd-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="213fd-157">Обратите внимание, что это значение не используется в кампаниях по вредоносным программам.</span><span class="sxs-lookup"><span data-stu-id="213fd-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="213fd-158">**Просмотрено**: количество пользователей, фактически выполненных на веб-сайте полезных данных.</span><span class="sxs-lookup"><span data-stu-id="213fd-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="213fd-159">Если **выбраны значения,** но безопасные ссылки блокировали доступ к веб-сайту, это значение будет равно нулю.</span><span class="sxs-lookup"><span data-stu-id="213fd-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="213fd-160">На вкладке **Источник кампании** показаны источники сообщений на карте мира.</span><span class="sxs-lookup"><span data-stu-id="213fd-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="213fd-161">Фильтры и параметры</span><span class="sxs-lookup"><span data-stu-id="213fd-161">Filters and settings</span></span>

<span data-ttu-id="213fd-162">В верхней части страницы представления кампании есть несколько параметров фильтрации и запросов, которые помогут вам найти и изолировать конкретные кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Фильтры кампании](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="213fd-164">Наиболее простой способ фильтрации — Дата и время начала и Дата и время окончания.</span><span class="sxs-lookup"><span data-stu-id="213fd-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="213fd-165">Чтобы дополнительно отфильтровать представление, можно выполнить фильтрацию по одному свойству с несколькими значениями, нажав кнопку **тип кампании** , сделав выбор, а затем нажав кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="213fd-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="213fd-166">Доступные свойства кампании описаны в приведенном ниже списке.</span><span class="sxs-lookup"><span data-stu-id="213fd-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="213fd-167">Базовая</span><span class="sxs-lookup"><span data-stu-id="213fd-167">Basic</span></span>

  - <span data-ttu-id="213fd-168">**Тип кампании**: выбор **вредоносных программ** или **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="213fd-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="213fd-169">Очистка выбранных значений приводит к тому же результату, что и выбор обоих вариантов.</span><span class="sxs-lookup"><span data-stu-id="213fd-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="213fd-170">**Название кампании**</span><span class="sxs-lookup"><span data-stu-id="213fd-170">**Campaign name**</span></span>
  - <span data-ttu-id="213fd-171">**Подтип кампании**</span><span class="sxs-lookup"><span data-stu-id="213fd-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="213fd-172">**Sender**</span><span class="sxs-lookup"><span data-stu-id="213fd-172">**Sender**</span></span>
  - <span data-ttu-id="213fd-173">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="213fd-173">**Recipients**</span></span>
  - <span data-ttu-id="213fd-174">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="213fd-174">**Sender domain**</span></span>
  - <span data-ttu-id="213fd-175">**Тема**</span><span class="sxs-lookup"><span data-stu-id="213fd-175">**Subject**</span></span>
  - <span data-ttu-id="213fd-176">**Имя файла вложения**</span><span class="sxs-lookup"><span data-stu-id="213fd-176">**Attachment filename**</span></span>
  - <span data-ttu-id="213fd-177">**Семейство вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="213fd-177">**Malware family**</span></span>
  - <span data-ttu-id="213fd-178">**Действие доставки**</span><span class="sxs-lookup"><span data-stu-id="213fd-178">**Delivery action**</span></span>
  - <span data-ttu-id="213fd-179">**Технология обнаружения**</span><span class="sxs-lookup"><span data-stu-id="213fd-179">**Detection technology**</span></span>
  - <span data-ttu-id="213fd-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="213fd-180">**Tags**</span></span>
  - <span data-ttu-id="213fd-181">**Переопределение системы**</span><span class="sxs-lookup"><span data-stu-id="213fd-181">**System overrides**</span></span>

- <span data-ttu-id="213fd-182">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="213fd-182">Advanced</span></span>

  - <span data-ttu-id="213fd-183">**Идентификатор сообщения Интернета**: доступен в поле заголовка сообщения **с идентификатором** в заголовке сообщения.</span><span class="sxs-lookup"><span data-stu-id="213fd-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="213fd-184">Пример значения: `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="213fd-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="213fd-185">**Идентификатор сетевого сообщения**: значение GUID, которое доступно в поле заголовка **X – MS – Exchange – Organization – Network — Message — ID** в заголовке сообщения.</span><span class="sxs-lookup"><span data-stu-id="213fd-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="213fd-186">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="213fd-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="213fd-187">**Вложение SHA256**: чтобы найти хэш-значение SHA256 файла в Windows, выполните следующую команду в командной строки: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="213fd-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="213fd-188">**ИДЕНТИФИКАТОР кластера**</span><span class="sxs-lookup"><span data-stu-id="213fd-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="213fd-189">**Идентификатор политики оповещений**</span><span class="sxs-lookup"><span data-stu-id="213fd-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="213fd-190">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="213fd-190">URLs</span></span>

  - <span data-ttu-id="213fd-191">**Домен URL-адресов**</span><span class="sxs-lookup"><span data-stu-id="213fd-191">**URL domain**</span></span>
  - <span data-ttu-id="213fd-192">**Домен и путь URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="213fd-192">**URL domain and path**</span></span>
  - <span data-ttu-id="213fd-193">**URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="213fd-193">**URL**</span></span>
  - <span data-ttu-id="213fd-194">**Путь URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="213fd-194">**URL path**</span></span>
  - <span data-ttu-id="213fd-195">**Нажмите кнопку вредоносности**</span><span class="sxs-lookup"><span data-stu-id="213fd-195">**Click verdict**</span></span>

<span data-ttu-id="213fd-196">Для более расширенной фильтрации, включая фильтрацию по нескольким свойствам, можно нажать кнопку **Расширенный фильтр** , чтобы создать запрос.</span><span class="sxs-lookup"><span data-stu-id="213fd-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="213fd-197">Доступны те же свойства кампании, но со следующими расширениями:</span><span class="sxs-lookup"><span data-stu-id="213fd-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="213fd-198">Можно нажать кнопку **Добавить условие** , чтобы выбрать несколько условий.</span><span class="sxs-lookup"><span data-stu-id="213fd-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="213fd-199">Вы можете выбрать оператор **and** или **or** между условиями.</span><span class="sxs-lookup"><span data-stu-id="213fd-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="213fd-200">Вы можете выбрать элемент **Группа условий** в нижней части списка условий, чтобы сформировать сложные составные условия.</span><span class="sxs-lookup"><span data-stu-id="213fd-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="213fd-201">Когда все будет готово, нажмите кнопку **запрос** .</span><span class="sxs-lookup"><span data-stu-id="213fd-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="213fd-202">После создания базового или расширенного фильтра его можно сохранить с помощью команды **Сохранить запрос** или **Сохранить запрос как**.</span><span class="sxs-lookup"><span data-stu-id="213fd-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="213fd-203">Позже, когда вы вернетесь к представлениям кампании, вы можете загрузить сохраненный фильтр, щелкнув **сохраненные параметры запросов**.</span><span class="sxs-lookup"><span data-stu-id="213fd-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="213fd-204">Чтобы экспортировать диаграмму или список кампаний, нажмите кнопку **Экспорт** и выберите **Экспорт данных диаграммы** или **Экспорт списка кампаний**.</span><span class="sxs-lookup"><span data-stu-id="213fd-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="213fd-205">Если у вас есть подписка на Microsoft Defender ATP, вы можете щелкнуть **вдатп** , чтобы подключиться к сведениям о кампаниях и отключить их с помощью Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="213fd-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="213fd-206">Дополнительную информацию можно найти [в статье интеграция Office 365 ATP с защитником Microsoft](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="213fd-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="213fd-207">Сведения о кампании</span><span class="sxs-lookup"><span data-stu-id="213fd-207">Campaign details</span></span>

<span data-ttu-id="213fd-208">Если щелкнуть название кампании, сведения о кампании отобразятся в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="213fd-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="213fd-209">Сведения о кампании</span><span class="sxs-lookup"><span data-stu-id="213fd-209">Campaign information</span></span>

<span data-ttu-id="213fd-210">В верхней части представления сведений о кампании доступны следующие сведения о кампании:</span><span class="sxs-lookup"><span data-stu-id="213fd-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="213fd-211">**ID**: уникальный идентификатор кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="213fd-212">**Начато** и **завершено**: Дата начала и Дата окончания кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="213fd-213">Обратите внимание, что эти даты могут расширяться позже дат фильтрации, выбранных на странице Обзор.</span><span class="sxs-lookup"><span data-stu-id="213fd-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="213fd-214">**Воздействие**: в этом разделе содержатся следующие данные для выбранного фильтра диапазона дат (или выбранного на временной шкале):</span><span class="sxs-lookup"><span data-stu-id="213fd-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="213fd-215">Общее количество получателей.</span><span class="sxs-lookup"><span data-stu-id="213fd-215">The total number of recipients.</span></span>
  - <span data-ttu-id="213fd-216">Количество сообщений, отправленных в папку "Входящие" (то есть доставленных в папку "Входящие", а не в папку нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="213fd-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="213fd-217">Количество пользователей, которые щелкают в полезных данных URL-адреса в phishing-сообщениях.</span><span class="sxs-lookup"><span data-stu-id="213fd-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="213fd-218">Хове многие пользователи посещали URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="213fd-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="213fd-219">**Targeted**: процент, рассчитанный на: (число получателей кампании в организации)/(общее количество получателей в кампании для всех организаций в службе).</span><span class="sxs-lookup"><span data-stu-id="213fd-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="213fd-220">Обратите внимание, что это значение рассчитывается на протяжении всего жизненного цикла кампании и не изменяет даты фильтра.</span><span class="sxs-lookup"><span data-stu-id="213fd-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="213fd-221">Интерактивная временная шкала действий кампании: временная шкала показывает действия за весь срок жизни кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="213fd-222">По умолчанию затененная область включает фильтр диапазона дат, выбранный в обзоре.</span><span class="sxs-lookup"><span data-stu-id="213fd-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="213fd-223">Можно щелкнуть и перетащить для выбора определенной начальной точки и конечной точки, которая изменит <u>данные, отображаемые в области **влияния** , и на оставшейся части страницы, как описано в следующих разделах</u>.</span><span class="sxs-lookup"><span data-stu-id="213fd-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="213fd-224">В строке заголовка можно щелкнуть значок " **загрузить** кампанию для скачивания кампании" ![ ](../../media/download-campaign-write-up-button.png) , чтобы загрузить сведения о кампании в документ Word (по умолчанию с именем CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="213fd-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="213fd-225">Обратите внимание, что в этом документе содержатся сведения по всему сроку жизни кампании (а не только к выбранным датам фильтра).</span><span class="sxs-lookup"><span data-stu-id="213fd-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Сведения о кампании](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="213fd-227">Ход кампании</span><span class="sxs-lookup"><span data-stu-id="213fd-227">Campaign flow</span></span>

<span data-ttu-id="213fd-228">В центре представления сведений о кампании важные сведения о кампании представлены в разделе " **потоки** " в горизонтальной схеме (которая называется схемой _Санкэй_ ).</span><span class="sxs-lookup"><span data-stu-id="213fd-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="213fd-229">Эти сведения помогут вам изучить элементы кампании и ее потенциальное влияние на вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="213fd-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="213fd-230">Сведения, отображаемые на схеме **Flow** , контролируются затененным диапазоном дат на временной шкале, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="213fd-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Сведения о кампании без переходов пользователей по URL-адресам](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="213fd-232">Если навести указатель мыши на горизонтальную полоску на схеме, будет показано количество связанных с ней сообщений (например, сообщений с определенного исходного IP-адреса, сообщения из исходного IP-адреса с использованием указанного домена отправителя и т. д.).</span><span class="sxs-lookup"><span data-stu-id="213fd-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="213fd-233">Схема содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="213fd-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="213fd-234">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="213fd-234">**Sender IPs**</span></span>

- <span data-ttu-id="213fd-235">**Домены отправителей**</span><span class="sxs-lookup"><span data-stu-id="213fd-235">**Sender domains**</span></span>

- <span data-ttu-id="213fd-236">**Filter вердиктс**: эти значения связаны с доступными фильтрами фишинга и спама вердиктс, как описано в [заголовках сообщений по защите от нежелательной почты](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="213fd-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="213fd-237">Доступные значения описаны в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="213fd-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="213fd-238">**Значение**</span><span class="sxs-lookup"><span data-stu-id="213fd-238">**Value**</span></span>|<span data-ttu-id="213fd-239">**Вредоносности фильтра нежелательной почты**</span><span class="sxs-lookup"><span data-stu-id="213fd-239">**Spam filter verdict**</span></span>|<span data-ttu-id="213fd-240">**Описание**</span><span class="sxs-lookup"><span data-stu-id="213fd-240">**Description**</span></span>|
  |<span data-ttu-id="213fd-241">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="213fd-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="213fd-242">Сообщение помечено как нежелательная или пропущенная фильтрация перед оценкой при фильтрации нежелательной почты (например, с помощью правила для обработки нежелательной почты, которое также называется правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="213fd-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="213fd-243">Сообщение пропустила фильтрацию нежелательной почты по другим причинам (например, отправитель и получатель отображаются в одной и той же организации).</span><span class="sxs-lookup"><span data-stu-id="213fd-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="213fd-244">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="213fd-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="213fd-245">Сообщение было помечено как спам, прежде чем оно будет оценено при фильтрации нежелательной почты (например, с помощью правила для процесса обработки почты).</span><span class="sxs-lookup"><span data-stu-id="213fd-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="213fd-246">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="213fd-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="213fd-247">Сообщение помечено как нежелательное фильтром нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="213fd-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="213fd-248">**Не обнаружено**</span><span class="sxs-lookup"><span data-stu-id="213fd-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="213fd-249">При фильтрации нежелательной почты сообщение помечено как нежелательная почта.</span><span class="sxs-lookup"><span data-stu-id="213fd-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="213fd-250">**Снят**</span><span class="sxs-lookup"><span data-stu-id="213fd-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="213fd-251">Сообщение пропустило фильтрацию нежелательной почты, так как оно было выпущено из карантина.</span><span class="sxs-lookup"><span data-stu-id="213fd-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="213fd-252">**Разрешить клиентов**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="213fd-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="213fd-253">Сообщение пропустило фильтрацию нежелательной почты из-за параметров политики защиты от нежелательной почты (например, отправитель находится в списке разрешенных отправителей или список разрешенных доменов).</span><span class="sxs-lookup"><span data-stu-id="213fd-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="213fd-254">**Блок клиента**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="213fd-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="213fd-255">Сообщение заблокировано фильтром нежелательной почты из-за параметров политики защиты от нежелательной почты (например, отправитель находится в списке разрешенных отправителей или список разрешенных доменов).</span><span class="sxs-lookup"><span data-stu-id="213fd-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="213fd-256">**Разрешение пользователя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="213fd-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="213fd-257">Сообщение пропустило фильтрацию нежелательной почты, так как отправитель был в списке надежных отправителей пользователя в Outlook.</span><span class="sxs-lookup"><span data-stu-id="213fd-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="213fd-258">**Пользовательская блокировка**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="213fd-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="213fd-259">Сообщение заблокировано фильтром нежелательной почты, так как отправитель находится в списке заблокированных отправителей пользователя в Outlook.</span><span class="sxs-lookup"><span data-stu-id="213fd-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="213fd-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="213fd-260">**ZAP**</span></span>|<span data-ttu-id="213fd-261">н/д</span><span class="sxs-lookup"><span data-stu-id="213fd-261">n/a</span></span>|<span data-ttu-id="213fd-262">В соответствии с настройками политики защиты от нежелательной почты в почтовом сообщении (перемещено в папку "Нежелательная почта" или "помещено в карантин") было принято [нулевое автоматическое удаление (ZAP)](zero-hour-auto-purge.md) .</span><span class="sxs-lookup"><span data-stu-id="213fd-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="213fd-263"><sup>\*</sup>Проверьте политики защиты от нежелательной почты, так как разрешенное сообщение было бы заблокировано службой.</span><span class="sxs-lookup"><span data-stu-id="213fd-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="213fd-264"><sup>\*\*</sup>Просмотрите политики защиты от нежелательной почты, так как эти сообщения должны быть помещены в карантин, а не доставлены.</span><span class="sxs-lookup"><span data-stu-id="213fd-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="213fd-265">**Места доставки**: скорее всего, вы захотите исследовать сообщения, которые действительно были доставлены получателям (в папку "Входящие" или в папку "Нежелательная почта"), даже если пользователи не переходили по URL-адресам, указанным в сообщении.</span><span class="sxs-lookup"><span data-stu-id="213fd-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="213fd-266">Вы также можете удалить помещенные в карантин сообщения из карантина.</span><span class="sxs-lookup"><span data-stu-id="213fd-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="213fd-267">Дополнительные сведения см. [в статье сообщения электронной почты, помещенные в карантин в EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="213fd-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="213fd-268">**Удалена папка**</span><span class="sxs-lookup"><span data-stu-id="213fd-268">**Deleted folder**</span></span>
  - <span data-ttu-id="213fd-269">**Утерян**</span><span class="sxs-lookup"><span data-stu-id="213fd-269">**Dropped**</span></span>
  - <span data-ttu-id="213fd-270">**Внешний**: получатель находится в локальной организации электронной почты в гибридных средах.</span><span class="sxs-lookup"><span data-stu-id="213fd-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="213fd-271">**Не удалось выполнить**</span><span class="sxs-lookup"><span data-stu-id="213fd-271">**Failed**</span></span>
  - <span data-ttu-id="213fd-272">**Пересылаются**</span><span class="sxs-lookup"><span data-stu-id="213fd-272">**Forwarded**</span></span>
  - <span data-ttu-id="213fd-273">**Входящие**</span><span class="sxs-lookup"><span data-stu-id="213fd-273">**Inbox**</span></span>
  - <span data-ttu-id="213fd-274">**Нежелательная почта**</span><span class="sxs-lookup"><span data-stu-id="213fd-274">**Junk folder**</span></span>
  - <span data-ttu-id="213fd-275">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="213fd-275">**Quarantine**</span></span>
  - <span data-ttu-id="213fd-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="213fd-276">**Unknown**</span></span>

- <span data-ttu-id="213fd-277">**URL-адреса, которые вы щелкаете: эти URL-адреса**описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="213fd-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="213fd-278">Во всех слоях, содержащих более 10 элементов, отображаются первые 10 элементов, а остальные элементы объединяются в **другие**.</span><span class="sxs-lookup"><span data-stu-id="213fd-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="213fd-279">Переходы по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="213fd-279">URL clicks</span></span>

<span data-ttu-id="213fd-280">При доставке фишингового сообщения получателю (в папку "Входящие" или в папку "Нежелательная почта") всегда существует вероятность того, что пользователь выполнит щелчок URL-адреса полезных данных.</span><span class="sxs-lookup"><span data-stu-id="213fd-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="213fd-281">Не щелкая URL-адрес в доставленном сообщении — это незначительная мера успеха, но вам необходимо определить, почему сообщение фишинга было доставлено в свой почтовый ящик в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="213fd-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="213fd-282">Если пользователь щелкнул URL-адрес полезных данных в phishing-сообщении, действия отображаются в области схемы **щелчков URL-адресов** в представлении сведения о кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="213fd-283">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="213fd-283">**Allowed**</span></span>

- <span data-ttu-id="213fd-284">**Блоккпаже**: получатель щелкает URL-адрес полезных данных, но его доступ к вредоносному веб-сайту заблокирован политиками [безопасных ссылок ATP](atp-safe-links.md) в Организации.</span><span class="sxs-lookup"><span data-stu-id="213fd-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="213fd-285">**Блоккпажеоверриде**: получатель находился на URL-адрес полезных данных в сообщении, безопасные ссылки ATP попытались остановить их, но могут переопределять блок.</span><span class="sxs-lookup"><span data-stu-id="213fd-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="213fd-286">Необходимо изучить [политики безопасных ссылок](set-up-atp-safe-links-policies.md) , чтобы узнать, почему пользователям разрешено переопределять безопасные ссылки вредоносности и продолжить работу с вредоносным веб-сайтом.</span><span class="sxs-lookup"><span data-stu-id="213fd-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="213fd-287">**Пендингдетонатионпаже**: безопасные вложения ATP — это процесс открытия URL-адреса полезных данных в среде виртуального компьютера и просмотра того, что происходит.</span><span class="sxs-lookup"><span data-stu-id="213fd-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="213fd-288">**Пендингдетонатионпажеоверриде**: получателю разрешается переопределить процесс детонации полезных данных и открыть URL-адрес без ожидания результатов.</span><span class="sxs-lookup"><span data-stu-id="213fd-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="213fd-289">Вкладки</span><span class="sxs-lookup"><span data-stu-id="213fd-289">Tabs</span></span>

<span data-ttu-id="213fd-290">Вкладки в представлении сведения о кампании позволяют продолжить исследование кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="213fd-291">Сведения, отображаемые на вкладках, контролируются затененным диапазоном дат на временной шкале, как описано в разделе [сведения о кампании](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="213fd-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="213fd-292">**URL-адреса**: Если пользователи не щелкнули URL-адрес полезных данных в phishing-сообщении, этот раздел будет пустым.</span><span class="sxs-lookup"><span data-stu-id="213fd-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="213fd-293">Если пользователь мог щелкнуть URL-адрес, будут заполнены следующие значения:</span><span class="sxs-lookup"><span data-stu-id="213fd-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="213fd-294">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="213fd-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="213fd-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="213fd-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="213fd-296">**Щелкните время**</span><span class="sxs-lookup"><span data-stu-id="213fd-296">**Click time**</span></span>
  - <span data-ttu-id="213fd-297">**Нажмите кнопку вредоносности**</span><span class="sxs-lookup"><span data-stu-id="213fd-297">**Click verdict**</span></span>

- <span data-ttu-id="213fd-298">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="213fd-298">**Sender IPs**</span></span>

  - <span data-ttu-id="213fd-299">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="213fd-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="213fd-300">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="213fd-300">**Total count**</span></span>
  - <span data-ttu-id="213fd-301">**Папка "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="213fd-301">**Inboxed**</span></span>
  - <span data-ttu-id="213fd-302">**Нет папки "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="213fd-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="213fd-303">**Переданная SPF**: отправитель прошел проверку подлинности с помощью [инфраструктуры политики отправителей (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="213fd-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="213fd-304">Отправитель, не передающий проверку SPF, указывает на то, что отправитель не прошел проверку подлинности или что сообщение поддается подделке законному отправителю.</span><span class="sxs-lookup"><span data-stu-id="213fd-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="213fd-305">**Отправители**</span><span class="sxs-lookup"><span data-stu-id="213fd-305">**Senders**</span></span>

  - <span data-ttu-id="213fd-306">**Отправитель**: фактический адрес отправителя в команде SMTP MAIL FROM, который не обязательно является адресом электронной почты, который пользователи видят в своих почтовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="213fd-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="213fd-307">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="213fd-307">**Total count**</span></span>
  - <span data-ttu-id="213fd-308">**Папка "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="213fd-308">**Inboxed**</span></span>
  - <span data-ttu-id="213fd-309">**Нет папки "Входящие"**</span><span class="sxs-lookup"><span data-stu-id="213fd-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="213fd-310">**DKIM передан**: отправитель проходил проверку подлинности с помощью [ключей домена. определенная почта (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="213fd-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="213fd-311">Отправитель, который не проходит проверку DKIM, указывает, что отправитель не прошел проверку подлинности или что сообщение поддается подделке законному отправителю.</span><span class="sxs-lookup"><span data-stu-id="213fd-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="213fd-312">**DMARC передано**: прошедший проверку подлинности отправителя проводилась проверкой [подлинности сообщений на основе домена, созданием отчетов и соответствием (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="213fd-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="213fd-313">Отправитель, который не проходит проверку DMARC, указывает, что отправитель не прошел проверку подлинности или что сообщение поддается подделке законному отправителю.</span><span class="sxs-lookup"><span data-stu-id="213fd-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="213fd-314">**Вложения**</span><span class="sxs-lookup"><span data-stu-id="213fd-314">**Attachments**</span></span>

  - <span data-ttu-id="213fd-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="213fd-315">**Filename**</span></span>
  - <span data-ttu-id="213fd-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="213fd-316">**SHA256**</span></span>
  - <span data-ttu-id="213fd-317">**Семейство вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="213fd-317">**Malware family**</span></span>
  - <span data-ttu-id="213fd-318">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="213fd-318">**Total count**</span></span>

- <span data-ttu-id="213fd-319">**URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="213fd-319">**URL**</span></span>

  - <span data-ttu-id="213fd-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="213fd-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="213fd-321">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="213fd-321">**Total Count**</span></span>

<span data-ttu-id="213fd-322"><sup>\*</sup> Если щелкнуть это значение, в верхней части представления сведений о кампании откроется новое всплывающее окно с более подробными сведениями об указанном элементе (пользователь, URL-адрес и т. д.)</span><span class="sxs-lookup"><span data-stu-id="213fd-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="213fd-323">Чтобы вернуться в представление сведений о кампании, нажмите кнопку **Готово** в новом всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="213fd-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="213fd-324">Кнопки</span><span class="sxs-lookup"><span data-stu-id="213fd-324">Buttons</span></span>

<span data-ttu-id="213fd-325">Кнопки в представлении сведений о кампании позволяют использовать возможности обозревателя угроз для дальнейшего изучения кампании.</span><span class="sxs-lookup"><span data-stu-id="213fd-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="213fd-326">**Изучение кампании**: открывает новую вкладку поиска обозревателя угроз со значением **ID кампании** в качестве поискового фильтра.</span><span class="sxs-lookup"><span data-stu-id="213fd-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="213fd-327">**Просмотр сообщений, отправленных в папку "Входящие"**: открывает новую вкладку поиска угроз с помощью **идентификатора кампании** и **места доставки: "Входящие"** в качестве фильтра поиска.</span><span class="sxs-lookup"><span data-stu-id="213fd-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
