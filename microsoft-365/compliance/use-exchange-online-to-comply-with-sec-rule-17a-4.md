---
title: Соблюдение правила 17a-4 SEC с помощью Exchange Online и Центра безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Настройте Exchange Online и Центр соответствия требованиям для соблюдения нормативных требований правила 1.31 (c)–(d) CFTC, правила 4511 FINRA и правила 17a-4 SEC.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6dc53ec9dd016a2423ca96886bba400e2f17e17a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819079"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="b8844-103">Соблюдение правила 17a-4 SEC с помощью Exchange Online и Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b8844-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="b8844-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="b8844-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="b8844-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b8844-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span></span> <span data-ttu-id="b8844-106">This includes the ability to retain, audit, search, and export your data.</span><span class="sxs-lookup"><span data-stu-id="b8844-106">This includes the ability to retain, audit, search, and export your data.</span></span> <span data-ttu-id="b8844-107">These capabilities are sufficient to meet the needs of most organizations.</span><span class="sxs-lookup"><span data-stu-id="b8844-107">These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="b8844-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span><span class="sxs-lookup"><span data-stu-id="b8844-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span></span> <span data-ttu-id="b8844-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span><span class="sxs-lookup"><span data-stu-id="b8844-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span></span> <span data-ttu-id="b8844-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span><span class="sxs-lookup"><span data-stu-id="b8844-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="b8844-111">Чтобы помочь этим организациям лучше понять, как использовать Центр безопасности и соответствия требованиям для выполнения обязательств по соответствию нормативным требованиям для Exchange Online, в частности в отношении требований правила 17a-4, мы произвели оценку в сотрудничестве с Cohasset Associates.</span><span class="sxs-lookup"><span data-stu-id="b8844-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="b8844-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span><span class="sxs-lookup"><span data-stu-id="b8844-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span></span> <span data-ttu-id="b8844-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span><span class="sxs-lookup"><span data-stu-id="b8844-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="b8844-114">Скачивание оценки Cohasset</span><span class="sxs-lookup"><span data-stu-id="b8844-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="b8844-115">Вы можете скачать оценку Cohasset [здесь](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span><span class="sxs-lookup"><span data-stu-id="b8844-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Титульная страница доступной для загрузки оценки Cohasset Associates](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="b8844-117">Эта оценка относится к Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b8844-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="b8844-118">Note that this assessment is specific to Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b8844-118">Note that this assessment is specific to Exchange Online.</span></span> <span data-ttu-id="b8844-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span><span class="sxs-lookup"><span data-stu-id="b8844-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="b8844-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b8844-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span></span> <span data-ttu-id="b8844-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span><span class="sxs-lookup"><span data-stu-id="b8844-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="b8844-122">Использование блокировки для сохранения является ключевым пунктом рекомендованной конфигурации</span><span class="sxs-lookup"><span data-stu-id="b8844-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="b8844-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span><span class="sxs-lookup"><span data-stu-id="b8844-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span></span> <span data-ttu-id="b8844-124">The WORM requirement dictates a storage solution in which a record must be:</span><span class="sxs-lookup"><span data-stu-id="b8844-124">The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="b8844-125">Записи хранятся в течение обязательного периода хранения, который нельзя сократить, а можно только увеличить.</span><span class="sxs-lookup"><span data-stu-id="b8844-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="b8844-126">Записи являются неизменяемыми, то есть их нельзя перезаписывать, удалять или изменять в течение обязательного периода хранения.</span><span class="sxs-lookup"><span data-stu-id="b8844-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="b8844-127">In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span><span class="sxs-lookup"><span data-stu-id="b8844-127">In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span></span> <span data-ttu-id="b8844-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="b8844-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span></span> <span data-ttu-id="b8844-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span><span class="sxs-lookup"><span data-stu-id="b8844-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="b8844-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span><span class="sxs-lookup"><span data-stu-id="b8844-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span></span> <span data-ttu-id="b8844-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span><span class="sxs-lookup"><span data-stu-id="b8844-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="b8844-132">Период хранения политики может быть только увеличен, а не уменьшен.</span><span class="sxs-lookup"><span data-stu-id="b8844-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="b8844-133">Пользователи могут быть добавлены в политику, но не могут быть удалены из нее.</span><span class="sxs-lookup"><span data-stu-id="b8844-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="b8844-134">Администратор не может удалить политику хранения.</span><span class="sxs-lookup"><span data-stu-id="b8844-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="b8844-135">Блокировка для сохранения может обеспечить соответствие нормативным требованиям SEC 17a-4.</span><span class="sxs-lookup"><span data-stu-id="b8844-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="b8844-136">Настройка блокировки для сохранения</span><span class="sxs-lookup"><span data-stu-id="b8844-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="b8844-137">Можно заблокировать политику хранения с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8844-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="b8844-138">Дополнительные сведения см. в статье [Использование блокировки для сохранения с целью соблюдения нормативных требований](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span><span class="sxs-lookup"><span data-stu-id="b8844-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b8844-139">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="b8844-139">Known limitations</span></span>

<span data-ttu-id="b8844-140">В настоящее время существует несколько ограничений для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="b8844-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="b8844-141">Сообщения в чатах и каналах Teams нельзя объединить в цепочки.</span><span class="sxs-lookup"><span data-stu-id="b8844-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="b8844-142">Отметки "Мне нравится" не сохраняются для сообщений в чатах и каналах Teams.</span><span class="sxs-lookup"><span data-stu-id="b8844-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="b8844-143">Аудит на уровне элементов теперь доступен для почтовых ящиков групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8844-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="b8844-144">Дополнительные сведения см. в статье [Управление аудитом почтовых ящиков](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="b8844-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
