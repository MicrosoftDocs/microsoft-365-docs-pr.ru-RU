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
ms.openlocfilehash: bba51bed4409bfb933b577419f48ab6963d4f7d6
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577119"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="4bbac-103">Соблюдение правила 17a-4 SEC с помощью Exchange Online и Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4bbac-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="4bbac-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4bbac-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4bbac-p101">Если необходимо, чтобы ваша организация соответствовала нормативно-правовым стандартам в отношении хранения данных, в Центре безопасности и соответствия требованиям предоставлены возможности для управления жизненным циклом данных в Exchange Online. Они включают в себя хранение, аудит, экспорт данных и поиск по данным. Этих возможностей достаточно, чтобы соответствовать требованиям большинства организаций.</span><span class="sxs-lookup"><span data-stu-id="4bbac-p101">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="4bbac-p102">Однако на некоторые организации в отраслях с высоким уровнем регулирования распространяются более строгие нормативные требования. Например, финансовые учреждения, такие как банки и брокер-дилеры, должны соответствовать правилу Rule 17a-4 Комиссии по ценным бумагам и биржам США (SEC). В правиле 17a-4 есть определенные требования к хранению электронных данных, включая множество аспектов управления записями, например длительность хранения записей, их формат, качество, доступность, а также возможность их учета.</span><span class="sxs-lookup"><span data-stu-id="4bbac-p102">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="4bbac-111">Чтобы помочь этим организациям лучше понять, как использовать Центр безопасности и соответствия требованиям для выполнения обязательств по соответствию нормативным требованиям для Exchange Online, в частности в отношении требований правила 17a-4, мы произвели оценку в сотрудничестве с Cohasset Associates.</span><span class="sxs-lookup"><span data-stu-id="4bbac-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="4bbac-p103">Компания Cohasset Associates убедилась, что при рекомендованной настройке Exchange Online и Центра безопасности и соответствия требованиям соблюдаются соответствующие требования к хранилищам согласно правилу CFTC 1.31 (пункты c и d), правилу FINRA 4511 и правилу SEC 17a-4. Мы использовали именно такой набор правил, поскольку они представляют наиболее регламентированные международные указания в отношении хранения записей для финансовых учреждений.</span><span class="sxs-lookup"><span data-stu-id="4bbac-p103">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="4bbac-114">Скачивание оценки Cohasset</span><span class="sxs-lookup"><span data-stu-id="4bbac-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="4bbac-115">Вы можете скачать оценку Cohasset [здесь](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span><span class="sxs-lookup"><span data-stu-id="4bbac-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Титульная страница доступной для загрузки оценки Cohasset Associates](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="4bbac-117">Эта оценка относится к Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4bbac-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="4bbac-p104">Обратите внимание, что эта оценка относится исключительно к Exchange Online. Она не распространяется на службы Microsoft 365, такие как SharePoint Online и OneDrive для бизнеса. В будущем мы планируем поддерживать оценку таких служб на соответствие правилу SEC 17a-4.</span><span class="sxs-lookup"><span data-stu-id="4bbac-p104">Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="4bbac-p105">Важно понимать, что данные Skype для бизнеса и Teams также хранятся в Exchange Online. Поэтому в оценку не включены сообщения из Skype для бизнеса и сообщения в каналах и чатах из Teams.</span><span class="sxs-lookup"><span data-stu-id="4bbac-p105">It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="4bbac-122">Использование блокировки для сохранения является ключевым пунктом рекомендованной конфигурации</span><span class="sxs-lookup"><span data-stu-id="4bbac-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="4bbac-p106">В отраслях с высоким уровнем регулирования часто требуется сохранять электронные сообщения, чтобы соответствовать правилу WORM (однократная запись, многократное чтение). Для соблюдения правила WORM требуется решение, где выполняются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="4bbac-p106">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="4bbac-125">Записи хранятся в течение обязательного периода хранения, который нельзя сократить, а можно только увеличить.</span><span class="sxs-lookup"><span data-stu-id="4bbac-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="4bbac-126">Записи являются неизменяемыми, то есть их нельзя перезаписывать, удалять или изменять в течение обязательного периода хранения.</span><span class="sxs-lookup"><span data-stu-id="4bbac-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="4bbac-p107">Если в Exchange Online [политика хранения](retention.md) применена к почтовому ящику пользователя, то все содержимое, принадлежащее этому пользователю, будет храниться на основе условий этой политики. Например, если пользователь попытается удалить или изменить сообщение электронной почты, то копия этого электронного сообщения до его изменения сохранится в безопасном скрытом месте в почтовом ящике этого пользователя. Политики хранения помогают обеспечить хранения электронных сообщений в организации, но эти политики могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="4bbac-p107">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="4bbac-p108">Применяя блокировку для сохранения к политике хранения, организация обеспечивает неизменность политики. То есть после применения блокировки для сохранения к политике хранения будут действовать следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="4bbac-p108">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="4bbac-132">Период хранения политики может быть только увеличен, а не уменьшен.</span><span class="sxs-lookup"><span data-stu-id="4bbac-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="4bbac-133">Пользователи могут быть добавлены в политику, но не могут быть удалены из нее.</span><span class="sxs-lookup"><span data-stu-id="4bbac-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="4bbac-134">Администратор не может удалить политику хранения.</span><span class="sxs-lookup"><span data-stu-id="4bbac-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="4bbac-135">Блокировка для сохранения может обеспечить соответствие нормативным требованиям SEC 17a-4.</span><span class="sxs-lookup"><span data-stu-id="4bbac-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="4bbac-136">Настройка блокировки для сохранения</span><span class="sxs-lookup"><span data-stu-id="4bbac-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="4bbac-137">Можно заблокировать политику хранения с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bbac-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="4bbac-138">Дополнительные сведения см. в статье [Использование блокировки для сохранения с целью соблюдения нормативных требований](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span><span class="sxs-lookup"><span data-stu-id="4bbac-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

