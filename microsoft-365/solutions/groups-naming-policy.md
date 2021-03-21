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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Узнайте, как создать политику именования для групп Microsoft 365.
ms.openlocfilehash: 7fd2ea36b536924d85c7ca09b55593161a24dbe4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921052"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="c8c68-103">Политика именования групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8c68-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="c8c68-104">Вы можете использовать политику именования групп для обеспечения согласованной стратегии именования для групп, созданных пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c8c68-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="c8c68-105">Политика именования может помочь вам и вашим пользователям определить функции группы, членства, географического региона или создавшего группу.</span><span class="sxs-lookup"><span data-stu-id="c8c68-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="c8c68-106">Политика именования также может помочь классифицировать группы в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="c8c68-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="c8c68-107">Вы можете использовать политику, чтобы заблокировать использование определенных слов в именах групп и псевдонимах.</span><span class="sxs-lookup"><span data-stu-id="c8c68-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="c8c68-108">Политика именования применяется к группам, созданным во всех рабочих нагрузках групп (например, Outlook, Microsoft Teams, SharePoint, Planner, Yammer и т.д.).</span><span class="sxs-lookup"><span data-stu-id="c8c68-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="c8c68-109">Он применяется как к имени группы, так и к псевдониму группы.</span><span class="sxs-lookup"><span data-stu-id="c8c68-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="c8c68-110">Оно также применяется, когда пользователь создает группу и когда имя группы, псевдоним, описание или аватар редактированы для существующей группы.</span><span class="sxs-lookup"><span data-stu-id="c8c68-110">It also gets applied when a user creates a group and when the group name, alias, description, or avatar is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="c8c68-111">Политика именования групп Microsoft 365 применяется только к группам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8c68-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="c8c68-112">Это не относится к группам рассылки, созданным в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8c68-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="c8c68-113">Чтобы создать политику именования для групп рассылки, см. в этой ленте Создание политики именования [групп рассылки.](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)</span><span class="sxs-lookup"><span data-stu-id="c8c68-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="c8c68-114">Политика именования групп состоит из следующих функций:</span><span class="sxs-lookup"><span data-stu-id="c8c68-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="c8c68-115">Политика имен **prefix-Suffix:** для определения конвенции имен групп (например, "Инженерная группа США" можно использовать префиксы или суффиксы). \_ \_</span><span class="sxs-lookup"><span data-stu-id="c8c68-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="c8c68-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span><span class="sxs-lookup"><span data-stu-id="c8c68-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="c8c68-117">**Настраиваемые заблокированные слова.** Вы можете загрузить набор заблокированных слов, определенных для организации, которые будут заблокированы в группах, созданных пользователями.</span><span class="sxs-lookup"><span data-stu-id="c8c68-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="c8c68-118">(Например: "CEO, Payroll, HR").</span><span class="sxs-lookup"><span data-stu-id="c8c68-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c8c68-119">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="c8c68-119">Licensing requirements</span></span>

<span data-ttu-id="c8c68-120">Использование политики имен Azure AD для Microsoft 365 Groups требует, чтобы у вас была лицензия Azure Active Directory Premium P1 или лицензия Azure AD Basic EDU для каждого уникального пользователя (включая гостей), который является членом одной или более групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8c68-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="c8c68-121">Это также необходимо для администратора, который создает политику именования групп.</span><span class="sxs-lookup"><span data-stu-id="c8c68-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="c8c68-122">Prefix-Suffix политики именования</span><span class="sxs-lookup"><span data-stu-id="c8c68-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="c8c68-123">Префиксы и суффиксы могут быть фиксированными строками или атрибутами пользователя.</span><span class="sxs-lookup"><span data-stu-id="c8c68-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="c8c68-124">Фиксированные строки</span><span class="sxs-lookup"><span data-stu-id="c8c68-124">Fixed strings</span></span>

<span data-ttu-id="c8c68-125">Можно использовать короткие строки, которые помогут различать группы в GAL и левой навигации по рабочим нагрузкам группы.</span><span class="sxs-lookup"><span data-stu-id="c8c68-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="c8c68-126">Некоторые из распространенных суффиксов префиксов — это ключевые слова, такие как "Имя Grp", \_ \# "Имя", \_ "Имя"</span><span class="sxs-lookup"><span data-stu-id="c8c68-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="c8c68-127">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8c68-127">Attributes</span></span>

<span data-ttu-id="c8c68-128">Можно использовать атрибуты, которые могут помочь определить, кто создал группу типа [Department] и где она была создана из типа [Страна].</span><span class="sxs-lookup"><span data-stu-id="c8c68-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="c8c68-129">Примеры:</span><span class="sxs-lookup"><span data-stu-id="c8c68-129">Examples:</span></span>

- <span data-ttu-id="c8c68-130">Политика = "ГР [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="c8c68-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="c8c68-131">Отдел пользователя = Проектирование</span><span class="sxs-lookup"><span data-stu-id="c8c68-131">User's department = Engineering</span></span>
- <span data-ttu-id="c8c68-132">Имя создаваемой группы = "ГР Моя группа Проектирование"</span><span class="sxs-lookup"><span data-stu-id="c8c68-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="c8c68-133">Поддерживаемые атрибуты Azure Active Directory (Azure AD) — это атрибуты [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], и [Title].</span><span class="sxs-lookup"><span data-stu-id="c8c68-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="c8c68-134">Неподдермеченные атрибуты пользователей считаются фиксированными строками, например [postalCode].</span><span class="sxs-lookup"><span data-stu-id="c8c68-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="c8c68-135">Атрибуты расширения и настраиваемые атрибуты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c8c68-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="c8c68-136">Рекомендуется использовать атрибуты, значения которых заданы для всех пользователей в организации, и не применять атрибуты с длинными значениями.</span><span class="sxs-lookup"><span data-stu-id="c8c68-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="c8c68-137">На что нужно глядеть</span><span class="sxs-lookup"><span data-stu-id="c8c68-137">Things to look out for</span></span>

- <span data-ttu-id="c8c68-138">При создании политики общая длина строки префиксов и суффиксов ограничена 53 знаками.</span><span class="sxs-lookup"><span data-stu-id="c8c68-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="c8c68-139">Префиксы и суффиксы могут содержать специальные знаки, поддерживаемые в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="c8c68-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="c8c68-140">Если префиксы и суффиксы содержат специальные символы, которые не разрешены в псевдониме группы, они применяются только к имени группы.</span><span class="sxs-lookup"><span data-stu-id="c8c68-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="c8c68-141">В этом случае префиксы и суффиксы, применяемые к имени группы, будут отличаться от применяемых к псевдониму.</span><span class="sxs-lookup"><span data-stu-id="c8c68-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c8c68-142">Период (.) или дефис (-) разрешен в любом месте в названии группы, за исключением начала или конца имени.</span><span class="sxs-lookup"><span data-stu-id="c8c68-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="c8c68-143">Подчеркивать (_) разрешено в любом месте в названии группы, в том числе в начале или конце имени.</span><span class="sxs-lookup"><span data-stu-id="c8c68-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="c8c68-144">Если вы используете подключенные группы Yammer Office 365, избегайте использования следующих символов в политике именования: @, \# , \[ , , \] \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="c8c68-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="c8c68-145">Если эти символы находятся в политике именования, обычные пользователи Yammer не смогут создавать группы.</span><span class="sxs-lookup"><span data-stu-id="c8c68-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="c8c68-146">Используйте короткие строки в качестве суффикса.</span><span class="sxs-lookup"><span data-stu-id="c8c68-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="c8c68-147">Используйте атрибуты со значениями.</span><span class="sxs-lookup"><span data-stu-id="c8c68-147">Use attributes with values.</span></span>
> - <span data-ttu-id="c8c68-148">Не будьте слишком творчески, общая длина имени не более 264 символов.</span><span class="sxs-lookup"><span data-stu-id="c8c68-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="c8c68-149">Загрузите определенные заблокированные слова организации, чтобы ограничить использование.</span><span class="sxs-lookup"><span data-stu-id="c8c68-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="c8c68-150">Настраиваемые заблокированные слова</span><span class="sxs-lookup"><span data-stu-id="c8c68-150">Custom blocked words</span></span>

<span data-ttu-id="c8c68-151">Можно ввести разделенный запятой список заблокированных слов, которые будут заблокированы в названиях групп и псевдонимах.</span><span class="sxs-lookup"><span data-stu-id="c8c68-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="c8c68-152">Поиск суб-строки не выполняется; В частности, для запуска сбоя требуется точное совпадение между вписаным именем пользователя и пользовательскими заблокированными словами.</span><span class="sxs-lookup"><span data-stu-id="c8c68-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="c8c68-153">**Что нужно искать:**</span><span class="sxs-lookup"><span data-stu-id="c8c68-153">**Things to look out for**:</span></span>

- <span data-ttu-id="c8c68-154">При проверке запрещенных слов регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="c8c68-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="c8c68-155">Когда пользователь вводит запрещенное слово, в клиенте выводится сообщение об ошибке с указанием этого слова.</span><span class="sxs-lookup"><span data-stu-id="c8c68-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="c8c68-156">В запрещенных словах нет ограничений на используемые знаки.</span><span class="sxs-lookup"><span data-stu-id="c8c68-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="c8c68-157">Существует ограничение в 5000 слов, которые можно установить как заблокированные слова.</span><span class="sxs-lookup"><span data-stu-id="c8c68-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="c8c68-158">Переопределение администраторами</span><span class="sxs-lookup"><span data-stu-id="c8c68-158">Admin override</span></span>

<span data-ttu-id="c8c68-159">Некоторые администраторы освобождаются от этих политик во всех групповых рабочих нагрузках и конечных точках, чтобы они могли создавать группы с этими заблокированными словами и с помощью желаемых соглашений именования.</span><span class="sxs-lookup"><span data-stu-id="c8c68-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="c8c68-160">Из политики именования групп исключаются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="c8c68-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="c8c68-161">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="c8c68-161">Global admin</span></span>

- <span data-ttu-id="c8c68-162">Поддержка партнеров уровня 1</span><span class="sxs-lookup"><span data-stu-id="c8c68-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="c8c68-163">Поддержка партнеров уровня 2</span><span class="sxs-lookup"><span data-stu-id="c8c68-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="c8c68-164">Администратор учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="c8c68-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="c8c68-165">Настройка политики имен</span><span class="sxs-lookup"><span data-stu-id="c8c68-165">How to set up the naming policy</span></span>

<span data-ttu-id="c8c68-166">Настройка политики именования:</span><span class="sxs-lookup"><span data-stu-id="c8c68-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="c8c68-167">В [Azure Active Directory](https://aad.portal.azure.com)в **статье Управление** щелкните **Группы**.</span><span class="sxs-lookup"><span data-stu-id="c8c68-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="c8c68-168">В **статье Параметры** щелкните **политику именования**.</span><span class="sxs-lookup"><span data-stu-id="c8c68-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="c8c68-169">Выберите **вкладку политики именования группы.**</span><span class="sxs-lookup"><span data-stu-id="c8c68-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="c8c68-170">В **соответствии с текущей** политикой выберите, требуется ли вам префикс или суффикс или оба, и выберите соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="c8c68-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="c8c68-171">Выберите атрибут **и** **строку** для каждой строки, а затем укажите атрибут или строку.</span><span class="sxs-lookup"><span data-stu-id="c8c68-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="c8c68-172">При добавлении необходимых префиксов и суффиксов нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c8c68-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Снимок экрана параметров политики именования групп в Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="c8c68-174">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="c8c68-174">Related topics</span></span>

[<span data-ttu-id="c8c68-175">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="c8c68-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="c8c68-176">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="c8c68-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="c8c68-177">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="c8c68-177">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/enterprise-users/groups-settings-cmdlets)