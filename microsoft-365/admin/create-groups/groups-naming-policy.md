---
title: Политика именования групп Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Узнайте, как создать политику именования для групп Office 365.
ms.openlocfilehash: 11e2907462d325e4ad421914ae5a0deb5013e695
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352720"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="c9d1a-103">Политика именования групп Office 365</span><span class="sxs-lookup"><span data-stu-id="c9d1a-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="c9d1a-104">Политика именования групп используется для обеспечения согласованной стратегии именования для групп, создаваемых пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="c9d1a-105">Политика именования поможет вам и вашим пользователям определить функции группы, членства, географического региона или группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="c9d1a-106">С помощью политики именования можно также классифицировать группы в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="c9d1a-107">Вы можете использовать политику для блокирования использования определенных слов в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="c9d1a-108">Политика именования применяется к группам, созданным во всех рабочих нагрузках группы (например, Outlook, Microsoft Teams, SharePoint, Planner, Yammer и т. д.).</span><span class="sxs-lookup"><span data-stu-id="c9d1a-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span></span> <span data-ttu-id="c9d1a-109">Он применяется как к имени группы, так и к псевдониму группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="c9d1a-110">Он применяется, когда пользователь создает группу и при редактировании имени или псевдонима группы для существующей группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="c9d1a-111">Политика именования групп Office 365 применяется только к группам Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="c9d1a-112">Она не применяется к группам рассылки, созданным в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="c9d1a-113">Чтобы создать политику именования для групп рассылки, ознакомьтесь со статьей [Создание политики именования групп рассылки](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="c9d1a-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="c9d1a-114">Политика именования групп состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="c9d1a-115">**Политика именования префикса суффикса**: вы можете использовать префиксы или суффиксы, чтобы определить соглашение об именовании групп (например:\_"\_GRP US\_Group Engineering").</span><span class="sxs-lookup"><span data-stu-id="c9d1a-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering").</span></span> <span data-ttu-id="c9d1a-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="c9d1a-117">**Пользовательские заблокированные слова**: вы можете отправить набор заблокированных слов, относящихся к Организации, которые будут заблокированы в группах, созданных пользователями.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-117">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="c9d1a-118">(Например: "Генеральный директор, зарплата, HR").</span><span class="sxs-lookup"><span data-stu-id="c9d1a-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c9d1a-119">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="c9d1a-119">Licensing requirements</span></span>

<span data-ttu-id="c9d1a-120">Использование политики именования Azure AD для групп Office 365 требует, чтобы вы обладали лицензией на Azure Active Directory Premium P1 или Azure AD Basic EDU для каждого уникального пользователя (включая гостей), который является участником одной или нескольких групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="c9d1a-121">Это также необходимо для администратора, который создает политику именования групп.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="c9d1a-122">Политика именования префикса суффикса</span><span class="sxs-lookup"><span data-stu-id="c9d1a-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="c9d1a-123">Префиксы и суффиксы могут быть либо фиксированными строками, либо пользовательскими атрибутами.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="c9d1a-124">Фиксированные строки</span><span class="sxs-lookup"><span data-stu-id="c9d1a-124">Fixed strings</span></span>

<span data-ttu-id="c9d1a-125">Можно использовать короткие строки, которые помогут отличать группы в глобальном списке адресов и левой панели навигации по рабочим нагрузкам группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-125">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads.</span></span> <span data-ttu-id="c9d1a-126">Некоторые общие префиксы префиксов являются ключевыми словами, такими как\_' GRP name '\#, ' name '\_, ' name '.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-126">Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="c9d1a-127">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9d1a-127">Attributes</span></span>

<span data-ttu-id="c9d1a-128">Вы можете использовать атрибуты, которые помогут определить, кто создал эту группу (например, [Отдел], и где она была создана, например [Country]).</span><span class="sxs-lookup"><span data-stu-id="c9d1a-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9d1a-129">**Примеры**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-129">**Examples**</span></span>|<span data-ttu-id="c9d1a-130">Политика = "ГР [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="c9d1a-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="c9d1a-131">Отдел пользователя = Проектирование</span><span class="sxs-lookup"><span data-stu-id="c9d1a-131">User's department = Engineering</span></span>|
||<span data-ttu-id="c9d1a-132">Имя создаваемой группы = "ГР Моя группа Проектирование"</span><span class="sxs-lookup"><span data-stu-id="c9d1a-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="c9d1a-133">Поддерживаемые атрибуты Azure Active Directory (Azure AD): [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [title]</span><span class="sxs-lookup"><span data-stu-id="c9d1a-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="c9d1a-p108">Нераспознанные атрибуты считаются фиксированными строками. Пример: "[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="c9d1a-p108">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="c9d1a-137">Атрибуты расширения и настраиваемые атрибуты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="c9d1a-138">Рекомендуется использовать атрибуты, значения которых заданы для всех пользователей в организации, и не применять атрибуты с длинными значениями.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="c9d1a-139">Вопросы, которые нужно найти</span><span class="sxs-lookup"><span data-stu-id="c9d1a-139">Things to look out for</span></span>

- <span data-ttu-id="c9d1a-140">При создании политики общая длина строки префиксов и суффиксов ограничена 53 знаками.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="c9d1a-p109">Префиксы и суффиксы могут содержать специальные знаки, поддерживаемые в именах и псевдонимах групп. Если префикс или суффикс содержит специальные знаки, которые запрещено использовать в псевдонимах, то перед применением префикса или суффикса к псевдониму эти знаки удаляются. В этом случае префиксы и суффиксы, применяемые к имени группы, будут отличаться от применяемых к псевдониму.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-p109">Prefixes and suffixes can contain special characters supported in group name and group alias. When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias. So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="c9d1a-144">При использовании подключенных групп Yammer Office 365 следует избегать использования следующих символов в политике именования: \#@,, \[, \] \<, и. \></span><span class="sxs-lookup"><span data-stu-id="c9d1a-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="c9d1a-145">Если эти символы находятся в политике именования, обычные пользователи Yammer не смогут создавать группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="c9d1a-146">Пользовательские заблокированные слова</span><span class="sxs-lookup"><span data-stu-id="c9d1a-146">Custom blocked words</span></span>

<span data-ttu-id="c9d1a-147">Вы можете ввести разделенный запятыми список заблокированных слов, которые будут блокироваться в именах и псевдонимах групп.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="c9d1a-148">Проверка заблокированных слов выполняется для пользователя с введенным именем группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="c9d1a-149">Таким образом, если пользователь вводит "Дарнит",\_а "prefix" — это политика именования, произойдет ошибка "prefix\_Дарнит".</span><span class="sxs-lookup"><span data-stu-id="c9d1a-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="c9d1a-150">Поиск во вложенных строках не выполняется; в частности, для запуска сбоя требуется точное соответствие между введенным пользователем именем и пользовательскими заблокированными словами.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="c9d1a-151">Поиск в подстроке не выполняется, поэтому пользователи могут использовать некоторые распространенные слова, например "class", даже если "АСС" является заблокированным словом.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="c9d1a-152">**Вопросы, которые нужно найти**:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-152">**Things to look out for**:</span></span>

- <span data-ttu-id="c9d1a-153">При проверке запрещенных слов регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="c9d1a-154">Когда пользователь вводит запрещенное слово, в клиенте выводится сообщение об ошибке с указанием этого слова.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="c9d1a-155">В запрещенных словах нет ограничений на используемые знаки.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="c9d1a-156">Существует верхний предел 5000 слов, которые можно задать в качестве заблокированных слов.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="c9d1a-157">Переопределение администраторами</span><span class="sxs-lookup"><span data-stu-id="c9d1a-157">Admin override</span></span>

<span data-ttu-id="c9d1a-p113">Для некоторых администраторов эти политики не действуют, так что они могут создавать группы, используя запрещенные слова и собственные соглашения об именовании, в любых службах и конечных точках. Из политики именования групп исключаются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-p113">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="c9d1a-160">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="c9d1a-160">Global admin</span></span>

- <span data-ttu-id="c9d1a-161">Поддержка партнеров уровня 1</span><span class="sxs-lookup"><span data-stu-id="c9d1a-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="c9d1a-162">Поддержка партнеров уровня 2</span><span class="sxs-lookup"><span data-stu-id="c9d1a-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="c9d1a-163">Администратор учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="c9d1a-163">User account admin</span></span>

- <span data-ttu-id="c9d1a-164">Запись каталогов</span><span class="sxs-lookup"><span data-stu-id="c9d1a-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="c9d1a-165">Настройка политики именования</span><span class="sxs-lookup"><span data-stu-id="c9d1a-165">How to set up the naming policy</span></span>

<span data-ttu-id="c9d1a-166">Настройка политики именования:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="c9d1a-167">В разделе **Управление** [Azure Active Directory](https://aad.portal.azure.com)щелкните **группы**.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="c9d1a-168">В разделе **Параметры**выберите пункт **Политика именования**.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="c9d1a-169">Выберите вкладку **Политика именования групп** .</span><span class="sxs-lookup"><span data-stu-id="c9d1a-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="c9d1a-170">В разделе **Текущая политика**выберите необходимость использования префикса или суффикса или обеих этих флажков, а также установите соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="c9d1a-171">Выберите между **атрибутом** и **строкой** для каждой строки, а затем укажите атрибут или строку.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="c9d1a-172">Добавив необходимые префиксы и суффиксы, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Снимок экрана параметров политики именования групп в Azure Active Directory](../../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="c9d1a-174">Политика именования в приложениях Office 365</span><span class="sxs-lookup"><span data-stu-id="c9d1a-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="c9d1a-p114">Когда пользователь вводит имя и псевдоним группы, в приложениях Office 365 теперь приводится образец имени группы с учетом политики именования (с префиксами и суффиксами). Если пользователь вводит запрещенные слова, появляется сообщение об ошибке, после чего эти слова можно удалить.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-p114">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias. When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="c9d1a-177">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="c9d1a-177">Outlook on the web</span></span>

<span data-ttu-id="c9d1a-178">В Outlook в Интернете (ранее известном как Outlook Web App или OWA) отображается декорированное имя политики именования, когда пользователь вводит имя группы или псевдоним группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-178">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias.</span></span> <span data-ttu-id="c9d1a-179">Когда пользователь вводит пользовательское заблокированное слово, сообщение об ошибке отображается в пользовательском интерфейсе вместе с заблокированным словом, чтобы пользователь мог удалить его.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-179">When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it.</span></span> <span data-ttu-id="c9d1a-180">Моментальные снимки взаимодействия Outlook в Интернете показаны ниже.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-180">Outlook on the web experience snapshots are shown below.</span></span>

![Параллельное представление политики именования групп в Office 365 Groups](../../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="c9d1a-182">Классическое приложение Outlook</span><span class="sxs-lookup"><span data-stu-id="c9d1a-182">Outlook Desktop</span></span>

<span data-ttu-id="c9d1a-183">Группы, создаваемые в классической версии Outlook, согласуются с политикой именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-184">В этой версии пока не приводится образец политики именования и не выводятся сообщения о наличии настраиваемых запрещенных слов, когда пользователь вводит имя группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="c9d1a-185">Однако политика именования будет автоматически применена при выборе команды "создать/изменить", и пользователи будут отображаться с ошибками, если в имени или псевдониме группы есть нестандартные заблокированные слова.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="c9d1a-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9d1a-186">Microsoft Teams</span></span>

<span data-ttu-id="c9d1a-187">Microsoft Teams показывает декорированное имя политики именования, когда пользователь вводит имя группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-187">Microsoft Teams shows the naming policy decorated name when the user types a team name.</span></span> <span data-ttu-id="c9d1a-188">Когда пользователь вводит пользовательское заблокированное слово, вместе с заблокированным словом отображается сообщение об ошибке, чтобы пользователь мог удалить его.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-188">When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Пример политики именования групп в Microsoft Teams заблокирован](../../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="c9d1a-190">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9d1a-190">SharePoint</span></span>

<span data-ttu-id="c9d1a-191">В SharePoint отображается имя политики именования, когда пользователь вводит имя сайта или адрес электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="c9d1a-192">Когда пользователь вводит пользовательское заблокированное слово, отображается сообщение об ошибке вместе с заблокированным словом, чтобы пользователь мог удалить его.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![Политика именования групп — имя заблокированного сайта SharePoint](../../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="c9d1a-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="c9d1a-194">Microsoft Stream</span></span>

<span data-ttu-id="c9d1a-p119">Когда пользователь вводит имя или псевдоним электронной почты группы в Microsoft Stream, отображается декорированное имя согласно политике именования. Если пользователь вводит запрещенное слово, выводится сообщение об ошибке. В нем указывается запрещенное слово, чтобы пользователь мог удалить его.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-p119">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias. When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Пример заблокированной политики именования групп для Microsoft Stream](../../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="c9d1a-198">Приложение Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="c9d1a-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="c9d1a-199">Группы, создаваемые в приложениях Outlook, согласуются с политикой именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-200">В Outlook Mobile отображается предварительный просмотр политики именования при вводе имени группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="c9d1a-201">Когда пользователь вводит пользовательское заблокированное слово, при создании группы отображается сообщение об ошибке, поэтому пользователь может удалить заблокированное слово.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="c9d1a-202">Планировщик</span><span class="sxs-lookup"><span data-stu-id="c9d1a-202">Planner</span></span>

<span data-ttu-id="c9d1a-203">Политика именования действует в Планировщике.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-204">Планировщик Отображает предварительный просмотр политики именования при вводе имени плана.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="c9d1a-205">Когда пользователь вводит пользовательское заблокированное слово, при создании плана отображается сообщение об ошибке, поэтому пользователь может удалить заблокированное слово.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![Политика именования групп: создание нового плана заблокированный пример](../../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="c9d1a-207">Dynamics 365 для участия клиентов</span><span class="sxs-lookup"><span data-stu-id="c9d1a-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="c9d1a-208">Dynamics 365 для участия клиентов соответствует политике именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-209">В Dynamics 365 отображается декорированное имя политики именования, когда пользователь вводит имя группы или псевдоним электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="c9d1a-210">Когда пользователь вводит пользовательское заблокированное слово, отображается сообщение об ошибке с заблокированным словом, чтобы пользователь мог удалить его.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamics 365](../../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="c9d1a-212">School Data Sync (SDS)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="c9d1a-p123">Группы, создаваемые в SDS, должны соответствовать политике именования, однако она не применяется автоматически. Администраторам SDS необходимо добавить префиксы и суффиксы к названиям занятий, для которых требуется создать группы, а затем отправить их в SDS. В противном случае создать или изменить группу не удастся.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-p123">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically. SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS. Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="c9d1a-216">Диспетчер клиентов Outlook (ОКМ)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="c9d1a-217">Диспетчер клиентов Outlook соответствует политике именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-218">Политика именования автоматически применяется к группе, созданной в диспетчере клиентов Outlook.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="c9d1a-219">Если какое-либо слово из слова "вся группа продаж" определено как пользовательское заблокированное слово, создание группы в ОКМ будет заблокировано.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="c9d1a-220">Пользователь не сможет создать группу ОКМ и будет блокировать использование приложения ОКМ. "</span><span class="sxs-lookup"><span data-stu-id="c9d1a-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="c9d1a-221">Приложение Classroom</span><span class="sxs-lookup"><span data-stu-id="c9d1a-221">Classroom App</span></span>

<span data-ttu-id="c9d1a-p125">Группы, создаваемые в приложении Classroom, должны соответствовать политике именования, однако она не применяется автоматически. Когда пользователь вводит имя группы аудиторий, образец политики именования не отображается. Поэтому пользователю необходимо ввести декорированное имя группы аудиторий с префиксами и суффиксами. В противном случае создание или изменение группы аудиторий завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-p125">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name. So users would have to enter the decorated classroom group name with prefixes and suffixes. Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="c9d1a-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="c9d1a-225">Power BI</span></span>

<span data-ttu-id="c9d1a-226">Группы, созданные в рабочих областях Power BI, соответствуют политике именования, но политика именования не применяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="c9d1a-227">Кроме того, при вводе имени рабочей области Power BI Просмотр политики именования не отображается для пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="c9d1a-228">Рекомендуемое имя с примененной политикой именования показано в разделе сведения об ошибке при создании или изменении рабочих областей.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="c9d1a-229">Это означает, что пользователям необходимо ввести декорированное имя рабочей области с префиксами и суффиксами.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="c9d1a-230">В противном случае создание или редактирование рабочей области завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="c9d1a-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="c9d1a-231">Yammer</span></span>

<span data-ttu-id="c9d1a-232">Когда пользователь, вошедшего в Yammer с помощью своей учетной записи Azure Active Directory, создает группу или редактирует имя группы, имя группы будет соответствовать политике именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="c9d1a-233">Это применимо как к подключенным группам Office 365, так и ко всем остальным группам Yammer.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="c9d1a-234">Если группа, подключенная к Office 365, была создана до того, как будет создана политика именования, имя группы не будет автоматически соответствовать политикам именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="c9d1a-235">Когда пользователь редактирует имя группы, ему будет предложено добавить префикс и суффикс.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="c9d1a-236">Если политика именования содержит символы, которые не могут находиться в именах групп Yammer, только администраторы смогут создать подключенную группу в Yammer.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="c9d1a-237">StaffHub</span><span class="sxs-lookup"><span data-stu-id="c9d1a-237">StaffHub</span></span>

<span data-ttu-id="c9d1a-238">StaffHub Teams не следуют политике именования, но базовая группа Office 365 — это.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="c9d1a-239">К имени группы StaffHub не добавляются префиксы и суффиксы, и в них не проверяется наличие настраиваемых запрещенных слов.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="c9d1a-240">Однако StaffHub применяет префиксы и суффиксы и удаляет заблокированные слова из базовой группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="c9d1a-241">Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9d1a-241">Exchange PowerShell</span></span>

<span data-ttu-id="c9d1a-p131">В командлетах Exchange PowerShell политика именования соблюдается. Если соглашение об именовании нарушается в именах и псевдонимах групп, пользователи будут получать сообщения об ошибках с указанием требуемых префиксов и суффиксов, а также обнаруженных запрещенных слов.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-p131">Exchange PowerShell cmdlets are compliant with naming policy. Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="c9d1a-244">Командлеты PowerShell Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c9d1a-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="c9d1a-245">Командлеты Azure Active Directory PowerShell совместимы с политикой именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-246">Если соглашение об именовании нарушается в именах и псевдонимах групп, пользователи будут получать сообщения об ошибках с указанием требуемых префиксов и суффиксов, а также обнаруженных запрещенных слов.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="c9d1a-247">Центр администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="c9d1a-247">Exchange admin center</span></span>

<span data-ttu-id="c9d1a-248">Центр администрирования Exchange соответствует политике именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-249">Если соглашение об именовании нарушается в именах и псевдонимах групп, при создании или изменении групп пользователи будут получать сообщения об ошибках с указанием требуемых префиксов и суффиксов, а также обнаруженных запрещенных слов.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="c9d1a-250">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9d1a-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="c9d1a-251">Центр администрирования Microsoft 365 соответствует политике именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-252">Она автоматически применяется при создании или изменении групп.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="c9d1a-253">При вводе настраиваемых запрещенных слов пользователи получают сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="c9d1a-254">Центр администрирования Microsoft 365 еще не отображает Предварительный просмотр политики именования и не возвращает пользовательские ошибки блокированных слов, когда пользователь вводит имя группы.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="c9d1a-255">Портал Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c9d1a-255">Azure Active Directory portal</span></span>

<span data-ttu-id="c9d1a-256">Портал Azure Active Directory соответствует политике именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="c9d1a-257">На портале Azure Active Directory при вводе имени группы отображается предварительный просмотр политики именования.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="c9d1a-258">Когда пользователь вводит пользовательское заблокированное слово, при создании группы отображается сообщение об ошибке, поэтому пользователь может удалить заблокированное слово.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="c9d1a-259">Дополнительные статьи о политике именования</span><span class="sxs-lookup"><span data-stu-id="c9d1a-259">More articles on naming policy</span></span>

[<span data-ttu-id="c9d1a-260">Принудительная политика именования для групп Office 365 в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c9d1a-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="c9d1a-261">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="c9d1a-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
