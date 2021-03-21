---
title: Управление сведениями, которые регулируются правилами конфиденциальности данных
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Используйте метки и политики хранения Microsoft 365 для управления личными данными в среде Microsoft 365.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928440"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="350f4-103">Управление сведениями, которые регулируются правилами конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="350f4-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="350f4-104">Элементы управления информацией могут быть использованы в вашей среде для решения потребностей в соблюдении конфиденциальности данных, в том числе номера, которые специфичен для общего регулирования защиты данных (GDPR), HIPAA-HITECH (закон о конфиденциальности здравоохранения США), Закона о защите прав потребителей в Калифорнии (CCPA) и Закона о защите данных Бразилии (LGPD).</span><span class="sxs-lookup"><span data-stu-id="350f4-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="350f4-105">Эти элементы управления в основном попадают в следующие области решения:</span><span class="sxs-lookup"><span data-stu-id="350f4-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="350f4-106">Политики хранения</span><span class="sxs-lookup"><span data-stu-id="350f4-106">Retention policies</span></span>
- <span data-ttu-id="350f4-107">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="350f4-107">Retention labels</span></span>
- <span data-ttu-id="350f4-108">Управление записями</span><span class="sxs-lookup"><span data-stu-id="350f4-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="350f4-109">Правила конфиденциальности данных, влияющие на управление информацией</span><span class="sxs-lookup"><span data-stu-id="350f4-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="350f4-110">Вот пример списка правил конфиденциальности данных, которые могут относиться к средствам управления информацией:</span><span class="sxs-lookup"><span data-stu-id="350f4-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="350f4-111">Статья GDPR (13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="350f4-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="350f4-112">Статья GDPR (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="350f4-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="350f4-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="350f4-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="350f4-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="350f4-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="350f4-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(II))</span><span class="sxs-lookup"><span data-stu-id="350f4-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="350f4-116">Статья 46 LGPD</span><span class="sxs-lookup"><span data-stu-id="350f4-116">LGPD Article 46</span></span>

<span data-ttu-id="350f4-117">Дополнительные сведения об этих правилах см. в статье Оценка рисков конфиденциальности данных и [определение конфиденциальной статьи.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="350f4-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="350f4-118">Для управления информацией правила конфиденциальности данных обычно выявят следующие требования:</span><span class="sxs-lookup"><span data-stu-id="350f4-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="350f4-119">Необходимо использовать техническую схему хранения и удаления персональных данных, хранимой в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="350f4-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="350f4-120">Если вы собираетесь хранить персональные данные, сообщите субъекту о том, как долго будут храниться данные, что является стандартной практикой в настоящее время на передней веб-системы.</span><span class="sxs-lookup"><span data-stu-id="350f4-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="350f4-121">Персональные данные должны быть защищены от случайной обработки, потери или изменения с помощью проверяемых методов.</span><span class="sxs-lookup"><span data-stu-id="350f4-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="350f4-122">Любые действия, выполненные в отношении персональных данных, должны быть задокументированы, и эта документация должна храниться в течение указанного периода.</span><span class="sxs-lookup"><span data-stu-id="350f4-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="350f4-123">Поскольку правила конфиденциальности данных не являются очень конкретными для хранения и удаления данных, необходимо учитывать другие факторы, которые могут диктовать рекомендации по управлению информацией для персональных данных, хранимой в подписке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="350f4-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="350f4-124">Вот несколько примеров:</span><span class="sxs-lookup"><span data-stu-id="350f4-124">Here are a few examples:</span></span>

- <span data-ttu-id="350f4-125">Старение учетных записей потребителей после 5 лет бездействия и требует удаления или анонимизации данных учетных записей после этого момента, что требует оркестровки между системой хранения данных и рабочего процесса, связанного с уведомлениями и другой автоматизацией.</span><span class="sxs-lookup"><span data-stu-id="350f4-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="350f4-126">Настройка правил для хранения политик и процедур, связанных с GDPR, в течение трех лет после их изменения, что соответствует расписанию хранения политик и процедур организации.</span><span class="sxs-lookup"><span data-stu-id="350f4-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="350f4-127">Ведение отдельной подписки для общения с потребителями через организацию поддержки.</span><span class="sxs-lookup"><span data-stu-id="350f4-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="350f4-128">Все сообщения электронной почты были сохранены и удалены через две недели, чтобы уменьшить любое наращивание долгов конфиденциальности в системе.</span><span class="sxs-lookup"><span data-stu-id="350f4-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="350f4-129">Ключевой вопрос, на который нужно ответить:</span><span class="sxs-lookup"><span data-stu-id="350f4-129">A key question to answer is:</span></span> 

- <span data-ttu-id="350f4-130">Как долго необходимо хранить информацию, содержащую персональные данные, по веские бизнес-причинам, чтобы избежать практики "хранить ее навсегда"?</span><span class="sxs-lookup"><span data-stu-id="350f4-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="350f4-131">Это необходимо уравновешить с потребностями хранения для непрерывности бизнеса.</span><span class="sxs-lookup"><span data-stu-id="350f4-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="350f4-132">Независимо от юридических и бизнес-причин хранения или удаления персональных данных корпорация Майкрософт предоставляет ряд возможностей для реализации схемы управления данными в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="350f4-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="350f4-133">Управление управлением информацией в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="350f4-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="350f4-134">Для начала см. в руб. [Управление](../compliance/manage-information-governance.md) управлением информацией и хранением данных, удалением и уничтожением [в Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="350f4-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="350f4-135">Разработка расписания хранения данных для контейнеров, электронной почты и контента</span><span class="sxs-lookup"><span data-stu-id="350f4-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="350f4-136">Учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="350f4-136">Keep the following in mind:</span></span>

- <span data-ttu-id="350f4-137">Создание расписания хранения данных для определенных типов информации следует считать обязательным условием для реализации любой схемы хранения или удаления.</span><span class="sxs-lookup"><span data-stu-id="350f4-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="350f4-138">Учитывая количество типов информации, которые большинство организаций считают важными, а также соответствующие большие графики хранения записей, которые идут вместе с ними, реализация стратегии управления хранением данных и записями требует планирования.</span><span class="sxs-lookup"><span data-stu-id="350f4-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="350f4-139">Ключ к созданию эффективной стратегии управления данными этого типа заключается в том, чтобы сосредоточиться на наиболее приоритетных бизнес-функциях и типах информации, которые требуют более формального управления.</span><span class="sxs-lookup"><span data-stu-id="350f4-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="350f4-140">Примерами являются юридические контракты, финансовые отчеты и документация по нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="350f4-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="350f4-141">Старайтесь не иметь отдельного расписания хранения для каждого типа сведений.</span><span class="sxs-lookup"><span data-stu-id="350f4-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="350f4-142">Попробуйте максимально использовать общие категории, например, с графиками хранения 7 лет для общего бизнес-контента.</span><span class="sxs-lookup"><span data-stu-id="350f4-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="350f4-143">После того как типы персональных данных в вашей среде будут лучше известны, создайте графики хранения и удаления этого типа контента и отрегулируете архитектуру информации, чтобы упростить управление данными.</span><span class="sxs-lookup"><span data-stu-id="350f4-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="350f4-144">Например, изолировать личную информацию на отдельных сайтах, библиотеках или папках с контролируемым доступом.</span><span class="sxs-lookup"><span data-stu-id="350f4-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="350f4-145">Политики и метки хранения</span><span class="sxs-lookup"><span data-stu-id="350f4-145">Retention policies and retention labels</span></span>

<span data-ttu-id="350f4-146">Используйте [политики хранения и метки](../compliance/retention.md) хранения для хранения или удаления контента в Microsoft 365, который содержит или, как ожидается, содержит персональные данные.</span><span class="sxs-lookup"><span data-stu-id="350f4-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="350f4-147">Управление записями</span><span class="sxs-lookup"><span data-stu-id="350f4-147">Records management</span></span>

<span data-ttu-id="350f4-148">Используйте метки хранения, которые объявляют контент записью, для реализации [решения](../compliance/records-management.md) по управлению записями для данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="350f4-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="350f4-149">Для конфиденциальности данных запросы субъекта данных (DSRs), полученные юридическим отделом, объявляются записью и могут храниться бесконечно или утилизироваться с доказательствами, чтобы придерживаться спецификаций хранения нормативных действий.</span><span class="sxs-lookup"><span data-stu-id="350f4-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>