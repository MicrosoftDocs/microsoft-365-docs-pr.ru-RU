---
title: Политика именования групп
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Узнайте, как создать политику именования для групп Microsoft 365.
ms.openlocfilehash: ae216d0d8f3319e9633d300d785b4a8c31702798
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702552"
---
# <a name="groups-naming-policy"></a><span data-ttu-id="ef94c-103">Политика именования групп</span><span class="sxs-lookup"><span data-stu-id="ef94c-103">Groups naming policy</span></span>

<span data-ttu-id="ef94c-104">Политика именования групп используется для обеспечения согласованной стратегии именования для групп, создаваемых пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="ef94c-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="ef94c-105">Политика именования поможет вам и вашим пользователям определить функции группы, членства, географического региона или группы.</span><span class="sxs-lookup"><span data-stu-id="ef94c-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="ef94c-106">С помощью политики именования можно также классифицировать группы в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="ef94c-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="ef94c-107">Вы можете использовать политику для блокирования использования определенных слов в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="ef94c-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="ef94c-108">Политика именования применяется к группам, созданным во всех рабочих нагрузках группы (например, Outlook, Microsoft Teams, SharePoint, Planner, Yammer и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ef94c-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="ef94c-109">Он применяется как к имени группы, так и к псевдониму группы.</span><span class="sxs-lookup"><span data-stu-id="ef94c-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="ef94c-110">Он применяется, когда пользователь создает группу и при редактировании имени или псевдонима группы для существующей группы.</span><span class="sxs-lookup"><span data-stu-id="ef94c-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="ef94c-111">Политика именования групп Microsoft 365 применяется только к группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef94c-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="ef94c-112">Она не применяется к группам рассылки, созданным в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ef94c-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="ef94c-113">Чтобы создать политику именования для групп рассылки, ознакомьтесь со статьей [Создание политики именования групп рассылки](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="ef94c-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="ef94c-114">Политика именования групп состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="ef94c-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="ef94c-115">**Политика именования префикса суффикса**: вы можете использовать префиксы или суффиксы, чтобы определить соглашение об именовании групп (например, "US \_ My Group \_ Engineer").</span><span class="sxs-lookup"><span data-stu-id="ef94c-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="ef94c-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span><span class="sxs-lookup"><span data-stu-id="ef94c-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="ef94c-117">**Пользовательские заблокированные слова**: вы можете отправить набор заблокированных слов, относящихся к вашей организации, которые будут блокироваться в группах, созданных пользователями.</span><span class="sxs-lookup"><span data-stu-id="ef94c-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="ef94c-118">(Например: "Генеральный директор, зарплата, HR").</span><span class="sxs-lookup"><span data-stu-id="ef94c-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="ef94c-119">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="ef94c-119">Licensing requirements</span></span>

<span data-ttu-id="ef94c-120">Использование политики именования Azure AD для групп Microsoft 365 требует, чтобы вы обладали лицензией на Azure Active Directory Premium P1 или Azure AD Basic EDU для каждого уникального пользователя (включая гостей), который является участником одной или нескольких групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef94c-120">Using Azure AD naming policy for Microsoft 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="ef94c-121">Это также необходимо для администратора, который создает политику именования групп.</span><span class="sxs-lookup"><span data-stu-id="ef94c-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="ef94c-122">Политика именования префикса суффикса</span><span class="sxs-lookup"><span data-stu-id="ef94c-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="ef94c-123">Префиксы и суффиксы могут быть либо фиксированными строками, либо пользовательскими атрибутами.</span><span class="sxs-lookup"><span data-stu-id="ef94c-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="ef94c-124">Фиксированные строки</span><span class="sxs-lookup"><span data-stu-id="ef94c-124">Fixed strings</span></span>

<span data-ttu-id="ef94c-125">Можно использовать короткие строки, которые помогут отличать группы в глобальном списке адресов и левую навигацию по рабочим нагрузкам группы.</span><span class="sxs-lookup"><span data-stu-id="ef94c-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="ef94c-126">Некоторые общие префиксы префиксов являются ключевыми словами, такими как ' GRP \_ name ', ' \# name ', ' \_ name '.</span><span class="sxs-lookup"><span data-stu-id="ef94c-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="ef94c-127">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ef94c-127">Attributes</span></span>

<span data-ttu-id="ef94c-128">Вы можете использовать атрибуты, которые помогут определить, кто создал эту группу (например, [Отдел], и где она была создана, например [Country]).</span><span class="sxs-lookup"><span data-stu-id="ef94c-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ef94c-129">**Примеры**</span><span class="sxs-lookup"><span data-stu-id="ef94c-129">**Examples**</span></span>|<span data-ttu-id="ef94c-130">Политика = "ГР [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="ef94c-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="ef94c-131">Отдел пользователя = Проектирование</span><span class="sxs-lookup"><span data-stu-id="ef94c-131">User's department = Engineering</span></span>|
||<span data-ttu-id="ef94c-132">Имя создаваемой группы = "ГР Моя группа Проектирование"</span><span class="sxs-lookup"><span data-stu-id="ef94c-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="ef94c-133">Поддерживаемые атрибуты Azure Active Directory (Azure AD): [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] и [title].</span><span class="sxs-lookup"><span data-stu-id="ef94c-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="ef94c-p107">Нераспознанные атрибуты считаются фиксированными строками. Пример: "[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="ef94c-p107">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="ef94c-137">Атрибуты расширения и настраиваемые атрибуты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ef94c-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="ef94c-138">Рекомендуется использовать атрибуты, значения которых заданы для всех пользователей в организации, и не применять атрибуты с длинными значениями.</span><span class="sxs-lookup"><span data-stu-id="ef94c-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="ef94c-139">Вопросы, которые нужно найти</span><span class="sxs-lookup"><span data-stu-id="ef94c-139">Things to look out for</span></span>

- <span data-ttu-id="ef94c-140">При создании политики общая длина строки префиксов и суффиксов ограничена 53 знаками.</span><span class="sxs-lookup"><span data-stu-id="ef94c-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="ef94c-141">Префиксы и суффиксы могут содержать специальные знаки, поддерживаемые в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="ef94c-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="ef94c-142">Если префиксы и суффиксы содержат специальные символы, которые не разрешены в псевдониме группы, они применяются только к имени группы.</span><span class="sxs-lookup"><span data-stu-id="ef94c-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="ef94c-143">В этом случае префиксы и суффиксы, применяемые к имени группы, будут отличаться от применяемых к псевдониму.</span><span class="sxs-lookup"><span data-stu-id="ef94c-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef94c-144">Точка (.) или дефис (-) разрешается в любом месте имени группы, за исключением имени в начале или конце имени.</span><span class="sxs-lookup"><span data-stu-id="ef94c-144">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="ef94c-145">Знак подчеркивания (_) разрешается в любом месте имени группы, в том числе в начале или конце имени.</span><span class="sxs-lookup"><span data-stu-id="ef94c-145">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="ef94c-146">Если вы используете Объединенные группы Yammer Microsoft 365, не используйте следующие символы в политике именования: @, \# , \[ , \] , \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="ef94c-146">If you are using Yammer Microsoft 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="ef94c-147">Если эти символы находятся в политике именования, обычные пользователи Yammer не смогут создавать группы.</span><span class="sxs-lookup"><span data-stu-id="ef94c-147">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="ef94c-148">Пользовательские заблокированные слова</span><span class="sxs-lookup"><span data-stu-id="ef94c-148">Custom blocked words</span></span>

<span data-ttu-id="ef94c-149">Вы можете ввести разделенный запятыми список заблокированных слов, которые будут блокироваться в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="ef94c-149">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="ef94c-150">Поиск во вложенных строках не выполняется; в частности, для запуска сбоя требуется точное соответствие между введенным пользователем именем и пользовательскими заблокированными словами.</span><span class="sxs-lookup"><span data-stu-id="ef94c-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="ef94c-151">Поиск в подстроке не выполняется, поэтому пользователи могут использовать некоторые распространенные слова, например "class", даже если "АСС" является заблокированным словом.</span><span class="sxs-lookup"><span data-stu-id="ef94c-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="ef94c-152">**Вопросы, которые нужно найти**:</span><span class="sxs-lookup"><span data-stu-id="ef94c-152">**Things to look out for**:</span></span>

- <span data-ttu-id="ef94c-153">При проверке запрещенных слов регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="ef94c-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="ef94c-154">Когда пользователь вводит запрещенное слово, в клиенте выводится сообщение об ошибке с указанием этого слова.</span><span class="sxs-lookup"><span data-stu-id="ef94c-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="ef94c-155">В запрещенных словах нет ограничений на используемые знаки.</span><span class="sxs-lookup"><span data-stu-id="ef94c-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="ef94c-156">Ограничено 5000 слов, которые можно задать в качестве заблокированных слов.</span><span class="sxs-lookup"><span data-stu-id="ef94c-156">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="ef94c-157">Переопределение администраторами</span><span class="sxs-lookup"><span data-stu-id="ef94c-157">Admin override</span></span>

<span data-ttu-id="ef94c-p112">Для некоторых администраторов эти политики не действуют, так что они могут создавать группы, используя запрещенные слова и собственные соглашения об именовании, в любых службах и конечных точках. Из политики именования групп исключаются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="ef94c-p112">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="ef94c-160">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="ef94c-160">Global admin</span></span>

- <span data-ttu-id="ef94c-161">Поддержка партнеров уровня 1</span><span class="sxs-lookup"><span data-stu-id="ef94c-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="ef94c-162">Поддержка партнеров уровня 2</span><span class="sxs-lookup"><span data-stu-id="ef94c-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="ef94c-163">Администратор учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="ef94c-163">User account admin</span></span>

- <span data-ttu-id="ef94c-164">Запись каталогов</span><span class="sxs-lookup"><span data-stu-id="ef94c-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="ef94c-165">Настройка политики именования</span><span class="sxs-lookup"><span data-stu-id="ef94c-165">How to set up the naming policy</span></span>

<span data-ttu-id="ef94c-166">Настройка политики именования:</span><span class="sxs-lookup"><span data-stu-id="ef94c-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="ef94c-167">В разделе **Управление** [Azure Active Directory](https://aad.portal.azure.com)щелкните **группы**.</span><span class="sxs-lookup"><span data-stu-id="ef94c-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="ef94c-168">В разделе **Параметры**выберите пункт **Политика именования**.</span><span class="sxs-lookup"><span data-stu-id="ef94c-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="ef94c-169">Выберите вкладку **Политика именования групп** .</span><span class="sxs-lookup"><span data-stu-id="ef94c-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="ef94c-170">В разделе **Текущая политика**выберите необходимость использования префикса или суффикса или обеих этих флажков, а также установите соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="ef94c-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="ef94c-171">Выберите между **атрибутом** и **строкой** для каждой строки, а затем укажите атрибут или строку.</span><span class="sxs-lookup"><span data-stu-id="ef94c-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="ef94c-172">Добавив необходимые префиксы и суффиксы, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ef94c-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Снимок экрана параметров политики именования групп в Azure Active Directory](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> <span data-ttu-id="ef94c-174">StaffHub Teams не следуют политике именования, но базовая группа Microsoft 365 — это.</span><span class="sxs-lookup"><span data-stu-id="ef94c-174">StaffHub teams do not follow the naming policy, but the underlying Microsoft 365 group does.</span></span> <span data-ttu-id="ef94c-175">К имени группы StaffHub не добавляются префиксы и суффиксы, и в них не проверяется наличие настраиваемых запрещенных слов.</span><span class="sxs-lookup"><span data-stu-id="ef94c-175">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="ef94c-176">Однако StaffHub применяет префиксы и суффиксы и удаляет заблокированные слова из базовой группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef94c-176">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Microsoft 365 group.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="ef94c-177">Дополнительные статьи о политике именования</span><span class="sxs-lookup"><span data-stu-id="ef94c-177">More articles on naming policy</span></span>

[<span data-ttu-id="ef94c-178">Применение политики именования для групп Microsoft 365 в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ef94c-178">Enforce a naming policy for Microsoft 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="ef94c-179">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="ef94c-179">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
