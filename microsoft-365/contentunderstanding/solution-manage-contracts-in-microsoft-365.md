---
title: Управление контрактами с помощью Microsoft 365 решения
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как управлять контрактами с Microsoft 365 решения SharePoint, Microsoft Teams и Power Automate.
ms.openlocfilehash: 057c581559aa2e5cfd6e98b379783a7d73e0bccc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538571"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="e2d1a-103">Управление контрактами с помощью Microsoft 365 решения</span><span class="sxs-lookup"><span data-stu-id="e2d1a-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="e2d1a-104">В этой статье описывается создание решения по управлению контрактами для организации с помощью SharePoint Syntex и компонентов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="e2d1a-105">Она предоставляет вам рамки, которые помогут вам спланировать и создать решение, которое соответствует вашим уникальным бизнес-потребностям.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="e2d1a-106">Даже если это решение не подходит для бизнеса в целом, его части можно использовать при планировании создания настраиваемого решения по управлению контрактами.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-106">Even if this solution doesn't suit your business needs as a whole, parts of it can be adopted in your planning to create a custom contract management solution.</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="e2d1a-107">Определение бизнес-проблемы</span><span class="sxs-lookup"><span data-stu-id="e2d1a-107">Identify the business problem</span></span>

<span data-ttu-id="e2d1a-108">Первым шагом в планировании системы управления контрактами является понимание проблемы, которая вы пытаетесь решить.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-108">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="e2d1a-109">Для этого решения необходимо решить четыре ключевых вопроса:</span><span class="sxs-lookup"><span data-stu-id="e2d1a-109">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="e2d1a-110">**Определение контрактов.**</span><span class="sxs-lookup"><span data-stu-id="e2d1a-110">**Identify contracts**.</span></span> <span data-ttu-id="e2d1a-111">Организация работает со многими документами, такими как счета, контракты, выписки о работе и так далее.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-111">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="e2d1a-112">Некоторые из них являются цифровыми активами, отосланными по электронной почте, а некоторые — бумажными, отосланными по традиционной почте.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-112">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="e2d1a-113">Необходимо определить все контракты клиентов из всех других документов, а затем классифицировать их как таковую.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-113">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="e2d1a-114">**Отслеживание истории утверждений контрактов.**</span><span class="sxs-lookup"><span data-stu-id="e2d1a-114">**Track the history of contract approvals**.</span></span> <span data-ttu-id="e2d1a-115">Вашей организации необходим надежный способ узнать, были ли контракты утверждены или отклонены, и была ли обработана оплата.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-115">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="e2d1a-116">**Сайт для управления утверждениями контрактов**.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-116">**Site to manage contract approvals**.</span></span> <span data-ttu-id="e2d1a-117">Вашей организации необходимо создать совместный сайт, на котором все заинтересованные стороны могут легко просмотреть контракты.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-117">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="e2d1a-118">Заинтересованные стороны должны иметь возможность при необходимости просмотреть весь контракт, но в основном необходимо просмотреть несколько ключевых полей из каждого контракта (например, имя клиента, номер PO и общие затраты).</span><span class="sxs-lookup"><span data-stu-id="e2d1a-118">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="e2d1a-119">Заинтересованные стороны должны иметь возможность легко утверждать или отклонить входящие контракты.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-119">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="e2d1a-120">**Маршрут рассмотренных контрактов**.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-120">**Route reviewed contracts**.</span></span> <span data-ttu-id="e2d1a-121">Утвержденные и отклоненные контракты должны быть маршрутными через определенный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-121">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="e2d1a-122">Утвержденные контракты должны быть маршрутными в стороне приложение для обработки платежей.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-122">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="e2d1a-123">Отклонить контракты необходимо для дополнительного рассмотрения.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-123">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="e2d1a-124">Обзор решения</span><span class="sxs-lookup"><span data-stu-id="e2d1a-124">Overview of the solution</span></span>

  ![Схема решения с использованием SharePoint, SharePoint списков, Teams и Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="e2d1a-126">Это руководство по управлению контрактами включает четыре компонента Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e2d1a-126">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="e2d1a-127">**Microsoft SharePoint Syntex:** Создание моделей для определения и классификации файлов контрактов, а затем извлечения соответствующих данных из них.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-127">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="e2d1a-128">**Списки SharePoint** Microsoft: Используйте форматирование, доступное в современных списках SharePoint, чтобы представить контракты в удобном для бизнеса формате.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-128">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="e2d1a-129">**Microsoft Teams:** Используйте функциональность канала Teams и связанных вкладок, чтобы позволить заинтересованным сторонам просмотреть и управлять контрактами.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-129">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="e2d1a-130">**Power Automate:** Используйте потоки для руководства контрактами в процессе утверждения, а затем для сторонних приложений для оплаты.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-130">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="e2d1a-131">Как все это работает</span><span class="sxs-lookup"><span data-stu-id="e2d1a-131">How it all works</span></span>

  ![Схема решения, показывающая рабочий процесс для отправки документов, извлечения данных, уведомления заинтересованных сторон и утверждения или отказа от контракта.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="e2d1a-133">Документы загружаются в библиотеку SharePoint документов.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-133">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="e2d1a-134">К библиотеке документов применена SharePoint модель понимания документов Syntex.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-134">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="e2d1a-135">Он проверяет каждый файл, чтобы узнать, совпадает ли какой-либо тип контента с "контрактом", который он обучен искать.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-135">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="e2d1a-136">Если он находит совпадение, он классифицирует файл как "контракт" и обновляет тип контента для документа.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-136">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="e2d1a-137">Модель также извлекет конкретные данные из каждого файла контрактов, которые заинтересованные стороны заинтересованы в том, чтобы увидеть, например, *клиент,* *подрядчик* и сумма *платы.*</span><span class="sxs-lookup"><span data-stu-id="e2d1a-137">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="e2d1a-138">Следующая страница — пример контракта, который модель обучена для идентификации.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-138">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![Пример контракта.](../media/content-understanding/contract.png)

3. <span data-ttu-id="e2d1a-140">В Microsoft Teams все заинтересованные стороны являются членами защищенного канала Teams, в котором все контракты в библиотеке документов видны для утверждения или отклонения.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-140">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="e2d1a-141">Используя Teams, все заинтересованные стороны уведомлены о необходимости пересмотра новых контрактов.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-141">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>
 
4. <span data-ttu-id="e2d1a-142">С помощью Power Automate, контракты перемещаются в процессе утверждения в Teams канале.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-142">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="e2d1a-143">Когда участник утверждает контракт, статус контракта меняется для утверждения, все участники уведомлены через Teams, и элемент строки создается, чтобы показать, что контракт готов к выплате.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-143">When a member approves a contract, the contract status is changed to approve, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="e2d1a-144">Этот процесс можно расширить для записи непосредственно в стороне финансовое приложение для оплаты.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-144">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5.  <span data-ttu-id="e2d1a-145">Когда участник отклоняет контракт, статус меняется на отклонение, и все участники уведомлены через Teams сообщение.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-145">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="e2d1a-146">Конечным результатом этого решения является автоматизированный бизнес-процесс для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-146">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="e2d1a-147">Сотрудники могут легко использовать настраиваемый вид плитки в Teams, чтобы инициировать и отслеживать рабочий процесс утверждения документов.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-147">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![Вкладка Контракты.](../media/content-understanding/tile-view.png)

## <a name="create-the-solution"></a><span data-ttu-id="e2d1a-149">Создание решения</span><span class="sxs-lookup"><span data-stu-id="e2d1a-149">Create the solution</span></span>

<span data-ttu-id="e2d1a-150">В следующих разделах будут подробно изуметь, как настроить решение по управлению контрактами.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-150">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="e2d1a-151">Она разделена на три этапа:</span><span class="sxs-lookup"><span data-stu-id="e2d1a-151">It's divided into three steps:</span></span>

- [<span data-ttu-id="e2d1a-152">Шаг 1. Использование SharePoint Syntex для определения файлов контрактов и извлечения данных</span><span class="sxs-lookup"><span data-stu-id="e2d1a-152">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="e2d1a-153">Шаг 2. Используйте Microsoft Teams для создания канала управления контрактами</span><span class="sxs-lookup"><span data-stu-id="e2d1a-153">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="e2d1a-154">Шаг 3. Используйте Power Automate для создания потока для обработки контрактов</span><span class="sxs-lookup"><span data-stu-id="e2d1a-154">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
