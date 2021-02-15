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
description: Описание подготовки пользователей к использованию Microsoft 365 с помощью синхронизации службы каталогов и долгосрочных преимуществ использования этого метода.
ms.openlocfilehash: e49cc4472b47320650d8a0ca90395b69ae5b6df7
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371628"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="085bf-103">Подготовка к синхронизации каталогов с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="085bf-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="085bf-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="085bf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="085bf-105">Преимущества гибридной синхронизации удостоверений и каталогов в организации:</span><span class="sxs-lookup"><span data-stu-id="085bf-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="085bf-106">Сокращение административных программ в организации</span><span class="sxs-lookup"><span data-stu-id="085bf-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="085bf-107">При желании включение сценария единого входов</span><span class="sxs-lookup"><span data-stu-id="085bf-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="085bf-108">Автоматизация изменений учетных записей в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="085bf-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="085bf-109">Дополнительные сведения о преимуществах синхронизации службы каталогов см. в гибридном удостоверении с [Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) и гибридном удостоверении [для Microsoft 365.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="085bf-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="085bf-110">Однако синхронизация службы каталогов требует планирования и подготовки, чтобы ваши доменные службы Active Directory (AD DS) синхронизировались с клиентом Azure AD подписки На Microsoft 365 с минимальным количеством ошибок.</span><span class="sxs-lookup"><span data-stu-id="085bf-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="085bf-111">Выполните следующие действия, чтобы получить наилучшие результаты.</span><span class="sxs-lookup"><span data-stu-id="085bf-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="085bf-112">1. Задачи очистки каталога</span><span class="sxs-lookup"><span data-stu-id="085bf-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="085bf-113">Перед синхронизацией AD DS с клиентом Azure AD необходимо очистить AD DS.</span><span class="sxs-lookup"><span data-stu-id="085bf-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="085bf-114">Если вы не выполните очистку AD DS перед синхронизацией, это может значительно отрицательно сказаться на процессе развертывания.</span><span class="sxs-lookup"><span data-stu-id="085bf-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="085bf-115">Цикл синхронизации каталогов, выявления ошибок и повторной синхронизации может занять несколько дней или даже недель.</span><span class="sxs-lookup"><span data-stu-id="085bf-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="085bf-116">В AD DS выполните следующие задачи очистки для каждой учетной записи пользователя, для которых будет назначена лицензия Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="085bf-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="085bf-117">Убедитесь, что в атрибуте **proxyAddresses** допустимый и уникальный адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="085bf-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="085bf-118">Удалите повторяющиеся значения в **атрибуте proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="085bf-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="085bf-119">По возможности убедитесь в допустимом и уникальном значении атрибута **userPrincipalName** в объекте **пользователя.**</span><span class="sxs-lookup"><span data-stu-id="085bf-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="085bf-120">Для лучшей синхронизации убедитесь, что upN AD DS соответствует upN Azure AD.</span><span class="sxs-lookup"><span data-stu-id="085bf-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="085bf-121">Если у пользователя нет значения атрибута **userPrincipalName,** объект пользователя должен содержать допустимое и уникальное значение атрибута **sAMAccountName.** </span><span class="sxs-lookup"><span data-stu-id="085bf-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="085bf-122">Удалите повторяющиеся значения в **атрибуте userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="085bf-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="085bf-123">Для оптимального использования глобального списка адресов (GAL) убедитесь в правильности сведений в следующих атрибутах учетной записи пользователя AD DS:</span><span class="sxs-lookup"><span data-stu-id="085bf-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="085bf-124">givenName;</span><span class="sxs-lookup"><span data-stu-id="085bf-124">givenName</span></span>
   - <span data-ttu-id="085bf-125">surname</span><span class="sxs-lookup"><span data-stu-id="085bf-125">surname</span></span>
   - <span data-ttu-id="085bf-126">displayName</span><span class="sxs-lookup"><span data-stu-id="085bf-126">displayName</span></span>
   - <span data-ttu-id="085bf-127">должность;</span><span class="sxs-lookup"><span data-stu-id="085bf-127">Job Title</span></span>
   - <span data-ttu-id="085bf-128">Отдел</span><span class="sxs-lookup"><span data-stu-id="085bf-128">Department</span></span>
   - <span data-ttu-id="085bf-129">Кабинет</span><span class="sxs-lookup"><span data-stu-id="085bf-129">Office</span></span>
   - <span data-ttu-id="085bf-130">рабочий телефон;</span><span class="sxs-lookup"><span data-stu-id="085bf-130">Office Phone</span></span>
   - <span data-ttu-id="085bf-131">мобильный телефон;</span><span class="sxs-lookup"><span data-stu-id="085bf-131">Mobile Phone</span></span>
   - <span data-ttu-id="085bf-132">номер факса;</span><span class="sxs-lookup"><span data-stu-id="085bf-132">Fax Number</span></span>
   - <span data-ttu-id="085bf-133">адрес;</span><span class="sxs-lookup"><span data-stu-id="085bf-133">Street Address</span></span>
   - <span data-ttu-id="085bf-134">Город</span><span class="sxs-lookup"><span data-stu-id="085bf-134">City</span></span>
   - <span data-ttu-id="085bf-135">регион или область;</span><span class="sxs-lookup"><span data-stu-id="085bf-135">State or Province</span></span>
   - <span data-ttu-id="085bf-136">почтовый индекс;</span><span class="sxs-lookup"><span data-stu-id="085bf-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="085bf-137">страна или регион.</span><span class="sxs-lookup"><span data-stu-id="085bf-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="085bf-138">2. Подготовка объекта каталога и атрибутов</span><span class="sxs-lookup"><span data-stu-id="085bf-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="085bf-139">Для успешной синхронизации службы каталогов между AD DS и Microsoft 365 необходимо правильно подготовить атрибуты AD DS.</span><span class="sxs-lookup"><span data-stu-id="085bf-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="085bf-140">Например, необходимо убедиться, что определенные символы не используются в определенных атрибутах, синхронизируются со средой Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085bf-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="085bf-141">Непредвиденные символы не приводят к сбойу синхронизации каталогов, но могут возвращать предупреждение.</span><span class="sxs-lookup"><span data-stu-id="085bf-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="085bf-142">Недопустимые символы приводят к сбойу синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="085bf-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="085bf-143">Синхронизация каталогов также не удастся, если у некоторых пользователей AD DS есть один или несколько дублирующихся атрибутов.</span><span class="sxs-lookup"><span data-stu-id="085bf-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="085bf-144">Каждый пользователь должен иметь уникальные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="085bf-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="085bf-145">Ниже перечислены атрибуты, которые необходимо подготовить.</span><span class="sxs-lookup"><span data-stu-id="085bf-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="085bf-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="085bf-146">**displayName**</span></span>

  - <span data-ttu-id="085bf-147">Если атрибут существует в объекте пользователя, он будет синхронизирован с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085bf-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="085bf-148">Если этот атрибут существует в объекте пользователя, для него должно быть значение.</span><span class="sxs-lookup"><span data-stu-id="085bf-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="085bf-149">То есть атрибут не должен быть пустым.</span><span class="sxs-lookup"><span data-stu-id="085bf-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="085bf-150">Максимальное число символов: 256</span><span class="sxs-lookup"><span data-stu-id="085bf-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="085bf-151">**givenName;**</span><span class="sxs-lookup"><span data-stu-id="085bf-151">**givenName**</span></span>

  - <span data-ttu-id="085bf-152">Если атрибут существует в объекте пользователя, он будет синхронизирован с Microsoft 365, но Microsoft 365 не требует или не использует его.</span><span class="sxs-lookup"><span data-stu-id="085bf-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="085bf-153">Максимальное число символов: 64</span><span class="sxs-lookup"><span data-stu-id="085bf-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="085bf-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="085bf-154">**mail**</span></span>

  - <span data-ttu-id="085bf-155">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="085bf-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="085bf-156">Если имеются повторяющиеся значения, синхронизируется первый пользователь со значением.</span><span class="sxs-lookup"><span data-stu-id="085bf-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="085bf-157">Последующие пользователи не будут отображаться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085bf-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="085bf-158">Необходимо изменить либо значение в Microsoft 365, либо оба значения в AD DS, чтобы оба пользователя появились в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085bf-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="085bf-159">**mailNickname** (псевдоним Exchange)</span><span class="sxs-lookup"><span data-stu-id="085bf-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="085bf-160">Значение атрибута не может начинаться с точка (.).</span><span class="sxs-lookup"><span data-stu-id="085bf-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="085bf-161">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="085bf-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="085bf-162">Символы подчеркиваия ("_") в синхронизированном имени указывают, что исходное значение этого атрибута содержит недопустимые символы.</span><span class="sxs-lookup"><span data-stu-id="085bf-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="085bf-163">Дополнительные сведения об этом атрибуте см. в [атрибуте псевдонима Exchange.](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="085bf-163">For more information on this attribute, see [Exchange alias attribute](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="085bf-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="085bf-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="085bf-165">Атрибут с несколькими значениями</span><span class="sxs-lookup"><span data-stu-id="085bf-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="085bf-166">Максимальное количество символов на значение: 256</span><span class="sxs-lookup"><span data-stu-id="085bf-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="085bf-167">Значение атрибута не должно содержать пробел.</span><span class="sxs-lookup"><span data-stu-id="085bf-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="085bf-168">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="085bf-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="085bf-169">Недопустимые символы: \< \> ( ) ; , [ ] " '</span><span class="sxs-lookup"><span data-stu-id="085bf-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="085bf-170">Обратите внимание, что недопустимые символы применяются к символам, следующим за типом "delimiter" и ":", таким образом, SMTP:User@contso.com разрешено, SMTP:user:M@contoso.com нет.</span><span class="sxs-lookup"><span data-stu-id="085bf-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="085bf-171">Все SMTP-адреса должны соответствовать стандартам обмена сообщениями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="085bf-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="085bf-172">Удалите дублирующиеся или нежелательные адреса, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="085bf-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="085bf-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="085bf-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="085bf-174">Максимальное число символов: 20</span><span class="sxs-lookup"><span data-stu-id="085bf-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="085bf-175">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="085bf-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="085bf-176">Недопустимые символы: [ \ " | , / : \< \> + = ; ?</span><span class="sxs-lookup"><span data-stu-id="085bf-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="085bf-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="085bf-177">\* ']</span></span>
  - <span data-ttu-id="085bf-178">Если у пользователя есть недопустимый **атрибут sAMAccountName,** но допустимый атрибут **userPrincipalName,** учетная запись пользователя создается в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085bf-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="085bf-179">Если **параметры sAMAccountName** и **userPrincipalName** недопустимы, необходимо обновить атрибут **userPrincipalName** AD DS.</span><span class="sxs-lookup"><span data-stu-id="085bf-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="085bf-180">**sn** (фамилия)</span><span class="sxs-lookup"><span data-stu-id="085bf-180">**sn** (surname)</span></span>

  - <span data-ttu-id="085bf-181">Если атрибут существует в объекте пользователя, он будет синхронизирован с Microsoft 365, но Microsoft 365 не требует или не использует его.</span><span class="sxs-lookup"><span data-stu-id="085bf-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="085bf-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="085bf-182">**targetAddress**</span></span>

    <span data-ttu-id="085bf-183">Необходимо, чтобы атрибут **targetAddress** (например, SMTP:tom@contoso.com), который был заполнен для пользователя, должен отображаться в gal Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085bf-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="085bf-184">В сценариях миграции сообщений сторонних пользователей для этого потребуется расширение схемы Microsoft 365 для AD DS.</span><span class="sxs-lookup"><span data-stu-id="085bf-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="085bf-185">Расширение схемы Microsoft 365 также добавит другие полезные атрибуты для управления объектами Microsoft 365, которые заполняются с помощью средства синхронизации каталогов из AD DS.</span><span class="sxs-lookup"><span data-stu-id="085bf-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="085bf-186">Например, добавляется атрибут **msExchHideFromAddressLists** для управления скрытыми почтовыми ящиками или группами рассылки.</span><span class="sxs-lookup"><span data-stu-id="085bf-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="085bf-187">Максимальное число символов: 256</span><span class="sxs-lookup"><span data-stu-id="085bf-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="085bf-188">Значение атрибута не должно содержать пробел.</span><span class="sxs-lookup"><span data-stu-id="085bf-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="085bf-189">Значение атрибута должно быть уникальным в каталоге.</span><span class="sxs-lookup"><span data-stu-id="085bf-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="085bf-190">Недопустимые символы: \ \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="085bf-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="085bf-191">Все SMTP-адреса должны соответствовать стандартам обмена сообщениями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="085bf-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="085bf-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="085bf-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="085bf-193">Атрибут **userPrincipalName** должен иметь формат для доступа в Интернет, в котором за именем пользователя следует знак @и доменное имя: например, user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="085bf-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="085bf-194">Все SMTP-адреса должны соответствовать стандартам обмена сообщениями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="085bf-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="085bf-195">Максимальное количество символов для **атрибута userPrincipalName** — 113.</span><span class="sxs-lookup"><span data-stu-id="085bf-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="085bf-196">До и после знака @разрешается определенное количество символов:</span><span class="sxs-lookup"><span data-stu-id="085bf-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="085bf-197">Максимальное количество символов для имени пользователя перед знаком @: 64</span><span class="sxs-lookup"><span data-stu-id="085bf-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="085bf-198">Максимальное количество символов для имени домена после знака @: 48</span><span class="sxs-lookup"><span data-stu-id="085bf-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="085bf-199">Недопустимые символы: \ % &amp; \* + / = ?</span><span class="sxs-lookup"><span data-stu-id="085bf-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="085bf-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="085bf-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="085bf-201">Разрешенные символы: A – Z, a - z, 0 – 9, ' .</span><span class="sxs-lookup"><span data-stu-id="085bf-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="085bf-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="085bf-202">- _ !</span></span> <span data-ttu-id="085bf-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="085bf-203"># ^ ~</span></span>
  - <span data-ttu-id="085bf-204">Буквы с диакритичными знаками, такими как umlauts, accents и tildes, являются недопустимыми символами.</span><span class="sxs-lookup"><span data-stu-id="085bf-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="085bf-205">Символ @требуется в каждом значении **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="085bf-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="085bf-206">Символ "@" не может быть первым символом в каждом значении **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="085bf-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="085bf-207">Имя пользователя не может быть оканчено точками (.), амперанд ( ), пробелом или знаком &amp; @.</span><span class="sxs-lookup"><span data-stu-id="085bf-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="085bf-208">Имя пользователя не может содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="085bf-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="085bf-209">Необходимо использовать домены с маршрутией; например, нельзя использовать локальные или внутренние домены.</span><span class="sxs-lookup"><span data-stu-id="085bf-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="085bf-210">Символы кодировки Юникод преобразуются в символы подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="085bf-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="085bf-211">**UserPrincipalName** не может содержать повторяющиеся значения в каталоге.</span><span class="sxs-lookup"><span data-stu-id="085bf-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="085bf-212">3. Подготовка атрибута userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="085bf-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="085bf-213">Active Directory позволяет конечным пользователям в организации войти в каталог с помощью **sAMAccountName** или **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="085bf-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="085bf-214">Аналогичным образом, конечные пользователи могут войти в Microsoft 365, используя имя участников-пользователей (UPN) своей работы или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="085bf-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="085bf-215">Синхронизация службы каталогов пытается создать новых пользователей в Azure Active Directory с помощью того же upN, что и в AD DS.</span><span class="sxs-lookup"><span data-stu-id="085bf-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="085bf-216">UpN форматирован как адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="085bf-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="085bf-217">В Microsoft 365 upN является атрибутом по умолчанию, используемым для создания адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="085bf-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="085bf-218">Легко получить **userPrincipalName** (в AD DS и в Azure AD) и основной адрес электронной почты в **proxyAddresses,** задав разные значения.</span><span class="sxs-lookup"><span data-stu-id="085bf-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="085bf-219">Если для них установлены разные значения, администраторы и конечные пользователи могут запутаться.</span><span class="sxs-lookup"><span data-stu-id="085bf-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="085bf-220">Лучше всего выровнять эти атрибуты, чтобы уменьшить путаницу.</span><span class="sxs-lookup"><span data-stu-id="085bf-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="085bf-221">Чтобы обеспечить соответствие требований единого вход с помощью служб федерации Active Directory (AD FS) 2.0, необходимо убедиться, что имена субъектов-пользователей в Azure Active Directory и доменных службах Active Directory совпадают и используют действительное пространство имен домена.</span><span class="sxs-lookup"><span data-stu-id="085bf-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="085bf-222">4. Добавление альтернативного суффикса upN в AD DS</span><span class="sxs-lookup"><span data-stu-id="085bf-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="085bf-223">Вам может потребоваться добавить альтернативный суффикс upN, чтобы связать корпоративные учетные данные пользователя со средой Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085bf-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="085bf-224">Суффикс UPN — это часть имени участника-пользователя, расположенная справа от символа @.</span><span class="sxs-lookup"><span data-stu-id="085bf-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="085bf-225">UPN-имена, которые используются для единого входа, могут содержать буквы, цифры, точки, дефисы и подчеркивания, другие символы запрещены.</span><span class="sxs-lookup"><span data-stu-id="085bf-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="085bf-226">Дополнительные сведения о добавлении альтернативного суффикса upN в Active Directory см. в подготовьтесь к синхронизации [службы каталогов.]( https://go.microsoft.com/fwlink/p/?LinkId=525430)</span><span class="sxs-lookup"><span data-stu-id="085bf-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="085bf-227">5. Соответствие upN AD DS с upN Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="085bf-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="085bf-228">Если вы уже настроили синхронизацию службы каталогов, имя пользователя для Microsoft 365 может не совпадать с ИД пользователя AD DS UPN, которое определено в AD DS.</span><span class="sxs-lookup"><span data-stu-id="085bf-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="085bf-229">Это может произойти, если пользователю была назначена лицензия до проверки домена.</span><span class="sxs-lookup"><span data-stu-id="085bf-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="085bf-230">Чтобы устранить эту проблему, исправьте дублирующееся имя пользователя-пользователя с помощью [PowerShell,](https://go.microsoft.com/fwlink/p/?LinkId=396730) чтобы убедиться, что имя пользователя Microsoft 365 соответствует корпоративному имени пользователя и домену.</span><span class="sxs-lookup"><span data-stu-id="085bf-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="085bf-231">Если вы обновляете имя пользователя в AD DS и хотите синхронизировать его с удостоверением Azure Active Directory, необходимо удалить лицензию пользователя в Microsoft 365 перед внесением изменений в AD DS.</span><span class="sxs-lookup"><span data-stu-id="085bf-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="085bf-232">См. также, как подготовить не маршрутизируемый домен [(например, локальный домен) для синхронизации каталогов.](prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="085bf-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="085bf-233">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="085bf-233">Next steps</span></span>

<span data-ttu-id="085bf-234">Если вы сделали шаги с 1 по 5 выше, см. ["Настройка синхронизации каталогов".](set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="085bf-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
