---
title: Обзор приложений LTI
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman, sovaish
ms.date: 06/15/2021
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- M365-modern-desktop
localization_priority: None
description: Узнайте о приложениях Обучение Tools Interoperability (LTI) Office m365, а также о том, как они помогут преподавателям при интеграции Office приложений в свою систему управления Обучение (LMS).
ms.openlocfilehash: 4fd7b25b6463eec4f681e3090bb65db8b00351a8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256686"
---
# <a name="integrating-microsoft-products-with-your-learning-management-system-lms"></a><span data-ttu-id="b5333-103">Интеграция продуктов Майкрософт с Обучение системой управления (LMS)</span><span class="sxs-lookup"><span data-stu-id="b5333-103">Integrating Microsoft products with your Learning Management System (LMS)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5333-104">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="b5333-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b5333-105">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="b5333-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

- [<span data-ttu-id="b5333-106">OneDrive LTI с Canvas</span><span class="sxs-lookup"><span data-stu-id="b5333-106">OneDrive LTI with Canvas</span></span>](#onedrive-lti-with-canvas)
- [<span data-ttu-id="b5333-107">Teams Встречи LTI с Canvas</span><span class="sxs-lookup"><span data-stu-id="b5333-107">Teams Meetings LTI with Canvas</span></span>](#teams-meetings-lti-with-canvas)
- [<span data-ttu-id="b5333-108">Teams Классы LTI</span><span class="sxs-lookup"><span data-stu-id="b5333-108">Teams Classes LTI</span></span>](#teams-classes-lti)

<span data-ttu-id="b5333-109">Microsoft Education и наши сторонние партнеры понимают, что поток обучения и обучения неизменно пересекает границы решений.</span><span class="sxs-lookup"><span data-stu-id="b5333-109">Microsoft Education and our third-party partners understand that the flow of teaching and learning invariably crosses solution boundaries.</span></span> <span data-ttu-id="b5333-110">Мы работаем над предоставлением более бесшовных опытом, чтобы преподаватели и обучающиеся были сосредоточены на своих целях, а не на том, чтобы использовать инструменты.</span><span class="sxs-lookup"><span data-stu-id="b5333-110">We're working on providing more seamless experiences, keeping educators and learners focused on their goals, rather than having to juggle tools.</span></span> <span data-ttu-id="b5333-111">Мы интегрировали продукты Майкрософт везде, где происходит обучение и обучение, в том числе в рамках Обучение систем управления (LMS).</span><span class="sxs-lookup"><span data-stu-id="b5333-111">We're integrating Microsoft products wherever teaching and learning occurs, including within and alongside Learning Management Systems (LMS).</span></span> <span data-ttu-id="b5333-112">Мы работали с нашими партнерами по LMS, чтобы создать набор инструментов с использованием стандарта Обучение Средства [интероперабельности (LTI),](https://www.imsglobal.org/activity/learning-tools-interoperability) который приносит лучшее из Microsoft непосредственно в ваш LMS.</span><span class="sxs-lookup"><span data-stu-id="b5333-112">We've worked with our LMS partners to create a suite of tools using the [Learning Tools Interoperability (LTI) standard](https://www.imsglobal.org/activity/learning-tools-interoperability) that brings the best of Microsoft directly into your LMS.</span></span>

<span data-ttu-id="b5333-113">Эти средства включают новое OneDrive LTI, новое приложение Teams meetings LTI и новое приложение класса Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="b5333-113">These tools include a new OneDrive LTI app, a new Teams Meetings LTI app, and a new Class Teams LTI app.</span></span> <span data-ttu-id="b5333-114">Эти новые средства очень безопасны и полностью совместимы со стандартами LTI 1.3 и LTI Advantage.</span><span class="sxs-lookup"><span data-stu-id="b5333-114">These new tools are highly secure and fully compatible with LTI 1.3 and LTI Advantage standards.</span></span> <span data-ttu-id="b5333-115">Приложение OneDrive LTI позволяет преподавателям и учащимся непосредственно OneDrive облачное хранилище и Office 365 файлы в рабочие процессы назначения и создания контента в пределах LMS.</span><span class="sxs-lookup"><span data-stu-id="b5333-115">The OneDrive LTI app allows educators and students to bring OneDrive cloud storage and Office 365 files directly into assignment and content creation workflows within an LMS.</span></span> <span data-ttu-id="b5333-116">Приложение Teams Meetings LTI позволяет преподавателям и учащимся управлять, планировать и получать доступ к Teams собраниям из центра собраний в их LMS.</span><span class="sxs-lookup"><span data-stu-id="b5333-116">The Teams Meetings LTI app allows educators and students to manage, schedule, and access their Teams Meetings from within a meetings hub in their LMS.</span></span> <span data-ttu-id="b5333-117">Приложение класса Teams LTI позволяет преподавателям создавать команду для своего курса в пределах их LMS с помощью реестра курсов LMS с ежедневными обновлениями реестра.</span><span class="sxs-lookup"><span data-stu-id="b5333-117">The Class Teams LTI app allows educators to create a team for their course within their LMS using the LMS course roster with daily roster updates.</span></span> <span data-ttu-id="b5333-118">Затем учащиеся могут получить доступ к группе прямо из LMS.</span><span class="sxs-lookup"><span data-stu-id="b5333-118">Students can then access the team right from within the LMS.</span></span> <span data-ttu-id="b5333-119">Мы рады довести эти новые средства до клиентов и продолжать улучшать наши решения в соответствии с вашими отзывами.</span><span class="sxs-lookup"><span data-stu-id="b5333-119">We are excited to bring these new tools to customers and continue to improve our solutions according to your feedback.</span></span>

## <a name="onedrive-lti-with-canvas"></a><span data-ttu-id="b5333-120">OneDrive LTI с Canvas</span><span class="sxs-lookup"><span data-stu-id="b5333-120">OneDrive LTI with Canvas</span></span>

<span data-ttu-id="b5333-121">Узнайте больше об использовании Microsoft OneDrive с Обучение системой управления (LMS).</span><span class="sxs-lookup"><span data-stu-id="b5333-121">Learn more about using Microsoft OneDrive with your Learning Management System (LMS).</span></span>

- <span data-ttu-id="b5333-122">**Приносит Microsoft Office 365 непосредственно в ваши процессы**</span><span class="sxs-lookup"><span data-stu-id="b5333-122">**Brings Microsoft Office 365 directly into your workflows**</span></span>

<span data-ttu-id="b5333-123">Приложение Microsoft OneDrive LTI интегрируется с вашим LMS, чтобы Microsoft OneDrive и Microsoft Office 365 непосредственно в наиболее важные процессы, которые включают:</span><span class="sxs-lookup"><span data-stu-id="b5333-123">The Microsoft OneDrive LTI app integrates with your LMS to bring Microsoft OneDrive and Microsoft Office 365 directly into your most important workflows that include:</span></span>

- <span data-ttu-id="b5333-124">Присоединение ресурсов и организация контента.</span><span class="sxs-lookup"><span data-stu-id="b5333-124">Attaching resources and organizing content.</span></span>
- <span data-ttu-id="b5333-125">Начало совместной работы документов.</span><span class="sxs-lookup"><span data-stu-id="b5333-125">Starting collaborative documents.</span></span>
- <span data-ttu-id="b5333-126">Создание и классификация назначений.</span><span class="sxs-lookup"><span data-stu-id="b5333-126">Creating and grading assignments.</span></span>

- <span data-ttu-id="b5333-127">**Безопасность и полное соответствие последним стандартам LTI**</span><span class="sxs-lookup"><span data-stu-id="b5333-127">**Secure and fully compliant with latest LTI standards**</span></span>

<span data-ttu-id="b5333-128">Приложение Microsoft OneDrive LTI совместимо с LTI 1.3 и LTI Advantage.</span><span class="sxs-lookup"><span data-stu-id="b5333-128">The Microsoft OneDrive LTI App is compatible with LTI 1.3 and LTI Advantage.</span></span> <span data-ttu-id="b5333-129">Это преимущество позволяет обеспечить высокую безопасность и тесное интегрирование пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b5333-129">This advantage allows for a highly secure and tightly integrated user experience.</span></span>

- <span data-ttu-id="b5333-130">**Современный и богатый пользовательский опыт**</span><span class="sxs-lookup"><span data-stu-id="b5333-130">**Modern and Rich User Experience**</span></span>

<span data-ttu-id="b5333-131">Приложение Microsoft OneDrive LTI вносит лучшее из Microsoft прямо в ваш LMS-опыт.</span><span class="sxs-lookup"><span data-stu-id="b5333-131">The Microsoft OneDrive LTI App brings the best of Microsoft right into your LMS experience.</span></span> <span data-ttu-id="b5333-132">Мы улучшаем существующую интеграцию Office 365 в LMS путем предоставления более современного пользовательского интерфейса, в комплекте с новым и расширенным выборщиком Microsoft OneDrive файлов и более богатыми опытом редактирования для Office файлов.</span><span class="sxs-lookup"><span data-stu-id="b5333-132">We're improving upon the existing Office 365 integration in your LMS by delivering a more modern user experience, complete with a new and expanded Microsoft OneDrive file picker and richer editing experiences for Office files.</span></span> <span data-ttu-id="b5333-133">Корпорация Майкрософт также полностью Microsoft OneDrive LTI App, что означает, что вы всегда будете получать последнюю и самую последнюю версию от Microsoft автоматически.</span><span class="sxs-lookup"><span data-stu-id="b5333-133">Microsoft will also fully own the Microsoft OneDrive LTI App going forward, which means you’ll always get the latest and greatest from Microsoft automatically.</span></span>

<span data-ttu-id="b5333-134">Приложение Microsoft OneDrive LTI позволяет:</span><span class="sxs-lookup"><span data-stu-id="b5333-134">The Microsoft OneDrive LTI App allows you to:</span></span>

- <span data-ttu-id="b5333-135">Прикрепить Office 365, включая документы Word, PowerPoint презентации и Excel из редактора богатого контента.</span><span class="sxs-lookup"><span data-stu-id="b5333-135">Attach Office 365 files including Word documents, PowerPoint presentations, and Excel from the Rich Content Editor.</span></span>
- <span data-ttu-id="b5333-136">Распространение Office 365 облачных назначений.</span><span class="sxs-lookup"><span data-stu-id="b5333-136">Distribute Office 365 cloud assignments.</span></span>
- <span data-ttu-id="b5333-137">Просмотр и организация личных и Microsoft OneDrive файлов.</span><span class="sxs-lookup"><span data-stu-id="b5333-137">View and organize your personal and course Microsoft OneDrive files.</span></span>
- <span data-ttu-id="b5333-138">Создание совместной работы, в которой участники курсов могут работать вместе над общими документами в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="b5333-138">Create collaborations where course members can work together on shared documents in real time.</span></span>
- <span data-ttu-id="b5333-139">Доступ к нескольким Microsoft OneDrive учетным записям, включая личные и школьные.</span><span class="sxs-lookup"><span data-stu-id="b5333-139">Access multiple Microsoft OneDrive accounts, including personal and school accounts.</span></span>
- <span data-ttu-id="b5333-140">Интеграция Office 365 файлов с модулями курса.</span><span class="sxs-lookup"><span data-stu-id="b5333-140">Integrate Office 365 files with your course modules.</span></span>
- <span data-ttu-id="b5333-141">Использование учетной записи Майкрософт для единой регистрации с помощью службы LMS.</span><span class="sxs-lookup"><span data-stu-id="b5333-141">Use your Microsoft account for single sign-on with your LMS.</span></span>

<span data-ttu-id="b5333-142">Для действий по настройке см. [в Microsoft OneDrive LTI с Canvas.](use-onedrive-with-lms.md)</span><span class="sxs-lookup"><span data-stu-id="b5333-142">For configuration steps, see [Use Microsoft OneDrive LTI with Canvas](use-onedrive-with-lms.md).</span></span>

## <a name="teams-lti-apps"></a><span data-ttu-id="b5333-143">Teams Приложения LTI</span><span class="sxs-lookup"><span data-stu-id="b5333-143">Teams LTI apps</span></span>

### <a name="teams-meetings-lti-with-canvas"></a><span data-ttu-id="b5333-144">Teams Встречи LTI с Canvas</span><span class="sxs-lookup"><span data-stu-id="b5333-144">Teams Meetings LTI with Canvas</span></span>

<span data-ttu-id="b5333-145">Microsoft Teams для собраний приложение LTI помогает администраторам включать Teams собрания в курс LMS учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="b5333-145">Microsoft Teams meetings LTI app helps admins incorporate Teams meetings into their educational institution's LMS course.</span></span> <span data-ttu-id="b5333-146">Преподаватели и студенты могут просматривать прошлые и предстоящие собрания, планировать отдельные или повторяющиеся собрания, а также присоединяться к собраниям команд, связанным с курсом, все из их LMS.</span><span class="sxs-lookup"><span data-stu-id="b5333-146">Educators and students can view past and upcoming meetings, schedule individual or recurring meetings, and join team meetings related to the course, all from within their LMS.</span></span>

<span data-ttu-id="b5333-147">Для действий по настройке см. [в Microsoft Teams собраниях с Canvas.](teams-meetings-with-canvas.md)</span><span class="sxs-lookup"><span data-stu-id="b5333-147">For configuration steps, see [Use Microsoft Teams meetings with Canvas](teams-meetings-with-canvas.md).</span></span>

### <a name="teams-classes-lti"></a><span data-ttu-id="b5333-148">Teams Классы LTI</span><span class="sxs-lookup"><span data-stu-id="b5333-148">Teams Classes LTI</span></span>

<span data-ttu-id="b5333-149">Приложение Microsoft Teams классов LTI помогает преподавателям и учащимся перемещаться между их LMS и Teams.</span><span class="sxs-lookup"><span data-stu-id="b5333-149">The Microsoft Teams classes LTI app helps educators and students navigate between their LMS and Teams.</span></span> <span data-ttu-id="b5333-150">Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.</span><span class="sxs-lookup"><span data-stu-id="b5333-150">Users can access their class teams associated with their course directly from within their LMS.</span></span> <span data-ttu-id="b5333-151">Ниже приведены действия по настройке:</span><span class="sxs-lookup"><span data-stu-id="b5333-151">You can find configuration steps below:</span></span>

- <span data-ttu-id="b5333-152">**Teams классов LTI** с canvas [Use Microsoft Teams с Canvas](teams-classes-with-canvas.md).</span><span class="sxs-lookup"><span data-stu-id="b5333-152">**Teams Classes LTI with Canvas** [Use Microsoft Teams classes with Canvas](teams-classes-with-canvas.md).</span></span>
