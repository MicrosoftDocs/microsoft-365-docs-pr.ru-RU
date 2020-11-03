---
title: Теги карантина
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Администраторы могут узнать, как использовать теги карантина, чтобы контролировать, какие пользователи могут выполнять действия с сообщениями, помещенными в карантин.
ms.openlocfilehash: e50d7eea4cec3c87231dda855725b1e901f5fa33
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845700"
---
# <a name="quarantine-tags"></a><span data-ttu-id="0665e-103">Теги карантина</span><span class="sxs-lookup"><span data-stu-id="0665e-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="0665e-104">Функции, описанные в этой статье, в настоящее время доступны для всех и могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="0665e-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="0665e-105">Теги карантина в Exchange Online Protection (EOP) позволяют администраторам контролировать, какие пользователи могут выполнять действия с сообщениями в карантине в зависимости от того, как сообщение поступило в карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="0665e-106">В EOP традиционно разрешены или запрещены определенные уровни взаимодействия для сообщений в [карантине](find-and-release-quarantined-messages-as-a-user.md) и [уведомления о нежелательной почте конечных пользователей](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0665e-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="0665e-107">Например, конечные пользователи могут просматривать и освобождать сообщения, помещенные в карантин с помощью фильтрации нежелательной почты в качестве нежелательной почты или массовых сообщений, но не могут просматривать или освобождать сообщения, помещенные в карантин в качестве высокодостоверных фишинга.</span><span class="sxs-lookup"><span data-stu-id="0665e-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="0665e-108">Для [поддерживаемых функций защиты](#step-2-assign-a-quarantine-tag-to-supported-features)Теги карантина указывают, какие пользователи могут выполнять в сообщениях уведомления о нежелательной почте, а также в карантинных сообщениях в карантине (сообщения, в которых пользователь является получателем).</span><span class="sxs-lookup"><span data-stu-id="0665e-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="0665e-109">Теги карантина по умолчанию автоматически назначаются для применения исторических возможностей для конечных пользователей в сообщениях, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="0665e-110">Можно также создать и назначить пользовательские теги карантина, чтобы разрешить или запретить конечным пользователям выполнять определенные действия в сообщениях, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="0665e-111">Индивидуальные разрешения объединяются в следующие предварительно заданные группы разрешений:</span><span class="sxs-lookup"><span data-stu-id="0665e-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="0665e-112">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="0665e-112">No access</span></span>
- <span data-ttu-id="0665e-113">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="0665e-113">Limited access</span></span>
- <span data-ttu-id="0665e-114">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="0665e-114">Full access</span></span>

<span data-ttu-id="0665e-115">В следующей таблице описаны доступные индивидуальные разрешения, а также включенные и не включенные в предустановленные группы разрешений.</span><span class="sxs-lookup"><span data-stu-id="0665e-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="0665e-116">Разрешение</span><span class="sxs-lookup"><span data-stu-id="0665e-116">Permission</span></span>|<span data-ttu-id="0665e-117">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="0665e-117">No access</span></span>|<span data-ttu-id="0665e-118">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="0665e-118">Limited access</span></span>|<span data-ttu-id="0665e-119">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="0665e-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="0665e-120">**Разрешить отправителя** ( _пермиссионтоалловсендер_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-120">**Allow sender** ( _PermissionToAllowSender_ )</span></span>|||![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="0665e-122">**Блокировка отправителя** ( _пермиссионтоблокксендер_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-122">**Block sender** ( _PermissionToBlockSender_ )</span></span>||![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="0665e-125">**Delete** ( _пермиссионтоделете_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-125">**Delete** ( _PermissionToDelete_ )</span></span>||![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="0665e-128">**Предварительная версия** ( _пермиссионтопревиев_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-128">**Preview** ( _PermissionToPreview_ )</span></span>||![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="0665e-131">**Разрешить получателям выпустить сообщение из карантина** ( _пермиссионторелеасе_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-131">**Allow recipients to release a message from quarantine** ( _PermissionToRelease_ )</span></span>|||![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="0665e-133">**Разрешить получателям запрашивать сообщение для освобождения из карантина** ( _пермиссионторекуестрелеасе_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-133">**Allow recipients to request a message to be released from quarantine** ( _PermissionToRequestRelease_ )</span></span>||![Флажок](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

<span data-ttu-id="0665e-135">Если вы не хотите использовать разрешения по умолчанию в предустановленных группах разрешений, вы можете использовать настраиваемые разрешения при создании или изменении пользовательских тегов карантина.</span><span class="sxs-lookup"><span data-stu-id="0665e-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="0665e-136">Дополнительные сведения о том, что делает каждый из разрешений, можно найти в разделе [сведения о разрешениях для тегов карантина](#quarantine-tag-permission-details) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0665e-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="0665e-137">Теги карантина создаются и назначаются в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками Exchange Online; изолированный EOP PowerShell в организациях EOP без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="0665e-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0665e-138">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="0665e-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0665e-139">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0665e-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0665e-140">Чтобы перейти непосредственно на страницу **теги карантина** , откройте страницу <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="0665e-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="0665e-141">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0665e-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0665e-142">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="0665e-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0665e-143">Чтобы просматривать, создавать, изменять или удалять теги карантина, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="0665e-143">To view, create, modify, or remove quarantine tags, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="0665e-144">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0665e-144">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="0665e-145">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="0665e-145">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="0665e-146">Шаг 1: Создание тегов карантина в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0665e-146">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="0665e-147">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** а затем выберите пункт **теги карантина**.</span><span class="sxs-lookup"><span data-stu-id="0665e-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="0665e-148">На странице " **теги карантина** " выберите **Добавить настраиваемый тег**.</span><span class="sxs-lookup"><span data-stu-id="0665e-148">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="0665e-149">Откроется мастер **создания нового тега** .</span><span class="sxs-lookup"><span data-stu-id="0665e-149">The **New tag** wizard opens.</span></span> <span data-ttu-id="0665e-150">На странице **имя тега** введите краткое, но уникальное имя в поле **имя тега** .</span><span class="sxs-lookup"><span data-stu-id="0665e-150">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="0665e-151">Вам потребуется определить и выбрать тег по имени на следующих этапах.</span><span class="sxs-lookup"><span data-stu-id="0665e-151">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="0665e-152">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0665e-152">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0665e-153">На странице **доступа к сообщениям получателя** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0665e-153">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="0665e-154">**Нет доступа**</span><span class="sxs-lookup"><span data-stu-id="0665e-154">**No access**</span></span>
   - <span data-ttu-id="0665e-155">**Ограниченный доступ**</span><span class="sxs-lookup"><span data-stu-id="0665e-155">**Limited access**</span></span>
   - <span data-ttu-id="0665e-156">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="0665e-156">**Full access**</span></span>

   <span data-ttu-id="0665e-157">Отдельные разрешения, включенные в эти группы разрешений, описаны ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0665e-157">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="0665e-158">Чтобы указать настраиваемые разрешения, выберите **задать определенный доступ (дополнительно)** и настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0665e-158">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="0665e-159">**Выберите параметр действия при выпуске** : выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0665e-159">**Select release action preference** : Select one of the following values:</span></span>
       - <span data-ttu-id="0665e-160">**Не выпустите действие** : это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0665e-160">**No release action** : This is the default value.</span></span>
       - <span data-ttu-id="0665e-161">**Разрешить получателям выпустить сообщение из карантина**</span><span class="sxs-lookup"><span data-stu-id="0665e-161">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="0665e-162">**Разрешение получателям запросить отправку сообщения из карантина**</span><span class="sxs-lookup"><span data-stu-id="0665e-162">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="0665e-163">**Выберите дополнительные действия получатели могут принимать участие в сообщениях, помещенных в карантин** : выберите некоторые, все или ничего из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0665e-163">**Select additional actions recipients can take on quarantined messages** : Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="0665e-164">**удаление** ;</span><span class="sxs-lookup"><span data-stu-id="0665e-164">**Delete**</span></span>
       - <span data-ttu-id="0665e-165">**Предварительная версия**</span><span class="sxs-lookup"><span data-stu-id="0665e-165">**Preview**</span></span>
       - <span data-ttu-id="0665e-166">**Разрешить отправителя**</span><span class="sxs-lookup"><span data-stu-id="0665e-166">**Allow sender**</span></span>
       - <span data-ttu-id="0665e-167">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="0665e-167">**Block sender**</span></span>

   <span data-ttu-id="0665e-168">Эти разрешения и их последствия для сообщений, помещенных в карантин, и уведомления о нежелательной почте приведены в разделе [сведения о разрешениях для тегов карантина](#quarantine-tag-permission-details) , приведенных далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0665e-168">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="0665e-169">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0665e-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0665e-170">На появившейся странице **сводки** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="0665e-170">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="0665e-171">Для изменения каждого параметра можно нажать кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="0665e-171">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0665e-172">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0665e-172">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="0665e-173">Нажмите кнопку **done (Готово** ) на появившейся странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="0665e-173">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="0665e-174">Теперь вы готовы присвоить метку карантина функции карантина, как описано в разделе [Шаг 2](#step-2-assign-a-quarantine-tag-to-supported-features) .</span><span class="sxs-lookup"><span data-stu-id="0665e-174">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="0665e-175">Создание тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="0665e-175">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="0665e-176">Если вы предпочитаете создавать теги карантина с помощью PowerShell, подключитесь к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте командлет **New-куарантинетаг** .</span><span class="sxs-lookup"><span data-stu-id="0665e-176">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="0665e-177">Существует два разных способа выбора:</span><span class="sxs-lookup"><span data-stu-id="0665e-177">You have two different methods to choose from:</span></span>

- <span data-ttu-id="0665e-178">Используйте параметр _ендусеркуарантинепермиссионсвалуе_ .</span><span class="sxs-lookup"><span data-stu-id="0665e-178">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="0665e-179">Используйте параметр _ендусеркуарантинепермиссионс_ .</span><span class="sxs-lookup"><span data-stu-id="0665e-179">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="0665e-180">Эти методы описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="0665e-180">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="0665e-181">Использование параметра Ендусеркуарантинепермиссионсвалуе</span><span class="sxs-lookup"><span data-stu-id="0665e-181">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="0665e-182">Чтобы создать тег карантина с помощью параметра _ендусеркуарантинепермиссионсвалуе_ , используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0665e-182">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="0665e-183">Параметр _ендусеркуарантинепермиссионсвалуе_ использует десятичное значение, которое преобразуется из двоичного значения.</span><span class="sxs-lookup"><span data-stu-id="0665e-183">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="0665e-184">Двоичное значение соответствует доступным карантинным разрешениям конечного пользователя в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="0665e-184">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="0665e-185">Для каждого разрешения значение 1 равно true, а значение 0 равно false.</span><span class="sxs-lookup"><span data-stu-id="0665e-185">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="0665e-186">Обязательный порядок и значения для каждого отдельного разрешения в предустановленных группах разрешений описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="0665e-186">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="0665e-187">Разрешение</span><span class="sxs-lookup"><span data-stu-id="0665e-187">Permission</span></span>|<span data-ttu-id="0665e-188">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="0665e-188">No access</span></span>|<span data-ttu-id="0665e-189">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="0665e-189">Limited access</span></span>|<span data-ttu-id="0665e-190">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="0665e-190">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="0665e-191">пермиссионтоалловсендер</span><span class="sxs-lookup"><span data-stu-id="0665e-191">PermissionToAllowSender</span></span>|<span data-ttu-id="0665e-192">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-192">0</span></span>|<span data-ttu-id="0665e-193">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-193">0</span></span>|<span data-ttu-id="0665e-194">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-194">1</span></span>|
|<span data-ttu-id="0665e-195">пермиссионтоблокксендер</span><span class="sxs-lookup"><span data-stu-id="0665e-195">PermissionToBlockSender</span></span>|<span data-ttu-id="0665e-196">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-196">0</span></span>|<span data-ttu-id="0665e-197">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-197">1</span></span>|<span data-ttu-id="0665e-198">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-198">1</span></span>|
|<span data-ttu-id="0665e-199">пермиссионтоделете</span><span class="sxs-lookup"><span data-stu-id="0665e-199">PermissionToDelete</span></span>|<span data-ttu-id="0665e-200">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-200">0</span></span>|<span data-ttu-id="0665e-201">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-201">1</span></span>|<span data-ttu-id="0665e-202">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-202">1</span></span>|
|<span data-ttu-id="0665e-203">пермиссионтодовнлоад<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0665e-203">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="0665e-204">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-204">0</span></span>|<span data-ttu-id="0665e-205">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-205">0</span></span>|<span data-ttu-id="0665e-206">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-206">0</span></span>|
|<span data-ttu-id="0665e-207">пермиссионтопревиев</span><span class="sxs-lookup"><span data-stu-id="0665e-207">PermissionToPreview</span></span>|<span data-ttu-id="0665e-208">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-208">0</span></span>|<span data-ttu-id="0665e-209">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-209">1</span></span>|<span data-ttu-id="0665e-210">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-210">1</span></span>|
|<span data-ttu-id="0665e-211">пермиссионторелеасе<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="0665e-211">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="0665e-212">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-212">0</span></span>|<span data-ttu-id="0665e-213">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-213">0</span></span>|<span data-ttu-id="0665e-214">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-214">1</span></span>|
|<span data-ttu-id="0665e-215">пермиссионторекуестрелеасе<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="0665e-215">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="0665e-216">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-216">0</span></span>|<span data-ttu-id="0665e-217">1,1</span><span class="sxs-lookup"><span data-stu-id="0665e-217">1</span></span>|<span data-ttu-id="0665e-218">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-218">0</span></span>|
|<span data-ttu-id="0665e-219">пермиссионтовиевхеадер<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0665e-219">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="0665e-220">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-220">0</span></span>|<span data-ttu-id="0665e-221">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-221">0</span></span>|<span data-ttu-id="0665e-222">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-222">0</span></span>|
|<span data-ttu-id="0665e-223">Двоичное значение</span><span class="sxs-lookup"><span data-stu-id="0665e-223">Binary value</span></span>|<span data-ttu-id="0665e-224">00000001</span><span class="sxs-lookup"><span data-stu-id="0665e-224">00000000</span></span>|<span data-ttu-id="0665e-225">01101010</span><span class="sxs-lookup"><span data-stu-id="0665e-225">01101010</span></span>|<span data-ttu-id="0665e-226">11101100</span><span class="sxs-lookup"><span data-stu-id="0665e-226">11101100</span></span>|
|<span data-ttu-id="0665e-227">Используемое десятичное значение</span><span class="sxs-lookup"><span data-stu-id="0665e-227">Decimal value to use</span></span>|<span data-ttu-id="0665e-228">нуль</span><span class="sxs-lookup"><span data-stu-id="0665e-228">0</span></span>|<span data-ttu-id="0665e-229">106</span><span class="sxs-lookup"><span data-stu-id="0665e-229">106</span></span>|<span data-ttu-id="0665e-230">236</span><span class="sxs-lookup"><span data-stu-id="0665e-230">236</span></span>|

<span data-ttu-id="0665e-231"><sup>\*</sup> В настоящее время это значение всегда равно 0.</span><span class="sxs-lookup"><span data-stu-id="0665e-231"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="0665e-232">Для Пермиссионтовиевхеадер значение 0 не скрывает кнопку **Просмотр заголовка сообщения** в сведениях из помещенного в карантин сообщения (кнопка доступна всегда).</span><span class="sxs-lookup"><span data-stu-id="0665e-232">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="0665e-233"><sup>\*\*</sup> Не устанавливайте оба этих значения равными 1.</span><span class="sxs-lookup"><span data-stu-id="0665e-233"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="0665e-234">Задайте для одного из них значение 1, а другое — значение 0.</span><span class="sxs-lookup"><span data-stu-id="0665e-234">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="0665e-235">В этом примере показано создание нового имени тега карантина без доступа, который назначает разрешения без доступа, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="0665e-235">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="0665e-236">Для разрешений с ограниченным доступом используйте значение 106.</span><span class="sxs-lookup"><span data-stu-id="0665e-236">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="0665e-237">Для разрешений полного доступа используйте значение 236.</span><span class="sxs-lookup"><span data-stu-id="0665e-237">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="0665e-238">Для настраиваемых разрешений используйте предыдущую таблицу, чтобы получить двоичное значение, соответствующее требуемым разрешениям.</span><span class="sxs-lookup"><span data-stu-id="0665e-238">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="0665e-239">Преобразуйте двоичное значение в десятичное и используйте десятичное значение для параметра _ендусеркуарантинепермиссионсвалуе_ .</span><span class="sxs-lookup"><span data-stu-id="0665e-239">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="0665e-240">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – куарантинетаг](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="0665e-240">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="0665e-241">Использование параметра Ендусеркуарантинепермиссионс</span><span class="sxs-lookup"><span data-stu-id="0665e-241">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="0665e-242">Чтобы создать тег карантина с помощью параметра _ендусеркуарантинепермиссионсвалуе_ , выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0665e-242">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="0665e-243">О.</span><span class="sxs-lookup"><span data-stu-id="0665e-243">A.</span></span> <span data-ttu-id="0665e-244">Сохраните объект разрешений карантина в переменной с помощью командлета **New – куарантинепермиссионс** .</span><span class="sxs-lookup"><span data-stu-id="0665e-244">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>
<br/>
<span data-ttu-id="0665e-245">B.</span><span class="sxs-lookup"><span data-stu-id="0665e-245">B.</span></span> <span data-ttu-id="0665e-246">Используйте переменную в качестве значения _ендусеркуарантинепермиссионс_ в команде **New – куарантинетаг** .</span><span class="sxs-lookup"><span data-stu-id="0665e-246">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="0665e-247">Шаг A: сохранение объекта разрешений карантина в переменной</span><span class="sxs-lookup"><span data-stu-id="0665e-247">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="0665e-248">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0665e-248">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="0665e-249">Значение по умолчанию для всех неиспользуемых параметров `$false` , поэтому необходимо использовать только те параметры, для которых нужно задать значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="0665e-249">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="0665e-250">В следующих примерах показано, как создавать объекты разрешений, соответствующие предварительно заданным группам разрешений:</span><span class="sxs-lookup"><span data-stu-id="0665e-250">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="0665e-251">**Нет доступа** :</span><span class="sxs-lookup"><span data-stu-id="0665e-251">**No access** :</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="0665e-252">**Ограниченный доступ** :</span><span class="sxs-lookup"><span data-stu-id="0665e-252">**Limited access** :</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="0665e-253">**Полный доступ** :</span><span class="sxs-lookup"><span data-stu-id="0665e-253">**Full access** :</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="0665e-254">Чтобы просмотреть заданные значения, выполните имя переменной в виде команды (например, выполните команду `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="0665e-254">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="0665e-255">Для настраиваемых разрешений не устанавливайте для параметров _пермиссионторелеасе_ и _пермиссионторекуестрелеасе_ значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="0665e-255">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="0665e-256">Задайте для параметра значение `$true` and и оставьте значение `$false` , а не оба `$false` .</span><span class="sxs-lookup"><span data-stu-id="0665e-256">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="0665e-257">Вы также можете изменить существующую переменную объекта Permissions после создания, но перед ее использованием с помощью командлета **Set – куарантинепермиссионс** .</span><span class="sxs-lookup"><span data-stu-id="0665e-257">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="0665e-258">Подробные сведения о синтаксисе и параметрах можно найти в статье [New/куарантинепермиссионс](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) и [Set – куарантинепермиссионс](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="0665e-258">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="0665e-259">Шаг б: использование переменной в команде New-QuarantineTag</span><span class="sxs-lookup"><span data-stu-id="0665e-259">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="0665e-260">После создания и сохранения объекта Permissions в переменной используйте значение параметра _ендусеркуарантинепермиссион_ в следующей команде **New – куарантинетаг** :</span><span class="sxs-lookup"><span data-stu-id="0665e-260">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="0665e-261">В этом примере создается новый тег карантина с именем Лимитедакцесс с использованием `$LimitedAccess` объекта Permissions, описанного и созданного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="0665e-261">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="0665e-262">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – куарантинетаг](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="0665e-262">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="0665e-263">Шаг 2: назначение тегов карантина поддерживаемым функциям</span><span class="sxs-lookup"><span data-stu-id="0665e-263">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="0665e-264">В _поддерживаемых_ функциях защиты, которые размещаются в карантине для сообщений или файлов (автоматически или как настраиваемое действие), можно назначить для доступных действий карантина тег карантина.</span><span class="sxs-lookup"><span data-stu-id="0665e-264">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="0665e-265">В приведенной ниже таблице описаны функции, в которых сообщения и доступность тегов карантина помещены в карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-265">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="0665e-266">Компонент</span><span class="sxs-lookup"><span data-stu-id="0665e-266">Feature</span></span>|<span data-ttu-id="0665e-267">Поддерживаются теги карантина?</span><span class="sxs-lookup"><span data-stu-id="0665e-267">Quarantine tags supported?</span></span>|<span data-ttu-id="0665e-268">Используемые по умолчанию теги карантина</span><span class="sxs-lookup"><span data-stu-id="0665e-268">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="0665e-269">[Политики защиты от нежелательной почты](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="0665e-269">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="0665e-270">**Спам** ( _спамактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-270">**Spam** ( _SpamAction_ )</span></span></li><li><span data-ttu-id="0665e-271">**Нежелательная почта высокой надежности** ( _хигхконфиденцеспамактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-271">**High confidence spam** ( _HighConfidenceSpamAction_ )</span></span></li><li><span data-ttu-id="0665e-272">**Фишинговый адрес электронной почты** ( _фишспамактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-272">**Phishing email** ( _PhishSpamAction_ )</span></span></li><li><span data-ttu-id="0665e-273">**Phishing-сообщения с высокой достоверностью** ( _хигхконфиденцефишактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-273">**High confidence phishing email** ( _HighConfidencePhishAction_ )</span></span></li><li><span data-ttu-id="0665e-274">**Массовая Электронная почта** ( _булкспамактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-274">**Bulk email** ( _BulkSpamAction_ )</span></span></li></ul>|<span data-ttu-id="0665e-275">Да</span><span class="sxs-lookup"><span data-stu-id="0665e-275">Yes</span></span>|<ul><li><span data-ttu-id="0665e-276">Дефаултспамтаг (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="0665e-276">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="0665e-277">Дефаулсигхконфспамтаг (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="0665e-277">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="0665e-278">Дефаултфиштаг (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="0665e-278">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="0665e-279">Дефаулсигхконффиштаг (нет доступа)</span><span class="sxs-lookup"><span data-stu-id="0665e-279">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="0665e-280">Дефаултбулктаг (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="0665e-280">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="0665e-281">Политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="0665e-281">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="0665e-282">[Защита от подделки](set-up-anti-phishing-policies.md#spoof-settings) ( _аусентикатионфаилактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-282">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) ( _AuthenticationFailAction_ )</span></span></li><li><span data-ttu-id="0665e-283">[Защита от олицетворения](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0665e-283">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="0665e-284">**Если с помощью олицетворенного пользователя отправляется сообщение электронной почты** ( _таржетедусерпротектионактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-284">**If email is sent by an impersonated user** ( _TargetedUserProtectionAction_ )</span></span></li><li><span data-ttu-id="0665e-285">**Если с олицетворенным доменом отправляется сообщение электронной почты** ( _таржетеддомаинпротектионактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-285">**If email is sent by an impersonated domain** ( _TargetedDomainProtectionAction_ )</span></span></li><li><span data-ttu-id="0665e-286">Аналитика почтовых **ящиков** \> **Если с помощью олицетворенного пользователя отправляется сообщение электронной почты** ( _маилбоксинтеллиженцепротектионактион_ )</span><span class="sxs-lookup"><span data-stu-id="0665e-286">**Mailbox intelligence** \> **If email is sent by an impersonated user** ( _MailboxIntelligenceProtectionAction_ )</span></span></li></ul></li></ul></ul>|<span data-ttu-id="0665e-287">Нет</span><span class="sxs-lookup"><span data-stu-id="0665e-287">No</span></span>|<span data-ttu-id="0665e-288">н/д</span><span class="sxs-lookup"><span data-stu-id="0665e-288">n/a</span></span>|
|<span data-ttu-id="0665e-289">[Политики защиты от вредоносных программ](configure-anti-malware-policies.md): все обнаруженные сообщения всегда хранятся в карантине.</span><span class="sxs-lookup"><span data-stu-id="0665e-289">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="0665e-290">Нет</span><span class="sxs-lookup"><span data-stu-id="0665e-290">No</span></span>|<span data-ttu-id="0665e-291">н/д</span><span class="sxs-lookup"><span data-stu-id="0665e-291">n/a</span></span>|
|[<span data-ttu-id="0665e-292">ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0665e-292">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="0665e-293">Нет</span><span class="sxs-lookup"><span data-stu-id="0665e-293">No</span></span>|<span data-ttu-id="0665e-294">н/д</span><span class="sxs-lookup"><span data-stu-id="0665e-294">n/a</span></span>|
|<span data-ttu-id="0665e-295">[Правила для поток обработки почты](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (также называемые правилами транспорта) с действием: **Доставка сообщения в размещенный карантин** ( _Карантин_ ).</span><span class="sxs-lookup"><span data-stu-id="0665e-295">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** ( _Quarantine_ ).</span></span>|<span data-ttu-id="0665e-296">Нет</span><span class="sxs-lookup"><span data-stu-id="0665e-296">No</span></span>|<span data-ttu-id="0665e-297">н/д</span><span class="sxs-lookup"><span data-stu-id="0665e-297">n/a</span></span>|
|

<span data-ttu-id="0665e-298"><sup>\*</sup> Параметры защиты от олицетворения доступны только в политиках защиты от фишинга в защитнике Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="0665e-298"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="0665e-299">Если вы довольны разрешениями для конечных пользователей, которые предоставляются тегами карантина по умолчанию, вам не нужно ничего делать.</span><span class="sxs-lookup"><span data-stu-id="0665e-299">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="0665e-300">Если вы хотите настроить возможности конечного пользователя (доступные кнопки) в уведомлениях о нежелательной почте или сообщениях в карантине, можно назначить настраиваемый тег карантина.</span><span class="sxs-lookup"><span data-stu-id="0665e-300">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="0665e-301">Назначение тегов карантина в политиках защиты от нежелательной почты в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0665e-301">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="0665e-302">Подробные инструкции по созданию и изменению политик защиты от нежелательной почты описаны в разделе [Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0665e-302">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="0665e-303">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** \> а затем выберите пункт **Защита от нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="0665e-303">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="0665e-304">Или откройте <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="0665e-304">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="0665e-305">Найдите и выберите существующую политику защиты от нежелательной почты, которую необходимо изменить, или создайте новую политику защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="0665e-305">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="0665e-306">В всплывающем окне сведения о политике разверните раздел **Нежелательная почта и групповые действия** .</span><span class="sxs-lookup"><span data-stu-id="0665e-306">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>
  
4. <span data-ttu-id="0665e-307">Если вы выбрали **сообщение в карантине** для действия доступной фильтрации нежелательной почты (вредоносности), поле **Применить метку политики карантина** будет доступно для выбора тега карантина для этого вредоносности.</span><span class="sxs-lookup"><span data-stu-id="0665e-307">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="0665e-308">**Note** : при создании новой политики значение пустого тега карантина для фильтрации нежелательной почты вредоносности указывает, что используется тег карантина по умолчанию для этого вредоносности.</span><span class="sxs-lookup"><span data-stu-id="0665e-308">**Note** : When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="0665e-309">При последующем изменении политики пустые значения заменяются на фактические имена тегов карантина по умолчанию, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="0665e-309">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>
  
   ![Выбор тегов карантина в политике защиты от нежелательной почты](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="0665e-311">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0665e-311">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="0665e-312">Назначение тегов карантина в политиках защиты от нежелательной почты в PowerShell</span><span class="sxs-lookup"><span data-stu-id="0665e-312">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="0665e-313">Если вы предпочитаете использовать PowerShell для назначения тегов карантина в политиках защиты от нежелательной почты, подключитесь к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="0665e-313">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="0665e-314">**Примечания** :</span><span class="sxs-lookup"><span data-stu-id="0665e-314">**Notes** :</span></span>

- <span data-ttu-id="0665e-315">Значение по умолчанию для параметра _хигхконфиденцефишактион_ — карантин, поэтому нет необходимости устанавливать действие карантина для обнаружения фишинга высокого уровня доверия в новых политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="0665e-315">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="0665e-316">Для всех остальных вердиктс фильтрации нежелательной почты в новых или существующих политиках защиты от нежелательной почты тег карантина применяется только в том случае, если значение действия — карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-316">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="0665e-317">Чтобы просмотреть значения действий в существующих политиках защиты от нежелательной почты, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0665e-317">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="0665e-318">Сведения о значениях действий по умолчанию и рекомендуемых значениях действий для стандартных и ограниченных [параметров политики защиты от нежелательной почты см EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="0665e-318">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="0665e-319">Фильтрация нежелательной почты вредоносности без соответствующего параметра тега карантина означает, что используется [тег карантина по умолчанию](#step-2-assign-a-quarantine-tag-to-supported-features) для этого вредоносности.</span><span class="sxs-lookup"><span data-stu-id="0665e-319">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="0665e-320">Необходимо заменить тег карантина по умолчанию на настраиваемый тег карантина, если вы хотите изменить функции конечного пользователя по умолчанию для сообщений, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-320">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="0665e-321">Для новой политики защиты от нежелательной почты в PowerShell требуется политика фильтрации нежелательной почты (параметры) с помощью командлета **New-HostedContentFilterPolicy** и нового правила фильтрации нежелательной почты (фильтры получателей) с помощью командлета **New-hostedcontentfilterrule используется** .</span><span class="sxs-lookup"><span data-stu-id="0665e-321">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="0665e-322">Инструкции можно найти [в разделе Использование PowerShell для создания политик защиты от нежелательной почты](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="0665e-322">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="0665e-323">В этом примере создается новая политика фильтрации нежелательной почты с именем Research Department со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="0665e-323">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="0665e-324">Действие для всех вердиктс фильтрации нежелательной почты настроено как карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-324">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="0665e-325">Настраиваемый тег карантина с именем "без доступа", который назначает разрешения " **нет на доступе** ", заменяет все теги карантина по умолчанию, которые по умолчанию не назначают разрешения на **доступ** .</span><span class="sxs-lookup"><span data-stu-id="0665e-325">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="0665e-326">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="0665e-326">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="0665e-327">В этом примере изменяется существующая политика фильтрации нежелательной почты с именем "Отдел кадров".</span><span class="sxs-lookup"><span data-stu-id="0665e-327">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="0665e-328">Для действия вредоносности карантина нежелательной почты задано значение карантин, и назначен настраиваемый тег карантина с именем "недоступно".</span><span class="sxs-lookup"><span data-stu-id="0665e-328">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="0665e-329">Дополнительные сведения о синтаксисе и параметрах см. в статье [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="0665e-329">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="0665e-330">Настройка глобальных параметров уведомлений в карантине в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0665e-330">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="0665e-331">Глобальные параметры для тегов карантина позволяют настраивать уведомления конечных пользователей о нежелательной почте, которые отправляются получателям сообщений, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-331">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="0665e-332">Для получения дополнительных сведений об этих уведомлениях обратитесь к разделу [уведомления о нежелательной почте конечных пользователей](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0665e-332">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="0665e-333">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** а затем выберите пункт **теги карантина**.</span><span class="sxs-lookup"><span data-stu-id="0665e-333">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="0665e-334">На странице **теги карантина** выберите **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="0665e-334">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="0665e-335">В открывшемся всплывающем окне **Параметры уведомления о карантине** настройте некоторые или все из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="0665e-335">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="0665e-336">**Использовать мою фирменную эмблему** : Выберите этот параметр, чтобы заменить логотип Майкрософт по умолчанию, который будет использоваться в начале уведомления о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="0665e-336">**Use my company logo** : Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="0665e-337">Прежде чем выполнить это действие, выполните инструкции, приведенные в статье [Настройка темы Microsoft 365 для Организации](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) , чтобы отправить настраиваемый логотип.</span><span class="sxs-lookup"><span data-stu-id="0665e-337">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="0665e-338">На приведенном ниже снимке экрана показан настраиваемый логотип в уведомлении о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0665e-338">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Настраиваемый логотип в уведомлении о нежелательной почте конечных пользователей](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="0665e-340">**Выбрать язык** : уведомления о нежелательной почте для конечных пользователей уже локализованы на основе языковых параметров получателя.</span><span class="sxs-lookup"><span data-stu-id="0665e-340">**Choose language** : End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="0665e-341">Можно указать настраиваемый текст на разных языках для **отображаемого имени** и значения **заявления об отказе** .</span><span class="sxs-lookup"><span data-stu-id="0665e-341">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="0665e-342">Выберите по крайней мере один язык в поле первый язык, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0665e-342">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="0665e-343">Чтобы выбрать несколько языков, нажмите кнопку **Добавить** после каждого из них.</span><span class="sxs-lookup"><span data-stu-id="0665e-343">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="0665e-344">В поле язык раздела отображаются все выбранные языки:</span><span class="sxs-lookup"><span data-stu-id="0665e-344">A section language box shows all of the languages that you've selected:</span></span>

     ![Выбранные языки в поле второго языка в параметрах уведомлений глобального карантина тегов карантина](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="0665e-346">**Отображаемое имя** : Настройка отображаемого имени отправителя, используемого в уведомлениях о нежелательной почте для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0665e-346">**Display name** : Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="0665e-347">Для каждого добавленного языка выберите язык в поле второй язык (не щелкайте X) и введите нужное текстовое значение в поле **Отображаемое имя** .</span><span class="sxs-lookup"><span data-stu-id="0665e-347">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="0665e-348">На приведенном ниже снимке экрана показано настраиваемое отображаемое имя в уведомлении о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0665e-348">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Настраиваемое имя отправителя в уведомлении о нежелательной почте конечных пользователей](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="0665e-350">**Заявление об отказе** : Добавление настраиваемого заявления об отказе в конец уведомлений конечных пользователей о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="0665e-350">**Disclaimer** : Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="0665e-351">Локализованный текст, **заявление об отказе от вашей организации:** всегда включается в первую очередь, за которым следует заданный текст.</span><span class="sxs-lookup"><span data-stu-id="0665e-351">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="0665e-352">Для каждого добавленного языка выберите язык в поле второй язык (не щелкайте X) и введите нужное текстовое значение в поле **заявление об отказе** .</span><span class="sxs-lookup"><span data-stu-id="0665e-352">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="0665e-353">На следующем снимке экрана показан настраиваемый заявление об отказе в уведомлении пользователя о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="0665e-353">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Настраиваемый отказ от ответственности в нижней части уведомления о нежелательной почте для конечных пользователей](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="0665e-355">Просмотр тегов карантина в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0665e-355">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="0665e-356">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** а затем выберите пункт **теги карантина**.</span><span class="sxs-lookup"><span data-stu-id="0665e-356">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="0665e-357">Чтобы просмотреть параметры встроенных или пользовательских тегов карантина, выберите тег карантина в списке (не устанавливайте флажок).</span><span class="sxs-lookup"><span data-stu-id="0665e-357">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="0665e-358">Чтобы просмотреть глобальные параметры, выберите **глобальные параметры** .</span><span class="sxs-lookup"><span data-stu-id="0665e-358">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="0665e-359">Просмотр тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="0665e-359">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="0665e-360">Если вы предпочитаете использовать PowerShell для просмотра тегов карантина, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="0665e-360">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="0665e-361">Чтобы просмотреть сводный список всех встроенных или настраиваемых тегов, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0665e-361">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="0665e-362">Чтобы просмотреть параметры встроенных или пользовательских тегов карантина, замените на \<TagName\> имя тега карантина и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0665e-362">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="0665e-363">Чтобы просмотреть глобальные параметры, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0665e-363">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="0665e-364">Дополнительные сведения о синтаксисе и параметрах см. в статье [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="0665e-364">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="0665e-365">Удаление тегов карантина в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0665e-365">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="0665e-366">**Примечания** :</span><span class="sxs-lookup"><span data-stu-id="0665e-366">**Notes** :</span></span>

- <span data-ttu-id="0665e-367">Встроенные теги карантина удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="0665e-367">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="0665e-368">Перед удалением настраиваемого тега карантина убедитесь, что он не используется.</span><span class="sxs-lookup"><span data-stu-id="0665e-368">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="0665e-369">Например, выполните следующую команду в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0665e-369">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="0665e-370">Если используется тег карантина, [замените назначенный тег карантина](#step-2-assign-a-quarantine-tag-to-supported-features) перед удалением.</span><span class="sxs-lookup"><span data-stu-id="0665e-370">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="0665e-371">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** а затем выберите пункт **теги карантина**.</span><span class="sxs-lookup"><span data-stu-id="0665e-371">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="0665e-372">На странице " **теги карантина** " выберите настраиваемый тег карантина, который нужно удалить, и **тег Delete Delete (удалить** ).</span><span class="sxs-lookup"><span data-stu-id="0665e-372">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="0665e-373">Нажмите кнопку **Удалить тег** в появившемся диалоговом окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="0665e-373">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="0665e-374">Удаление тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="0665e-374">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="0665e-375">Если вы предпочитаете использовать PowerShell для удаления настраиваемого тега карантина, замените \<TagName\> его именем тега карантина и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0665e-375">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="0665e-376">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – куарантинетаг](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="0665e-376">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="0665e-377">Сведения о разрешениях для тега карантина</span><span class="sxs-lookup"><span data-stu-id="0665e-377">Quarantine tag permission details</span></span>

<span data-ttu-id="0665e-378">В следующих разделах описывается влияние предустановленных групп разрешений и отдельных разрешений в сведениях о сообщениях, помещенных в карантин, и уведомлениях о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0665e-378">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="0665e-379">Предварительно заданные группы разрешений</span><span class="sxs-lookup"><span data-stu-id="0665e-379">Preset permissions groups</span></span>

<span data-ttu-id="0665e-380">Индивидуальные разрешения, которые включены в предварительно установленные группы разрешений, перечислены в таблице в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="0665e-380">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="0665e-381">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="0665e-381">No access</span></span>

<span data-ttu-id="0665e-382">Если в теге карантина назначаются разрешения **без доступа** (нет разрешений), пользователи по-прежнему получают некоторые базовые возможности:</span><span class="sxs-lookup"><span data-stu-id="0665e-382">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="0665e-383">**Сведения о сообщении в карантине** : кнопка **Просмотр заголовка сообщения** доступна всегда.</span><span class="sxs-lookup"><span data-stu-id="0665e-383">**Quarantined message details** : The **View message header** button is always available.</span></span>

  ![Доступные кнопки в сведениях о сообщении в карантине, если тег карантина предоставляет пользователю разрешения на доступ](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="0665e-385">**Уведомления конечных пользователей о нежелательной почте** : кнопка " **Рецензирование** ", которая принимает пользователя на сообщение в карантине, доступна всегда.</span><span class="sxs-lookup"><span data-stu-id="0665e-385">**End-user spam notifications** : The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет пользователю разрешения на доступ](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="0665e-387">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="0665e-387">Limited access</span></span>

<span data-ttu-id="0665e-388">Если тег карантина назначает разрешения **с ограниченным доступом** , пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="0665e-388">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="0665e-389">**Сведения о сообщении в карантине** : доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="0665e-389">**Quarantined message details** : The following buttons are available:</span></span>
  - <span data-ttu-id="0665e-390">**Выпуск запроса**</span><span class="sxs-lookup"><span data-stu-id="0665e-390">**Request release**</span></span>
  - <span data-ttu-id="0665e-391">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="0665e-391">**View message header**</span></span>
  - <span data-ttu-id="0665e-392">**Предварительная версия сообщения**</span><span class="sxs-lookup"><span data-stu-id="0665e-392">**Preview message**</span></span>
  - <span data-ttu-id="0665e-393">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="0665e-393">**Block sender**</span></span>
  - <span data-ttu-id="0665e-394">**Удалить из карантина**</span><span class="sxs-lookup"><span data-stu-id="0665e-394">**Remove from quarantine**</span></span>

  ![Доступные кнопки в сведениях о сообщении в карантине, если тег карантина предоставляет разрешения на ограниченный доступ пользователя](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="0665e-396">**Уведомления конечных пользователей о нежелательной почте** : доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="0665e-396">**End-user spam notifications** : The following buttons are available:</span></span>
  - <span data-ttu-id="0665e-397">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="0665e-397">**Block sender**</span></span>
  - <span data-ttu-id="0665e-398">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="0665e-398">**Review**</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет разрешения ограниченного доступа пользователя](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="0665e-400">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="0665e-400">Full access</span></span>

<span data-ttu-id="0665e-401">Если тег карантина назначает разрешения на **полный доступ** (все доступные разрешения), пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="0665e-401">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="0665e-402">**Сведения о сообщении в карантине** : доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="0665e-402">**Quarantined message details** : The following buttons are available:</span></span>
  - <span data-ttu-id="0665e-403">**Сообщение об освобождении**</span><span class="sxs-lookup"><span data-stu-id="0665e-403">**Release message**</span></span>
  - <span data-ttu-id="0665e-404">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="0665e-404">**View message header**</span></span>
  - <span data-ttu-id="0665e-405">**Предварительная версия сообщения**</span><span class="sxs-lookup"><span data-stu-id="0665e-405">**Preview message**</span></span>
  - <span data-ttu-id="0665e-406">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="0665e-406">**Block sender**</span></span>
  - <span data-ttu-id="0665e-407">**Разрешить отправителя**</span><span class="sxs-lookup"><span data-stu-id="0665e-407">**Allow sender**</span></span>
  - <span data-ttu-id="0665e-408">**Удалить из карантина**</span><span class="sxs-lookup"><span data-stu-id="0665e-408">**Remove from quarantine**</span></span>

  ![Доступные кнопки в сведениях о сообщении в карантине, если тег карантина предоставляет разрешения на полный доступ для пользователя](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="0665e-410">**Уведомления конечных пользователей о нежелательной почте** : доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="0665e-410">**End-user spam notifications** : The following buttons are available:</span></span>
  - <span data-ttu-id="0665e-411">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="0665e-411">**Block sender**</span></span>
  - <span data-ttu-id="0665e-412">**Выпуск**</span><span class="sxs-lookup"><span data-stu-id="0665e-412">**Release**</span></span>
  - <span data-ttu-id="0665e-413">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="0665e-413">**Review**</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет разрешения на полный доступ для пользователя](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="0665e-415">Индивидуальные разрешения</span><span class="sxs-lookup"><span data-stu-id="0665e-415">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="0665e-416">Помните, что пользователи всегда получают кнопки, описанные в разделе " [нет доступа](#no-access) ".</span><span class="sxs-lookup"><span data-stu-id="0665e-416">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="0665e-417">Эти кнопки не включены в описание отдельных разрешений.</span><span class="sxs-lookup"><span data-stu-id="0665e-417">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="0665e-418">Разрешение "разрешить отправителю"</span><span class="sxs-lookup"><span data-stu-id="0665e-418">Allow sender permission</span></span>

<span data-ttu-id="0665e-419">Разрешение " **Разрешить отправителю** " ( _пермиссионтоалловсендер_ ) управляет доступом к кнопке, позволяющей пользователям легко добавить отправителя сообщения, помещенного в карантин, в список надежных отправителей.</span><span class="sxs-lookup"><span data-stu-id="0665e-419">The **Allow sender** permission ( _PermissionToAllowSender_ ) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="0665e-420">**Сведения о сообщении в карантине** :</span><span class="sxs-lookup"><span data-stu-id="0665e-420">**Quarantined message details** :</span></span>
  - <span data-ttu-id="0665e-421">**Разрешить отправителю разрешить** отправку: доступна кнопка **Разрешить отправителя** .</span><span class="sxs-lookup"><span data-stu-id="0665e-421">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="0665e-422">Разрешить отправку **отправителей** отключено: кнопка " **Разрешить отправителя** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-422">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="0665e-423">**Уведомления конечных пользователей о нежелательной почте** не вступают в противодействия.</span><span class="sxs-lookup"><span data-stu-id="0665e-423">**End-user spam notifications** : No effect.</span></span>

<span data-ttu-id="0665e-424">Дополнительные сведения о списке надежных отправителей можно найти в статье [предотвращение блокирования надежных отправителей](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) и [использование Exchange Online PowerShell для настройки коллекции списков надежных отправителей в почтовом ящике](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="0665e-424">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="0665e-425">Блокировать разрешение отправителей</span><span class="sxs-lookup"><span data-stu-id="0665e-425">Block sender permission</span></span>

<span data-ttu-id="0665e-426">Разрешение **блокировать отправителя** ( _пермиссионтоблокксендер_ ) управляет доступом к кнопке, позволяющей пользователям легко добавить отправителя сообщения, помещенного в карантин, в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="0665e-426">The **Block sender** permission ( _PermissionToBlockSender_ ) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="0665e-427">**Сведения о сообщении в карантине** :</span><span class="sxs-lookup"><span data-stu-id="0665e-427">**Quarantined message details** :</span></span>
  - <span data-ttu-id="0665e-428">**Блокировать разрешение отправителей** : кнопка " **блокировать отправителя** " доступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-428">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="0665e-429">**Блокировать разрешение отправителя** отключено: кнопка " **блокировать отправителя** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="0665e-430">**Уведомления конечных пользователей о нежелательной почте** :</span><span class="sxs-lookup"><span data-stu-id="0665e-430">**End-user spam notifications** :</span></span>
  - <span data-ttu-id="0665e-431">**Блокировать разрешение отправителя** отключено: кнопка " **блокировать отправителя** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-431">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="0665e-432">**Блокировать разрешение отправителей** : кнопка " **блокировать отправителя** " доступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-432">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="0665e-433">Дополнительные сведения о списке заблокированных отправителей можно узнать в статье [Блокировать сообщения от кого-либо с](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) [помощью Exchange Online PowerShell для настройки коллекции списков надежных отправителей для почтового ящика](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="0665e-433">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="0665e-434">Разрешения на удаление</span><span class="sxs-lookup"><span data-stu-id="0665e-434">Delete permission</span></span>

<span data-ttu-id="0665e-435">Разрешение **Delete** ( _пермиссионтоделете_ ) управляет возможностью пользователей удалять свои сообщения (сообщения, в которых пользователь является получателем) из карантина.</span><span class="sxs-lookup"><span data-stu-id="0665e-435">The **Delete** permission ( _PermissionToDelete_ ) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="0665e-436">**Сведения о сообщении в карантине** :</span><span class="sxs-lookup"><span data-stu-id="0665e-436">**Quarantined message details** :</span></span>
  - <span data-ttu-id="0665e-437">Разрешение на **Удаление** включено: доступна кнопка **удалить из карантина** .</span><span class="sxs-lookup"><span data-stu-id="0665e-437">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="0665e-438">Разрешение на **Удаление** отключено: кнопка **удалить из карантина** недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-438">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="0665e-439">**Уведомления конечных пользователей о нежелательной почте** не вступают в противодействия.</span><span class="sxs-lookup"><span data-stu-id="0665e-439">**End-user spam notifications** : No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="0665e-440">Разрешение на предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="0665e-440">Preview permission</span></span>

<span data-ttu-id="0665e-441">Разрешение на **Предварительный просмотр** ( _пермиссионтопревиев_ ) управляет возможностью пользователей просматривать сообщения в карантине.</span><span class="sxs-lookup"><span data-stu-id="0665e-441">The **Preview** permission ( _PermissionToPreview_ ) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="0665e-442">**Сведения о сообщении в карантине** :</span><span class="sxs-lookup"><span data-stu-id="0665e-442">**Quarantined message details** :</span></span>
  - <span data-ttu-id="0665e-443">Разрешение на **Предварительный просмотр** включен: кнопка **предварительного просмотра сообщения** доступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-443">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="0665e-444">Разрешение на **Просмотр** отключено: кнопка " **просмотреть сообщение** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-444">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="0665e-445">**Уведомления конечных пользователей о нежелательной почте** не вступают в противодействия.</span><span class="sxs-lookup"><span data-stu-id="0665e-445">**End-user spam notifications** : No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="0665e-446">Разрешить получателям освобождать сообщение от разрешения "карантин"</span><span class="sxs-lookup"><span data-stu-id="0665e-446">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="0665e-447">**Разрешить получателям выпустить сообщение из карантинного** разрешения ( _пермиссионторелеасе_ ) управляет возможностью пользователей напрямую освобождать сообщения, помещенные на карантин, и без утверждения администратора.</span><span class="sxs-lookup"><span data-stu-id="0665e-447">The **Allow recipients to release a message from quarantine** permission ( _PermissionToRelease_ ) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="0665e-448">**Сведения о сообщении в карантине** :</span><span class="sxs-lookup"><span data-stu-id="0665e-448">**Quarantined message details** :</span></span>
  - <span data-ttu-id="0665e-449">Разрешение включено: доступна кнопка **выпустить сообщение** .</span><span class="sxs-lookup"><span data-stu-id="0665e-449">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="0665e-450">Разрешение отключено: кнопка **освобождения сообщения** недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-450">Permission disabled: The **Release message** button is not available.</span></span>
  
- <span data-ttu-id="0665e-451">**Уведомления конечных пользователей о нежелательной почте** :</span><span class="sxs-lookup"><span data-stu-id="0665e-451">**End-user spam notifications** :</span></span>
  - <span data-ttu-id="0665e-452">Разрешение включено: доступна кнопка **выпустить** .</span><span class="sxs-lookup"><span data-stu-id="0665e-452">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="0665e-453">Разрешение отключено: кнопка " **выпустить** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-453">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="0665e-454">Разрешить получателям запрашивать разрешение на отправку сообщения из карантина</span><span class="sxs-lookup"><span data-stu-id="0665e-454">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="0665e-455">**Разрешить получателям запрашивать сообщение из карантинного** разрешения ( _пермиссионторекуестрелеасе_ ) управляет возможностью пользователей _запрашивать_ выпуск сообщений, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="0665e-455">The **Allow recipients to request a message to be released from quarantine** permission ( _PermissionToRequestRelease_ ) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="0665e-456">Сообщение будет выпущено только после того, как администратор утвердит запрос.</span><span class="sxs-lookup"><span data-stu-id="0665e-456">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="0665e-457">**Сведения о сообщении в карантине** :</span><span class="sxs-lookup"><span data-stu-id="0665e-457">**Quarantined message details** :</span></span>
  - <span data-ttu-id="0665e-458">Разрешение включено: доступна кнопка **выпустить запрос** .</span><span class="sxs-lookup"><span data-stu-id="0665e-458">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="0665e-459">Разрешение отключено: кнопка " **запрос на выпуск** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-459">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="0665e-460">**Уведомления конечных пользователей о нежелательной почте** : кнопка " **выпуск** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="0665e-460">**End-user spam notifications** : The **Release** button is not available.</span></span>
