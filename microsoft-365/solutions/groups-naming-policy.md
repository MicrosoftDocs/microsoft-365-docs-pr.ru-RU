---
title: Политика именования групп Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Узнайте, как создать политику именования для групп Microsoft 365.
ms.openlocfilehash: 0072abf4f249af544e8234fdedec584a71c214a7
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662804"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="c0bad-103">Политика именования групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c0bad-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="c0bad-104">Вы можете использовать политику именования групп, чтобы обеспечить согласованную стратегию именования для групп, создаваемых пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="c0bad-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="c0bad-105">Политика именования поможет вам и вашим пользователям определить функции группы, членства, географического региона или группы.</span><span class="sxs-lookup"><span data-stu-id="c0bad-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="c0bad-106">С помощью политики именования можно также классифицировать группы в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="c0bad-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="c0bad-107">Вы можете использовать политику для блокирования использования определенных слов в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="c0bad-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="c0bad-108">Политика именования применяется к группам, созданным во всех рабочих нагрузках группы (например, Outlook, Microsoft Teams, SharePoint, Planner, Yammer и т. д.).</span><span class="sxs-lookup"><span data-stu-id="c0bad-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="c0bad-109">Он применяется как к имени группы, так и к псевдониму группы.</span><span class="sxs-lookup"><span data-stu-id="c0bad-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="c0bad-110">Он применяется, когда пользователь создает группу и при редактировании имени или псевдонима группы для существующей группы.</span><span class="sxs-lookup"><span data-stu-id="c0bad-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="c0bad-111">Политика именования групп Microsoft 365 применяется только к группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0bad-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="c0bad-112">Она не применяется к группам рассылки, созданным в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c0bad-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="c0bad-113">Чтобы создать политику именования для групп рассылки, ознакомьтесь со статьей [Создание политики именования групп рассылки](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="c0bad-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="c0bad-114">Политика именования групп состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="c0bad-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="c0bad-115">**Политика именования префикса суффикса**: вы можете использовать префиксы или суффиксы, чтобы определить соглашение об именовании групп (например, "US \_ My Group \_ Engineer").</span><span class="sxs-lookup"><span data-stu-id="c0bad-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="c0bad-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span><span class="sxs-lookup"><span data-stu-id="c0bad-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="c0bad-117">**Пользовательские заблокированные слова**: вы можете отправить набор заблокированных слов, относящихся к вашей организации, которые будут блокироваться в группах, созданных пользователями.</span><span class="sxs-lookup"><span data-stu-id="c0bad-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="c0bad-118">(Например: "Генеральный директор, зарплата, HR").</span><span class="sxs-lookup"><span data-stu-id="c0bad-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c0bad-119">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="c0bad-119">Licensing requirements</span></span>

<span data-ttu-id="c0bad-120">Использование политики именования Azure AD для групп Microsoft 365 требует, чтобы вы обладали лицензией на Azure Active Directory Premium P1 или Azure AD Basic EDU для каждого уникального пользователя (включая гостей), который является участником одной или нескольких групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0bad-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="c0bad-121">Это также необходимо для администратора, который создает политику именования групп.</span><span class="sxs-lookup"><span data-stu-id="c0bad-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="c0bad-122">Политика именования префикса суффикса</span><span class="sxs-lookup"><span data-stu-id="c0bad-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="c0bad-123">Префиксы и суффиксы могут быть либо фиксированными строками, либо пользовательскими атрибутами.</span><span class="sxs-lookup"><span data-stu-id="c0bad-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="c0bad-124">Фиксированные строки</span><span class="sxs-lookup"><span data-stu-id="c0bad-124">Fixed strings</span></span>

<span data-ttu-id="c0bad-125">Можно использовать короткие строки, которые помогут отличать группы в глобальном списке адресов и левую навигацию по рабочим нагрузкам группы.</span><span class="sxs-lookup"><span data-stu-id="c0bad-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="c0bad-126">Некоторые общие префиксы префиксов являются ключевыми словами, такими как ' GRP \_ name ', ' \# name ', ' \_ name '.</span><span class="sxs-lookup"><span data-stu-id="c0bad-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="c0bad-127">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0bad-127">Attributes</span></span>

<span data-ttu-id="c0bad-128">Вы можете использовать атрибуты, которые помогут определить, кто создал эту группу (например, [Отдел], и где она была создана, например [Country]).</span><span class="sxs-lookup"><span data-stu-id="c0bad-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="c0bad-129">Примеры:</span><span class="sxs-lookup"><span data-stu-id="c0bad-129">Examples:</span></span>

- <span data-ttu-id="c0bad-130">Политика = "ГР [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="c0bad-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="c0bad-131">Отдел пользователя = Проектирование</span><span class="sxs-lookup"><span data-stu-id="c0bad-131">User's department = Engineering</span></span>
- <span data-ttu-id="c0bad-132">Имя создаваемой группы = "ГР Моя группа Проектирование"</span><span class="sxs-lookup"><span data-stu-id="c0bad-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="c0bad-133">Поддерживаемые атрибуты Azure Active Directory (Azure AD): [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] и [title].</span><span class="sxs-lookup"><span data-stu-id="c0bad-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="c0bad-134">Неподдерживаемые атрибуты пользователей считаются фиксированными строками, например [postalCode].</span><span class="sxs-lookup"><span data-stu-id="c0bad-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="c0bad-135">Атрибуты расширения и настраиваемые атрибуты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c0bad-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="c0bad-136">Рекомендуется использовать атрибуты, значения которых заданы для всех пользователей в организации, и не применять атрибуты с длинными значениями.</span><span class="sxs-lookup"><span data-stu-id="c0bad-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="c0bad-137">Вопросы, которые нужно найти</span><span class="sxs-lookup"><span data-stu-id="c0bad-137">Things to look out for</span></span>

- <span data-ttu-id="c0bad-138">При создании политики общая длина строки префиксов и суффиксов ограничена 53 знаками.</span><span class="sxs-lookup"><span data-stu-id="c0bad-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="c0bad-139">Префиксы и суффиксы могут содержать специальные знаки, поддерживаемые в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="c0bad-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="c0bad-140">Если префиксы и суффиксы содержат специальные символы, которые не разрешены в псевдониме группы, они применяются только к имени группы.</span><span class="sxs-lookup"><span data-stu-id="c0bad-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="c0bad-141">В этом случае префиксы и суффиксы, применяемые к имени группы, будут отличаться от применяемых к псевдониму.</span><span class="sxs-lookup"><span data-stu-id="c0bad-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0bad-142">Точка (.) или дефис (-) разрешается в любом месте имени группы, за исключением имени в начале или конце имени.</span><span class="sxs-lookup"><span data-stu-id="c0bad-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="c0bad-143">Знак подчеркивания (_) разрешается в любом месте имени группы, в том числе в начале или конце имени.</span><span class="sxs-lookup"><span data-stu-id="c0bad-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="c0bad-144">При использовании подключенных групп Yammer Office 365 следует избегать использования следующих символов в политике именования: @, \# , \[ , \] , \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="c0bad-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="c0bad-145">Если эти символы находятся в политике именования, обычные пользователи Yammer не смогут создавать группы.</span><span class="sxs-lookup"><span data-stu-id="c0bad-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="c0bad-146">Используйте короткие строки в качестве суффикса.</span><span class="sxs-lookup"><span data-stu-id="c0bad-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="c0bad-147">Используйте атрибуты со значениями.</span><span class="sxs-lookup"><span data-stu-id="c0bad-147">Use attributes with values.</span></span>
> - <span data-ttu-id="c0bad-148">Не слишком изобретательно, Общая длина имени не должна превышать 264 символов.</span><span class="sxs-lookup"><span data-stu-id="c0bad-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="c0bad-149">Отправьте определенные заблокированные слова в Организации, чтобы ограничить использование.</span><span class="sxs-lookup"><span data-stu-id="c0bad-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="c0bad-150">Пользовательские заблокированные слова</span><span class="sxs-lookup"><span data-stu-id="c0bad-150">Custom blocked words</span></span>

<span data-ttu-id="c0bad-151">Вы можете ввести разделенный запятыми список заблокированных слов, которые будут блокироваться в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="c0bad-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="c0bad-152">Поиск во вложенных строках не выполняется; в частности, для запуска сбоя требуется точное соответствие между введенным пользователем именем и пользовательскими заблокированными словами.</span><span class="sxs-lookup"><span data-stu-id="c0bad-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="c0bad-153">**Вопросы, которые нужно найти**:</span><span class="sxs-lookup"><span data-stu-id="c0bad-153">**Things to look out for**:</span></span>

- <span data-ttu-id="c0bad-154">При проверке запрещенных слов регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="c0bad-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="c0bad-155">Когда пользователь вводит запрещенное слово, в клиенте выводится сообщение об ошибке с указанием этого слова.</span><span class="sxs-lookup"><span data-stu-id="c0bad-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="c0bad-156">В запрещенных словах нет ограничений на используемые знаки.</span><span class="sxs-lookup"><span data-stu-id="c0bad-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="c0bad-157">Ограничено 5000 слов, которые можно задать в качестве заблокированных слов.</span><span class="sxs-lookup"><span data-stu-id="c0bad-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="c0bad-158">Переопределение администраторами</span><span class="sxs-lookup"><span data-stu-id="c0bad-158">Admin override</span></span>

<span data-ttu-id="c0bad-159">Некоторые администраторы исключены из этих политик во всех рабочих нагрузках и конечных точках группы, чтобы они могли создавать группы с этими заблокированными словами и их соглашения об именовании.</span><span class="sxs-lookup"><span data-stu-id="c0bad-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="c0bad-160">Из политики именования групп исключаются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="c0bad-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="c0bad-161">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="c0bad-161">Global admin</span></span>

- <span data-ttu-id="c0bad-162">Поддержка партнеров уровня 1</span><span class="sxs-lookup"><span data-stu-id="c0bad-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="c0bad-163">Поддержка партнеров уровня 2</span><span class="sxs-lookup"><span data-stu-id="c0bad-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="c0bad-164">Администратор учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="c0bad-164">User account admin</span></span>

- <span data-ttu-id="c0bad-165">Запись каталогов</span><span class="sxs-lookup"><span data-stu-id="c0bad-165">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="c0bad-166">Настройка политики именования</span><span class="sxs-lookup"><span data-stu-id="c0bad-166">How to set up the naming policy</span></span>

<span data-ttu-id="c0bad-167">Настройка политики именования:</span><span class="sxs-lookup"><span data-stu-id="c0bad-167">To set up a naming policy:</span></span>

1. <span data-ttu-id="c0bad-168">В разделе **Управление** [Azure Active Directory](https://aad.portal.azure.com)щелкните **группы**.</span><span class="sxs-lookup"><span data-stu-id="c0bad-168">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="c0bad-169">В разделе **Параметры**выберите пункт **Политика именования**.</span><span class="sxs-lookup"><span data-stu-id="c0bad-169">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="c0bad-170">Выберите вкладку **Политика именования групп** .</span><span class="sxs-lookup"><span data-stu-id="c0bad-170">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="c0bad-171">В разделе **Текущая политика**выберите необходимость использования префикса или суффикса или обеих этих флажков, а также установите соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="c0bad-171">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="c0bad-172">Выберите между **атрибутом** и **строкой** для каждой строки, а затем укажите атрибут или строку.</span><span class="sxs-lookup"><span data-stu-id="c0bad-172">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="c0bad-173">Добавив необходимые префиксы и суффиксы, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c0bad-173">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Снимок экрана параметров политики именования групп в Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="c0bad-175">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c0bad-175">Related topics</span></span>

[<span data-ttu-id="c0bad-176">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="c0bad-176">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
