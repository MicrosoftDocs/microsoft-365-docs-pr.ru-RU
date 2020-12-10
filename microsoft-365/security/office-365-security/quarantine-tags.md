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
ms.openlocfilehash: 498a5f45fa62481f7f4f8dfe5ece8a51a038f99a
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616012"
---
# <a name="quarantine-tags"></a><span data-ttu-id="be95a-103">Теги карантина</span><span class="sxs-lookup"><span data-stu-id="be95a-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="be95a-104">Функции, описанные в этой статье, в настоящее время доступны для всех и могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="be95a-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="be95a-105">Теги карантина в Exchange Online Protection (EOP) позволяют администраторам контролировать, какие пользователи могут выполнять действия с сообщениями в карантине в зависимости от того, как сообщение поступило в карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="be95a-106">В EOP традиционно разрешены или запрещены определенные уровни взаимодействия для сообщений в [карантине](find-and-release-quarantined-messages-as-a-user.md) и [уведомления о нежелательной почте конечных пользователей](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="be95a-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="be95a-107">Например, конечные пользователи могут просматривать и освобождать сообщения, помещенные в карантин с помощью фильтрации нежелательной почты в качестве нежелательной почты или массовых сообщений, но не могут просматривать или освобождать сообщения, помещенные в карантин в качестве высокодостоверных фишинга.</span><span class="sxs-lookup"><span data-stu-id="be95a-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="be95a-108">Для [поддерживаемых функций защиты](#step-2-assign-a-quarantine-tag-to-supported-features)Теги карантина указывают, какие пользователи могут выполнять в сообщениях уведомления о нежелательной почте, а также в карантинных сообщениях в карантине (сообщения, в которых пользователь является получателем).</span><span class="sxs-lookup"><span data-stu-id="be95a-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="be95a-109">Теги карантина по умолчанию автоматически назначаются для применения исторических возможностей для конечных пользователей в сообщениях, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="be95a-110">Можно также создать и назначить пользовательские теги карантина, чтобы разрешить или запретить конечным пользователям выполнять определенные действия в сообщениях, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="be95a-111">Индивидуальные разрешения объединяются в следующие предварительно заданные группы разрешений:</span><span class="sxs-lookup"><span data-stu-id="be95a-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="be95a-112">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="be95a-112">No access</span></span>
- <span data-ttu-id="be95a-113">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="be95a-113">Limited access</span></span>
- <span data-ttu-id="be95a-114">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="be95a-114">Full access</span></span>

<span data-ttu-id="be95a-115">В следующей таблице описаны доступные индивидуальные разрешения, а также включенные и не включенные в предустановленные группы разрешений.</span><span class="sxs-lookup"><span data-stu-id="be95a-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="be95a-116">Разрешение</span><span class="sxs-lookup"><span data-stu-id="be95a-116">Permission</span></span>|<span data-ttu-id="be95a-117">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="be95a-117">No access</span></span>|<span data-ttu-id="be95a-118">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="be95a-118">Limited access</span></span>|<span data-ttu-id="be95a-119">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="be95a-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="be95a-120">**Разрешить отправителя** (_пермиссионтоалловсендер_)</span><span class="sxs-lookup"><span data-stu-id="be95a-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="be95a-122">**Блокировка отправителя** (_пермиссионтоблокксендер_)</span><span class="sxs-lookup"><span data-stu-id="be95a-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="be95a-125">**Delete** (_пермиссионтоделете_)</span><span class="sxs-lookup"><span data-stu-id="be95a-125">**Delete** (_PermissionToDelete_)</span></span>||![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="be95a-128">**Предварительная версия** (_пермиссионтопревиев_)</span><span class="sxs-lookup"><span data-stu-id="be95a-128">**Preview** (_PermissionToPreview_)</span></span>||![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="be95a-131">**Разрешить получателям выпустить сообщение из карантина** (_пермиссионторелеасе_)</span><span class="sxs-lookup"><span data-stu-id="be95a-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="be95a-133">**Разрешить получателям запрашивать сообщение для освобождения из карантина** (_пермиссионторекуестрелеасе_)</span><span class="sxs-lookup"><span data-stu-id="be95a-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Галочка](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

<span data-ttu-id="be95a-135">Если вы не хотите использовать разрешения по умолчанию в предустановленных группах разрешений, вы можете использовать настраиваемые разрешения при создании или изменении пользовательских тегов карантина.</span><span class="sxs-lookup"><span data-stu-id="be95a-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="be95a-136">Дополнительные сведения о том, что делает каждый из разрешений, можно найти в разделе [сведения о разрешениях для тегов карантина](#quarantine-tag-permission-details) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="be95a-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="be95a-137">Теги карантина создаются и назначаются в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками Exchange Online; изолированный EOP PowerShell в организациях EOP без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="be95a-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="be95a-138">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="be95a-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="be95a-139">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="be95a-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="be95a-140">Чтобы перейти непосредственно на страницу **теги карантина** , откройте страницу <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="be95a-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="be95a-141">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="be95a-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="be95a-142">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="be95a-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="be95a-143">Чтобы просматривать, создавать, изменять или удалять теги карантина, необходимо быть участником ролей " **Управление организацией** " или " **администратор безопасности** " в [центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="be95a-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="be95a-144">Шаг 1: Создание тегов карантина в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="be95a-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="be95a-145">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** а затем выберите пункт **теги карантина**.</span><span class="sxs-lookup"><span data-stu-id="be95a-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="be95a-146">На странице " **теги карантина** " выберите **Добавить настраиваемый тег**.</span><span class="sxs-lookup"><span data-stu-id="be95a-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="be95a-147">Откроется мастер **создания нового тега** .</span><span class="sxs-lookup"><span data-stu-id="be95a-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="be95a-148">На странице **имя тега** введите краткое, но уникальное имя в поле **имя тега** .</span><span class="sxs-lookup"><span data-stu-id="be95a-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="be95a-149">Вам потребуется определить и выбрать тег по имени на следующих этапах.</span><span class="sxs-lookup"><span data-stu-id="be95a-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="be95a-150">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="be95a-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="be95a-151">На странице **доступа к сообщениям получателя** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="be95a-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="be95a-152">**Нет доступа**</span><span class="sxs-lookup"><span data-stu-id="be95a-152">**No access**</span></span>
   - <span data-ttu-id="be95a-153">**Ограниченный доступ**</span><span class="sxs-lookup"><span data-stu-id="be95a-153">**Limited access**</span></span>
   - <span data-ttu-id="be95a-154">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="be95a-154">**Full access**</span></span>

   <span data-ttu-id="be95a-155">Отдельные разрешения, включенные в эти группы разрешений, описаны ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="be95a-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="be95a-156">Чтобы указать настраиваемые разрешения, выберите **задать определенный доступ (дополнительно)** и настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="be95a-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="be95a-157">**Выберите параметр действия при выпуске**: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="be95a-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="be95a-158">**Не выпустите действие**: это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="be95a-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="be95a-159">**Разрешить получателям выпустить сообщение из карантина**</span><span class="sxs-lookup"><span data-stu-id="be95a-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="be95a-160">**Разрешение получателям запросить отправку сообщения из карантина**</span><span class="sxs-lookup"><span data-stu-id="be95a-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="be95a-161">**Выберите дополнительные действия получатели могут принимать участие в сообщениях, помещенных в карантин**: выберите некоторые, все или ничего из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="be95a-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="be95a-162">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="be95a-162">**Delete**</span></span>
       - <span data-ttu-id="be95a-163">**Предварительная версия**</span><span class="sxs-lookup"><span data-stu-id="be95a-163">**Preview**</span></span>
       - <span data-ttu-id="be95a-164">**Разрешить отправителя**</span><span class="sxs-lookup"><span data-stu-id="be95a-164">**Allow sender**</span></span>
       - <span data-ttu-id="be95a-165">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="be95a-165">**Block sender**</span></span>

   <span data-ttu-id="be95a-166">Эти разрешения и их последствия для сообщений, помещенных в карантин, и уведомления о нежелательной почте приведены в разделе [сведения о разрешениях для тегов карантина](#quarantine-tag-permission-details) , приведенных далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="be95a-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="be95a-167">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="be95a-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="be95a-168">На появившейся странице **сводки** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="be95a-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="be95a-169">Для изменения каждого параметра можно нажать кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="be95a-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="be95a-170">По завершении нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="be95a-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="be95a-171">Нажмите кнопку **done (Готово** ) на появившейся странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="be95a-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="be95a-172">Теперь вы готовы присвоить метку карантина функции карантина, как описано в разделе [Шаг 2](#step-2-assign-a-quarantine-tag-to-supported-features) .</span><span class="sxs-lookup"><span data-stu-id="be95a-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="be95a-173">Создание тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="be95a-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="be95a-174">Если вы предпочитаете создавать теги карантина с помощью PowerShell, подключитесь к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте командлет **New-куарантинетаг** .</span><span class="sxs-lookup"><span data-stu-id="be95a-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="be95a-175">Существует два разных способа выбора:</span><span class="sxs-lookup"><span data-stu-id="be95a-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="be95a-176">Используйте параметр _ендусеркуарантинепермиссионсвалуе_ .</span><span class="sxs-lookup"><span data-stu-id="be95a-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="be95a-177">Используйте параметр _ендусеркуарантинепермиссионс_ .</span><span class="sxs-lookup"><span data-stu-id="be95a-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="be95a-178">Эти методы описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="be95a-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="be95a-179">Использование параметра Ендусеркуарантинепермиссионсвалуе</span><span class="sxs-lookup"><span data-stu-id="be95a-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="be95a-180">Чтобы создать тег карантина с помощью параметра _ендусеркуарантинепермиссионсвалуе_ , используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="be95a-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="be95a-181">Параметр _ендусеркуарантинепермиссионсвалуе_ использует десятичное значение, которое преобразуется из двоичного значения.</span><span class="sxs-lookup"><span data-stu-id="be95a-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="be95a-182">Двоичное значение соответствует доступным карантинным разрешениям конечного пользователя в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="be95a-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="be95a-183">Для каждого разрешения значение 1 равно true, а значение 0 равно false.</span><span class="sxs-lookup"><span data-stu-id="be95a-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="be95a-184">Обязательный порядок и значения для каждого отдельного разрешения в предустановленных группах разрешений описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="be95a-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="be95a-185">Разрешение</span><span class="sxs-lookup"><span data-stu-id="be95a-185">Permission</span></span>|<span data-ttu-id="be95a-186">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="be95a-186">No access</span></span>|<span data-ttu-id="be95a-187">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="be95a-187">Limited access</span></span>|<span data-ttu-id="be95a-188">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="be95a-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="be95a-189">пермиссионтоалловсендер</span><span class="sxs-lookup"><span data-stu-id="be95a-189">PermissionToAllowSender</span></span>|<span data-ttu-id="be95a-190">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-190">0</span></span>|<span data-ttu-id="be95a-191">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-191">0</span></span>|<span data-ttu-id="be95a-192">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-192">1</span></span>|
|<span data-ttu-id="be95a-193">пермиссионтоблокксендер</span><span class="sxs-lookup"><span data-stu-id="be95a-193">PermissionToBlockSender</span></span>|<span data-ttu-id="be95a-194">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-194">0</span></span>|<span data-ttu-id="be95a-195">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-195">1</span></span>|<span data-ttu-id="be95a-196">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-196">1</span></span>|
|<span data-ttu-id="be95a-197">пермиссионтоделете</span><span class="sxs-lookup"><span data-stu-id="be95a-197">PermissionToDelete</span></span>|<span data-ttu-id="be95a-198">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-198">0</span></span>|<span data-ttu-id="be95a-199">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-199">1</span></span>|<span data-ttu-id="be95a-200">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-200">1</span></span>|
|<span data-ttu-id="be95a-201">пермиссионтодовнлоад<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="be95a-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="be95a-202">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-202">0</span></span>|<span data-ttu-id="be95a-203">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-203">0</span></span>|<span data-ttu-id="be95a-204">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-204">0</span></span>|
|<span data-ttu-id="be95a-205">пермиссионтопревиев</span><span class="sxs-lookup"><span data-stu-id="be95a-205">PermissionToPreview</span></span>|<span data-ttu-id="be95a-206">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-206">0</span></span>|<span data-ttu-id="be95a-207">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-207">1</span></span>|<span data-ttu-id="be95a-208">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-208">1</span></span>|
|<span data-ttu-id="be95a-209">пермиссионторелеасе<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="be95a-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="be95a-210">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-210">0</span></span>|<span data-ttu-id="be95a-211">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-211">0</span></span>|<span data-ttu-id="be95a-212">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-212">1</span></span>|
|<span data-ttu-id="be95a-213">пермиссионторекуестрелеасе<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="be95a-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="be95a-214">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-214">0</span></span>|<span data-ttu-id="be95a-215">1 </span><span class="sxs-lookup"><span data-stu-id="be95a-215">1</span></span>|<span data-ttu-id="be95a-216">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-216">0</span></span>|
|<span data-ttu-id="be95a-217">пермиссионтовиевхеадер<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="be95a-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="be95a-218">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-218">0</span></span>|<span data-ttu-id="be95a-219">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-219">0</span></span>|<span data-ttu-id="be95a-220">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-220">0</span></span>|
|<span data-ttu-id="be95a-221">Двоичное значение</span><span class="sxs-lookup"><span data-stu-id="be95a-221">Binary value</span></span>|<span data-ttu-id="be95a-222">00000001</span><span class="sxs-lookup"><span data-stu-id="be95a-222">00000000</span></span>|<span data-ttu-id="be95a-223">01101010</span><span class="sxs-lookup"><span data-stu-id="be95a-223">01101010</span></span>|<span data-ttu-id="be95a-224">11101100</span><span class="sxs-lookup"><span data-stu-id="be95a-224">11101100</span></span>|
|<span data-ttu-id="be95a-225">Используемое десятичное значение</span><span class="sxs-lookup"><span data-stu-id="be95a-225">Decimal value to use</span></span>|<span data-ttu-id="be95a-226">нуль</span><span class="sxs-lookup"><span data-stu-id="be95a-226">0</span></span>|<span data-ttu-id="be95a-227">106</span><span class="sxs-lookup"><span data-stu-id="be95a-227">106</span></span>|<span data-ttu-id="be95a-228">236</span><span class="sxs-lookup"><span data-stu-id="be95a-228">236</span></span>|

<span data-ttu-id="be95a-229"><sup>\*</sup> В настоящее время это значение всегда равно 0.</span><span class="sxs-lookup"><span data-stu-id="be95a-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="be95a-230">Для Пермиссионтовиевхеадер значение 0 не скрывает кнопку **Просмотр заголовка сообщения** в сведениях из помещенного в карантин сообщения (кнопка доступна всегда).</span><span class="sxs-lookup"><span data-stu-id="be95a-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="be95a-231"><sup>\*\*</sup> Не устанавливайте оба этих значения равными 1.</span><span class="sxs-lookup"><span data-stu-id="be95a-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="be95a-232">Задайте для одного из них значение 1, а другое — значение 0.</span><span class="sxs-lookup"><span data-stu-id="be95a-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="be95a-233">В этом примере показано создание нового имени тега карантина без доступа, который назначает разрешения без доступа, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="be95a-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="be95a-234">Для разрешений с ограниченным доступом используйте значение 106.</span><span class="sxs-lookup"><span data-stu-id="be95a-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="be95a-235">Для разрешений полного доступа используйте значение 236.</span><span class="sxs-lookup"><span data-stu-id="be95a-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="be95a-236">Для настраиваемых разрешений используйте предыдущую таблицу, чтобы получить двоичное значение, соответствующее требуемым разрешениям.</span><span class="sxs-lookup"><span data-stu-id="be95a-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="be95a-237">Преобразуйте двоичное значение в десятичное и используйте десятичное значение для параметра _ендусеркуарантинепермиссионсвалуе_ .</span><span class="sxs-lookup"><span data-stu-id="be95a-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="be95a-238">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – куарантинетаг](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="be95a-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="be95a-239">Использование параметра Ендусеркуарантинепермиссионс</span><span class="sxs-lookup"><span data-stu-id="be95a-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="be95a-240">Чтобы создать тег карантина с помощью параметра _ендусеркуарантинепермиссионсвалуе_ , выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="be95a-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="be95a-241">О.</span><span class="sxs-lookup"><span data-stu-id="be95a-241">A.</span></span> <span data-ttu-id="be95a-242">Сохраните объект разрешений карантина в переменной с помощью командлета **New – куарантинепермиссионс** .</span><span class="sxs-lookup"><span data-stu-id="be95a-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="be95a-243">B.</span><span class="sxs-lookup"><span data-stu-id="be95a-243">B.</span></span> <span data-ttu-id="be95a-244">Используйте переменную в качестве значения _ендусеркуарантинепермиссионс_ в команде **New – куарантинетаг** .</span><span class="sxs-lookup"><span data-stu-id="be95a-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="be95a-245">Шаг A: сохранение объекта разрешений карантина в переменной</span><span class="sxs-lookup"><span data-stu-id="be95a-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="be95a-246">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="be95a-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="be95a-247">Значение по умолчанию для всех неиспользуемых параметров `$false` , поэтому необходимо использовать только те параметры, для которых нужно задать значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="be95a-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="be95a-248">В следующих примерах показано, как создавать объекты разрешений, соответствующие предварительно заданным группам разрешений:</span><span class="sxs-lookup"><span data-stu-id="be95a-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="be95a-249">**Нет доступа**:</span><span class="sxs-lookup"><span data-stu-id="be95a-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="be95a-250">**Ограниченный доступ**:</span><span class="sxs-lookup"><span data-stu-id="be95a-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="be95a-251">**Полный доступ**:</span><span class="sxs-lookup"><span data-stu-id="be95a-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="be95a-252">Чтобы просмотреть заданные значения, выполните имя переменной в виде команды (например, выполните команду `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="be95a-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="be95a-253">Для настраиваемых разрешений не устанавливайте для параметров _пермиссионторелеасе_ и _пермиссионторекуестрелеасе_ значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="be95a-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="be95a-254">Задайте для параметра значение `$true` and и оставьте значение `$false` , а не оба `$false` .</span><span class="sxs-lookup"><span data-stu-id="be95a-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="be95a-255">Вы также можете изменить существующую переменную объекта Permissions после создания, но перед ее использованием с помощью командлета **Set – куарантинепермиссионс** .</span><span class="sxs-lookup"><span data-stu-id="be95a-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="be95a-256">Подробные сведения о синтаксисе и параметрах можно найти в статье [New/куарантинепермиссионс](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) и [Set – куарантинепермиссионс](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="be95a-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="be95a-257">Шаг б: использование переменной в команде New-QuarantineTag</span><span class="sxs-lookup"><span data-stu-id="be95a-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="be95a-258">После создания и сохранения объекта Permissions в переменной используйте значение параметра _ендусеркуарантинепермиссион_ в следующей команде **New – куарантинетаг** :</span><span class="sxs-lookup"><span data-stu-id="be95a-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="be95a-259">В этом примере создается новый тег карантина с именем Лимитедакцесс с использованием `$LimitedAccess` объекта Permissions, описанного и созданного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="be95a-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="be95a-260">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – куарантинетаг](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="be95a-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="be95a-261">Шаг 2: назначение тегов карантина поддерживаемым функциям</span><span class="sxs-lookup"><span data-stu-id="be95a-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="be95a-262">В _поддерживаемых_ функциях защиты, которые размещаются в карантине для сообщений или файлов (автоматически или как настраиваемое действие), можно назначить для доступных действий карантина тег карантина.</span><span class="sxs-lookup"><span data-stu-id="be95a-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="be95a-263">В приведенной ниже таблице описаны функции, в которых сообщения и доступность тегов карантина помещены в карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="be95a-264">Компонент</span><span class="sxs-lookup"><span data-stu-id="be95a-264">Feature</span></span>|<span data-ttu-id="be95a-265">Поддерживаются теги карантина?</span><span class="sxs-lookup"><span data-stu-id="be95a-265">Quarantine tags supported?</span></span>|<span data-ttu-id="be95a-266">Используемые по умолчанию теги карантина</span><span class="sxs-lookup"><span data-stu-id="be95a-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="be95a-267">[Политики защиты от нежелательной почты](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="be95a-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="be95a-268">**Спам** (_спамактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="be95a-269">**Нежелательная почта высокой надежности** (_хигхконфиденцеспамактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="be95a-270">**Фишинговый адрес электронной почты** (_фишспамактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="be95a-271">**Phishing-сообщения с высокой достоверностью** (_хигхконфиденцефишактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="be95a-272">**Массовая Электронная почта** (_булкспамактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="be95a-273">Да</span><span class="sxs-lookup"><span data-stu-id="be95a-273">Yes</span></span>|<ul><li><span data-ttu-id="be95a-274">Дефаултспамтаг (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="be95a-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="be95a-275">Дефаулсигхконфспамтаг (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="be95a-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="be95a-276">Дефаултфиштаг (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="be95a-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="be95a-277">Дефаулсигхконффиштаг (нет доступа)</span><span class="sxs-lookup"><span data-stu-id="be95a-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="be95a-278">Дефаултбулктаг (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="be95a-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="be95a-279">Политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="be95a-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="be95a-280">[Защита от подделки](set-up-anti-phishing-policies.md#spoof-settings) (_аусентикатионфаилактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="be95a-281">[Защита от олицетворения](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="be95a-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="be95a-282">**Если с помощью олицетворенного пользователя отправляется сообщение электронной почты** (_таржетедусерпротектионактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="be95a-283">**Если с олицетворенным доменом отправляется сообщение электронной почты** (_таржетеддомаинпротектионактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="be95a-284">Аналитика почтовых **ящиков** \> **Если с помощью олицетворенного пользователя отправляется сообщение электронной почты** (_маилбоксинтеллиженцепротектионактион_)</span><span class="sxs-lookup"><span data-stu-id="be95a-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="be95a-285">Нет</span><span class="sxs-lookup"><span data-stu-id="be95a-285">No</span></span>|<span data-ttu-id="be95a-286">н/д</span><span class="sxs-lookup"><span data-stu-id="be95a-286">n/a</span></span>|
|<span data-ttu-id="be95a-287">[Политики защиты от вредоносных программ](configure-anti-malware-policies.md): все обнаруженные сообщения всегда хранятся в карантине.</span><span class="sxs-lookup"><span data-stu-id="be95a-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="be95a-288">Нет</span><span class="sxs-lookup"><span data-stu-id="be95a-288">No</span></span>|<span data-ttu-id="be95a-289">н/д</span><span class="sxs-lookup"><span data-stu-id="be95a-289">n/a</span></span>|
|[<span data-ttu-id="be95a-290">ATP для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be95a-290">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="be95a-291">Нет</span><span class="sxs-lookup"><span data-stu-id="be95a-291">No</span></span>|<span data-ttu-id="be95a-292">н/д</span><span class="sxs-lookup"><span data-stu-id="be95a-292">n/a</span></span>|
|<span data-ttu-id="be95a-293">[Правила для поток обработки почты](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (также называемые правилами транспорта) с действием: **Доставка сообщения в размещенный карантин** (_Карантин_).</span><span class="sxs-lookup"><span data-stu-id="be95a-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="be95a-294">Нет</span><span class="sxs-lookup"><span data-stu-id="be95a-294">No</span></span>|<span data-ttu-id="be95a-295">н/д</span><span class="sxs-lookup"><span data-stu-id="be95a-295">n/a</span></span>|
|

<span data-ttu-id="be95a-296"><sup>\*</sup> Параметры защиты от олицетворения доступны только в политиках защиты от фишинга в защитнике Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="be95a-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="be95a-297">Если вы довольны разрешениями для конечных пользователей, которые предоставляются тегами карантина по умолчанию, вам не нужно ничего делать.</span><span class="sxs-lookup"><span data-stu-id="be95a-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="be95a-298">Если вы хотите настроить возможности конечного пользователя (доступные кнопки) в уведомлениях о нежелательной почте или сообщениях в карантине, можно назначить настраиваемый тег карантина.</span><span class="sxs-lookup"><span data-stu-id="be95a-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="be95a-299">Назначение тегов карантина в политиках защиты от нежелательной почты в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="be95a-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="be95a-300">Подробные инструкции по созданию и изменению политик защиты от нежелательной почты описаны в разделе [Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="be95a-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="be95a-301">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** \> а затем выберите пункт **Защита от нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="be95a-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="be95a-302">Или откройте <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="be95a-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="be95a-303">Найдите и выберите существующую политику защиты от нежелательной почты, которую необходимо изменить, или создайте новую политику защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="be95a-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="be95a-304">В всплывающем окне сведения о политике разверните раздел **Нежелательная почта и групповые действия** .</span><span class="sxs-lookup"><span data-stu-id="be95a-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="be95a-305">Если вы выбрали **сообщение в карантине** для действия доступной фильтрации нежелательной почты (вредоносности), поле **Применить метку политики карантина** будет доступно для выбора тега карантина для этого вредоносности.</span><span class="sxs-lookup"><span data-stu-id="be95a-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="be95a-306">**Note**: при создании новой политики значение пустого тега карантина для фильтрации нежелательной почты вредоносности указывает, что используется тег карантина по умолчанию для этого вредоносности.</span><span class="sxs-lookup"><span data-stu-id="be95a-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="be95a-307">При последующем изменении политики пустые значения заменяются на фактические имена тегов карантина по умолчанию, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="be95a-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Выбор тегов карантина в политике защиты от нежелательной почты](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="be95a-309">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="be95a-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="be95a-310">Назначение тегов карантина в политиках защиты от нежелательной почты в PowerShell</span><span class="sxs-lookup"><span data-stu-id="be95a-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="be95a-311">Если вы предпочитаете использовать PowerShell для назначения тегов карантина в политиках защиты от нежелательной почты, подключитесь к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="be95a-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="be95a-312">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="be95a-312">**Notes**:</span></span>

- <span data-ttu-id="be95a-313">Значение по умолчанию для параметра _хигхконфиденцефишактион_ — карантин, поэтому нет необходимости устанавливать действие карантина для обнаружения фишинга высокого уровня доверия в новых политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="be95a-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="be95a-314">Для всех остальных вердиктс фильтрации нежелательной почты в новых или существующих политиках защиты от нежелательной почты тег карантина применяется только в том случае, если значение действия — карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="be95a-315">Чтобы просмотреть значения действий в существующих политиках защиты от нежелательной почты, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="be95a-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="be95a-316">Сведения о значениях действий по умолчанию и рекомендуемых значениях действий для стандартных и ограниченных [параметров политики защиты от нежелательной почты см EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="be95a-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="be95a-317">Фильтрация нежелательной почты вредоносности без соответствующего параметра тега карантина означает, что используется [тег карантина по умолчанию](#step-2-assign-a-quarantine-tag-to-supported-features) для этого вредоносности.</span><span class="sxs-lookup"><span data-stu-id="be95a-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="be95a-318">Необходимо заменить тег карантина по умолчанию на настраиваемый тег карантина, если вы хотите изменить функции конечного пользователя по умолчанию для сообщений, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="be95a-319">Для новой политики защиты от нежелательной почты в PowerShell требуется политика фильтрации нежелательной почты (параметры) с помощью командлета **New-HostedContentFilterPolicy** и нового правила фильтрации нежелательной почты (фильтры получателей) с помощью командлета **New-hostedcontentfilterrule используется** .</span><span class="sxs-lookup"><span data-stu-id="be95a-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="be95a-320">Инструкции можно найти [в разделе Использование PowerShell для создания политик защиты от нежелательной почты](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="be95a-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="be95a-321">В этом примере создается новая политика фильтрации нежелательной почты с именем Research Department со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="be95a-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="be95a-322">Действие для всех вердиктс фильтрации нежелательной почты настроено как карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="be95a-323">Настраиваемый тег карантина с именем "без доступа", который назначает разрешения " **нет на доступе** ", заменяет все теги карантина по умолчанию, которые по умолчанию не назначают разрешения на **доступ** .</span><span class="sxs-lookup"><span data-stu-id="be95a-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="be95a-324">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="be95a-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="be95a-325">В этом примере изменяется существующая политика фильтрации нежелательной почты с именем "Отдел кадров".</span><span class="sxs-lookup"><span data-stu-id="be95a-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="be95a-326">Для действия вредоносности карантина нежелательной почты задано значение карантин, и назначен настраиваемый тег карантина с именем "недоступно".</span><span class="sxs-lookup"><span data-stu-id="be95a-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="be95a-327">Дополнительные сведения о синтаксисе и параметрах см. в статье [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="be95a-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="be95a-328">Настройка глобальных параметров уведомлений в карантине в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="be95a-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="be95a-329">Глобальные параметры для тегов карантина позволяют настраивать уведомления конечных пользователей о нежелательной почте, которые отправляются получателям сообщений, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="be95a-330">Для получения дополнительных сведений об этих уведомлениях обратитесь к разделу [уведомления о нежелательной почте конечных пользователей](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="be95a-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="be95a-331">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** а затем выберите пункт **теги карантина**.</span><span class="sxs-lookup"><span data-stu-id="be95a-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="be95a-332">На странице **теги карантина** выберите **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="be95a-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="be95a-333">В открывшемся всплывающем окне **Параметры уведомления о карантине** настройте некоторые или все из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="be95a-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="be95a-334">**Использовать мою фирменную эмблему**: Выберите этот параметр, чтобы заменить логотип Майкрософт по умолчанию, который будет использоваться в начале уведомления о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="be95a-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="be95a-335">Прежде чем выполнить это действие, выполните инструкции, приведенные в статье [Настройка темы Microsoft 365 для Организации](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) , чтобы отправить настраиваемый логотип.</span><span class="sxs-lookup"><span data-stu-id="be95a-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="be95a-336">На приведенном ниже снимке экрана показан настраиваемый логотип в уведомлении о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="be95a-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Настраиваемый логотип в уведомлении о нежелательной почте конечных пользователей](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="be95a-338">**Выбрать язык**: уведомления о нежелательной почте для конечных пользователей уже локализованы на основе языковых параметров получателя.</span><span class="sxs-lookup"><span data-stu-id="be95a-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="be95a-339">Можно указать настраиваемый текст на разных языках для **отображаемого имени** и значения **заявления об отказе** .</span><span class="sxs-lookup"><span data-stu-id="be95a-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="be95a-340">Выберите по крайней мере один язык в поле первый язык, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="be95a-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="be95a-341">Чтобы выбрать несколько языков, нажмите кнопку **Добавить** после каждого из них.</span><span class="sxs-lookup"><span data-stu-id="be95a-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="be95a-342">В поле язык раздела отображаются все выбранные языки:</span><span class="sxs-lookup"><span data-stu-id="be95a-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Выбранные языки в поле второго языка в параметрах уведомлений глобального карантина тегов карантина](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="be95a-344">**Отображаемое имя**: Настройка отображаемого имени отправителя, используемого в уведомлениях о нежелательной почте для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="be95a-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="be95a-345">Для каждого добавленного языка выберите язык в поле второй язык (не щелкайте X) и введите нужное текстовое значение в поле **Отображаемое имя** .</span><span class="sxs-lookup"><span data-stu-id="be95a-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="be95a-346">На приведенном ниже снимке экрана показано настраиваемое отображаемое имя в уведомлении о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="be95a-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Настраиваемое имя отправителя в уведомлении о нежелательной почте конечных пользователей](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="be95a-348">**Заявление об отказе**: Добавление настраиваемого заявления об отказе в конец уведомлений конечных пользователей о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="be95a-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="be95a-349">Локализованный текст, **заявление об отказе от вашей организации:** всегда включается в первую очередь, за которым следует заданный текст.</span><span class="sxs-lookup"><span data-stu-id="be95a-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="be95a-350">Для каждого добавленного языка выберите язык в поле второй язык (не щелкайте X) и введите нужное текстовое значение в поле **заявление об отказе** .</span><span class="sxs-lookup"><span data-stu-id="be95a-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="be95a-351">На следующем снимке экрана показан настраиваемый заявление об отказе в уведомлении пользователя о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="be95a-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Настраиваемый отказ от ответственности в нижней части уведомления о нежелательной почте для конечных пользователей](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="be95a-353">Просмотр тегов карантина в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="be95a-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="be95a-354">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** а затем выберите пункт **теги карантина**.</span><span class="sxs-lookup"><span data-stu-id="be95a-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="be95a-355">Чтобы просмотреть параметры встроенных или пользовательских тегов карантина, выберите тег карантина в списке (не устанавливайте флажок).</span><span class="sxs-lookup"><span data-stu-id="be95a-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="be95a-356">Чтобы просмотреть глобальные параметры, выберите **глобальные параметры** .</span><span class="sxs-lookup"><span data-stu-id="be95a-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="be95a-357">Просмотр тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="be95a-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="be95a-358">Если вы предпочитаете использовать PowerShell для просмотра тегов карантина, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="be95a-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="be95a-359">Чтобы просмотреть сводный список всех встроенных или настраиваемых тегов, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="be95a-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="be95a-360">Чтобы просмотреть параметры встроенных или пользовательских тегов карантина, замените на \<TagName\> имя тега карантина и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="be95a-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="be95a-361">Чтобы просмотреть глобальные параметры, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="be95a-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="be95a-362">Дополнительные сведения о синтаксисе и параметрах см. в статье [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="be95a-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="be95a-363">Удаление тегов карантина в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="be95a-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="be95a-364">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="be95a-364">**Notes**:</span></span>

- <span data-ttu-id="be95a-365">Встроенные теги карантина удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="be95a-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="be95a-366">Перед удалением настраиваемого тега карантина убедитесь, что он не используется.</span><span class="sxs-lookup"><span data-stu-id="be95a-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="be95a-367">Например, выполните следующую команду в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="be95a-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="be95a-368">Если используется тег карантина, [замените назначенный тег карантина](#step-2-assign-a-quarantine-tag-to-supported-features) перед удалением.</span><span class="sxs-lookup"><span data-stu-id="be95a-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="be95a-369">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** , \> **Policy** а затем выберите пункт **теги карантина**.</span><span class="sxs-lookup"><span data-stu-id="be95a-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="be95a-370">На странице " **теги карантина** " выберите настраиваемый тег карантина, который нужно удалить, и **тег Delete Delete (удалить**).</span><span class="sxs-lookup"><span data-stu-id="be95a-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="be95a-371">Нажмите кнопку **Удалить тег** в появившемся диалоговом окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="be95a-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="be95a-372">Удаление тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="be95a-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="be95a-373">Если вы предпочитаете использовать PowerShell для удаления настраиваемого тега карантина, замените \<TagName\> его именем тега карантина и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="be95a-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="be95a-374">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – куарантинетаг](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="be95a-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="be95a-375">Сведения о разрешениях для тега карантина</span><span class="sxs-lookup"><span data-stu-id="be95a-375">Quarantine tag permission details</span></span>

<span data-ttu-id="be95a-376">В следующих разделах описывается влияние предустановленных групп разрешений и отдельных разрешений в сведениях о сообщениях, помещенных в карантин, и уведомлениях о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="be95a-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="be95a-377">Предварительно заданные группы разрешений</span><span class="sxs-lookup"><span data-stu-id="be95a-377">Preset permissions groups</span></span>

<span data-ttu-id="be95a-378">Индивидуальные разрешения, которые включены в предварительно установленные группы разрешений, перечислены в таблице в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="be95a-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="be95a-379">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="be95a-379">No access</span></span>

<span data-ttu-id="be95a-380">Если в теге карантина назначаются разрешения **без доступа** (нет разрешений), пользователи по-прежнему получают некоторые базовые возможности:</span><span class="sxs-lookup"><span data-stu-id="be95a-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="be95a-381">**Сведения о сообщении в карантине**: кнопка **Просмотр заголовка сообщения** доступна всегда.</span><span class="sxs-lookup"><span data-stu-id="be95a-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Доступные кнопки в сведениях о сообщении в карантине, если тег карантина предоставляет пользователю разрешения на доступ](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="be95a-383">**Уведомления конечных пользователей о нежелательной почте**: кнопка " **Рецензирование** ", которая принимает пользователя на сообщение в карантине, доступна всегда.</span><span class="sxs-lookup"><span data-stu-id="be95a-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет пользователю разрешения на доступ](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="be95a-385">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="be95a-385">Limited access</span></span>

<span data-ttu-id="be95a-386">Если тег карантина назначает разрешения **с ограниченным доступом** , пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="be95a-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="be95a-387">**Сведения о сообщении в карантине**: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="be95a-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="be95a-388">**Выпуск запроса**</span><span class="sxs-lookup"><span data-stu-id="be95a-388">**Request release**</span></span>
  - <span data-ttu-id="be95a-389">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="be95a-389">**View message header**</span></span>
  - <span data-ttu-id="be95a-390">**Предварительная версия сообщения**</span><span class="sxs-lookup"><span data-stu-id="be95a-390">**Preview message**</span></span>
  - <span data-ttu-id="be95a-391">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="be95a-391">**Block sender**</span></span>
  - <span data-ttu-id="be95a-392">**Удалить из карантина**</span><span class="sxs-lookup"><span data-stu-id="be95a-392">**Remove from quarantine**</span></span>

  ![Доступные кнопки в сведениях о сообщении в карантине, если тег карантина предоставляет разрешения на ограниченный доступ пользователя](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="be95a-394">**Уведомления конечных пользователей о нежелательной почте**: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="be95a-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="be95a-395">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="be95a-395">**Block sender**</span></span>
  - <span data-ttu-id="be95a-396">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="be95a-396">**Review**</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет разрешения ограниченного доступа пользователя](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="be95a-398">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="be95a-398">Full access</span></span>

<span data-ttu-id="be95a-399">Если тег карантина назначает разрешения на **полный доступ** (все доступные разрешения), пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="be95a-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="be95a-400">**Сведения о сообщении в карантине**: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="be95a-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="be95a-401">**Сообщение об освобождении**</span><span class="sxs-lookup"><span data-stu-id="be95a-401">**Release message**</span></span>
  - <span data-ttu-id="be95a-402">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="be95a-402">**View message header**</span></span>
  - <span data-ttu-id="be95a-403">**Предварительная версия сообщения**</span><span class="sxs-lookup"><span data-stu-id="be95a-403">**Preview message**</span></span>
  - <span data-ttu-id="be95a-404">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="be95a-404">**Block sender**</span></span>
  - <span data-ttu-id="be95a-405">**Разрешить отправителя**</span><span class="sxs-lookup"><span data-stu-id="be95a-405">**Allow sender**</span></span>
  - <span data-ttu-id="be95a-406">**Удалить из карантина**</span><span class="sxs-lookup"><span data-stu-id="be95a-406">**Remove from quarantine**</span></span>

  ![Доступные кнопки в сведениях о сообщении в карантине, если тег карантина предоставляет разрешения на полный доступ для пользователя](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="be95a-408">**Уведомления конечных пользователей о нежелательной почте**: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="be95a-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="be95a-409">**Блокировка отправителя**</span><span class="sxs-lookup"><span data-stu-id="be95a-409">**Block sender**</span></span>
  - <span data-ttu-id="be95a-410">**Выпуск**</span><span class="sxs-lookup"><span data-stu-id="be95a-410">**Release**</span></span>
  - <span data-ttu-id="be95a-411">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="be95a-411">**Review**</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет разрешения на полный доступ для пользователя](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="be95a-413">Индивидуальные разрешения</span><span class="sxs-lookup"><span data-stu-id="be95a-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="be95a-414">Помните, что пользователи всегда получают кнопки, описанные в разделе " [нет доступа](#no-access) ".</span><span class="sxs-lookup"><span data-stu-id="be95a-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="be95a-415">Эти кнопки не включены в описание отдельных разрешений.</span><span class="sxs-lookup"><span data-stu-id="be95a-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="be95a-416">Разрешение "разрешить отправителю"</span><span class="sxs-lookup"><span data-stu-id="be95a-416">Allow sender permission</span></span>

<span data-ttu-id="be95a-417">Разрешение " **Разрешить отправителю** " (_пермиссионтоалловсендер_) управляет доступом к кнопке, позволяющей пользователям легко добавить отправителя сообщения, помещенного в карантин, в список надежных отправителей.</span><span class="sxs-lookup"><span data-stu-id="be95a-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="be95a-418">**Сведения о сообщении в карантине**:</span><span class="sxs-lookup"><span data-stu-id="be95a-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="be95a-419">**Разрешить отправителю разрешить** отправку: доступна кнопка **Разрешить отправителя** .</span><span class="sxs-lookup"><span data-stu-id="be95a-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="be95a-420">Разрешить отправку **отправителей** отключено: кнопка " **Разрешить отправителя** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="be95a-421">**Уведомления конечных пользователей о нежелательной почте** не вступают в противодействия.</span><span class="sxs-lookup"><span data-stu-id="be95a-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="be95a-422">Дополнительные сведения о списке надежных отправителей можно найти в статье [предотвращение блокирования надежных отправителей](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) и [использование Exchange Online PowerShell для настройки коллекции списков надежных отправителей в почтовом ящике](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="be95a-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="be95a-423">Блокировать разрешение отправителей</span><span class="sxs-lookup"><span data-stu-id="be95a-423">Block sender permission</span></span>

<span data-ttu-id="be95a-424">Разрешение **блокировать отправителя** (_пермиссионтоблокксендер_) управляет доступом к кнопке, позволяющей пользователям легко добавить отправителя сообщения, помещенного в карантин, в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="be95a-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="be95a-425">**Сведения о сообщении в карантине**:</span><span class="sxs-lookup"><span data-stu-id="be95a-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="be95a-426">**Блокировать разрешение отправителей** : кнопка " **блокировать отправителя** " доступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="be95a-427">**Блокировать разрешение отправителя** отключено: кнопка " **блокировать отправителя** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="be95a-428">**Уведомления конечных пользователей о нежелательной почте**:</span><span class="sxs-lookup"><span data-stu-id="be95a-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="be95a-429">**Блокировать разрешение отправителя** отключено: кнопка " **блокировать отправителя** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="be95a-430">**Блокировать разрешение отправителей** : кнопка " **блокировать отправителя** " доступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="be95a-431">Дополнительные сведения о списке заблокированных отправителей можно узнать в статье [Блокировать сообщения от кого-либо с](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) [помощью Exchange Online PowerShell для настройки коллекции списков надежных отправителей для почтового ящика](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="be95a-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="be95a-432">Удаление разрешения</span><span class="sxs-lookup"><span data-stu-id="be95a-432">Delete permission</span></span>

<span data-ttu-id="be95a-433">Разрешение **Delete** (_пермиссионтоделете_) управляет возможностью пользователей удалять свои сообщения (сообщения, в которых пользователь является получателем) из карантина.</span><span class="sxs-lookup"><span data-stu-id="be95a-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="be95a-434">**Сведения о сообщении в карантине**:</span><span class="sxs-lookup"><span data-stu-id="be95a-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="be95a-435">Разрешение на **Удаление** включено: доступна кнопка **удалить из карантина** .</span><span class="sxs-lookup"><span data-stu-id="be95a-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="be95a-436">Разрешение на **Удаление** отключено: кнопка **удалить из карантина** недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="be95a-437">**Уведомления конечных пользователей о нежелательной почте** не вступают в противодействия.</span><span class="sxs-lookup"><span data-stu-id="be95a-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="be95a-438">Разрешение на предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="be95a-438">Preview permission</span></span>

<span data-ttu-id="be95a-439">Разрешение на **Предварительный просмотр** (_пермиссионтопревиев_) управляет возможностью пользователей просматривать сообщения в карантине.</span><span class="sxs-lookup"><span data-stu-id="be95a-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="be95a-440">**Сведения о сообщении в карантине**:</span><span class="sxs-lookup"><span data-stu-id="be95a-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="be95a-441">Разрешение на **Предварительный просмотр** включен: кнопка **предварительного просмотра сообщения** доступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="be95a-442">Разрешение на **Просмотр** отключено: кнопка " **просмотреть сообщение** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="be95a-443">**Уведомления конечных пользователей о нежелательной почте** не вступают в противодействия.</span><span class="sxs-lookup"><span data-stu-id="be95a-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="be95a-444">Разрешить получателям освобождать сообщение от разрешения "карантин"</span><span class="sxs-lookup"><span data-stu-id="be95a-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="be95a-445">**Разрешить получателям выпустить сообщение из карантинного** разрешения (_пермиссионторелеасе_) управляет возможностью пользователей напрямую освобождать сообщения, помещенные на карантин, и без утверждения администратора.</span><span class="sxs-lookup"><span data-stu-id="be95a-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="be95a-446">**Сведения о сообщении в карантине**:</span><span class="sxs-lookup"><span data-stu-id="be95a-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="be95a-447">Разрешение включено: доступна кнопка **выпустить сообщение** .</span><span class="sxs-lookup"><span data-stu-id="be95a-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="be95a-448">Разрешение отключено: кнопка **освобождения сообщения** недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="be95a-449">**Уведомления конечных пользователей о нежелательной почте**:</span><span class="sxs-lookup"><span data-stu-id="be95a-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="be95a-450">Разрешение включено: доступна кнопка **выпустить** .</span><span class="sxs-lookup"><span data-stu-id="be95a-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="be95a-451">Разрешение отключено: кнопка " **выпустить** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="be95a-452">Разрешить получателям запрашивать разрешение на отправку сообщения из карантина</span><span class="sxs-lookup"><span data-stu-id="be95a-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="be95a-453">**Разрешить получателям запрашивать сообщение из карантинного** разрешения (_пермиссионторекуестрелеасе_) управляет возможностью пользователей _запрашивать_ выпуск сообщений, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="be95a-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="be95a-454">Сообщение будет выпущено только после того, как администратор утвердит запрос.</span><span class="sxs-lookup"><span data-stu-id="be95a-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="be95a-455">**Сведения о сообщении в карантине**:</span><span class="sxs-lookup"><span data-stu-id="be95a-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="be95a-456">Разрешение включено: доступна кнопка **выпустить запрос** .</span><span class="sxs-lookup"><span data-stu-id="be95a-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="be95a-457">Разрешение отключено: кнопка " **запрос на выпуск** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="be95a-458">**Уведомления конечных пользователей о нежелательной почте**: кнопка " **выпуск** " недоступна.</span><span class="sxs-lookup"><span data-stu-id="be95a-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
