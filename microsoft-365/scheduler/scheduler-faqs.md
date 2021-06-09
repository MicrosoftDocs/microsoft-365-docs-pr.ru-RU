---
title: Планировка Microsoft 365 faQ
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Планировка Microsoft 365 faQ
ms.openlocfilehash: d4cedf420dd605d04328b7f1edeabbd4e1bb5ac7
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809171"
---
# <a name="scheduler-for-microsoft-365-faqs"></a><span data-ttu-id="176c0-103">Планировка Microsoft 365 faQ</span><span class="sxs-lookup"><span data-stu-id="176c0-103">Scheduler for Microsoft 365 FAQs</span></span>

<span data-ttu-id="176c0-104">**Вопрос:** Как scheduler интегрируется с другими функциями Кортаны, такими как *Кортана* для Windows, ежедневная электронная почта для брифингов *и* Play My *Emails?*</span><span class="sxs-lookup"><span data-stu-id="176c0-104">**Question:** How does Scheduler integrate with other Cortana features, such as *Cortana for Windows*, *Daily Briefing Email*, and *Play My Emails*?</span></span></br>
<span data-ttu-id="176c0-105">Scheduler — это независимая служба от других функций Кортаны.</span><span class="sxs-lookup"><span data-stu-id="176c0-105">Scheduler is an independent service from other Cortana features.</span></span> <span data-ttu-id="176c0-106">Другие функции Кортаны можно отключить на уровне клиента, а scheduler можно включить с помощью cortana@yourdomain.com электронной почты.</span><span class="sxs-lookup"><span data-stu-id="176c0-106">Other Cortana features can be disabled at the tenant level, and Scheduler can still be enabled by using the cortana@yourdomain.com email address.</span></span> <span data-ttu-id="176c0-107">В настоящее время пользователи могут взаимодействовать с Scheduler только по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="176c0-107">Currently, users can only interact with Scheduler via email.</span></span>

<span data-ttu-id="176c0-108">**Вопрос:** Это работает только с Outlook?</span><span class="sxs-lookup"><span data-stu-id="176c0-108">**Question:** Does this work only with Outlook?</span></span> <span data-ttu-id="176c0-109">Поддерживаются ли другие продукты электронной почты?</span><span class="sxs-lookup"><span data-stu-id="176c0-109">Are other email products supported?</span></span></br>
<span data-ttu-id="176c0-110">До тех пор, пока у вас есть лицензия, помимо трех вышеуказанных требований, пользователи могут отправлять сообщения cortana@yourdomain.com с любого клиента электронной почты на любом устройстве.</span><span class="sxs-lookup"><span data-stu-id="176c0-110">As long as you have a license, other than the three requirements above, users can email cortana@yourdomain.com from any email client on any device.</span></span>

<span data-ttu-id="176c0-111">**Вопрос:** Могут ли контакты быть в личном списке контактов на Outlook и GAL или в другом эквиваленте компании?</span><span class="sxs-lookup"><span data-stu-id="176c0-111">**Question:** Can contacts be in a personal contact list on Outlook and GAL or other company equivalent?</span></span></br>
<span data-ttu-id="176c0-112">Участниками собрания могут быть все, у кого есть адрес электронной почты в компании или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="176c0-112">Meeting attendees can be anyone with an email address inside or outside the company.</span></span> <span data-ttu-id="176c0-113">К сожалению, scheduler не может автоматически переводить имена на адреса электронной почты или псевдонимы, глядя его в GAL сегодня.</span><span class="sxs-lookup"><span data-stu-id="176c0-113">Unfortunately, Scheduler cannot automatically translate names to email addresses / alias by looking it up in the GAL today.</span></span>

<span data-ttu-id="176c0-114">**Вопрос:** Можно ли использовать scheduler с установленной версией (локальной) Outlook?</span><span class="sxs-lookup"><span data-stu-id="176c0-114">**Question:** Can I use Scheduler with my installed version (on-premises) version of Outlook?</span></span></br>
<span data-ttu-id="176c0-115">Планировщик требует Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="176c0-115">Scheduler requires Exchange Online.</span></span> <span data-ttu-id="176c0-116">Не работает с Exchange Server (on-prem).</span><span class="sxs-lookup"><span data-stu-id="176c0-116">Does not work with Exchange Server (On-prem).</span></span> <span data-ttu-id="176c0-117">Работает с любым клиентом электронной почты, Outlook desktop, OWA, iOS, android, gmail и т. д.</span><span class="sxs-lookup"><span data-stu-id="176c0-117">Works with any email client, Outlook Desktop, OWA, iOS, android, gmail, and so on.</span></span>

<span data-ttu-id="176c0-118">**Вопрос:** Нужно Outlook в фоновом режиме?</span><span class="sxs-lookup"><span data-stu-id="176c0-118">**Question:** Does Outlook have to be open in the background?</span></span></br>
<span data-ttu-id="176c0-119">Outlook не нужно открывать в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="176c0-119">Outlook doesn't need to be open in the background.</span></span> <span data-ttu-id="176c0-120">Все, что вам нужно сделать, это отправить Кортану почту и полагаться на нее, чтобы сделать основную часть работы.</span><span class="sxs-lookup"><span data-stu-id="176c0-120">All you need to do is send Cortana a mail and rely on it to do the bulk of the work.</span></span>

## <a name="frequently-asked-trust-and-privacy-questions"></a><span data-ttu-id="176c0-121">Часто задамые вопросы о доверии и конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="176c0-121">Frequently Asked Trust and Privacy Questions</span></span>

<span data-ttu-id="176c0-122">**Вопрос:** Как работает scheduler?</span><span class="sxs-lookup"><span data-stu-id="176c0-122">**Question:** How does Scheduler work?</span></span></br>
<span data-ttu-id="176c0-123">Планировщик использует Scheduling Intelligence (AI), дополненный помощниками человека.</span><span class="sxs-lookup"><span data-stu-id="176c0-123">Scheduler uses Scheduling Intelligence (AI) augmented with human assistants.</span></span> <span data-ttu-id="176c0-124">Если модели AI создают потребность в поддержке на естественном языке общения с Кортаной, запрос на собрание перерастает в человека для проверки и завершения.</span><span class="sxs-lookup"><span data-stu-id="176c0-124">If AI models generate a need for support in the natural language of communication with Cortana, the meeting request escalates to a human for review and completion.</span></span>

<span data-ttu-id="176c0-125">**Вопрос:** Кто являются ли люди, которые проверяют возрастание запросов?</span><span class="sxs-lookup"><span data-stu-id="176c0-125">**Question:** Who are the humans that review escalated requests?</span></span> </br>
<span data-ttu-id="176c0-126">Помощники планировщика — это службы безопасности поставщиков Майкрософт и гарантии конфиденциальности (SSPA), сертифицированные для получения личной и конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="176c0-126">Scheduler assistants are Microsoft Supplier Security and Privacy Assurance (SSPA) certified for personal and highly confidential information.</span></span> 

<span data-ttu-id="176c0-127">**Вопрос:** Что могут просматривать помощники SSPA?</span><span class="sxs-lookup"><span data-stu-id="176c0-127">**Question:** What can SSPA Assistants view?</span></span></br>
<span data-ttu-id="176c0-128">Планировщик и помощники SSPA могут просматривать сообщения электронной почты, адресованные Кортане.</span><span class="sxs-lookup"><span data-stu-id="176c0-128">Scheduler and the SSPA Assistants can view  the emails that are addressed to Cortana.</span></span> <span data-ttu-id="176c0-129">В потоковом обмене электронной почтой обрабатываются только электронные сообщения, в том числе адрес электронной почты Кортаны, а не предыдущие сообщения электронной почты в потоке до того, как кортана была добавлена.</span><span class="sxs-lookup"><span data-stu-id="176c0-129">In a threaded email exchange, only the emails that include Cortana’s email address will be processed, not the previous emails in the thread before Cortana was added.</span></span>   

<span data-ttu-id="176c0-130">**Вопрос:** Сохраняются ли данные клиентов в области данных планировщика Flow?</span><span class="sxs-lookup"><span data-stu-id="176c0-130">**Question:** Is customer data retained in the Scheduler’s Data Flow?</span></span> </br>
<span data-ttu-id="176c0-131">Планировщик сохраняет все содержимое клиента в границах клиента и сохраняет данные в соответствии с рекомендациями GDPR, Microsoft 365 trust & конфиденциальности и политиками электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="176c0-131">Scheduler stores all customer content within the tenant boundaries and retains data in accordance with GDPR guidelines, Microsoft 365 Trust & Privacy policies, and tenant email policies.</span></span>

<span data-ttu-id="176c0-132">**Вопрос:** Как scheduler обрабатывает свободные и загруженные данные внутренних участников?</span><span class="sxs-lookup"><span data-stu-id="176c0-132">**Question:** How does Scheduler process the free/busy data of internal attendees?</span></span> </br>
<span data-ttu-id="176c0-133">Автоматизация планировщика использует *службу findMeetingTimes* для определения времени, которое взаимодоступно для участников и организатора.</span><span class="sxs-lookup"><span data-stu-id="176c0-133">Scheduler’s automation uses the *findMeetingTimes* service to identify times that are mutually available for attendees and the organizer.</span></span> <span data-ttu-id="176c0-134">Эта служба позволяет использовать другие Outlook, такие как *Suggested Times* в Outlook собраний.</span><span class="sxs-lookup"><span data-stu-id="176c0-134">This service powers other Outlook experiences such as *Suggested Times* in the Outlook meeting form.</span></span> <span data-ttu-id="176c0-135">Сведения о бесплатных и занятых участниках не потребляются явно в качестве бесплатных/занятых блоков.</span><span class="sxs-lookup"><span data-stu-id="176c0-135">Free/busy attendee information is not consumed explicitly as free/busy blocks.</span></span> 

<span data-ttu-id="176c0-136">**Вопрос:** Соответствует ли планировщик GDPR?</span><span class="sxs-lookup"><span data-stu-id="176c0-136">**Question:** Is Scheduler GDPR Compliant?</span></span> </br>
<span data-ttu-id="176c0-137">Да.</span><span class="sxs-lookup"><span data-stu-id="176c0-137">Yes.</span></span>

<span data-ttu-id="176c0-138">**Вопрос:** Кто имеет доступ к почтовому ящику Кортаны?</span><span class="sxs-lookup"><span data-stu-id="176c0-138">**Question:** Who has access to the Cortana mailbox?</span></span> </br>
<span data-ttu-id="176c0-139">Планировщик обрабатывает запросы на собрания и связанные сообщения электронной почты, которые отправляются в почтовый ящик Кортаны клиента.</span><span class="sxs-lookup"><span data-stu-id="176c0-139">Scheduler processes meeting requests and associated emails that are sent to your tenant’s Cortana mailbox.</span></span> <span data-ttu-id="176c0-140">Корпорация Майкрософт не имеет другого доступа к почтовому ящику Кортаны, за исключением утверждения Lockbox по запросу администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="176c0-140">Microsoft does not have any other access to the Cortana mailbox except through Lockbox approval at the request of the tenant admin.</span></span>  

<span data-ttu-id="176c0-141">**Вопрос:** Используются ли данные клиентов для подготовки моделей ИИ?</span><span class="sxs-lookup"><span data-stu-id="176c0-141">**Question:** Is customer data used for training AI models?</span></span></br>
<span data-ttu-id="176c0-142">Содержимое клиента из Scheduler для Microsoft 365 не может использоваться для наборов подготовки данных.</span><span class="sxs-lookup"><span data-stu-id="176c0-142">No customer content from Scheduler for Microsoft 365 can be used for data training sets.</span></span> <span data-ttu-id="176c0-143">Все содержимое клиента находится в клиенте клиента.</span><span class="sxs-lookup"><span data-stu-id="176c0-143">All customer content resides in the customer tenant.</span></span>  

<span data-ttu-id="176c0-144">**Вопрос:** Будет ли scheduler обрабатывать зашифрованную почту?</span><span class="sxs-lookup"><span data-stu-id="176c0-144">**Question:** Will Scheduler process encrypted mail?</span></span></br>
<span data-ttu-id="176c0-145">Нет, зашифрованная почта будет отклонена рабочий процесс Scheduler.</span><span class="sxs-lookup"><span data-stu-id="176c0-145">No, encrypted mail will be rejected by the Scheduler workflow.</span></span> 




