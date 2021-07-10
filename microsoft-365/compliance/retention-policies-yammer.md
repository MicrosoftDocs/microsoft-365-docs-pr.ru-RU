---
title: Сведения о хранении содержимого Yammer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Сведения о политиках хранения, применимых к Yammer.
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362298"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="1b0ac-103">Сведения о хранении содержимого Yammer</span><span class="sxs-lookup"><span data-stu-id="1b0ac-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="1b0ac-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="1b0ac-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="1b0ac-105">Эта функция в настоящее время находится на этапе тестирования и может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="1b0ac-106">Эта статья дополняет [сведения о хранении](retention.md), так как в ней содержатся сведения, относящиеся к Yammer.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="1b0ac-107">Другие нагрузки:</span><span class="sxs-lookup"><span data-stu-id="1b0ac-107">For other workloads, see:</span></span>

- [<span data-ttu-id="1b0ac-108">Хранение в SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="1b0ac-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="1b0ac-109">Хранение контента Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b0ac-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="1b0ac-110">Хранение контента Exchange</span><span class="sxs-lookup"><span data-stu-id="1b0ac-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="1b0ac-111">Что включается в хранение и удаление</span><span class="sxs-lookup"><span data-stu-id="1b0ac-111">What's included for retention and deletion</span></span>

<span data-ttu-id="1b0ac-112">С помощью политик хранения для Yammer можно хранить и удалять следующие элементы: сообщения сообщества и сообщения пользователей.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and user messages.</span></span>

<span data-ttu-id="1b0ac-113">Реакции от других пользователей в виде смайликов не включаются в эти сообщения.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="1b0ac-114">Порядок хранения содержимого Yammer</span><span class="sxs-lookup"><span data-stu-id="1b0ac-114">How retention works with Yammer</span></span>

<span data-ttu-id="1b0ac-115">В этом разделе содержится информация о том, как убедиться в соответствии требованиям внутреннего хранилища и процессов, как проверить соответствие с помощью инструментов обнаружения электронных данных, а не сообщений, отображаемых в приложении Yammer.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-115">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Yammer app.</span></span>

<span data-ttu-id="1b0ac-116">Политику хранения можно использовать для получения данных из сообщений сообщества и сообщений пользователей в Yammer, а также для удаления этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-116">You can use a retention policy to retain data from community messages and user messages in Yammer, and delete these messages.</span></span> <span data-ttu-id="1b0ac-117">С технической точки зрения для хранения данных, скопированных из таких сообщений, используются почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-117">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="1b0ac-118">Данные из сообщений пользователей Yammer хранятся в скрытой папке в почтовом ящике каждого пользователя, участвующего в сообщениях пользователей, а для сообщений сообщества используется похожая скрытая папка в почтовом ящике группы.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-118">Data from Yammer user messages is stored in a hidden folder in the mailbox of each user included in the user message, and a similar hidden folder in a group mailbox is used for community messages.</span></span>

<span data-ttu-id="1b0ac-119">Копии сообщений сообщества также могут сохраняться в скрытой папке почтовых ящиков пользователей, когда они @упоминают пользователей или уведомляют пользователя об ответе.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-119">Copies of community messages can also be stored in the hidden folder of user mailboxes when they @ mention users or notify the user of a reply.</span></span> <span data-ttu-id="1b0ac-120">Хотя эти сообщения создаются как сообщения сообщества, политика хранения для сообщений пользователей Yammer часто включает копии сообщений сообщества.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-120">Although these messages originate as a community message, a retention policy for Yammer user messages will often include copies of community messages.</span></span>

<span data-ttu-id="1b0ac-121">Эти скрытые папки не предназначены для непосредственного доступа пользователей и администраторов. В этих папках хранятся данные, доступные для поиска администраторам по соответствию требованиям, использующим инструменты обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-121">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b0ac-122">Так как копии сообщений сообщества также могут храниться в почтовых ящиках пользователей, политика хранения с действием удаления для сообщений пользователей Yammer может привести к тому, что исходное сообщение сообщества перестанет отображаться пользователям в приложении Yammer.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-122">Because copies of community messages can also be stored in user mailboxes, a retention policy with a delete action for Yammer user messages can result in the original community message no longer visible to users in the Yammer app.</span></span>
> 
> <span data-ttu-id="1b0ac-123">Однако копия исходного сообщения по-прежнему доступна в скрытой папке почтового ящика группы сообщества и при обнаружении электронных данных в целях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-123">However, a copy of the original message is still available in the hidden folder of the community group mailbox, and accessible with eDiscovery searches for compliance purposes.</span></span>

<span data-ttu-id="1b0ac-124">На сообщения Yammer не влияют политики хранения, настроенные для почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-124">Yammer messages are not affected by retention policies that are configured for Exchange mailboxes.</span></span> <span data-ttu-id="1b0ac-125">Хотя сообщения Yammer хранятся в Exchange, эти данные Yammer включаются только политикой хранения, настроенной для расположений **Сообщения сообщества Yammer** и **Сообщения пользователей Yammer**.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-125">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="1b0ac-126">Если пользователь включен в активную политику хранения, которая сохраняет данные Yammer, и вы удаляете почтовый ящик пользователя, включенного в эту политику, чтобы сохранить данные Yammer, почтовый ящик преобразуется в [неактивный почтовый ящик](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1b0ac-126">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="1b0ac-127">Если эти данные пользователя Yammer сохранять не нужно, исключите его учетную запись из политики хранения, прежде чем удалять его почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-127">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="1b0ac-128">После настройки политики хранения для сообщений Yammer задание таймера службы Exchange периодически оценивает элементы в скрытой папке, где хранятся эти сообщения Yammer.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-128">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="1b0ac-129">Выполнение задания таймера занимает до семи дней.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-129">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="1b0ac-130">Когда период хранения этих элементов завершается, они перемещаются в папку SubstrateHolds — скрытую папку, которая есть в каждом почтовом ящике пользователя или группы для хранения обратимо удаленных элементов до их окончательного удаления.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-130">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="1b0ac-131">Из-за [первого принципа хранения](retention.md#the-principles-of-retention-or-what-takes-precedence) окончательное удаление всегда приостанавливается, если тот же элемент требуется сохранить в рамках другой политики хранения или на него распространяются удержания при обнаружении электронных данных по юридическим причинам или для расследований. </span><span class="sxs-lookup"><span data-stu-id="1b0ac-131">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="1b0ac-132">После настройки политики хранения для сообщений Yammer, пути к содержимому зависят от настроек политики хранения: хранение и удаление, только хранение или только удаление.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-132">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="1b0ac-133">Если политика хранения предусматривает хранение и удаление:</span><span class="sxs-lookup"><span data-stu-id="1b0ac-133">When the retention policy is to retain and then delete:</span></span>

![Схема хранения сообщений Yammer](../media/yammerretentionlifecycle.png)

<span data-ttu-id="1b0ac-135">Для двух путей на схеме:</span><span class="sxs-lookup"><span data-stu-id="1b0ac-135">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="1b0ac-136">**Если сообщение Yammer редактируется или удаляется** пользователем в течение периода хранения, исходное сообщение сразу копируется (если отредактировано) или перемещается (если удалено) в папку SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-136">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="1b0ac-137">Сообщение хранится там до завершения периода хранения, а затем сразу и окончательно удаляется.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-137">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="1b0ac-138">**Если сообщение Yammer не удаляется** (для текущих сообщений после редактирования), оно перемещается в папку SubstrateHolds после завершения периода хранения.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-138">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="1b0ac-139">Это действие занимает до семи дней с момента завершения периода хранения.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-139">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="1b0ac-140">Попадая в папку SubstrateHolds, сообщение сразу и окончательно удаляется.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-140">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="1b0ac-141">Сообщения в папке SubstrateHolds доступны для поиска средствами обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-141">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="1b0ac-142">Пока сообщения не будут окончательно удалены (в папке SubstrateHolds), они остаются доступными для поиска средствами обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-142">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="1b0ac-143">Если политика хранения предусматривает только хранение или только удаление, пути к содержимому представляют собой разновидности путей политики хранения и удаления.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-143">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="1b0ac-144">Пути к содержимому для политики хранения, предусматривающей только хранение</span><span class="sxs-lookup"><span data-stu-id="1b0ac-144">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="1b0ac-145">**Если сообщение Yammer редактируется или удаляется**: копия исходного сообщения сразу создается в папке SubstrateHolds и сохраняется там до завершения периода хранения.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-145">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="1b0ac-146">Затем сообщение сразу и окончательно удаляется из папки SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-146">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="1b0ac-147">**Если сообщение Yammer не было изменено или удалено** (для текущих сообщений после редактирования) в течение периода хранения: ничего не происходит до или после периода хранения; сообщение остается в своем первоначальном расположении.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-147">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="1b0ac-148">Пути к содержимому для политики хранения, предусматривающей только удаление</span><span class="sxs-lookup"><span data-stu-id="1b0ac-148">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="1b0ac-149">**Если сообщение Yammer не удаляется** в течение периода хранения: в конце периода хранения сообщение перемещается в папку SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-149">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="1b0ac-150">Это действие занимает до семи дней с момента завершения периода хранения.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-150">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="1b0ac-151">Затем сообщение сразу и окончательно удаляется из папки SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-151">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="1b0ac-152">**Если сообщение Yammer удалено пользователем** в течение периода хранения, оно немедленно перемещается в папку SubstrateHolds, откуда сразу и окончательно удаляется.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-152">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="1b0ac-153">Сообщения и внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="1b0ac-153">Messages and external users</span></span>

<span data-ttu-id="1b0ac-154">По умолчанию политика хранения для сообщений пользователей Yammer применяется ко всем пользователям в вашей организации, но она не применяется к внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-154">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="1b0ac-155">Политику хранения можно применить к внешним пользователям, использовав параметр **Изменить** и указав их учетную запись.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-155">You can apply a retention policy to external users if you use the **Edit** option for users included, and specify their account.</span></span>

<span data-ttu-id="1b0ac-156">В настоящее время гостевые пользователи Azure B2B не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-156">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="1b0ac-157">Если пользователь покидает организацию</span><span class="sxs-lookup"><span data-stu-id="1b0ac-157">When a user leaves the organization</span></span> 

<span data-ttu-id="1b0ac-158">Если пользователь покидает организацию, а его учетная запись Microsoft 365 удаляется, его подлежащие хранению сообщения пользователя Yammer находятся в неактивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-158">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="1b0ac-159">На эти сообщения по-прежнему распространяется политика хранения, которая была применена к пользователю до того, как его почтовый ящик стал неактивным, и содержимое доступно для поиска средствами обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-159">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="1b0ac-160">Дополнительные сведения см. в разделе [Неактивные почтовые ящики в Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1b0ac-160">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="1b0ac-161">Если пользователь хранил файлы в Yammer, см. [аналогичный раздел](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-161">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="1b0ac-162">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1b0ac-162">Limitations</span></span>

<span data-ttu-id="1b0ac-163">В настоящее время политики хранения Yammer доступны в предварительной версии. Мы постоянно работаем над оптимизацией функций хранения.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-163">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="1b0ac-164">Кроме того, при использовании политики хранения для сообщений сообщества и сообщений пользователей Yammer следует учитывать следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-164">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and user messages:</span></span>

- <span data-ttu-id="1b0ac-165">Если нажать **Изменить** для расположения **Сообщения пользователей Yammer**, могут отображаться гости и пользователи, не входящие в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-165">When you select **Edit** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="1b0ac-166">Политики хранения не предназначены для этих пользователей, поэтому не выбирайте их.</span><span class="sxs-lookup"><span data-stu-id="1b0ac-166">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="1b0ac-167">Рекомендации по настройке</span><span class="sxs-lookup"><span data-stu-id="1b0ac-167">Configuration guidance</span></span>

<span data-ttu-id="1b0ac-168">Если вы не знакомы с хранением в Microsoft 365, см. статью [Начало работы с политиками хранения и метками хранения](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="1b0ac-168">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="1b0ac-169">Если вы готовы настроить политику хранения для Yammer, см. статью [Создание и настройка политик хранения](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1b0ac-169">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>