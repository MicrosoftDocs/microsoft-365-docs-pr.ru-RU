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
ms.openlocfilehash: 0426fdf04090e535a99f8acd3bf376adfb016796
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917805"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="848b1-103">Сведения о хранении содержимого Yammer</span><span class="sxs-lookup"><span data-stu-id="848b1-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="848b1-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="848b1-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="848b1-105">Эта возможность находится на этапе предварительной версии и еще недоступна всем клиентам.</span><span class="sxs-lookup"><span data-stu-id="848b1-105">This feature is in preview and not yet available for all customers.</span></span>

<span data-ttu-id="848b1-106">Эта статья дополняет [сведения о хранении](retention.md), так как в ней содержатся сведения, относящиеся к Yammer.</span><span class="sxs-lookup"><span data-stu-id="848b1-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="848b1-107">Другие нагрузки:</span><span class="sxs-lookup"><span data-stu-id="848b1-107">For other workloads, see:</span></span>

- [<span data-ttu-id="848b1-108">Хранение в SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="848b1-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="848b1-109">Хранение контента Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="848b1-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="848b1-110">Хранение контента Exchange</span><span class="sxs-lookup"><span data-stu-id="848b1-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="848b1-111">Что включается в хранение и удаление</span><span class="sxs-lookup"><span data-stu-id="848b1-111">What's included for retention and deletion</span></span>

<span data-ttu-id="848b1-112">С помощью политик хранения для Yammer можно хранить и удалять следующие элементы: сообщения сообществ и частные сообщения.</span><span class="sxs-lookup"><span data-stu-id="848b1-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="848b1-113">Реакции от других пользователей в виде смайликов не включаются в эти сообщения.</span><span class="sxs-lookup"><span data-stu-id="848b1-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="848b1-114">Порядок хранения содержимого Yammer</span><span class="sxs-lookup"><span data-stu-id="848b1-114">How retention works with Yammer</span></span>

<span data-ttu-id="848b1-115">Политику хранения можно использовать для хранения и удаления сообщений сообществ и личных сообщений в Yammer.</span><span class="sxs-lookup"><span data-stu-id="848b1-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="848b1-116">Личные сообщения хранятся в скрытой папке в почтовом ящике каждого пользователя, участвующего в общении, а сообщения сообществ — в похожей скрытой папке в почтовом ящике группы для сообщества.</span><span class="sxs-lookup"><span data-stu-id="848b1-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="848b1-117">На сообщения Yammer не влияют политики хранения, настроенные для почтовых ящиков пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="848b1-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="848b1-118">Несмотря на то, что сообщения Yammer хранятся в Exchange, эти данные Yammer включаются только политикой хранения, настроенной для расположения **сообщений сообществ Yammer** и **личных сообщений Yammer**.</span><span class="sxs-lookup"><span data-stu-id="848b1-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer private messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="848b1-119">Если пользователь включен в активную политику хранения, которая сохраняет данные Yammer, и вы удаляете почтовый ящик пользователя, включенного в эту политику, чтобы сохранить данные Yammer, почтовый ящик преобразуется в [неактивный почтовый ящик](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="848b1-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="848b1-120">Если эти данные пользователя Yammer сохранять не нужно, исключите его учетную запись из политики хранения, прежде чем удалять его почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="848b1-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="848b1-121">После настройки политики хранения для сообщений Yammer задание таймера службы Exchange периодически оценивает элементы в скрытой папке, где хранятся эти сообщения Yammer.</span><span class="sxs-lookup"><span data-stu-id="848b1-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="848b1-122">Выполнение задания таймера занимает до семи дней.</span><span class="sxs-lookup"><span data-stu-id="848b1-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="848b1-123">Когда период хранения этих элементов завершается, они перемещаются в папку SubstrateHolds — скрытую папку, которая есть в каждом почтовом ящике пользователя или группы для хранения обратимо удаленных элементов до их окончательного удаления.</span><span class="sxs-lookup"><span data-stu-id="848b1-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="848b1-124">После настройки политики хранения для сообщений Yammer, пути к содержимому зависят от настроек политики хранения: хранение и удаление, только хранение или только удаление.</span><span class="sxs-lookup"><span data-stu-id="848b1-124">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="848b1-125">Если политика хранения предусматривает хранение и удаление:</span><span class="sxs-lookup"><span data-stu-id="848b1-125">When the retention policy is to retain and then delete:</span></span>

![Схема хранения сообщений Yammer](../media/yammerretentionlifecycle.png)

<span data-ttu-id="848b1-127">Для двух путей на схеме:</span><span class="sxs-lookup"><span data-stu-id="848b1-127">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="848b1-128">**Если сообщение Yammer редактируется или удаляется** пользователем в течение периода хранения, исходное сообщение сразу копируется (если отредактировано) или перемещается (если удалено) в папку SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="848b1-128">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="848b1-129">Сообщение хранится там до завершения периода хранения, а затем сразу и окончательно удаляется.</span><span class="sxs-lookup"><span data-stu-id="848b1-129">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="848b1-130">**Если сообщение Yammer не удаляется** (для текущих сообщений после редактирования), оно перемещается в папку SubstrateHolds после завершения периода хранения.</span><span class="sxs-lookup"><span data-stu-id="848b1-130">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="848b1-131">Это действие занимает до семи дней с момента завершения периода хранения.</span><span class="sxs-lookup"><span data-stu-id="848b1-131">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="848b1-132">Попадая в папку SubstrateHolds, сообщение сразу и окончательно удаляется.</span><span class="sxs-lookup"><span data-stu-id="848b1-132">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="848b1-133">Сообщения в папке SubstrateHolds доступны для поиска средствами обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="848b1-133">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="848b1-134">Пока сообщения не будут окончательно удалены (в папке SubstrateHolds), они остаются доступными для поиска средствами обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="848b1-134">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="848b1-135">Если политика хранения предусматривает только хранение или только удаление, пути к содержимому представляют собой разновидности путей политики хранения и удаления.</span><span class="sxs-lookup"><span data-stu-id="848b1-135">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="848b1-136">Пути к содержимому для политики хранения, предусматривающей только хранение</span><span class="sxs-lookup"><span data-stu-id="848b1-136">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="848b1-137">**Если сообщение Yammer редактируется или удаляется**: копия исходного сообщения сразу создается в папке SubstrateHolds и сохраняется там до завершения периода хранения.</span><span class="sxs-lookup"><span data-stu-id="848b1-137">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="848b1-138">Затем сообщение сразу и окончательно удаляется из папки SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="848b1-138">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="848b1-139">**Если сообщение Yammer не было изменено или удалено** (для текущих сообщений после редактирования) в течение периода хранения: ничего не происходит до или после периода хранения; сообщение остается в своем первоначальном расположении.</span><span class="sxs-lookup"><span data-stu-id="848b1-139">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="848b1-140">Пути к содержимому для политики хранения, предусматривающей только удаление</span><span class="sxs-lookup"><span data-stu-id="848b1-140">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="848b1-141">**Если сообщение Yammer не удаляется** в течение периода хранения: в конце периода хранения сообщение перемещается в папку SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="848b1-141">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="848b1-142">Это действие занимает до семи дней с момента завершения периода хранения.</span><span class="sxs-lookup"><span data-stu-id="848b1-142">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="848b1-143">Затем сообщение сразу и окончательно удаляется из папки SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="848b1-143">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="848b1-144">**Если сообщение Yammer удалено пользователем** в течение периода хранения, оно немедленно перемещается в папку SubstrateHolds, откуда сразу и окончательно удаляется.</span><span class="sxs-lookup"><span data-stu-id="848b1-144">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="848b1-145">Сообщения и внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="848b1-145">Messages and external users</span></span>

<span data-ttu-id="848b1-146">По умолчанию политика хранения для личных сообщений Yammer применяются ко всем пользователям в вашей организации, но она не применяется к внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="848b1-146">By default, a retention policy for Yammer private messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="848b1-147">Политику хранения можно применить к внешним пользователям, использовав **Выбрать пользователя** и уточнив их учетную запись.</span><span class="sxs-lookup"><span data-stu-id="848b1-147">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="848b1-148">В настоящее время гостевые пользователи Azure B2B не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="848b1-148">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="848b1-149">Если пользователь покидает организацию</span><span class="sxs-lookup"><span data-stu-id="848b1-149">When a user leaves the organization</span></span> 

<span data-ttu-id="848b1-150">Если пользователь покидает организацию, а его учетная запись Microsoft 365 удаляется, его подлежащие хранению личные сообщения Yammer находятся в неактивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="848b1-150">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer private messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="848b1-151">На эти сообщения по-прежнему распространяется политика хранения, которая была применена к пользователю до того, как его почтовый ящик стал неактивным, и содержимое доступно для поиска средствами обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="848b1-151">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="848b1-152">Дополнительные сведения см. в разделе [Неактивные почтовые ящики в Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="848b1-152">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="848b1-153">Если пользователь хранил файлы в Yammer, см. [аналогичный раздел](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="848b1-153">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="848b1-154">Ограничения</span><span class="sxs-lookup"><span data-stu-id="848b1-154">Limitations</span></span>

<span data-ttu-id="848b1-155">В настоящее время политики хранения Yammer доступны в предварительной версии. Мы постоянно работаем над оптимизацией функций хранения.</span><span class="sxs-lookup"><span data-stu-id="848b1-155">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="848b1-156">Кроме того, при использовании политики хранения для сообщений сообществ и личных сообщений Yammer следует учитывать следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="848b1-156">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="848b1-157">При выборе **Выбор пользователей** для расположения **личных сообщений Yammer** могут отображаться гости и пользователи, не входящие в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="848b1-157">When you select **Choose users** for the **Yammer private messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="848b1-158">Политики хранения не предназначены для этих пользователей, поэтому не выбирайте их.</span><span class="sxs-lookup"><span data-stu-id="848b1-158">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="848b1-159">Рекомендации по настройке</span><span class="sxs-lookup"><span data-stu-id="848b1-159">Configuration guidance</span></span>

<span data-ttu-id="848b1-160">Если вы не знакомы с хранением в Microsoft 365, см. статью [Начало работы с политиками хранения и метками хранения](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="848b1-160">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="848b1-161">Если вы готовы настроить политику хранения для Yammer, см. статью [Создание и настройка политик хранения](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="848b1-161">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>