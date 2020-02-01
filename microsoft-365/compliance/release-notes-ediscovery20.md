---
title: Заметки о выпуске для расширенного обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: В этой статье содержатся заметки о выпуске для расширенного обнаружения электронных данных.
ms.openlocfilehash: e51647e56e7fb29d8f67d36941a2847278c1e1c0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601646"
---
# <a name="release-notes-for-advanced-ediscovery"></a><span data-ttu-id="47459-103">Заметки о выпуске для расширенного обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="47459-103">Release notes for Advanced eDiscovery</span></span>

<span data-ttu-id="47459-104">Общедоступная программа предварительной версии для расширенного обнаружения электронных данных — это способ получить ранний доступ к будущим функциям и обновлениям.</span><span class="sxs-lookup"><span data-stu-id="47459-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="47459-105">Чтобы получить более ранний доступ к новейшим функциям, просто создайте и используйте расширенное дело eDiscovery в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="47459-105">To get early access to the newest features, just create and use an Advanced eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="47459-106">Ознакомьтесь [со статьей Создание нового дела](create-new-ediscovery-case.md).</span><span class="sxs-lookup"><span data-stu-id="47459-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="47459-107">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="47459-107">Known issues</span></span>

<span data-ttu-id="47459-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="47459-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="47459-109">Данные, соответствующие форме, созданной до 31 января, 2019 будут недоступны для поиска при использовании средства поиска в Advanced eDiscovery для поиска почтовых ящиков хранитель.</span><span class="sxs-lookup"><span data-stu-id="47459-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="47459-110">Формы, созданные после этой даты, будут доступны для поиска.</span><span class="sxs-lookup"><span data-stu-id="47459-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="47459-111">Форма, созданная пользователем, по-прежнему может получать ответы даже после удаления пользователя, создавшего форму.</span><span class="sxs-lookup"><span data-stu-id="47459-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="47459-112">Тем не менее соответствующие данные для этих ответов (которые произошли после удаления почтового ящика хранитель) не будут использоваться для поиска при использовании средства поиска в Advanced eDiscovery для поиска почтовых ящиков хранитель.</span><span class="sxs-lookup"><span data-stu-id="47459-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span>
 
<span data-ttu-id="47459-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="47459-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="47459-114">Если пользователь редактирует Sway перед удалением учетной записи пользователя для владельца Sway, эти изменения могут быть недоступны для поиска при использовании средства поиска в Advanced eDiscovery для поиска почтовых ящиков хранитель.</span><span class="sxs-lookup"><span data-stu-id="47459-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="47459-115">Sway блокирует изменения в Sway сразу же после получения сигнала о том, что учетная запись была удалена.</span><span class="sxs-lookup"><span data-stu-id="47459-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="47459-116">Однако существует небольшая вероятность того, что вы можете редактировать Sway до получения этого сигнала.</span><span class="sxs-lookup"><span data-stu-id="47459-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="47459-117">Проблемы, устраняемые в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="47459-117">Issues fixed in this release</span></span>

- <span data-ttu-id="47459-118">ДКР: обработка исключений для неиндексированных элементов и потерянных элементов</span><span class="sxs-lookup"><span data-stu-id="47459-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="47459-119">ДКР: уведомления об удержаниях</span><span class="sxs-lookup"><span data-stu-id="47459-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="47459-120">ДКР: custodians в eDiscovery</span><span class="sxs-lookup"><span data-stu-id="47459-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="47459-121">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="47459-121">What’s new</span></span>

- <span data-ttu-id="47459-122">**Переработанная Навигация в центре безопасности & соответствия требованиям** — Расширенное обнаружение электронных данных выглядит новым видом и привычным поведением.</span><span class="sxs-lookup"><span data-stu-id="47459-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery has a new look and feel.</span></span> <span data-ttu-id="47459-123">Использование расширенного обнаружения электронных данных для управления рабочими процессами вашего случая.</span><span class="sxs-lookup"><span data-stu-id="47459-123">Use Advanced eDiscovery to manage more of your case workflow.</span></span>

- <span data-ttu-id="47459-124">**Управление делами** — существует дополнительная поддержка новых типов обращений.</span><span class="sxs-lookup"><span data-stu-id="47459-124">**Case management** – There’s additional support for new case types.</span></span> <span data-ttu-id="47459-125">Вы также можете выбрать и сохранить последние и избранные обращения.</span><span class="sxs-lookup"><span data-stu-id="47459-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="47459-126">Отслеживание и отслеживание активности в разных случаях с помощью новых панелей мониторинга.</span><span class="sxs-lookup"><span data-stu-id="47459-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="47459-127">**Хранитель Management** — добавлять и удалять пользователей в качестве данных custodians в случае.</span><span class="sxs-lookup"><span data-stu-id="47459-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="47459-128">**Интеграция Exchange, onedrive и Teams** — автоматическое добавление текущего почтового ящика, учетной записи OneDrive для бизнеса и сайтов Microsoft Teams к обращению.</span><span class="sxs-lookup"><span data-stu-id="47459-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user’s current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="47459-129">**Хранитель Communications** — отправка и Управление уведомлениями о юридических удержаниях от имени Организации.</span><span class="sxs-lookup"><span data-stu-id="47459-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="47459-130">**Портал хранитель** — новый портал для custodians для доступа к интерактивным уведомлениям об удержаниях.</span><span class="sxs-lookup"><span data-stu-id="47459-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="47459-131">**Глубокое индексирование** — повторный обход элементов с частичным индексированием по запросу.</span><span class="sxs-lookup"><span data-stu-id="47459-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="47459-132">**Устранение ошибок** — исправить или скачать ошибки обработки; к ним относятся поддержка обновлений для больших типов файлов, защищенных паролем файлов и многого другого.</span><span class="sxs-lookup"><span data-stu-id="47459-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="47459-133">**Улучшения поиска** — создайте Поиск, определив custodians и/или расположения.</span><span class="sxs-lookup"><span data-stu-id="47459-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="47459-134">**Обзор наборов** — управление, отслеживание и аудит статических наборов документов.</span><span class="sxs-lookup"><span data-stu-id="47459-134">**Review sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="47459-135">**Обзор** — используйте собственное, текстовое и почти собственное представление для просмотра документов, добавленных в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="47459-135">**Review** – Use a native, text, and near-native view to review documents added to your review set.</span></span>

- <span data-ttu-id="47459-136">**Редактирование, теги и заметки** — редактирование текста, применение тегов и создание примечаний при рецензировании документов.</span><span class="sxs-lookup"><span data-stu-id="47459-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="47459-137">**Проверка на основе анализа**— использование расширенной аналитики обнаружения электронных данных для поиска, поиска и отбора результатов в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="47459-137">**Analytics-powered review**– Leverage Advanced eDiscovery analytics to find, search, and cull results within a review set.</span></span>

- <span data-ttu-id="47459-138">**Задания** — отслеживание состояния длительно выполняемых процессов.</span><span class="sxs-lookup"><span data-stu-id="47459-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="47459-139">**Новые действия аудита** — отслеживание и просмотр новых действий аудита для расширенного обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="47459-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>
