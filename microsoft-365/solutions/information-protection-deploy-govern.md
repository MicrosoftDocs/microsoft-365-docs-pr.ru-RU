---
title: Управление сведениями, которые подчиняются нормам конфиденциальности данных
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
- M365solutions
ms.custom: ''
description: Используйте метки и политики хранения Microsoft 365 для управления личными данными в среде Microsoft 365.
ms.openlocfilehash: 4c65eafa167d7224c4022d5634ce089952fada19
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695165"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="e309e-103">Управление сведениями, которые подчиняются нормам конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="e309e-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="e309e-104">Управление сведениями в среде можно использовать для обеспечения соответствия требованиям к конфиденциальности данных, включая номер, который относится к общему нормативу по защите данных (GDPR), HIPAA-HITECH (ACT на конфиденциальность в США), ACT-(ККПА) и ACT защиты данных в Бразилии (ЛГПД).</span><span class="sxs-lookup"><span data-stu-id="e309e-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="e309e-105">Эти элементы управления в основном делятся на следующие области решений:</span><span class="sxs-lookup"><span data-stu-id="e309e-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="e309e-106">Политики хранения</span><span class="sxs-lookup"><span data-stu-id="e309e-106">Retention policies</span></span>
- <span data-ttu-id="e309e-107">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="e309e-107">Retention labels</span></span>
- <span data-ttu-id="e309e-108">Управление записями</span><span class="sxs-lookup"><span data-stu-id="e309e-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="e309e-109">Правила конфиденциальности данных влияют на управление информацией</span><span class="sxs-lookup"><span data-stu-id="e309e-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="e309e-110">Ниже приведен пример списка нормативных актов о конфиденциальности данных, которые могут относиться к элементам управления для управления сведениями:</span><span class="sxs-lookup"><span data-stu-id="e309e-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="e309e-111">Статья GDPR (13) (2) (a)</span><span class="sxs-lookup"><span data-stu-id="e309e-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="e309e-112">Статья GDPR (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="e309e-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="e309e-113">HIPAA-HITECH (45 CFR 164.312 (c) (2))</span><span class="sxs-lookup"><span data-stu-id="e309e-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="e309e-114">HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))</span><span class="sxs-lookup"><span data-stu-id="e309e-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="e309e-115">HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))</span><span class="sxs-lookup"><span data-stu-id="e309e-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="e309e-116">ЛГПД статья 46</span><span class="sxs-lookup"><span data-stu-id="e309e-116">LGPD Article 46</span></span>

<span data-ttu-id="e309e-117">Для получения дополнительных сведений об этих нормативных требованиях ознакомьтесь со [статьей Оценка конфиденциальности данных и определение конфиденциальной информации](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="e309e-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="e309e-118">Для управления сведениями нормативные требования обычно вызывают следующее:</span><span class="sxs-lookup"><span data-stu-id="e309e-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="e309e-119">Для хранения и удаления персональных данных, хранящихся в Microsoft 365, необходимо использовать техническую схему.</span><span class="sxs-lookup"><span data-stu-id="e309e-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="e309e-120">Если вы собираетесь хранить персональные данные, сообщите о том, как долго будут храниться данные, что является стандартной практикой на интерфейсных веб-системах.</span><span class="sxs-lookup"><span data-stu-id="e309e-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="e309e-121">Персональные данные должны быть защищены от случайной обработки, потери или изменения с помощью методов, которые можно проверить.</span><span class="sxs-lookup"><span data-stu-id="e309e-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="e309e-122">Все действия, выполняемые с личными данными, необходимо задокументировать, и эта документация должна храниться в течение указанного периода.</span><span class="sxs-lookup"><span data-stu-id="e309e-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="e309e-123">Так как правила конфиденциальности данных не очень специфичны, если речь идет о хранении и удалении данных, необходимо учитывать другие факторы, которые могут зависеть от сведений о персональных данных, хранящихся в вашей подписке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e309e-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="e309e-124">Вот несколько примеров:</span><span class="sxs-lookup"><span data-stu-id="e309e-124">Here are a few examples:</span></span>

- <span data-ttu-id="e309e-125">Устаревание учетных записей потребителей через 5 лет неактивности и требует удаления или анонимной обработки данных учетной записи после этого момента, требуя согласования между системой хранения данных и рабочих процессов, связанных с уведомлениями и другими средствами автоматизации.</span><span class="sxs-lookup"><span data-stu-id="e309e-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="e309e-126">Настройка правил для хранения политик и процедур, относящихся к GDPR, в течение трех лет после их замены, что соответствует графику хранения в Организации для политик и процедур.</span><span class="sxs-lookup"><span data-stu-id="e309e-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="e309e-127">Обслуживание отдельной подписки для связи с потребителями через свою организацию поддержки.</span><span class="sxs-lookup"><span data-stu-id="e309e-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="e309e-128">Все почтовые сообщения были сохранены и удалены через две недели, чтобы уменьшить задолженность количества в системе.</span><span class="sxs-lookup"><span data-stu-id="e309e-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="e309e-129">Ключевой вопрос для ответа:</span><span class="sxs-lookup"><span data-stu-id="e309e-129">A key question to answer is:</span></span> 

- <span data-ttu-id="e309e-130">Как долго информация, содержащая персональные данные, должна содержаться в допустимых бизнес-целях, чтобы избежать этого?</span><span class="sxs-lookup"><span data-stu-id="e309e-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="e309e-131">Это должно быть сбалансировано с потребностями хранения для непрерывности бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e309e-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="e309e-132">Независимо от юридических и деловых причин для хранения персональных данных или их удаления Корпорация Майкрософт предоставляет ряд возможностей по внедрению схемы управления данными в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e309e-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="e309e-133">Управление сведениями в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e309e-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="e309e-134">Для начала ознакомьтесь со статьей [Управление сведениями](../compliance/manage-information-governance.md) и [хранение данных, удаление и уничтожение в Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="e309e-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="e309e-135">Разработка расписаний хранения данных для контейнеров, электронной почты и контента</span><span class="sxs-lookup"><span data-stu-id="e309e-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="e309e-136">Учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e309e-136">Keep the following in mind:</span></span>

- <span data-ttu-id="e309e-137">Создание расписания хранения данных для определенных типов информации следует считать необходимым условием для реализации схемы хранения или удаления.</span><span class="sxs-lookup"><span data-stu-id="e309e-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="e309e-138">С учетом количества типов информации, которые большинство организаций считают важными и соответствующие расписания хранения больших записей, которые вместе с ними помещаются, для реализации стратегии хранения данных и управления записями требуется планирование.</span><span class="sxs-lookup"><span data-stu-id="e309e-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="e309e-139">Ключевое значение для создания эффективной стратегии управления данными этого типа состоит в том, чтобы сосредоточиться на самых важных бизнес-функциях и типах данных, для которых требуется более формальное управление.</span><span class="sxs-lookup"><span data-stu-id="e309e-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="e309e-140">Примеры — это юридические контракты, финансовые отчеты и документация по соответствию нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="e309e-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="e309e-141">Старайтесь не иметь отдельного расписания хранения для каждого типа данных Single.</span><span class="sxs-lookup"><span data-stu-id="e309e-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="e309e-142">Старайтесь по мере возможности использовать общие категории, например с расписаниями хранения 7 лет для общего бизнес-контента.</span><span class="sxs-lookup"><span data-stu-id="e309e-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="e309e-143">После того, как типы персональных данных в вашей среде больше известны, создайте расписания хранения и удаления контента этого типа и настройте архитектуру информации, чтобы упростить управление этим сведениями.</span><span class="sxs-lookup"><span data-stu-id="e309e-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="e309e-144">Например, изолируйте персональные данные на разных сайтах, библиотеках или папках с контролируемым доступом.</span><span class="sxs-lookup"><span data-stu-id="e309e-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="e309e-145">Политики хранения</span><span class="sxs-lookup"><span data-stu-id="e309e-145">Retention policies</span></span>

<span data-ttu-id="e309e-146">Создание и развертывание [политик хранения](../compliance/retention-policies.md) для контента на сайтах, которые автоматически применяются.</span><span class="sxs-lookup"><span data-stu-id="e309e-146">Create and deploy [retention policies](../compliance/retention-policies.md) for content in sites that are automatically applied.</span></span>

<span data-ttu-id="e309e-147">Для обеспечения конфиденциальности данных для сайтов, содержащих персональные данные, укажите правила хранения или удаления для адресов организационных стандартов.</span><span class="sxs-lookup"><span data-stu-id="e309e-147">For data privacy for sites that contain or are expected to contain personal data, specify retention or deletion rules to address organizational standards.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="e309e-148">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="e309e-148">Retention labels</span></span>

<span data-ttu-id="e309e-149">Создание и развертывание [меток хранения](../compliance/labels.md) для контента и электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e309e-149">Create and deploy [retention labels](../compliance/labels.md) for content and email.</span></span>

<span data-ttu-id="e309e-150">Для обеспечения конфиденциальности данных для сайтов, библиотек, папок и сообщений электронной почты, содержащих персональные данные, укажите правила автоматического хранения или удаления для адресов организационных стандартов.</span><span class="sxs-lookup"><span data-stu-id="e309e-150">For data privacy for sites, libraries, folders, and email that contain or are expected to contain personal data, specify auto retention or deletion rules to address organizational standards.</span></span>

### <a name="records-management"></a><span data-ttu-id="e309e-151">Управление записями</span><span class="sxs-lookup"><span data-stu-id="e309e-151">Records management</span></span>

<span data-ttu-id="e309e-152">Создание и развертывание меток хранения для управления записями на основе расписания хранения записей и плана файлов.</span><span class="sxs-lookup"><span data-stu-id="e309e-152">Create and deploy retention labels for records management based on a records retention schedule and file plan.</span></span>

<span data-ttu-id="e309e-153">Для обеспечения конфиденциальности данных запросы субъектов данных (DSR), полученные юридическим отделом, объявляются записью и хранятся в течение неограниченного срока.</span><span class="sxs-lookup"><span data-stu-id="e309e-153">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and stored indefinitely to adhere to regulatory activity retention specifications.</span></span>

<span data-ttu-id="e309e-154">Дополнительные сведения можно найти в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="e309e-154">See these resources for more information:</span></span> 

- [<span data-ttu-id="e309e-155">Управление записями</span><span class="sxs-lookup"><span data-stu-id="e309e-155">Records Management</span></span>](../compliance/records-management.md)
- [<span data-ttu-id="e309e-156">Диспетчер планов хранения</span><span class="sxs-lookup"><span data-stu-id="e309e-156">File plan manager</span></span>](../compliance/file-plan-manager.md)
- [<span data-ttu-id="e309e-157">Хранение на основе событий для управления записями</span><span class="sxs-lookup"><span data-stu-id="e309e-157">Event-based retention for records management</span></span>](../compliance/automate-event-driven-retention.md)
- [<span data-ttu-id="e309e-158">Расстановка контента</span><span class="sxs-lookup"><span data-stu-id="e309e-158">Disposition of content</span></span>](../compliance/disposition-reviews.md)
