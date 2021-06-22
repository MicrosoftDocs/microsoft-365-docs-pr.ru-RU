---
title: Политики карантина
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Администраторы могут узнать, как использовать политики карантина для управления тем, что пользователи могут делать с их карантинными сообщениями.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055213"
---
# <a name="quarantine-policies"></a><span data-ttu-id="88d73-103">Политики карантина</span><span class="sxs-lookup"><span data-stu-id="88d73-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="88d73-104">Функции, описанные в этой статье, в настоящее время находятся в предварительном просмотре, недоступны для всех и могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="88d73-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="88d73-105">Политики карантина (ранее известные как теги карантина) в Exchange Online Protection (EOP) позволяют администраторам управлять тем, что пользователи могут сделать с их карантинными сообщениями на основе того, как сообщение поступило в карантин.</span><span class="sxs-lookup"><span data-stu-id="88d73-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="88d73-106">EOP традиционно разрешает или предотвращает определенные уровни интерактивности [](find-and-release-quarantined-messages-as-a-user.md) для сообщений в карантине и в уведомлениях о нежелательной почте конечного [пользователя.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="88d73-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="88d73-107">Например, пользователи могут просматривать и выпускать сообщения, которые были карантинными с помощью фильтрации от нежелательной почты, как спам или массовые, но они не могут просматривать или выпускать сообщения, которые были на карантине, как высокой уверенности в фишинге (только администраторы могут это сделать).</span><span class="sxs-lookup"><span data-stu-id="88d73-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="88d73-108">Для [](#step-2-assign-a-quarantine-policy-to-supported-features)поддерживаемых функций защиты политики карантина указывают, что пользователям разрешено делать в сообщениях уведомлений о нежелательной почте конечных пользователей и в карантинных сообщениях в карантине (сообщения, в которых пользователь является получателем).</span><span class="sxs-lookup"><span data-stu-id="88d73-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="88d73-109">Политики карантина по умолчанию автоматически назначены для обеспечения выполнения исторических возможностей пользователей в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="88d73-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="88d73-110">Или можно создать и назначить настраиваемые политики карантина, чтобы разрешить или запретить конечным пользователям выполнять конкретные действия в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="88d73-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="88d73-111">Отдельные разрешения объединяются в следующие группы предварительного разрешения:</span><span class="sxs-lookup"><span data-stu-id="88d73-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="88d73-112">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="88d73-112">No access</span></span>
- <span data-ttu-id="88d73-113">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="88d73-113">Limited access</span></span>
- <span data-ttu-id="88d73-114">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="88d73-114">Full access</span></span>

<span data-ttu-id="88d73-115">Доступные отдельные разрешения и то, что включено или не включено в предустановленные группы разрешений, описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="88d73-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="88d73-116">Разрешение</span><span class="sxs-lookup"><span data-stu-id="88d73-116">Permission</span></span>|<span data-ttu-id="88d73-117">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="88d73-117">No access</span></span>|<span data-ttu-id="88d73-118">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="88d73-118">Limited access</span></span>|<span data-ttu-id="88d73-119">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="88d73-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="88d73-120">**Разрешить отправитель** _(PermissionToAllowSender)_</span><span class="sxs-lookup"><span data-stu-id="88d73-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="88d73-122">**Отправитель блока** _(PermissionToBlockSender)_</span><span class="sxs-lookup"><span data-stu-id="88d73-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="88d73-125">**Удаление** _(PermissionToDelete)_</span><span class="sxs-lookup"><span data-stu-id="88d73-125">**Delete** (_PermissionToDelete_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="88d73-128">**Предварительный** просмотр _(PermissionToPreview)_</span><span class="sxs-lookup"><span data-stu-id="88d73-128">**Preview** (_PermissionToPreview_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="88d73-131">**Разрешить получателям освободить сообщение из карантина** _(PermissionToRelease)_</span><span class="sxs-lookup"><span data-stu-id="88d73-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="88d73-133">**Разрешить получателям запрашивать сообщение, которое будет выпущено из** карантина _(PermissionToRequestRelease)_</span><span class="sxs-lookup"><span data-stu-id="88d73-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Флажок](../../media/checkmark.png)||
|

<span data-ttu-id="88d73-135">Если вам не нравятся разрешения по умолчанию в предустановленных группах разрешений, можно использовать настраиваемые разрешения при создании или изменении настраиваемой политики карантина.</span><span class="sxs-lookup"><span data-stu-id="88d73-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="88d73-136">Дополнительные сведения о том, что делает каждое разрешение, см. в разделе [Сведения](#quarantine-policy-permission-details) о разрешении политики карантина в этой статье.</span><span class="sxs-lookup"><span data-stu-id="88d73-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="88d73-137">Вы создаете и назначаете политики карантина на портале Microsoft 365 Defender или в PowerShell (Exchange Online PowerShell для Microsoft 365 организаций с Exchange Online почтовыми ящиками; автономных EOP PowerShell в организациях EOP без Exchange Online почтовых ящиков).</span><span class="sxs-lookup"><span data-stu-id="88d73-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="88d73-138">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="88d73-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="88d73-139">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="88d73-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="88d73-140">Или перейдите непосредственно **на** страницу политики карантина, откройте <https://security.microsoft.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="88d73-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="88d73-141">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="88d73-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="88d73-142">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="88d73-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="88d73-143">Чтобы просмотреть, создать, изменить или удалить политики карантина, необходимо  быть  членом ролей администратора организации или администратора безопасности на Microsoft 365 Defender портале.</span><span class="sxs-lookup"><span data-stu-id="88d73-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="88d73-144">Дополнительные сведения см. в статье [Разрешения на портале Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="88d73-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="88d73-145">Шаг 1. Создание политик карантина на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="88d73-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="88d73-146">На портале Microsoft 365 Defender перейдите в раздел Правила политики **&** угрозы совместной работы, а затем выберите политики \>  \>  \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="88d73-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="88d73-147">На странице **Политики карантина** нажмите кнопку ![ Добавить значок настраиваемой политики Добавить ](../../media/m365-cc-sc-create-icon.png) **настраиваемую политику.**</span><span class="sxs-lookup"><span data-stu-id="88d73-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="88d73-148">Откроется **мастер** новой политики.</span><span class="sxs-lookup"><span data-stu-id="88d73-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="88d73-149">На странице **Имя политики** введите краткое, но уникальное имя в поле **Имя** политики.</span><span class="sxs-lookup"><span data-stu-id="88d73-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="88d73-150">В предстоящих действиях необходимо определить и выбрать политику карантина по имени.</span><span class="sxs-lookup"><span data-stu-id="88d73-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="88d73-151">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="88d73-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="88d73-152">На странице **доступа к сообщению получателя** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="88d73-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="88d73-153">**Нет доступа**</span><span class="sxs-lookup"><span data-stu-id="88d73-153">**No access**</span></span>
   - <span data-ttu-id="88d73-154">**Ограниченный доступ**</span><span class="sxs-lookup"><span data-stu-id="88d73-154">**Limited access**</span></span>
   - <span data-ttu-id="88d73-155">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="88d73-155">**Full access**</span></span>

   <span data-ttu-id="88d73-156">Отдельные разрешения, включенные в эти группы разрешений, описаны ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="88d73-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="88d73-157">Чтобы указать настраиваемые разрешения, выберите Задать определенный **доступ (Расширенный)** и настроить следующие параметры, которые отображаются:</span><span class="sxs-lookup"><span data-stu-id="88d73-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="88d73-158">**Выберите предпочтение действий выпуска:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="88d73-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="88d73-159">**Действие выпуска:** это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88d73-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="88d73-160">**Разрешить получателям освободить сообщение из карантина**</span><span class="sxs-lookup"><span data-stu-id="88d73-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="88d73-161">**Разрешить получателям запрашивать сообщение, которое будет выпущено из карантина**</span><span class="sxs-lookup"><span data-stu-id="88d73-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="88d73-162">**Выберите дополнительные действия, которые** получатели могут принимать на карантин сообщения: Выберите некоторые, все или ни одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="88d73-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="88d73-163">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="88d73-163">**Delete**</span></span>
       - <span data-ttu-id="88d73-164">**Предварительная версия**</span><span class="sxs-lookup"><span data-stu-id="88d73-164">**Preview**</span></span>
       - <span data-ttu-id="88d73-165">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="88d73-165">**Block sender**</span></span>

   <span data-ttu-id="88d73-166">Эти разрешения и их влияние на карантинные сообщения и уведомления о нежелательной почте конечных пользователей описаны в разделе Сведения о разрешении политики карантина в этой статье. [](#quarantine-policy-permission-details)</span><span class="sxs-lookup"><span data-stu-id="88d73-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="88d73-167">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="88d73-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="88d73-168">На странице **Политика обзора,** которая отображается, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="88d73-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="88d73-169">Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="88d73-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="88d73-170">Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.</span><span class="sxs-lookup"><span data-stu-id="88d73-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="88d73-171">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="88d73-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="88d73-172">На странице подтверждения, которая откроется, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="88d73-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="88d73-173">Теперь вы готовы назначить политику карантина функции карантина, как описано в разделе [Шаг 2.](#step-2-assign-a-quarantine-policy-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="88d73-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="88d73-174">Создание политик карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="88d73-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="88d73-175">Если вы хотите использовать PowerShell для создания политик карантина, подключись к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте комлет **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="88d73-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="88d73-176">У вас есть два различных метода на выбор:</span><span class="sxs-lookup"><span data-stu-id="88d73-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="88d73-177">Используйте параметр _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="88d73-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="88d73-178">Используйте параметр _EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="88d73-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="88d73-179">Эти методы описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="88d73-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="88d73-180">Используйте параметр EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="88d73-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="88d73-181">Чтобы создать политику карантина с помощью _параметра EndUserQuarantinePermissionsValue,_ используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="88d73-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="88d73-182">Параметр _EndUserQuarantinePermissionsValue_ использует десятичное значение, преобразованное из двоичного значения.</span><span class="sxs-lookup"><span data-stu-id="88d73-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="88d73-183">Двоичное значение соответствует доступным разрешениям карантина для конечных пользователей в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="88d73-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="88d73-184">Для каждого разрешения значение 1 равно True, а значение 0 - false.</span><span class="sxs-lookup"><span data-stu-id="88d73-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="88d73-185">Необходимый порядок и значения для каждого отдельного разрешения в предустановленных группах разрешений описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="88d73-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="88d73-186">Разрешение</span><span class="sxs-lookup"><span data-stu-id="88d73-186">Permission</span></span>|<span data-ttu-id="88d73-187">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="88d73-187">No access</span></span>|<span data-ttu-id="88d73-188">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="88d73-188">Limited access</span></span>|<span data-ttu-id="88d73-189">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="88d73-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="88d73-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="88d73-190">PermissionToAllowSender</span></span>|<span data-ttu-id="88d73-191">0</span><span class="sxs-lookup"><span data-stu-id="88d73-191">0</span></span>|<span data-ttu-id="88d73-192">0</span><span class="sxs-lookup"><span data-stu-id="88d73-192">0</span></span>|<span data-ttu-id="88d73-193">1</span><span class="sxs-lookup"><span data-stu-id="88d73-193">1</span></span>|
|<span data-ttu-id="88d73-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="88d73-194">PermissionToBlockSender</span></span>|<span data-ttu-id="88d73-195">0</span><span class="sxs-lookup"><span data-stu-id="88d73-195">0</span></span>|<span data-ttu-id="88d73-196">1</span><span class="sxs-lookup"><span data-stu-id="88d73-196">1</span></span>|<span data-ttu-id="88d73-197">1</span><span class="sxs-lookup"><span data-stu-id="88d73-197">1</span></span>|
|<span data-ttu-id="88d73-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="88d73-198">PermissionToDelete</span></span>|<span data-ttu-id="88d73-199">0</span><span class="sxs-lookup"><span data-stu-id="88d73-199">0</span></span>|<span data-ttu-id="88d73-200">1</span><span class="sxs-lookup"><span data-stu-id="88d73-200">1</span></span>|<span data-ttu-id="88d73-201">1</span><span class="sxs-lookup"><span data-stu-id="88d73-201">1</span></span>|
|<span data-ttu-id="88d73-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88d73-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="88d73-203">0</span><span class="sxs-lookup"><span data-stu-id="88d73-203">0</span></span>|<span data-ttu-id="88d73-204">0</span><span class="sxs-lookup"><span data-stu-id="88d73-204">0</span></span>|<span data-ttu-id="88d73-205">0</span><span class="sxs-lookup"><span data-stu-id="88d73-205">0</span></span>|
|<span data-ttu-id="88d73-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="88d73-206">PermissionToPreview</span></span>|<span data-ttu-id="88d73-207">0</span><span class="sxs-lookup"><span data-stu-id="88d73-207">0</span></span>|<span data-ttu-id="88d73-208">1</span><span class="sxs-lookup"><span data-stu-id="88d73-208">1</span></span>|<span data-ttu-id="88d73-209">1</span><span class="sxs-lookup"><span data-stu-id="88d73-209">1</span></span>|
|<span data-ttu-id="88d73-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="88d73-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="88d73-211">0</span><span class="sxs-lookup"><span data-stu-id="88d73-211">0</span></span>|<span data-ttu-id="88d73-212">0</span><span class="sxs-lookup"><span data-stu-id="88d73-212">0</span></span>|<span data-ttu-id="88d73-213">1</span><span class="sxs-lookup"><span data-stu-id="88d73-213">1</span></span>|
|<span data-ttu-id="88d73-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="88d73-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="88d73-215">0</span><span class="sxs-lookup"><span data-stu-id="88d73-215">0</span></span>|<span data-ttu-id="88d73-216">1</span><span class="sxs-lookup"><span data-stu-id="88d73-216">1</span></span>|<span data-ttu-id="88d73-217">0</span><span class="sxs-lookup"><span data-stu-id="88d73-217">0</span></span>|
|<span data-ttu-id="88d73-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88d73-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="88d73-219">0</span><span class="sxs-lookup"><span data-stu-id="88d73-219">0</span></span>|<span data-ttu-id="88d73-220">0</span><span class="sxs-lookup"><span data-stu-id="88d73-220">0</span></span>|<span data-ttu-id="88d73-221">0</span><span class="sxs-lookup"><span data-stu-id="88d73-221">0</span></span>|
|<span data-ttu-id="88d73-222">Двоичное значение</span><span class="sxs-lookup"><span data-stu-id="88d73-222">Binary value</span></span>|<span data-ttu-id="88d73-223">00000000</span><span class="sxs-lookup"><span data-stu-id="88d73-223">00000000</span></span>|<span data-ttu-id="88d73-224">01101010</span><span class="sxs-lookup"><span data-stu-id="88d73-224">01101010</span></span>|<span data-ttu-id="88d73-225">11101100</span><span class="sxs-lookup"><span data-stu-id="88d73-225">11101100</span></span>|
|<span data-ttu-id="88d73-226">Десятичная значения для использования</span><span class="sxs-lookup"><span data-stu-id="88d73-226">Decimal value to use</span></span>|<span data-ttu-id="88d73-227">0</span><span class="sxs-lookup"><span data-stu-id="88d73-227">0</span></span>|<span data-ttu-id="88d73-228">106</span><span class="sxs-lookup"><span data-stu-id="88d73-228">106</span></span>|<span data-ttu-id="88d73-229">236</span><span class="sxs-lookup"><span data-stu-id="88d73-229">236</span></span>|
|

<span data-ttu-id="88d73-230"><sup>\*</sup> В настоящее время это значение всегда 0.</span><span class="sxs-lookup"><span data-stu-id="88d73-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="88d73-231">Для PermissionToViewHeader значение 0 не скрывает кнопку Заголовок сообщения **View** в подробностях карантиного сообщения (кнопка всегда доступна).</span><span class="sxs-lookup"><span data-stu-id="88d73-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="88d73-232"><sup>\*\*</sup> Не устанавливайте оба этих значения до 1.</span><span class="sxs-lookup"><span data-stu-id="88d73-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="88d73-233">Установите одно к 1 и другое к 0, или установите оба к 0.</span><span class="sxs-lookup"><span data-stu-id="88d73-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="88d73-234">В этом примере создается новое имя политики карантина NoAccess, которое назначает разрешения на доступ без доступа, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="88d73-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="88d73-235">Для разрешений ограниченного доступа используйте значение 106.</span><span class="sxs-lookup"><span data-stu-id="88d73-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="88d73-236">Для разрешений полного доступа используйте значение 236.</span><span class="sxs-lookup"><span data-stu-id="88d73-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="88d73-237">Для пользовательских разрешений используйте предыдущую таблицу, чтобы получить двоичное значение, соответствующее нужным разрешениям.</span><span class="sxs-lookup"><span data-stu-id="88d73-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="88d73-238">Преобразование двоичного значения в десятичное значение и использование десятичного значения для параметра _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="88d73-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="88d73-239">Подробные сведения о синтаксисах и параметрах см. [в new-QuarantineTag.](/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="88d73-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="88d73-240">Использование параметра EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="88d73-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="88d73-241">Чтобы создать политику карантина с помощью _параметра EndUserQuarantinePermissionsValue,_ необходимо сделать следующие действия:</span><span class="sxs-lookup"><span data-stu-id="88d73-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="88d73-242">О.</span><span class="sxs-lookup"><span data-stu-id="88d73-242">A.</span></span> <span data-ttu-id="88d73-243">Храните объект разрешений карантина в переменной с помощью подраздела **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="88d73-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="88d73-244">B.</span><span class="sxs-lookup"><span data-stu-id="88d73-244">B.</span></span> <span data-ttu-id="88d73-245">Используйте переменную в качестве _значения EndUserQuarantinePermissions_ в **команде New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="88d73-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="88d73-246">Шаг A. Хранение объекта разрешений карантина в переменной</span><span class="sxs-lookup"><span data-stu-id="88d73-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="88d73-247">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="88d73-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="88d73-248">Значение по умолчанию для любых неиспользимых параметров , поэтому вам нужно использовать только параметры, в которых необходимо установить `$false` значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="88d73-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="88d73-249">В следующих примерах покажите, как создавать объекты разрешений, соответствующие заранее:</span><span class="sxs-lookup"><span data-stu-id="88d73-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="88d73-250">**Нет доступа:**</span><span class="sxs-lookup"><span data-stu-id="88d73-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="88d73-251">**Ограниченный доступ:**</span><span class="sxs-lookup"><span data-stu-id="88d73-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="88d73-252">**Полный доступ:**</span><span class="sxs-lookup"><span data-stu-id="88d73-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="88d73-253">Чтобы увидеть значения, которые вы установили, запустите имя переменной в качестве команды (например, запустите `$NoAccess` команду).</span><span class="sxs-lookup"><span data-stu-id="88d73-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="88d73-254">Для пользовательских разрешений не заданы параметры _PermissionToRelease_ и _PermissionToRequestRelease._ `$true`</span><span class="sxs-lookup"><span data-stu-id="88d73-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="88d73-255">Установите одно и `$true` оставьте другое как `$false` , или оставьте оба как `$false` .</span><span class="sxs-lookup"><span data-stu-id="88d73-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="88d73-256">Вы также можете изменить существующую переменную объектов разрешений после создания, но перед ее использованием с помощью **cmdlet Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="88d73-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="88d73-257">Подробные сведения о синтаксисах и параметрах см. в [new-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) и [Set-QuarantinePermissions.](/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="88d73-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="88d73-258">Шаг B. Использование переменной в New-QuarantineTag команде</span><span class="sxs-lookup"><span data-stu-id="88d73-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="88d73-259">После создания и хранения объекта разрешений в переменной используйте переменную для значения параметра _EndUserQuarantinePermission_ в следующей команде **New-QuarantineTag:**</span><span class="sxs-lookup"><span data-stu-id="88d73-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="88d73-260">В этом примере создается новая политика карантина с именем LimitedAccess с помощью объекта разрешений, который был описан и создан `$LimitedAccess` на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="88d73-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="88d73-261">Подробные сведения о синтаксисах и параметрах см. [в new-QuarantineTag.](/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="88d73-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="88d73-262">Шаг 2. Назначение политики карантина поддерживаемых функций</span><span class="sxs-lookup"><span data-stu-id="88d73-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="88d73-263">В _поддерживаемых_ средствах защиты, карантиных сообщениях или файлах (автоматически или в качестве настраиваемого действия), можно назначить политику карантина доступным карантиным действиям.</span><span class="sxs-lookup"><span data-stu-id="88d73-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="88d73-264">Функции карантиных сообщений и наличие политик карантина описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="88d73-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="88d73-265">Функция</span><span class="sxs-lookup"><span data-stu-id="88d73-265">Feature</span></span>|<span data-ttu-id="88d73-266">Поддерживаемые политики карантина?</span><span class="sxs-lookup"><span data-stu-id="88d73-266">Quarantine policies supported?</span></span>|<span data-ttu-id="88d73-267">Используемые политики карантина по умолчанию</span><span class="sxs-lookup"><span data-stu-id="88d73-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="88d73-268">[Политики борьбы со спамом:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="88d73-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="88d73-269">**Spam** _(SpamAction)_</span><span class="sxs-lookup"><span data-stu-id="88d73-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="88d73-270">**Высокая достоверность** нежелательной почты _(HighConfidenceSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="88d73-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="88d73-271">**Фишинг** _(PhishSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="88d73-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="88d73-272">**Фишинг с высокой уверенностью** _(HighConfidencePhishAction)_</span><span class="sxs-lookup"><span data-stu-id="88d73-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="88d73-273">**Bulk** _(BulkSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="88d73-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="88d73-274">Да</span><span class="sxs-lookup"><span data-stu-id="88d73-274">Yes</span></span>|<ul><li><span data-ttu-id="88d73-275">DefaultSpamTag (Полный доступ)</span><span class="sxs-lookup"><span data-stu-id="88d73-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="88d73-276">DefaultHighConfSpamTag (Полный доступ)</span><span class="sxs-lookup"><span data-stu-id="88d73-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="88d73-277">DefaultPhishTag (Полный доступ)</span><span class="sxs-lookup"><span data-stu-id="88d73-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="88d73-278">DefaultHighConfPhishTag (Без доступа)</span><span class="sxs-lookup"><span data-stu-id="88d73-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="88d73-279">DefaultBulkTag (Полный доступ)</span><span class="sxs-lookup"><span data-stu-id="88d73-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="88d73-280">Политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="88d73-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="88d73-281">[Защита от спуф-аналитики](set-up-anti-phishing-policies.md#spoof-settings) _(AuthenticationFailAction)_</span><span class="sxs-lookup"><span data-stu-id="88d73-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="88d73-282">[Защита от обезличения:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88d73-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="88d73-283">**Если сообщение обнаружено как обезличенный пользователь** _(TargetedUserProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="88d73-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="88d73-284">**Если сообщение обнаружено как обезличенный домен** _(TargetedDomainProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="88d73-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="88d73-285">**Если разведка почтовых ящиков обнаруживает и выдает** себя за пользователя _(MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="88d73-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="88d73-286">Нет</span><span class="sxs-lookup"><span data-stu-id="88d73-286">No</span></span>|<span data-ttu-id="88d73-287">н/д</span><span class="sxs-lookup"><span data-stu-id="88d73-287">n/a</span></span>|
|<span data-ttu-id="88d73-288">[Политики по борьбе с вредоносными](configure-anti-malware-policies.md)программами. Все обнаруженные сообщения всегда находятся на карантине.</span><span class="sxs-lookup"><span data-stu-id="88d73-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="88d73-289">Нет</span><span class="sxs-lookup"><span data-stu-id="88d73-289">No</span></span>|<span data-ttu-id="88d73-290">н/д</span><span class="sxs-lookup"><span data-stu-id="88d73-290">n/a</span></span>|
|[<span data-ttu-id="88d73-291">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88d73-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="88d73-292">Нет</span><span class="sxs-lookup"><span data-stu-id="88d73-292">No</span></span>|<span data-ttu-id="88d73-293">н/д</span><span class="sxs-lookup"><span data-stu-id="88d73-293">n/a</span></span>|
|<span data-ttu-id="88d73-294">[Правила потока почты](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (также известные как правила транспорта) с действием: **Доставка** сообщения на карантин(_карантин)._</span><span class="sxs-lookup"><span data-stu-id="88d73-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="88d73-295">Нет</span><span class="sxs-lookup"><span data-stu-id="88d73-295">No</span></span>|<span data-ttu-id="88d73-296">н/д</span><span class="sxs-lookup"><span data-stu-id="88d73-296">n/a</span></span>|
|

<span data-ttu-id="88d73-297"><sup>\*</sup>Параметры защиты от обезличения доступны только в политиках защиты от фишинга в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="88d73-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="88d73-298">Если вы довольны разрешениями конечных пользователей, предоставляемыми политиками карантина по умолчанию, вам не нужно ничего делать.</span><span class="sxs-lookup"><span data-stu-id="88d73-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="88d73-299">Если вы хотите настроить возможности конечных пользователей (доступные кнопки) в уведомлениях о нежелательной почте конечных пользователей или в карантиновом сообщении, можно назначить настраиваемую политику карантина.</span><span class="sxs-lookup"><span data-stu-id="88d73-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="88d73-300">Назначение политик карантина в политиках по борьбе со спамом на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="88d73-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="88d73-301">Полные инструкции по созданию и изменению политик борьбы со спамом описаны в настройках политик по борьбе со спамом [в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="88d73-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="88d73-302">На портале Microsoft 365 Defender перейдите к разделу Политики **совместной** & электронной почты & правила раздел \>  \>  \> **Anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="88d73-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="88d73-303">Или откройте <https://security.microsoft.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="88d73-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="88d73-304">На странице **Политики борьбы со спамом** сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="88d73-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="88d73-305">Найдите и выберите **существующую** политику противодействия нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="88d73-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="88d73-306">Создайте новую **политику противодействия** нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="88d73-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="88d73-307">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="88d73-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="88d73-308">**Изменить существующую политику борьбы со спамом.** В разделе Сведения о политике перейдите в раздел **Действия,** а затем нажмите **кнопку Изменить действия**.</span><span class="sxs-lookup"><span data-stu-id="88d73-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="88d73-309">**Создайте новую политику борьбы со спамом.** В новом мастере политики перейдите на страницу **Действия.**</span><span class="sxs-lookup"><span data-stu-id="88d73-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="88d73-310">На странице **Действия.**</span><span class="sxs-lookup"><span data-stu-id="88d73-310">On the **Actions** page.</span></span> <span data-ttu-id="88d73-311">каждый вердикт, который **имеет** действие карантиного сообщения, также будет иметь поле **Политики** выбора карантина для выбора соответствующей политики карантина.</span><span class="sxs-lookup"><span data-stu-id="88d73-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="88d73-312">**Примечание.** При создании новой политики используется пустое значение **Политики** выбора карантиной политики, которое указывает на то, что для этого решения используется политика карантина по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88d73-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="88d73-313">После редактирования политики пустые значения заменяются фактическими именами политик карантина по умолчанию, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="88d73-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![Выбор политики карантина в политике борьбы со спамом](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="88d73-315">По завершении нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="88d73-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="88d73-316">Назначение политик карантина в политиках по борьбе со спамом в PowerShell</span><span class="sxs-lookup"><span data-stu-id="88d73-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="88d73-317">Если вы хотите использовать PowerShell для назначения политик карантина в политиках по борьбе со спамом, подключись к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="88d73-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="88d73-318">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="88d73-318">**Notes**:</span></span>

- <span data-ttu-id="88d73-319">Значение по умолчанию для параметра _HighConfidencePhishAction_ — карантин, поэтому не нужно устанавливать действие карантина для обнаружения фишинга с высокой уверенностью в новых политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="88d73-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="88d73-320">Для всех других приговоров по фильтрации нежелательной почты в новых или существующих политиках по борьбе со спамом политика карантина эффективна только в том случае, если значение действия — карантин.</span><span class="sxs-lookup"><span data-stu-id="88d73-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="88d73-321">Чтобы увидеть значения действий в существующих политиках по борьбе со спамом, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="88d73-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="88d73-322">Сведения о значениях действий по умолчанию и рекомендуемых значениях действий для Standard и Strict см. в параметров политики борьбы со спамом [EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="88d73-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="88d73-323">Вердикт фильтрации нежелательной почты без соответствующего [](#step-2-assign-a-quarantine-policy-to-supported-features) параметра политики карантина означает, что для этого решения используется политика карантина по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88d73-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="88d73-324">Чтобы изменить возможности конечных пользователей в карантинных сообщениях по умолчанию, необходимо заменить политику карантина по умолчанию на настраиваемую политику карантина.</span><span class="sxs-lookup"><span data-stu-id="88d73-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="88d73-325">Новая политика по борьбе со нежелательной почтой в PowerShell требует политики фильтрации нежелательной почты (параметры) с помощью комлета **New-HostedContentFilterPolicy** и нового правила фильтра нежелательной почты (фильтры получателей) с помощью комлета **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="88d73-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="88d73-326">Инструкции см. в [инструкции Use PowerShell для создания политик по борьбе со спамом.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="88d73-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="88d73-327">В этом примере создается новая политика фильтра нежелательной почты с именем Research Department со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="88d73-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="88d73-328">Действие для всех приговоров фильтрации нежелательной почты задавается карантином.</span><span class="sxs-lookup"><span data-stu-id="88d73-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="88d73-329">Настраиваемая политика карантина с именем  NoAccess, которая назначает разрешения на доступ без  доступа, заменяет любые политики карантина по умолчанию, которые еще не назначают разрешения доступа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88d73-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="88d73-330">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="88d73-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="88d73-331">В этом примере изменяется существующая политика фильтрации нежелательной почты с именем Human Resources.</span><span class="sxs-lookup"><span data-stu-id="88d73-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="88d73-332">Действие для вердикта карантина нежелательной почты задавается карантином, и назначена настраиваемая политика карантина с именем NoAccess.</span><span class="sxs-lookup"><span data-stu-id="88d73-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="88d73-333">Дополнительные сведения о синтаксисе и параметрах см. в статье [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="88d73-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="88d73-334">Настройка глобальных параметров уведомлений о карантине на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="88d73-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="88d73-335">Глобальные параметры политик карантина позволяют настраивать уведомления о нежелательной почте конечного пользователя, которые отправляются получателям сообщений, которые были на карантине.</span><span class="sxs-lookup"><span data-stu-id="88d73-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="88d73-336">Дополнительные сведения об этих уведомлениях см. в сообщении о нежелательной [почте конечных пользователей.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="88d73-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="88d73-337">На портале Microsoft 365 Defender перейдите в раздел Правила политики **&** угрозы совместной работы, а затем выберите политики \>  \>  \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="88d73-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="88d73-338">На странице **Политики карантина** выберите **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="88d73-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="88d73-339">В **открываемом** флаауте параметров уведомлений карантина настройте некоторые или все следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="88d73-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="88d73-340">**Отображение имени.** Настройте отображаемого имени отправитель, которое используется в уведомлениях о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="88d73-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="88d73-341">Для каждого добавленного языка выберите язык во втором языковом окне (не нажимайте на X) и введите текстовое значение, которое необходимо в поле **Отображайте имя.**</span><span class="sxs-lookup"><span data-stu-id="88d73-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="88d73-342">На следующем скриншоте показано настраиваемого имени отображения в уведомлении о нежелательной почте для конечных пользователей:</span><span class="sxs-lookup"><span data-stu-id="88d73-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Настраиваемый отправитель отображает имя в уведомлении о нежелательной почте для конечных пользователей](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="88d73-344">**Отказ от ответственности.** Добавьте настраиваемый отказ в нижней части уведомлений о нежелательной почте конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="88d73-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="88d73-345">Локализованный текст , **отказ от организации:** всегда включается в первую очередь, а затем текст, который вы указываете.</span><span class="sxs-lookup"><span data-stu-id="88d73-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="88d73-346">Для каждого добавленного языка выберите язык во втором языковом окне (не щелкните X) и введите текстовое значение, которое необходимо в поле **Отказ** от ответственности.</span><span class="sxs-lookup"><span data-stu-id="88d73-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="88d73-347">На следующем скриншоте показан настраиваемый отказ в уведомлении о нежелательной почте для конечных пользователей:</span><span class="sxs-lookup"><span data-stu-id="88d73-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Настраиваемый отказ в нижней части уведомления о нежелательной почте конечного пользователя](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="88d73-349">**Выберите язык.** Уведомления о нежелательной почте конечных пользователей уже локализованы в зависимости от параметров языка получателя.</span><span class="sxs-lookup"><span data-stu-id="88d73-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="88d73-350">Вы можете указать настраиваемый текст на разных языках для значений **Display и** **Disclaimer.**</span><span class="sxs-lookup"><span data-stu-id="88d73-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="88d73-351">Выберите хотя бы один язык из первого языкового окна и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88d73-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="88d73-352">Вы можете выбрать несколько языков, щелкнув **Добавить** после каждого из них.</span><span class="sxs-lookup"><span data-stu-id="88d73-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="88d73-353">В языковом окне раздела показаны все выбранные вами языки:</span><span class="sxs-lookup"><span data-stu-id="88d73-353">A section language box shows all of the languages that you've selected:</span></span>

     ![Выбранные языки во втором языковом поле в глобальных параметрах уведомлений о карантине политик карантина](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="88d73-355">**Используйте логотип моей компании.** Выберите этот параметр, чтобы заменить логотип Microsoft по умолчанию, который используется в верхней части уведомлений о нежелательной почте конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="88d73-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="88d73-356">Прежде чем это сделать, необходимо следовать инструкциям в [Настройка](../../admin/setup/customize-your-organization-theme.md) темы Microsoft 365 для вашей организации, чтобы загрузить свой пользовательский логотип.</span><span class="sxs-lookup"><span data-stu-id="88d73-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="88d73-357">На следующем скриншоте показан настраиваемый логотип в уведомлении о нежелательной почте для конечных пользователей:</span><span class="sxs-lookup"><span data-stu-id="88d73-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Настраиваемый логотип в уведомлении о нежелательной почте для конечных пользователей](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="88d73-359">Просмотр политик карантина на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="88d73-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="88d73-360">На портале Microsoft 365 Defender перейдите в раздел Правила политики **&** угрозы совместной работы, а затем выберите политики \>  \>  \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="88d73-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="88d73-361">На **странице политики карантина** показан список политик **по имени** и **последней обновленной дате.**</span><span class="sxs-lookup"><span data-stu-id="88d73-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="88d73-362">Чтобы просмотреть параметры встроенных или настраиваемой политики карантина, выберите политику карантина из списка, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="88d73-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="88d73-363">Чтобы просмотреть глобальные параметры, щелкните **Глобальные параметры**</span><span class="sxs-lookup"><span data-stu-id="88d73-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="88d73-364">Просмотр политик карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="88d73-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="88d73-365">Если вы хотите использовать PowerShell для просмотра политик карантина, сделайте любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="88d73-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="88d73-366">Чтобы просмотреть сводный список всех встроенных или настраиваемых политик, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="88d73-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="88d73-367">Чтобы просмотреть параметры встроенных или настраиваемых политик карантина, замените имя политики карантина и запустите \<QuarantinePolicyName\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="88d73-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="88d73-368">Чтобы просмотреть глобальные параметры, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="88d73-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="88d73-369">Дополнительные сведения о синтаксисе и параметрах см. в статье [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="88d73-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="88d73-370">Изменение политик карантина на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="88d73-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="88d73-371">На портале Microsoft 365 Defender перейдите в раздел Правила политики **&** угрозы совместной работы, а затем выберите политики \>  \>  \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="88d73-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="88d73-372">На странице **Политики карантина** выберите политику, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="88d73-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="88d73-373">После выбора политики щелкните значок Изменить значок политики ![ ](../../media/m365-cc-sc-edit-icon.png) **редактирования,** который отображается.</span><span class="sxs-lookup"><span data-stu-id="88d73-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="88d73-374">**Открывающийся** мастер политики редактирования  практически идентичен мастеру новой политики, как описано в разделе Создание политик карантина в разделе [Microsoft 365 Defender](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) портала ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="88d73-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="88d73-375">Главное отличие: нельзя переименовать существующую политику.</span><span class="sxs-lookup"><span data-stu-id="88d73-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="88d73-376">После изменения политики перейдите на страницу **Сводка** и нажмите **кнопку Отправить**.</span><span class="sxs-lookup"><span data-stu-id="88d73-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="88d73-377">Изменение политик карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="88d73-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="88d73-378">Если вы хотите использовать PowerShell для изменения настраиваемой политики карантина, замените имя политики карантина и используйте \<QuarantinePolicyName\> следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="88d73-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="88d73-379">Доступные параметры такие же, как описаны для создания политик карантина, описанных ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="88d73-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="88d73-380">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-QuarantineTag.](/powershell/module/exchange/set-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="88d73-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="88d73-381">Удаление политик карантина на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="88d73-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="88d73-382">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="88d73-382">**Notes**:</span></span>

- <span data-ttu-id="88d73-383">Нельзя удалить встроенные политики карантина.</span><span class="sxs-lookup"><span data-stu-id="88d73-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="88d73-384">Перед удалением настраиваемой политики карантина убедитесь, что она не используется.</span><span class="sxs-lookup"><span data-stu-id="88d73-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="88d73-385">Например, запустите следующую команду в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="88d73-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="88d73-386">Если используется политика карантина, [](#step-2-assign-a-quarantine-policy-to-supported-features) замените назначенную политику карантина перед ее удалением.</span><span class="sxs-lookup"><span data-stu-id="88d73-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="88d73-387">На портале Microsoft 365 Defender перейдите в раздел Правила политики **&** угрозы совместной работы, а затем выберите политики \>  \>  \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="88d73-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="88d73-388">На странице **Политики карантина** выберите настраиваемую политику карантина, которую необходимо удалить, нажав на имя.</span><span class="sxs-lookup"><span data-stu-id="88d73-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="88d73-389">После выбора политики щелкните значок Удалить значок ![ ](../../media/m365-cc-sc-delete-icon.png) **политики Удаления,** который отображается.</span><span class="sxs-lookup"><span data-stu-id="88d73-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="88d73-390">Нажмите **кнопку Удалить политику** в диалоговом окте подтверждения, который отображается.</span><span class="sxs-lookup"><span data-stu-id="88d73-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="88d73-391">Удаление политик карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="88d73-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="88d73-392">Если вы хотите использовать PowerShell для удаления настраиваемой политики карантина, замените имя политики карантина и запустите \<QuarantinePolicyName\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="88d73-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="88d73-393">Подробные сведения о синтаксисах и параметрах см. в [инструкции Remove-QuarantineTag.](/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="88d73-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="88d73-394">Сведения о разрешении политики карантина</span><span class="sxs-lookup"><span data-stu-id="88d73-394">Quarantine policy permission details</span></span>

<span data-ttu-id="88d73-395">В следующих разделах описаны последствия групп предварительного разрешения и отдельных разрешений в подробностях карантиновых сообщений и уведомлений о нежелательной почте конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="88d73-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="88d73-396">Группы предустановленных разрешений</span><span class="sxs-lookup"><span data-stu-id="88d73-396">Preset permissions groups</span></span>

<span data-ttu-id="88d73-397">Отдельные разрешения, включенные в группы предварительного разрешения, перечислены в таблице в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="88d73-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="88d73-398">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="88d73-398">No access</span></span>

<span data-ttu-id="88d73-399">Если политика карантина назначает  разрешения без доступа (без разрешений), пользователи по-прежнему получают некоторые базовые возможности:</span><span class="sxs-lookup"><span data-stu-id="88d73-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="88d73-400">**Карантинные сведения о сообщении.** Кнопка **"Просмотр"** всегда доступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Доступные кнопки в карантиновом сообщении, если политика карантина не дает пользователю разрешений на доступ](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="88d73-402">**Уведомления о нежелательной почте** конечных пользователей: кнопка **Обзор,** которая принимает пользователя к сообщению на карантине, всегда доступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Доступные кнопки в уведомлении о нежелательной почте для конечных пользователей, если политика карантина не дает пользователю разрешений на доступ](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="88d73-404">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="88d73-404">Limited access</span></span>

<span data-ttu-id="88d73-405">Если политика карантина назначает  разрешения ограниченного доступа, пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="88d73-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="88d73-406">**Сведения о карантинном сообщении:** доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="88d73-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="88d73-407">**Выпуск запроса**</span><span class="sxs-lookup"><span data-stu-id="88d73-407">**Request release**</span></span>
  - <span data-ttu-id="88d73-408">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="88d73-408">**View message header**</span></span>
  - <span data-ttu-id="88d73-409">**Предварительное сообщение**</span><span class="sxs-lookup"><span data-stu-id="88d73-409">**Preview message**</span></span>
  - <span data-ttu-id="88d73-410">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="88d73-410">**Block sender**</span></span>
  - <span data-ttu-id="88d73-411">**Удаление из карантина**</span><span class="sxs-lookup"><span data-stu-id="88d73-411">**Remove from quarantine**</span></span>

  ![Доступные кнопки в карантиновом сообщении, если политика карантина дает пользователю разрешения на ограниченный доступ](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="88d73-413">**Уведомления о нежелательной почте** конечных пользователей: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="88d73-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="88d73-414">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="88d73-414">**Block sender**</span></span>
  - <span data-ttu-id="88d73-415">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="88d73-415">**Review**</span></span>

  ![Доступные кнопки в уведомлении о нежелательной почте для конечных пользователей, если политика карантина дает пользователю разрешения на ограниченный доступ.](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="88d73-417">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="88d73-417">Full access</span></span>

<span data-ttu-id="88d73-418">Если политика карантина назначает  разрешения полного доступа (все доступные разрешения), пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="88d73-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="88d73-419">**Сведения о карантинном сообщении:** доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="88d73-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="88d73-420">**Сообщение о выпуске**</span><span class="sxs-lookup"><span data-stu-id="88d73-420">**Release message**</span></span>
  - <span data-ttu-id="88d73-421">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="88d73-421">**View message header**</span></span>
  - <span data-ttu-id="88d73-422">**Предварительное сообщение**</span><span class="sxs-lookup"><span data-stu-id="88d73-422">**Preview message**</span></span>
  - <span data-ttu-id="88d73-423">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="88d73-423">**Block sender**</span></span>
  - <span data-ttu-id="88d73-424">**Разрешить отправитель**</span><span class="sxs-lookup"><span data-stu-id="88d73-424">**Allow sender**</span></span>
  - <span data-ttu-id="88d73-425">**Удаление из карантина**</span><span class="sxs-lookup"><span data-stu-id="88d73-425">**Remove from quarantine**</span></span>

  ![Доступные кнопки в карантиновом сообщении, если политика карантина дает пользователю разрешения на полный доступ](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="88d73-427">**Уведомления о нежелательной почте** конечных пользователей: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="88d73-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="88d73-428">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="88d73-428">**Block sender**</span></span>
  - <span data-ttu-id="88d73-429">**Выпуск**</span><span class="sxs-lookup"><span data-stu-id="88d73-429">**Release**</span></span>
  - <span data-ttu-id="88d73-430">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="88d73-430">**Review**</span></span>

  ![Доступные кнопки в уведомлении о нежелательной почте для конечных пользователей, если политика карантина дает пользователю разрешения на полный доступ](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="88d73-432">Отдельные разрешения</span><span class="sxs-lookup"><span data-stu-id="88d73-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="88d73-433">Помните, что пользователи всегда получают кнопки, описанные в разделе [Нет доступа.](#no-access)</span><span class="sxs-lookup"><span data-stu-id="88d73-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="88d73-434">Эти кнопки не включены в отдельные описания разрешений.</span><span class="sxs-lookup"><span data-stu-id="88d73-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="88d73-435">Разрешить разрешение отправитель</span><span class="sxs-lookup"><span data-stu-id="88d73-435">Allow sender permission</span></span>

<span data-ttu-id="88d73-436">Разрешение **разрешить отправитель** _(PermissionToAllowSender)_ управляет доступом к кнопке, которая позволяет пользователям удобно добавлять отправитель сообщений, на карантин, в Сейф список отправителей.</span><span class="sxs-lookup"><span data-stu-id="88d73-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="88d73-437">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="88d73-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="88d73-438">**Разрешить разрешение отправитель** включен: **кнопка Разрешить отправитель** доступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="88d73-439">**Разрешить отключение** разрешения отправитель: кнопка **Разрешить** отправитель недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="88d73-440">**Уведомления о нежелательной почте конечных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="88d73-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="88d73-441">Дополнительные сведения о списке Сейф отправителей [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) см. в этой информации, чтобы предотвратить блокировку доверенных отправителей и использовать [Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)для настройки коллекции safelist на почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="88d73-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="88d73-442">Разрешение отправитель блокировки</span><span class="sxs-lookup"><span data-stu-id="88d73-442">Block sender permission</span></span>

<span data-ttu-id="88d73-443">Разрешение **отправителей** блокировки _(PermissionToBlockSender)_ управляет доступом к кнопке, которая позволяет пользователям удобно добавлять отправитель сообщений, на карантин, в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="88d73-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="88d73-444">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="88d73-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="88d73-445">**Включено разрешение отправитель** блока. Кнопка **"Отправитель** блока" доступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="88d73-446">**Отключено разрешение** отправитель блокировки. Кнопка **"Отправитель** блока" недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="88d73-447">**Уведомления о нежелательной почте конечных пользователей:**</span><span class="sxs-lookup"><span data-stu-id="88d73-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="88d73-448">**Отключено разрешение** отправитель блокировки. Кнопка **"Отправитель** блока" недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="88d73-449">**Включено разрешение отправитель** блока. Кнопка **"Отправитель** блока" доступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="88d73-450">Дополнительные сведения о списке заблокированных [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) отправителей см. в дополнительных сведениях о блокировке сообщений от кого-либо и использовании Exchange Online PowerShell для настройки коллекции safelist на [почтовом ящике.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="88d73-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="88d73-451">Разрешения на удаление</span><span class="sxs-lookup"><span data-stu-id="88d73-451">Delete permission</span></span>

<span data-ttu-id="88d73-452">Разрешение **Delete** _(PermissionToDelete)_ управляет возможностью пользователей удалять свои сообщения (сообщения, в которых пользователь является получателем) из карантина.</span><span class="sxs-lookup"><span data-stu-id="88d73-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="88d73-453">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="88d73-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="88d73-454">**Удаление** включенного разрешения. Кнопка Удаление из **карантина** доступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="88d73-455">**Удаление** отключенных разрешений. Кнопка Удалить из **карантина** недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="88d73-456">**Уведомления о нежелательной почте конечных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="88d73-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="88d73-457">Разрешение предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="88d73-457">Preview permission</span></span>

<span data-ttu-id="88d73-458">Разрешение **Preview** _(PermissionToPreview)_ контролирует возможность предварительного просмотра сообщений пользователями в карантине.</span><span class="sxs-lookup"><span data-stu-id="88d73-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="88d73-459">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="88d73-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="88d73-460">**Включено** разрешение предварительного просмотра: **доступна** кнопка предварительного просмотра сообщения.</span><span class="sxs-lookup"><span data-stu-id="88d73-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="88d73-461">**Отключено** разрешение предварительного просмотра. **Кнопка** предварительного просмотра недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="88d73-462">**Уведомления о нежелательной почте конечных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="88d73-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="88d73-463">Разрешить получателям освободить сообщение из разрешения карантина</span><span class="sxs-lookup"><span data-stu-id="88d73-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="88d73-464">Разрешить **получателям** освободить сообщение из разрешения карантина _(PermissionToRelease)_ контролирует возможность пользователей выпускать свои карантинные сообщения напрямую и без разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="88d73-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="88d73-465">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="88d73-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="88d73-466">Включено разрешение. Доступна кнопка **"Сообщение** о выпуске".</span><span class="sxs-lookup"><span data-stu-id="88d73-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="88d73-467">Отключено разрешение. **Кнопка "Сообщение о выпуске"** недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="88d73-468">**Уведомления о нежелательной почте конечных пользователей:**</span><span class="sxs-lookup"><span data-stu-id="88d73-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="88d73-469">Включено разрешение. Доступна кнопка **Release.**</span><span class="sxs-lookup"><span data-stu-id="88d73-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="88d73-470">Отключено разрешение. **Кнопка Выпуска** недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="88d73-471">Разрешить получателям запрашивать сообщение, которое будет выпущено из разрешения карантина</span><span class="sxs-lookup"><span data-stu-id="88d73-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="88d73-472">Разрешить **получателям** запрашивать сообщение, которое будет выпущено из разрешения карантина _(PermissionToRequestRelease)_ контролирует возможность пользователей запрашивать выпуск их карантинов. </span><span class="sxs-lookup"><span data-stu-id="88d73-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="88d73-473">Сообщение будет выпущено только после утверждения запроса администратором.</span><span class="sxs-lookup"><span data-stu-id="88d73-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="88d73-474">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="88d73-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="88d73-475">Включено разрешение: **доступна кнопка выпуска** запроса.</span><span class="sxs-lookup"><span data-stu-id="88d73-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="88d73-476">Отключено разрешение. **Кнопка выпуска запроса** недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="88d73-477">**Уведомления о нежелательной почте** конечных пользователей. Кнопка **Выпуска** недоступна.</span><span class="sxs-lookup"><span data-stu-id="88d73-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
