---
title: Представления кампаний в ATP
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
ms.openlocfilehash: f0f5d2305b4f17c7018d32eebd155b4ad2d459e7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825801"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="bb2db-103">Представления кампаний в ATP</span><span class="sxs-lookup"><span data-stu-id="bb2db-103">Campaign Views in ATP</span></span>

<span data-ttu-id="bb2db-104">Представления кампаний — это функция службы Advanced Threat Protection (ATP) в Центре безопасности & соответствия требованиям, которая определяет и классифицирует фишинговые атаки в службе.</span><span class="sxs-lookup"><span data-stu-id="bb2db-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="bb2db-105">Представления кампаний помогают:</span><span class="sxs-lookup"><span data-stu-id="bb2db-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="bb2db-106">эффективно анализировать фишинговые атаки и отвечать на них;</span><span class="sxs-lookup"><span data-stu-id="bb2db-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="bb2db-107">точнее устанавливать область, затронутую атакой;</span><span class="sxs-lookup"><span data-stu-id="bb2db-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="bb2db-108">демонстрировать проблему лицам, ответственным за принятие решений.</span><span class="sxs-lookup"><span data-stu-id="bb2db-108">Show value to decision makers.</span></span>

<span data-ttu-id="bb2db-109">Представления кампаний позволяют быстрее и полнее получить общую картину атаки.</span><span class="sxs-lookup"><span data-stu-id="bb2db-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="bb2db-110">Что такое кампания?</span><span class="sxs-lookup"><span data-stu-id="bb2db-110">What is a campaign?</span></span>

<span data-ttu-id="bb2db-111">Кампания — это скоординированная атака по электронной почте, направленная против одной или нескольких организаций.</span><span class="sxs-lookup"><span data-stu-id="bb2db-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="bb2db-112">Атаки, которые крадут учетные данные и данные компании, — это большой и йщикой отрасль.</span><span class="sxs-lookup"><span data-stu-id="bb2db-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="bb2db-113">По мере того, как технологии повышают усилия в станции атак, злоумышленники изменяют свои методы, чтобы обеспечить непродолжительное успех.</span><span class="sxs-lookup"><span data-stu-id="bb2db-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="bb2db-114">Для выявления кампаний корпорация Майкрософт использует в большой объем данных о защите от фишинга, нежелательной почты и вредоносных программ всей службы.</span><span class="sxs-lookup"><span data-stu-id="bb2db-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="bb2db-115">Анализирует и классифицируем информацию об атаке с учетом нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="bb2db-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="bb2db-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb2db-116">For example:</span></span>

- <span data-ttu-id="bb2db-117">**Источник атаки:** исходные IP-адреса и домены электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="bb2db-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="bb2db-118">**Свойства сообщений атаки:** содержимое, стиль и стиль сообщений.</span><span class="sxs-lookup"><span data-stu-id="bb2db-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="bb2db-119">**Объекты атаки**: домены получателей, должности получателей (администраторы, руководители и т. д.), типы компаний (крупные, мелкие, государственные, частные и т. д.) и отрасли.</span><span class="sxs-lookup"><span data-stu-id="bb2db-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="bb2db-120">**Полезные данные атаки:** вредоносные ссылки, вложения или другие данные в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="bb2db-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="bb2db-121">Кампания может быть коротким, или может занимать несколько дней, недель или месяцев с активными неактивными периодами.</span><span class="sxs-lookup"><span data-stu-id="bb2db-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="bb2db-122">Кампания могут запускаться в вашей конкретной организации или вашей организации является частью крупной кампании по нескольким компаниям.</span><span class="sxs-lookup"><span data-stu-id="bb2db-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="bb2db-123">Представления кампаний в Центре безопасности & требованиям</span><span class="sxs-lookup"><span data-stu-id="bb2db-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="bb2db-124">Представления кампаний доступны в Центре **Threat management** [безопасности & соответствия требованиям](https://protection.office.com) в кампаниях по управлению \> **Campaigns**угрозами или непосредственно в <https://protection.office.com/campaigns> ней.</span><span class="sxs-lookup"><span data-stu-id="bb2db-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Обзор кампаний в Центре безопасности и соответствия требованиям](../../media/campaigns-overview.png)

<span data-ttu-id="bb2db-126">Вы также можете получить доступ к представлениям кампаний в:</span><span class="sxs-lookup"><span data-stu-id="bb2db-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="bb2db-127">**Управление угрозами** \> **Проводник** \> **View** \> **Кампании**</span><span class="sxs-lookup"><span data-stu-id="bb2db-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="bb2db-128">**Управление угрозами** \> **Проводник** \> **View** \> **Вся почта** \> **Вкладка "Кампания"**</span><span class="sxs-lookup"><span data-stu-id="bb2db-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="bb2db-129">**Управление угрозами** \> **Проводник** \> **View** \> **Фишинг** \> **Вкладка "Кампания"**</span><span class="sxs-lookup"><span data-stu-id="bb2db-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="bb2db-130">**Управление угрозами** \> **Проводник** \> **View** \> **Вредонос** \> **Вкладка "Кампания"**</span><span class="sxs-lookup"><span data-stu-id="bb2db-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="bb2db-131">Чтобы получить доступ к представлениям кампаний, вам необходимо быть **членом групп ролей "Управление**организацией", **"Администратор**безопасности" **или "Читатель** безопасности" в Центре безопасности & соответствия требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="bb2db-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="bb2db-132">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bb2db-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="bb2db-133">Обзор кампаний</span><span class="sxs-lookup"><span data-stu-id="bb2db-133">Campaigns overview</span></span>

<span data-ttu-id="bb2db-134">На странице обзора приведены сведения обо всех кампаниях.</span><span class="sxs-lookup"><span data-stu-id="bb2db-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="bb2db-135">В области **типов кампаний** по умолчанию в области типов кампаний отображается гистограмма, в которой отображается количество получателей в день. **Campaign type**</span><span class="sxs-lookup"><span data-stu-id="bb2db-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="bb2db-136">По умолчанию на графике отображаются данные как **о фишинге,** так и **в рентабеляции.**</span><span class="sxs-lookup"><span data-stu-id="bb2db-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="bb2db-137">Если вы не видите данные кампаний, попробуйте изменить диапазон дат [или фильтры.](#filters-and-settings)</span><span class="sxs-lookup"><span data-stu-id="bb2db-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="bb2db-138">Далее на странице обзора отображаются следующие сведения на **вкладке "Кампания".**</span><span class="sxs-lookup"><span data-stu-id="bb2db-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="bb2db-139">**Название**</span><span class="sxs-lookup"><span data-stu-id="bb2db-139">**Name**</span></span>

- <span data-ttu-id="bb2db-140">**Образец темы**: строка темы одного из сообщений кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="bb2db-141">Обратите внимание, что все сообщения в кампании не обязательно будут иметь одинаковую тему.</span><span class="sxs-lookup"><span data-stu-id="bb2db-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="bb2db-142">**Targeted**: процент, рассчитанный следующим: (количество получателей кампании в организации) / (общее количество получателей в кампании во всей организации в службе).</span><span class="sxs-lookup"><span data-stu-id="bb2db-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="bb2db-143">Это значение указывает степень направления кампании специально для вашей организации (выше), а также направлена в других организациях (более низкое значение).</span><span class="sxs-lookup"><span data-stu-id="bb2db-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="bb2db-144">**Тип:** это значение может быть **фишинговым или** **вредоносным.**</span><span class="sxs-lookup"><span data-stu-id="bb2db-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="bb2db-145">**Подтип**— это значение содержит дополнительные сведения о кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="bb2db-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb2db-146">For example:</span></span>

  - <span data-ttu-id="bb2db-147">**Фишинг:** по мере возможности фишинг, который завершается в этой кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="bb2db-148">Например, `Microsoft` `365` , `Unknown` , `Outlook` , `DocuSign` или.</span><span class="sxs-lookup"><span data-stu-id="bb2db-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="bb2db-149">**"Вредоносная** `HTML/PHISH` программа: например" или `HTML/<MalwareFamilyName>` ".</span><span class="sxs-lookup"><span data-stu-id="bb2db-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="bb2db-150">Если эта кампания доступна, то она была фишинговой в этой кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="bb2db-151">Когда обнаружение используется технологией ATP, то к подтипу строка добавляется префикс **ATP.**</span><span class="sxs-lookup"><span data-stu-id="bb2db-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="bb2db-152">**Получатели**: количество пользователей, которые подверглись этой кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="bb2db-153">**В папку "Входящие"** количество пользователей, получавших сообщения из этой кампании в папке "Входящие" (не доставлялись в папку "Нежелательная почта").</span><span class="sxs-lookup"><span data-stu-id="bb2db-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="bb2db-154">**Щелкнут**: количество пользователей, которые щелкнули URL-адрес или открывали вложение в фишинговом сообщении.</span><span class="sxs-lookup"><span data-stu-id="bb2db-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="bb2db-155">**Скорость переходов:** процент, рассчитанный с помощью **"Птца;**  /  **"Птца".**</span><span class="sxs-lookup"><span data-stu-id="bb2db-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="bb2db-156">Это значение является индикатором эффективности кампании, и удаляла ли получатель возможность идентифицировать сообщение как фишинг и избегать щелчка по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="bb2db-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="bb2db-157">Обратите внимание, что это значение не используется в кампаниях, включающих вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="bb2db-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="bb2db-158">**Посещаемость:** количество фактически от ведущих через веб-сайт для полезных данных.</span><span class="sxs-lookup"><span data-stu-id="bb2db-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="bb2db-159">Если на странице **имеются нажатые** значения, но функция "Безопасные ссылки" заблокирована, то у него будет значение 0.</span><span class="sxs-lookup"><span data-stu-id="bb2db-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="bb2db-160">Вкладка **"Происхождение кампании"** отображает источники сообщений на карте мира.</span><span class="sxs-lookup"><span data-stu-id="bb2db-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="bb2db-161">Фильтры и параметры</span><span class="sxs-lookup"><span data-stu-id="bb2db-161">Filters and settings</span></span>

<span data-ttu-id="bb2db-162">В верхней части страницы "Представления кампании" существует несколько параметров фильтрации и запросов, которые помогут вам найти и изолировать кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Фильтры кампаний](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="bb2db-164">Основными доступными основными параметрами фильтрации является дата/время начала и дата и время окончания.</span><span class="sxs-lookup"><span data-stu-id="bb2db-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="bb2db-165">Для дальнейшей фильтрации представления можно выполнить фильтрацию одного свойства с несколькими значениями путем нажатия кнопки типа кампании, выбора и нажав **кнопку "Обновить".** **Campaign type**</span><span class="sxs-lookup"><span data-stu-id="bb2db-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="bb2db-166">Свойства доступных кампаний описаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="bb2db-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="bb2db-167">Базовая</span><span class="sxs-lookup"><span data-stu-id="bb2db-167">Basic</span></span>

  - <span data-ttu-id="bb2db-168">**Тип кампании: выберите** **"Вредоносные"** или **"Фишинг".**</span><span class="sxs-lookup"><span data-stu-id="bb2db-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="bb2db-169">При удалении выбранных фрагментов результат аналогичен выбору обоих.</span><span class="sxs-lookup"><span data-stu-id="bb2db-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="bb2db-170">**Имя кампании**</span><span class="sxs-lookup"><span data-stu-id="bb2db-170">**Campaign name**</span></span>
  - <span data-ttu-id="bb2db-171">**Подтип кампании**</span><span class="sxs-lookup"><span data-stu-id="bb2db-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="bb2db-172">**Sender**</span><span class="sxs-lookup"><span data-stu-id="bb2db-172">**Sender**</span></span>
  - <span data-ttu-id="bb2db-173">**Получатели**</span><span class="sxs-lookup"><span data-stu-id="bb2db-173">**Recipients**</span></span>
  - <span data-ttu-id="bb2db-174">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="bb2db-174">**Sender domain**</span></span>
  - <span data-ttu-id="bb2db-175">**Тема**</span><span class="sxs-lookup"><span data-stu-id="bb2db-175">**Subject**</span></span>
  - <span data-ttu-id="bb2db-176">**Имя файла вложения**</span><span class="sxs-lookup"><span data-stu-id="bb2db-176">**Attachment filename**</span></span>
  - <span data-ttu-id="bb2db-177">**Семейство вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="bb2db-177">**Malware family**</span></span>
  - <span data-ttu-id="bb2db-178">**Действие доставки**</span><span class="sxs-lookup"><span data-stu-id="bb2db-178">**Delivery action**</span></span>
  - <span data-ttu-id="bb2db-179">**Технология обнаружения**</span><span class="sxs-lookup"><span data-stu-id="bb2db-179">**Detection technology**</span></span>
  - <span data-ttu-id="bb2db-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="bb2db-180">**Tags**</span></span>
  - <span data-ttu-id="bb2db-181">**Переопределения системы**</span><span class="sxs-lookup"><span data-stu-id="bb2db-181">**System overrides**</span></span>

- <span data-ttu-id="bb2db-182">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="bb2db-182">Advanced</span></span>

  - <span data-ttu-id="bb2db-183">**Идентификатор сообщения Интернета:** доступно в **поле заголовка Message-ID** заголовка сообщения.</span><span class="sxs-lookup"><span data-stu-id="bb2db-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="bb2db-184">Пример значения — `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (обратите внимание на угловые скобки).</span><span class="sxs-lookup"><span data-stu-id="bb2db-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="bb2db-185">**Идентификатор сообщения сети:** значение GUID, которое доступно в поле **заголовка Сообщения X-MS-Exchange-Organization-Network-Message-Id.**</span><span class="sxs-lookup"><span data-stu-id="bb2db-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="bb2db-186">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="bb2db-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="bb2db-187">**Блокировка SHA256**(вложение) для файла в Windows, выполните следующую команду в командной `certutil.exe -hashfile "<Path>\<Filename>" SHA256` строке:</span><span class="sxs-lookup"><span data-stu-id="bb2db-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="bb2db-188">**Идентификатор кластера**</span><span class="sxs-lookup"><span data-stu-id="bb2db-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="bb2db-189">**Идентификатор политики оповещений**</span><span class="sxs-lookup"><span data-stu-id="bb2db-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="bb2db-190">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="bb2db-190">URLs</span></span>

  - <span data-ttu-id="bb2db-191">**Домен URL-адреса**</span><span class="sxs-lookup"><span data-stu-id="bb2db-191">**URL domain**</span></span>
  - <span data-ttu-id="bb2db-192">**Домен и путь URL**</span><span class="sxs-lookup"><span data-stu-id="bb2db-192">**URL domain and path**</span></span>
  - <span data-ttu-id="bb2db-193">**URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="bb2db-193">**URL**</span></span>
  - <span data-ttu-id="bb2db-194">**Путь URL**</span><span class="sxs-lookup"><span data-stu-id="bb2db-194">**URL path**</span></span>
  - <span data-ttu-id="bb2db-195">**Нажмите "загода"**</span><span class="sxs-lookup"><span data-stu-id="bb2db-195">**Click verdict**</span></span>

<span data-ttu-id="bb2db-196">Для более расширенной фильтрации, в том числе фильтрации по нескольким свойствам, можно нажать кнопку **расширенного фильтра,** чтобы создать запрос.</span><span class="sxs-lookup"><span data-stu-id="bb2db-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="bb2db-197">Доступны те же свойства кампании, но усовершенствованы следующие улучшения:</span><span class="sxs-lookup"><span data-stu-id="bb2db-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="bb2db-198">Можно нажать **кнопку "Добавить условие",** чтобы выбрать несколько условий.</span><span class="sxs-lookup"><span data-stu-id="bb2db-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="bb2db-199">Вы можете **выбрать оператор** "И" или "Или" между условиями. **Or**</span><span class="sxs-lookup"><span data-stu-id="bb2db-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="bb2db-200">Вы можете выбрать **элемент группы** условий в нижней части списка условий для формы сложных составных условий.</span><span class="sxs-lookup"><span data-stu-id="bb2db-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="bb2db-201">По завершении нажмите кнопку **"Запрос".**</span><span class="sxs-lookup"><span data-stu-id="bb2db-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="bb2db-202">После создания базового или расширенного фильтра его можно сохранить, используя запрос **сохранения или** **сохранить в качестве.**</span><span class="sxs-lookup"><span data-stu-id="bb2db-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="bb2db-203">Позже, вернувшемуся в представления кампании, можно загрузить сохраненный фильтр, щелкнув **сохраненные параметры запроса.**</span><span class="sxs-lookup"><span data-stu-id="bb2db-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="bb2db-204">Чтобы экспортировать граф или список кампаний, выберите **"Экспортировать"** и выберите пункт **"Экспорт данных диаграммы"** **или список кампаний.**</span><span class="sxs-lookup"><span data-stu-id="bb2db-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="bb2db-205">Если у вас есть подписка на ATP в Microsoft Defender, можно **щелкнуть WDATP,** чтобы подключить или отключить сведения кампаний с помощью ATP в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bb2db-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="bb2db-206">Дополнительные сведения см. в разделе ["Интеграция ATP Office 365 с ATP в Microsoft Defender".](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)</span><span class="sxs-lookup"><span data-stu-id="bb2db-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="bb2db-207">Сведения о кампании</span><span class="sxs-lookup"><span data-stu-id="bb2db-207">Campaign details</span></span>

<span data-ttu-id="bb2db-208">Если щелкнуть название кампании, сведения о кампании отображаются во всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="bb2db-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="bb2db-209">Сведения о кампании</span><span class="sxs-lookup"><span data-stu-id="bb2db-209">Campaign information</span></span>

<span data-ttu-id="bb2db-210">В верхней части представления сведений о кампании доступны следующие сведения о кампании:</span><span class="sxs-lookup"><span data-stu-id="bb2db-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="bb2db-211">**ID**: уникальный идентификатор кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="bb2db-212">**Дата** **начала и окончания:** дата начала и дата окончания кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="bb2db-213">Обратите внимание, что даты могут длиться не только с выбранных на странице обзора, с начала фильтра.</span><span class="sxs-lookup"><span data-stu-id="bb2db-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="bb2db-214">**Влияние:** этот раздел содержит следующие данные для выбранного диапазона дат (или которые вы выбрали на временной шкале):</span><span class="sxs-lookup"><span data-stu-id="bb2db-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="bb2db-215">Общее количество получателей.</span><span class="sxs-lookup"><span data-stu-id="bb2db-215">The total number of recipients.</span></span>
  - <span data-ttu-id="bb2db-216">Количество сообщений, которые были «Входящие» (которые доставлены в папку "Входящие", а не в папку нежелательной почты).</span><span class="sxs-lookup"><span data-stu-id="bb2db-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="bb2db-217">Количество пользователей, щелкнувших по URL-адресу в фишинговом сообщении.</span><span class="sxs-lookup"><span data-stu-id="bb2db-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="bb2db-218">Однако URL-адрес посещал многие пользователи.</span><span class="sxs-lookup"><span data-stu-id="bb2db-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="bb2db-219">**Targeted**: процент, рассчитанный следующим: (количество получателей кампании в организации) / (общее количество получателей в кампании во всей организации в службе).</span><span class="sxs-lookup"><span data-stu-id="bb2db-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="bb2db-220">Обратите внимание, что это значение вычисляется на протяжении всего времени существования кампании и не изменяет даты фильтра.</span><span class="sxs-lookup"><span data-stu-id="bb2db-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="bb2db-221">Интерактивная временная шкала активности кампании. На временной шкале отображаются действия в течение всего жизненного цикла кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="bb2db-222">По умолчанию затененная область включает фильтр диапазона дат, выбранный в обзоре.</span><span class="sxs-lookup"><span data-stu-id="bb2db-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="bb2db-223">Щелкните и перетаскивайте, чтобы выбрать определенную начальную и конечную точки, изменяя данные, отображаемые в <u> **области** влияния, а также на оставшейся части страницы, как описано в следующих разделах.</u></span><span class="sxs-lookup"><span data-stu-id="bb2db-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="bb2db-224">В заголовке окна можно щелкнуть **значок записи** "Скачать кампанию" "Скачать кампанию" и скачать в документ Word сведения CampaignReport.docx о кампании ![ ](../../media/download-campaign-write-up-button.png) ().</span><span class="sxs-lookup"><span data-stu-id="bb2db-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="bb2db-225">Обратите внимание, что этот документ содержит сведения о всем времени существования кампании (а не только дат, которые вы выбрали).</span><span class="sxs-lookup"><span data-stu-id="bb2db-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Сведения о кампании](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="bb2db-227">Ход кампании</span><span class="sxs-lookup"><span data-stu-id="bb2db-227">Campaign flow</span></span>

<span data-ttu-id="bb2db-228">В центре представления сведений о кампании важные сведения о кампании представлены в разделе **"Поток"** на горизонтальной схеме потока _(также называемой схемой Sankey)._</span><span class="sxs-lookup"><span data-stu-id="bb2db-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="bb2db-229">Эти сведения помогут вам изучить элементы кампании и ее потенциальное влияние на вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="bb2db-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="bb2db-230">Информацией, отображаемой на схеме **потока,** управляет ся диапазон дат затененного диапазона на временной шкале, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="bb2db-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Сведения о кампании без переходов пользователей по URL-адресам](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="bb2db-232">Если навести указатель мыши на горизонтальную полоску на схеме, будет показано количество связанных с ней сообщений (например, сообщений с определенного исходного IP-адреса, сообщения из исходного IP-адреса с использованием указанного домена отправителя и т. д.).</span><span class="sxs-lookup"><span data-stu-id="bb2db-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="bb2db-233">Схема содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="bb2db-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="bb2db-234">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="bb2db-234">**Sender IPs**</span></span>

- <span data-ttu-id="bb2db-235">**Домены отправителей**</span><span class="sxs-lookup"><span data-stu-id="bb2db-235">**Sender domains**</span></span>

- <span data-ttu-id="bb2db-236">**Выводы фильтров:** эти значения относятся к выводам по доступным фишинговым и фильтрам нежелательной почты, описанным в [заголовках сообщений средства защиты от нежелательной почты.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="bb2db-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="bb2db-237">Доступные значения представлены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="bb2db-237">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="bb2db-238">Значение</span><span class="sxs-lookup"><span data-stu-id="bb2db-238">Value</span></span>|<span data-ttu-id="bb2db-239">Затрагиваемое фильтром нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="bb2db-239">Spam filter verdict</span></span>|<span data-ttu-id="bb2db-240">Description</span><span class="sxs-lookup"><span data-stu-id="bb2db-240">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="bb2db-241">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="bb2db-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="bb2db-242">Сообщение помечено как не спам или (или) пропущенная фильтрация, прежде чем будет оцениваться фильтром нежелательной почты (например, правилом транспорта).</span><span class="sxs-lookup"><span data-stu-id="bb2db-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="bb2db-243">Сообщение пропустило фильтрацию нежелательной почты по другим причинам (например, отправитель и получатель выглядят в одной организации).</span><span class="sxs-lookup"><span data-stu-id="bb2db-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="bb2db-244">**Заблокировано**</span><span class="sxs-lookup"><span data-stu-id="bb2db-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="bb2db-245">Сообщение помечено как нежелательное до оценки фильтром нежелательной почты (например, с помощью правила потока обработки почты).</span><span class="sxs-lookup"><span data-stu-id="bb2db-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="bb2db-246">**Обнаружено**</span><span class="sxs-lookup"><span data-stu-id="bb2db-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="bb2db-247">Сообщение помечено как нежелательное фильтром нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="bb2db-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="bb2db-248">**Не обнаружено**</span><span class="sxs-lookup"><span data-stu-id="bb2db-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="bb2db-249">Сообщение помечено фильтром нежелательной почты как не нежелательное.</span><span class="sxs-lookup"><span data-stu-id="bb2db-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="bb2db-250">**Выпущено**</span><span class="sxs-lookup"><span data-stu-id="bb2db-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="bb2db-251">Сообщение пропустило фильтрацию нежелательной почты, поскольку оно было освобождено из карантина.</span><span class="sxs-lookup"><span data-stu-id="bb2db-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="bb2db-252">**Разрешить клиент**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb2db-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="bb2db-253">Сообщение пропустило фильтрацию нежелательной почты из-за параметров политики защиты от нежелательной почты (например, если отправитель включен в список разрешенных или разрешенных доменов).</span><span class="sxs-lookup"><span data-stu-id="bb2db-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="bb2db-254">**Блокировка клиента**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb2db-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="bb2db-255">Сообщение заблокировано фильтром нежелательной почты из-за параметров политики защиты от нежелательной почты (например, список отправителей в списке разрешенных или разрешенных доменов).</span><span class="sxs-lookup"><span data-stu-id="bb2db-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="bb2db-256">**Разрешение пользователей**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb2db-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="bb2db-257">Сообщение пропустило фильтрацию спама, так как отправитель включен в список надежных отправителей пользователя в Outlook.</span><span class="sxs-lookup"><span data-stu-id="bb2db-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="bb2db-258">**Блокировка пользователя**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb2db-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="bb2db-259">Сообщение заблокировано фильтром нежелательной почты, поскольку отправитель включен в список заблокированных отправителей пользователя в Outlook.</span><span class="sxs-lookup"><span data-stu-id="bb2db-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="bb2db-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="bb2db-260">**ZAP**</span></span>|<span data-ttu-id="bb2db-261">н/д</span><span class="sxs-lookup"><span data-stu-id="bb2db-261">n/a</span></span>|<span data-ttu-id="bb2db-262">[Автоматическая очистка принято в](zero-hour-auto-purge.md) соответствии с параметрами политики защиты от нежелательной почты (перемещается в папку "Нежелательная почта" или "Помещено в карантин").</span><span class="sxs-lookup"><span data-stu-id="bb2db-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="bb2db-263"><sup>\*</sup> Проверьте политики защиты от нежелательной почты, так как разрешенное сообщение, скорее всего, было заблокировано службой.</span><span class="sxs-lookup"><span data-stu-id="bb2db-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="bb2db-264"><sup>\*\*</sup> Просмотрите политики защиты от нежелательной почты, так как они должны быть помещены в карантин и не доставляются.</span><span class="sxs-lookup"><span data-stu-id="bb2db-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="bb2db-265">**Места доставки**: скорее всего, вы захотите исследовать сообщения, которые действительно были доставлены получателям (в папку "Входящие" или в папку "Нежелательная почта"), даже если пользователи не переходили по URL-адресам, указанным в сообщении.</span><span class="sxs-lookup"><span data-stu-id="bb2db-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="bb2db-266">Также можно удалять сообщения, помещенные на карантин, из карантина.</span><span class="sxs-lookup"><span data-stu-id="bb2db-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="bb2db-267">Дополнительные сведения см. в статье "Сообщения [электронной почты, помещенные на карантин" в службе EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="bb2db-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="bb2db-268">**Удалена папка**</span><span class="sxs-lookup"><span data-stu-id="bb2db-268">**Deleted folder**</span></span>
  - <span data-ttu-id="bb2db-269">**Сокращен**</span><span class="sxs-lookup"><span data-stu-id="bb2db-269">**Dropped**</span></span>
  - <span data-ttu-id="bb2db-270">**Внешнее:** получатель находится в локальной организации электронной почты в гибридных средах.</span><span class="sxs-lookup"><span data-stu-id="bb2db-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="bb2db-271">**Не удалось выполнить**</span><span class="sxs-lookup"><span data-stu-id="bb2db-271">**Failed**</span></span>
  - <span data-ttu-id="bb2db-272">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="bb2db-272">**Forwarded**</span></span>
  - <span data-ttu-id="bb2db-273">**Входящие**</span><span class="sxs-lookup"><span data-stu-id="bb2db-273">**Inbox**</span></span>
  - <span data-ttu-id="bb2db-274">**Нежелательная почта**</span><span class="sxs-lookup"><span data-stu-id="bb2db-274">**Junk folder**</span></span>
  - <span data-ttu-id="bb2db-275">**Карантин**</span><span class="sxs-lookup"><span data-stu-id="bb2db-275">**Quarantine**</span></span>
  - <span data-ttu-id="bb2db-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="bb2db-276">**Unknown**</span></span>

- <span data-ttu-id="bb2db-277">**Щелчки**по URL-адресам: они описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="bb2db-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="bb2db-278">На всех уровнях, содержащих более 10 элементов, отображаются 10 верхних элементов, а остальные — вместе в **другие.**</span><span class="sxs-lookup"><span data-stu-id="bb2db-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="bb2db-279">Переходы по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="bb2db-279">URL clicks</span></span>

<span data-ttu-id="bb2db-280">Когда фишинговое сообщение доставляется получателю (в папку "Входящие" или папку нежелательной почты), всегда есть возможность щелкнуть URL-адрес полезных данных.</span><span class="sxs-lookup"><span data-stu-id="bb2db-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="bb2db-281">Не щелкать URL-адрес в доставленном сообщении неявляет ся успешной попыткой, но нужно определить, почему фишинговое сообщение было доставлено в его почтовый ящик в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="bb2db-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="bb2db-282">Если пользователь щелкнул URL-адрес полезных данных в фишинговом сообщении, действия отображаются в **области переходов по** URL-адресу на схеме в представлении сведений о кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="bb2db-283">**Разрешено**</span><span class="sxs-lookup"><span data-stu-id="bb2db-283">**Allowed**</span></span>

- <span data-ttu-id="bb2db-284">**BlockPage:** получатель щелкнул URL-адрес полезных данных, но его доступ к вредоносному веб-сайту был заблокирован политикой [безопасных](atp-safe-links.md) ссылок ATP в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bb2db-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="bb2db-285">**BlockPageOverride:** получатель щелкнул URL-адрес в сообщении, попытались остановить функции "Безопасные ссылки ATP", но ей было разрешено переопределить блокировку.</span><span class="sxs-lookup"><span data-stu-id="bb2db-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="bb2db-286">Необходимо изучить политики [безопасных ссылок,](set-up-atp-safe-links-policies.md) чтобы определить, почему пользователям разрешено переопределять уведомленные ссылки и перемещаться на вредоносный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="bb2db-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="bb2db-287">**PendingDetonationPage**: "Безопасные вложения ATP" открытие URL-адреса полезных данных в среде виртуального компьютера и просмотр того, что происходит.</span><span class="sxs-lookup"><span data-stu-id="bb2db-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="bb2db-288">**PendingDetonationPageOverride:** получателю разрешено переопределить процесс детонации полезных данных и открыть URL-адрес без ожидания результатов.</span><span class="sxs-lookup"><span data-stu-id="bb2db-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="bb2db-289">Вкладки</span><span class="sxs-lookup"><span data-stu-id="bb2db-289">Tabs</span></span>

<span data-ttu-id="bb2db-290">Вкладки в представлении сведений о кампании позволяют детально изучить кампанию.</span><span class="sxs-lookup"><span data-stu-id="bb2db-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="bb2db-291">Информацией, отображаемой на вкладках, управляет диапазон дат затененного диапазона на временной шкале, как описано в разделе [сведений о кампании.](#campaign-information)</span><span class="sxs-lookup"><span data-stu-id="bb2db-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="bb2db-292">**Переходы по**URL-адресу: если пользователи не щелкнули URL-адрес полезных данных в фишинговом сообщении, этот раздел будет пустым.</span><span class="sxs-lookup"><span data-stu-id="bb2db-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="bb2db-293">Если пользователь мог щелкнуть URL-адрес, будут заполняться следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bb2db-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="bb2db-294">**Пользователь**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb2db-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="bb2db-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb2db-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="bb2db-296">**Время перехода**</span><span class="sxs-lookup"><span data-stu-id="bb2db-296">**Click time**</span></span>
  - <span data-ttu-id="bb2db-297">**Нажмите "загода"**</span><span class="sxs-lookup"><span data-stu-id="bb2db-297">**Click verdict**</span></span>

- <span data-ttu-id="bb2db-298">**IP-адреса отправителей**</span><span class="sxs-lookup"><span data-stu-id="bb2db-298">**Sender IPs**</span></span>

  - <span data-ttu-id="bb2db-299">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb2db-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="bb2db-300">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="bb2db-300">**Total count**</span></span>
  - <span data-ttu-id="bb2db-301">**"Входящие"**</span><span class="sxs-lookup"><span data-stu-id="bb2db-301">**Inboxed**</span></span>
  - <span data-ttu-id="bb2db-302">**Не включено**</span><span class="sxs-lookup"><span data-stu-id="bb2db-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="bb2db-303">**Переданный spF:** отправитель прошел [проверку подлинности инфраструктурой политики отправителей (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="bb2db-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="bb2db-304">Отправитель, не проходящий проверку инфраструктуры политики отправителей, означает, что отправитель не проходит проверку подлинности либо сообщение подделается как поддельный отправитель.</span><span class="sxs-lookup"><span data-stu-id="bb2db-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="bb2db-305">**Отправители**</span><span class="sxs-lookup"><span data-stu-id="bb2db-305">**Senders**</span></span>

  - <span data-ttu-id="bb2db-306">**Sender**(Отправитель — это фактический адрес отправителя в команде SMTP MAIL FROM, которая не обязательно является адресом From:, который отображается для пользователей в своих почтовых клиентах).</span><span class="sxs-lookup"><span data-stu-id="bb2db-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="bb2db-307">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="bb2db-307">**Total count**</span></span>
  - <span data-ttu-id="bb2db-308">**"Входящие"**</span><span class="sxs-lookup"><span data-stu-id="bb2db-308">**Inboxed**</span></span>
  - <span data-ttu-id="bb2db-309">**Не включено**</span><span class="sxs-lookup"><span data-stu-id="bb2db-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="bb2db-310">**Переданные dKIM:** отправитель прошел проверку подлинности с [помощью DKIM.](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="bb2db-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="bb2db-311">Отправитель, не прошедший проверку DKIM, означает, что отправитель не прошел проверку подлинности или сообщение подделает ся доверенного отправителя.</span><span class="sxs-lookup"><span data-stu-id="bb2db-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="bb2db-312">**Проверка DMARC прошла**проверку подлинности сообщений, создания отчетов и [собрания DMARC.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="bb2db-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="bb2db-313">Отправитель, не прошедший проверку DMARC, означает, что отправитель не проходит проверку подлинности либо сообщение подделано доверенному отправителю.</span><span class="sxs-lookup"><span data-stu-id="bb2db-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="bb2db-314">**Вложения**</span><span class="sxs-lookup"><span data-stu-id="bb2db-314">**Attachments**</span></span>

  - <span data-ttu-id="bb2db-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="bb2db-315">**Filename**</span></span>
  - <span data-ttu-id="bb2db-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="bb2db-316">**SHA256**</span></span>
  - <span data-ttu-id="bb2db-317">**Семейство вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="bb2db-317">**Malware family**</span></span>
  - <span data-ttu-id="bb2db-318">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="bb2db-318">**Total count**</span></span>

- <span data-ttu-id="bb2db-319">**URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="bb2db-319">**URL**</span></span>

  - <span data-ttu-id="bb2db-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb2db-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="bb2db-321">**Общее количество**</span><span class="sxs-lookup"><span data-stu-id="bb2db-321">**Total Count**</span></span>

<span data-ttu-id="bb2db-322"><sup>\*</sup> Если щелкнуть это значение, в верхней части представления сведений о кампании откроется новое всплывающее окно с более подробными сведениями об указанном элементе (пользователь, URL-адрес и т. д.)</span><span class="sxs-lookup"><span data-stu-id="bb2db-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="bb2db-323">Чтобы вернуться в представление сведений о кампании, нажмите кнопку **Готово** в новом всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="bb2db-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="bb2db-324">Кнопки</span><span class="sxs-lookup"><span data-stu-id="bb2db-324">Buttons</span></span>

<span data-ttu-id="bb2db-325">Кнопки в представлении сведений о кампании позволяют использовать возможности обозревателя угроз для дальнейшего изучения кампании.</span><span class="sxs-lookup"><span data-stu-id="bb2db-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="bb2db-326">**Изучение кампании**: открывает новую вкладку поиска обозревателя угроз со значением **ID кампании** в качестве поискового фильтра.</span><span class="sxs-lookup"><span data-stu-id="bb2db-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="bb2db-327">**Изучение входящих сообщений:** открывает новую вкладку поиска обозревателя угроз с использованием **идентификатора кампании** и расположения **доставки: "Входящие"** в качестве поискового фильтра.</span><span class="sxs-lookup"><span data-stu-id="bb2db-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
