---
title: Подготовка к синхронизации каталогов с Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Описывает, как подготовить пользователей к Microsoft 365 с помощью синхронизации каталогов и долгосрочных преимуществ использования этого метода.
ms.openlocfilehash: ee6cfe9adfe029e620d2465f08a3fbe1e9290503
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229771"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="9307d-103">Подготовка к синхронизации каталогов с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9307d-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="9307d-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="9307d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9307d-105">Преимущества гибридной синхронизации удостоверений и каталогов в организации:</span><span class="sxs-lookup"><span data-stu-id="9307d-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="9307d-106">Сокращение административных программ в организации</span><span class="sxs-lookup"><span data-stu-id="9307d-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="9307d-107">Необязательный включение сценария с одним входом</span><span class="sxs-lookup"><span data-stu-id="9307d-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="9307d-108">Автоматизация изменений учетной записи в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9307d-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="9307d-109">Дополнительные сведения о преимуществах синхронизации каталогов см. в гибридных удостоверениях с [Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) и гибридной [идентификацией для Microsoft 365](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="9307d-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="9307d-110">Однако синхронизация каталогов требует планирования и подготовки, чтобы убедиться, что служба домена Active Directory (AD DS) синхронизируется с клиентом Azure AD вашей подписки Microsoft 365 с минимальным количеством ошибок.</span><span class="sxs-lookup"><span data-stu-id="9307d-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="9307d-111">Следуйте этим шагам, чтобы получить наилучшие результаты.</span><span class="sxs-lookup"><span data-stu-id="9307d-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="9307d-112">1. Задачи очистки каталогов</span><span class="sxs-lookup"><span data-stu-id="9307d-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="9307d-113">Прежде чем синхронизировать AD DS с клиентом Azure AD, необходимо очистить AD DS.</span><span class="sxs-lookup"><span data-stu-id="9307d-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9307d-114">Если вы не выполняете очистку AD DS перед синхронизацией, это может привести к значительному негативному влиянию на процесс развертывания.</span><span class="sxs-lookup"><span data-stu-id="9307d-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="9307d-115">Может потребоваться несколько дней или даже недель, чтобы пройти цикл синхронизации каталогов, выявления ошибок и повторной синхронизации.</span><span class="sxs-lookup"><span data-stu-id="9307d-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="9307d-116">В AD DS выполните следующие задачи очистки для каждой учетной записи пользователя, которая будет назначена Microsoft 365 лицензии:</span><span class="sxs-lookup"><span data-stu-id="9307d-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="9307d-117">Убедитесь, что допустимый и уникальный адрес электронной почты в **атрибуте proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="9307d-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="9307d-118">Удалите все дублирующиеся значения в **атрибуте proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="9307d-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="9307d-119">По возможности убедитесь в допустимом и уникальном значении **атрибута userPrincipalName** в объекте **пользователя.**</span><span class="sxs-lookup"><span data-stu-id="9307d-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="9307d-120">Для наилучшего синхронизации убедитесь, что upN AD DS соответствует upN Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9307d-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="9307d-121">Если у пользователя нет значения **атрибута userPrincipalName,** объект пользователя должен содержать допустимое и уникальное значение для **атрибута sAMAccountName.** </span><span class="sxs-lookup"><span data-stu-id="9307d-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="9307d-122">Удалите все дублирующиеся значения в **атрибуте userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="9307d-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="9307d-123">Для оптимального использования глобального списка адресов (GAL) убедитесь, что сведения в следующих атрибутах учетной записи пользователя AD DS верны:</span><span class="sxs-lookup"><span data-stu-id="9307d-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="9307d-124">givenName</span><span class="sxs-lookup"><span data-stu-id="9307d-124">givenName</span></span>
   - <span data-ttu-id="9307d-125">surname</span><span class="sxs-lookup"><span data-stu-id="9307d-125">surname</span></span>
   - <span data-ttu-id="9307d-126">displayName</span><span class="sxs-lookup"><span data-stu-id="9307d-126">displayName</span></span>
   - <span data-ttu-id="9307d-127">должность;</span><span class="sxs-lookup"><span data-stu-id="9307d-127">Job Title</span></span>
   - <span data-ttu-id="9307d-128">Отдел</span><span class="sxs-lookup"><span data-stu-id="9307d-128">Department</span></span>
   - <span data-ttu-id="9307d-129">Кабинет</span><span class="sxs-lookup"><span data-stu-id="9307d-129">Office</span></span>
   - <span data-ttu-id="9307d-130">рабочий телефон;</span><span class="sxs-lookup"><span data-stu-id="9307d-130">Office Phone</span></span>
   - <span data-ttu-id="9307d-131">мобильный телефон;</span><span class="sxs-lookup"><span data-stu-id="9307d-131">Mobile Phone</span></span>
   - <span data-ttu-id="9307d-132">номер факса;</span><span class="sxs-lookup"><span data-stu-id="9307d-132">Fax Number</span></span>
   - <span data-ttu-id="9307d-133">адрес;</span><span class="sxs-lookup"><span data-stu-id="9307d-133">Street Address</span></span>
   - <span data-ttu-id="9307d-134">Город</span><span class="sxs-lookup"><span data-stu-id="9307d-134">City</span></span>
   - <span data-ttu-id="9307d-135">регион или область;</span><span class="sxs-lookup"><span data-stu-id="9307d-135">State or Province</span></span>
   - <span data-ttu-id="9307d-136">почтовый индекс;</span><span class="sxs-lookup"><span data-stu-id="9307d-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="9307d-137">страна или регион.</span><span class="sxs-lookup"><span data-stu-id="9307d-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="9307d-138">2. Подготовка объекта и атрибута Directory</span><span class="sxs-lookup"><span data-stu-id="9307d-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="9307d-139">Успешная синхронизация каталогов между AD DS и Microsoft 365 требует правильной подготовки атрибутов AD DS.</span><span class="sxs-lookup"><span data-stu-id="9307d-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="9307d-140">Например, необходимо убедиться, что определенные символы не используются в определенных атрибутах, синхронизируются с Microsoft 365 средой.</span><span class="sxs-lookup"><span data-stu-id="9307d-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="9307d-141">Неожиданные символы не приводят к сбойу синхронизации каталогов, но могут возвращать предупреждение.</span><span class="sxs-lookup"><span data-stu-id="9307d-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="9307d-142">Недействительные символы приводят к сбойу синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="9307d-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="9307d-143">Синхронизация каталогов также не удалась, если некоторые пользователи AD DS имеют один или несколько атрибутов дубликатов.</span><span class="sxs-lookup"><span data-stu-id="9307d-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="9307d-144">Каждый пользователь должен иметь уникальные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="9307d-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="9307d-145">Атрибуты, которые необходимо подготовить, перечислены здесь:</span><span class="sxs-lookup"><span data-stu-id="9307d-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="9307d-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="9307d-146">**displayName**</span></span>

  - <span data-ttu-id="9307d-147">Если атрибут существует в объекте пользователя, он будет синхронизирован с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9307d-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="9307d-148">Если этот атрибут существует в объекте пользователя, для него должно быть значение.</span><span class="sxs-lookup"><span data-stu-id="9307d-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="9307d-149">То есть атрибут не должен быть пустым.</span><span class="sxs-lookup"><span data-stu-id="9307d-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="9307d-150">Максимальное число символов: 256</span><span class="sxs-lookup"><span data-stu-id="9307d-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="9307d-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="9307d-151">**givenName**</span></span>

  - <span data-ttu-id="9307d-152">Если атрибут существует в объекте пользователя, он будет синхронизирован с Microsoft 365, но Microsoft 365 не требует и не использует его.</span><span class="sxs-lookup"><span data-stu-id="9307d-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="9307d-153">Максимальное число символов: 64</span><span class="sxs-lookup"><span data-stu-id="9307d-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="9307d-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="9307d-154">**mail**</span></span>

  - <span data-ttu-id="9307d-155">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9307d-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9307d-156">Если имеются дублирующиеся значения, первый пользователь со значением синхронизируется.</span><span class="sxs-lookup"><span data-stu-id="9307d-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="9307d-157">Последующие пользователи не будут отображаться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9307d-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="9307d-158">Чтобы оба пользователя появились в Microsoft 365, необходимо изменить значение Microsoft 365 или изменить оба значения в AD DS.</span><span class="sxs-lookup"><span data-stu-id="9307d-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="9307d-159">**mailNickname** (Exchange псевдоним)</span><span class="sxs-lookup"><span data-stu-id="9307d-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="9307d-160">Значение атрибута не может начинаться с периода (.).</span><span class="sxs-lookup"><span data-stu-id="9307d-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="9307d-161">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9307d-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9307d-162">Подчеркивает ("_") в синхронизированном имени указывает, что исходное значение этого атрибута содержит недопустимые символы.</span><span class="sxs-lookup"><span data-stu-id="9307d-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="9307d-163">Дополнительные сведения об этом атрибуте [см. в Exchange атрибуте псевдонима](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9307d-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="9307d-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="9307d-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="9307d-165">Атрибут с несколькими значениями</span><span class="sxs-lookup"><span data-stu-id="9307d-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="9307d-166">Максимальное количество символов на значение: 256</span><span class="sxs-lookup"><span data-stu-id="9307d-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="9307d-167">Значение атрибута не должно содержать пробел.</span><span class="sxs-lookup"><span data-stu-id="9307d-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="9307d-168">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9307d-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="9307d-169">\< \>Недействительные символы: ( ) ; , [ ]</span><span class="sxs-lookup"><span data-stu-id="9307d-169">Invalid characters: \< \> ( ) ; , [ ] "</span></span>

    <span data-ttu-id="9307d-170">Обратите внимание, что недействительные символы применяются к символам, следующим типам delimiter и ":", таким образом, чтобы SMTP:User@contso.com разрешено, но SMTP:user:M@contoso.com нет.</span><span class="sxs-lookup"><span data-stu-id="9307d-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9307d-171">Все адреса Протокола транспорта простой почты (SMTP) должны соответствовать стандартам обмена сообщениями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9307d-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="9307d-172">Удалите дублирующие или нежелательные адреса, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="9307d-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="9307d-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="9307d-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="9307d-174">Максимальное число символов: 20</span><span class="sxs-lookup"><span data-stu-id="9307d-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="9307d-175">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9307d-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="9307d-176">Недействительные символы: [ \ " | , / : \< \> = = ;</span><span class="sxs-lookup"><span data-stu-id="9307d-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="9307d-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="9307d-177">\* ']</span></span>
  - <span data-ttu-id="9307d-178">Если пользователь имеет недействительный атрибут **sAMAccountName,** но имеет допустимый атрибут **userPrincipalName,** учетная запись пользователя создается в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9307d-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="9307d-179">Если **и sAMAccountName,** и **userPrincipalName** являются недействительными, необходимо обновить атрибут AD DS **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="9307d-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="9307d-180">**sn** (фамилия)</span><span class="sxs-lookup"><span data-stu-id="9307d-180">**sn** (surname)</span></span>

  - <span data-ttu-id="9307d-181">Если атрибут существует в объекте пользователя, он будет синхронизирован с Microsoft 365, но Microsoft 365 не требует и не использует его.</span><span class="sxs-lookup"><span data-stu-id="9307d-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="9307d-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="9307d-182">**targetAddress**</span></span>

    <span data-ttu-id="9307d-183">Необходимо, чтобы атрибут **targetAddress** (например, SMTP:tom@contoso.com), который был заполнен для пользователя, должен отображаться в Microsoft 365 GAL.</span><span class="sxs-lookup"><span data-stu-id="9307d-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="9307d-184">В сценариях миграции сторонних сообщений для этого потребуется Microsoft 365 расширения схемы для AD DS.</span><span class="sxs-lookup"><span data-stu-id="9307d-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="9307d-185">Расширение Microsoft 365 схемы также добавит другие полезные атрибуты для управления Microsoft 365 объектами, которые заполняются с помощью средства синхронизации каталогов из AD DS.</span><span class="sxs-lookup"><span data-stu-id="9307d-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="9307d-186">Например, будет добавлен **атрибут msExchHideFromAddressLists** для управления скрытыми почтовыми ящиками или группами рассылки.</span><span class="sxs-lookup"><span data-stu-id="9307d-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="9307d-187">Максимальное число символов: 256</span><span class="sxs-lookup"><span data-stu-id="9307d-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="9307d-188">Значение атрибута не должно содержать пробел.</span><span class="sxs-lookup"><span data-stu-id="9307d-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="9307d-189">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9307d-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="9307d-190">Недействительные символы: \ \< \> ( ) ; , [ ]</span><span class="sxs-lookup"><span data-stu-id="9307d-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="9307d-191">Все адреса Протокола транспорта простой почты (SMTP) должны соответствовать стандартам обмена сообщениями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9307d-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="9307d-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="9307d-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="9307d-193">Атрибут **userPrincipalName** должен быть в формате вход в Интернет, где за именем пользователя следует знак (@) и доменное имя: например, user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9307d-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="9307d-194">Все адреса Протокола транспорта простой почты (SMTP) должны соответствовать стандартам обмена сообщениями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9307d-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="9307d-195">Максимальное количество символов для **атрибута userPrincipalName** — 113.</span><span class="sxs-lookup"><span data-stu-id="9307d-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="9307d-196">До и после знака (@) разрешено определенное количество символов:</span><span class="sxs-lookup"><span data-stu-id="9307d-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="9307d-197">Максимальное количество символов для имени пользователя, которое находится перед знаком (@): 64</span><span class="sxs-lookup"><span data-stu-id="9307d-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="9307d-198">Максимальное количество символов для доменного имени после знака (@): 48</span><span class="sxs-lookup"><span data-stu-id="9307d-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="9307d-199">Недействительные символы: \ % &amp; \* + / = ?</span><span class="sxs-lookup"><span data-stu-id="9307d-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="9307d-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="9307d-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="9307d-201">Разрешены символы: A — Z, a - z, 0 — 9, ' .</span><span class="sxs-lookup"><span data-stu-id="9307d-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="9307d-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="9307d-202">- _ !</span></span> <span data-ttu-id="9307d-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="9307d-203"># ^ ~</span></span>
  - <span data-ttu-id="9307d-204">Буквы с диакритичными знаками, такими как umlauts, accents и tildes, являются недействительными символами.</span><span class="sxs-lookup"><span data-stu-id="9307d-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="9307d-205">Символ @требуется в каждом **значении userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="9307d-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="9307d-206">Символ "@" не может быть первым символом в каждом значении **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="9307d-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="9307d-207">Имя пользователя не может закончиться периодом (.), амперандом (), пробелом или знаком &amp; (@).</span><span class="sxs-lookup"><span data-stu-id="9307d-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="9307d-208">Имя пользователя не может содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="9307d-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="9307d-209">Необходимо использовать домены routable; например, нельзя использовать локальные или внутренние домены.</span><span class="sxs-lookup"><span data-stu-id="9307d-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="9307d-210">Символы кодировки Юникод преобразуются в символы подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="9307d-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="9307d-211">**UserPrincipalName не** может содержать какие-либо дублирующие значения в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9307d-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="9307d-212">3. Подготовка атрибута userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="9307d-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="9307d-213">Active Directory предназначен для того, чтобы позволить конечным пользователям вашей организации войти в каталог с помощью **sAMAccountName** или **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="9307d-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="9307d-214">Кроме того, конечные пользователи могут войти Microsoft 365 с помощью основного имени пользователя (UPN) своей работы или учетной записи школы.</span><span class="sxs-lookup"><span data-stu-id="9307d-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="9307d-215">Синхронизация каталогов пытается создать новых пользователей в Azure Active Directory с помощью того же upN, что и в вашей AD DS.</span><span class="sxs-lookup"><span data-stu-id="9307d-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="9307d-216">UpN форматирован как адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9307d-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="9307d-217">В Microsoft 365, upN — это атрибут по умолчанию, используемый для создания адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9307d-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="9307d-218">Легко получить **userPrincipalName** (в AD DS и Azure AD) и основной адрес электронной почты в **proxyAddresses,** задаваемом для различных значений.</span><span class="sxs-lookup"><span data-stu-id="9307d-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="9307d-219">Если они установлены для различных значений, администраторы и конечные пользователи могут быть не в себе.</span><span class="sxs-lookup"><span data-stu-id="9307d-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="9307d-220">Лучше всего согласовать эти атрибуты, чтобы уменьшить путаницу.</span><span class="sxs-lookup"><span data-stu-id="9307d-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="9307d-221">Чтобы соответствовать требованиям единого входного знака с службами Федерации Active Directory (AD FS) 2.0, необходимо убедиться, что upNs в Azure Active Directory и вашей AD DS совпадают и используют допустимую область имен домена.</span><span class="sxs-lookup"><span data-stu-id="9307d-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="9307d-222">4. Добавьте альтернативный суффикс upN в AD DS</span><span class="sxs-lookup"><span data-stu-id="9307d-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="9307d-223">Возможно, потребуется добавить альтернативный суффикс upN, чтобы связать корпоративные учетные данные пользователя с Microsoft 365 средой.</span><span class="sxs-lookup"><span data-stu-id="9307d-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="9307d-224">Суффикс UPN — это часть имени участника-пользователя, расположенная справа от символа @.</span><span class="sxs-lookup"><span data-stu-id="9307d-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="9307d-225">UPN-имена, которые используются для единого входа, могут содержать буквы, цифры, точки, дефисы и подчеркивания, другие символы запрещены.</span><span class="sxs-lookup"><span data-stu-id="9307d-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="9307d-226">Дополнительные сведения о добавлении альтернативного суффикса UPN в Active Directory см. в статью [Подготовка к синхронизации каталогов.](https://go.microsoft.com/fwlink/p/?LinkId=525430)</span><span class="sxs-lookup"><span data-stu-id="9307d-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="9307d-227">5. Соответствие upN AD DS с Microsoft 365 upN</span><span class="sxs-lookup"><span data-stu-id="9307d-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="9307d-228">Если вы уже настроили синхронизацию каталогов, upN пользователя для Microsoft 365 может не соответствовать AD DS upN пользователя, определенному в вашей AD DS.</span><span class="sxs-lookup"><span data-stu-id="9307d-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="9307d-229">Это может произойти, если пользователю была назначена лицензия до проверки домена.</span><span class="sxs-lookup"><span data-stu-id="9307d-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="9307d-230">Чтобы исправить это, используйте [PowerShell,](https://go.microsoft.com/fwlink/p/?LinkId=396730) чтобы исправить дубликат UPN для обновления upN пользователя, чтобы убедиться, что Microsoft 365 upN совпадает с корпоративным именем пользователя и доменом.</span><span class="sxs-lookup"><span data-stu-id="9307d-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="9307d-231">Если вы обновляете upN в AD DS и хотите, чтобы он синхронизировался с удостоверением Azure Active Directory, необходимо удалить лицензию пользователя в Microsoft 365 до внесения изменений в AD DS.</span><span class="sxs-lookup"><span data-stu-id="9307d-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="9307d-232">См. также, как подготовить домен без маршрутизации [(например, локальный домен) для синхронизации каталогов.](prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="9307d-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9307d-233">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="9307d-233">Next steps</span></span>

<span data-ttu-id="9307d-234">Если вы сделали шаги с 1 по 5 выше, см. в рублях [Настройка синхронизации каталогов.](set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="9307d-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
