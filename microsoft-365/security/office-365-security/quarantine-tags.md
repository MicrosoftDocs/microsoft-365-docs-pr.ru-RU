---
title: Теги карантина
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
description: Администраторы могут научиться использовать теги карантина для управления тем, что пользователи могут делать с их карантинными сообщениями.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8024894cdb4a4718422c250eff87fa6da5443a84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922416"
---
# <a name="quarantine-tags"></a><span data-ttu-id="06f9d-103">Теги карантина</span><span class="sxs-lookup"><span data-stu-id="06f9d-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="06f9d-104">Функции, описанные в этой статье, в настоящее время находятся в предварительном просмотре, недоступны для всех и могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="06f9d-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="06f9d-105">Теги карантина в Exchange Online Protection (EOP) позволяют администраторам управлять тем, что пользователи могут делать с их карантинными сообщениями в зависимости от того, как сообщение поступило в карантин.</span><span class="sxs-lookup"><span data-stu-id="06f9d-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="06f9d-106">EOP традиционно разрешает или предотвращает определенные уровни интерактивности [](find-and-release-quarantined-messages-as-a-user.md) для сообщений в карантине и в уведомлениях о нежелательной почте конечного [пользователя.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="06f9d-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="06f9d-107">Например, конечные пользователи могут просматривать и выпускать сообщения, которые были карантинными в результате фильтрации от нежелательной почты, как спам или массовые, но они не могут просматривать или выпускать сообщения, которые были на карантине, как фишинг с высокой уверенностью.</span><span class="sxs-lookup"><span data-stu-id="06f9d-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="06f9d-108">Для [](#step-2-assign-a-quarantine-tag-to-supported-features)поддерживаемых функций защиты в карантиных тегах указывается, что пользователям разрешено делать в сообщениях уведомлений о нежелательной почте конечных пользователей и в карантинных сообщениях в карантине (сообщения, в которых пользователь является получателем).</span><span class="sxs-lookup"><span data-stu-id="06f9d-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="06f9d-109">Теги карантина по умолчанию автоматически назначены для обеспечения выполнения исторических возможностей конечных пользователей в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="06f9d-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="06f9d-110">Или можно создать и назначить настраиваемые теги карантина, чтобы разрешить или запретить конечным пользователям выполнять определенные действия в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="06f9d-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="06f9d-111">Отдельные разрешения объединяются в следующие группы предварительного разрешения:</span><span class="sxs-lookup"><span data-stu-id="06f9d-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="06f9d-112">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="06f9d-112">No access</span></span>
- <span data-ttu-id="06f9d-113">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="06f9d-113">Limited access</span></span>
- <span data-ttu-id="06f9d-114">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="06f9d-114">Full access</span></span>

<span data-ttu-id="06f9d-115">Доступные отдельные разрешения и то, что включено или не включено в предустановленные группы разрешений, описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="06f9d-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="06f9d-116">Разрешение</span><span class="sxs-lookup"><span data-stu-id="06f9d-116">Permission</span></span>|<span data-ttu-id="06f9d-117">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="06f9d-117">No access</span></span>|<span data-ttu-id="06f9d-118">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="06f9d-118">Limited access</span></span>|<span data-ttu-id="06f9d-119">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="06f9d-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="06f9d-120">**Разрешить отправитель** _(PermissionToAllowSender)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="06f9d-122">**Отправитель блока** _(PermissionToBlockSender)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="06f9d-125">**Удаление** _(PermissionToDelete)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-125">**Delete** (_PermissionToDelete_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="06f9d-128">**Предварительный** просмотр _(PermissionToPreview)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-128">**Preview** (_PermissionToPreview_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="06f9d-131">**Разрешить получателям освободить сообщение из карантина** _(PermissionToRelease)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="06f9d-133">**Разрешить получателям запрашивать сообщение, которое будет выпущено из** карантина _(PermissionToRequestRelease)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Флажок](../../media/checkmark.png)||
|

<span data-ttu-id="06f9d-135">Если вам не нравятся разрешения по умолчанию в предустановленных группах разрешений, можно использовать настраиваемые разрешения при создании или изменении настраиваемой карантинской метки.</span><span class="sxs-lookup"><span data-stu-id="06f9d-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="06f9d-136">Дополнительные сведения о том, что делает каждое разрешение, см. в разделе [Сведения](#quarantine-tag-permission-details) о разрешении тегов карантина в этой статье.</span><span class="sxs-lookup"><span data-stu-id="06f9d-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="06f9d-137">Вы создаете и назначаете теги карантина в Центре & безопасности или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками Exchange Online; автономные EOP PowerShell в организациях EOP без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="06f9d-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="06f9d-138">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="06f9d-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="06f9d-139">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="06f9d-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="06f9d-140">Чтобы перейти непосредственно на страницу тегов **карантина,** откройте <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="06f9d-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="06f9d-141">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="06f9d-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="06f9d-142">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="06f9d-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="06f9d-143">Чтобы просмотреть, создать, изменить или удалить теги карантина,  необходимо быть  членом роли администратора организации или администратора безопасности в Центре & [соответствия](permissions-in-the-security-and-compliance-center.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="06f9d-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="06f9d-144">Шаг 1. Создание тегов карантина в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="06f9d-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="06f9d-145">В Центре & безопасности перейдите к  политике управления угрозами и выберите теги \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="06f9d-146">На странице **Теги карантина** выберите **Добавить настраиваемый тег**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="06f9d-147">Откроется **мастер тегов** New Tag.</span><span class="sxs-lookup"><span data-stu-id="06f9d-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="06f9d-148">На странице **Имя тега** введите краткое, но уникальное имя в **поле Имя тега.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="06f9d-149">В предстоящих действиях необходимо определить и выбрать тег по имени.</span><span class="sxs-lookup"><span data-stu-id="06f9d-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="06f9d-150">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="06f9d-151">На странице **доступа к сообщению получателя** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="06f9d-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="06f9d-152">**Нет доступа**</span><span class="sxs-lookup"><span data-stu-id="06f9d-152">**No access**</span></span>
   - <span data-ttu-id="06f9d-153">**Ограниченный доступ**</span><span class="sxs-lookup"><span data-stu-id="06f9d-153">**Limited access**</span></span>
   - <span data-ttu-id="06f9d-154">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="06f9d-154">**Full access**</span></span>

   <span data-ttu-id="06f9d-155">Отдельные разрешения, включенные в эти группы разрешений, описаны ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="06f9d-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="06f9d-156">Чтобы указать пользовательские разрешения, выберите Задать определенный **доступ (Расширенный)** и настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="06f9d-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="06f9d-157">**Выберите предпочтение действий выпуска:** Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="06f9d-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="06f9d-158">**Действие выпуска:** это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="06f9d-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="06f9d-159">**Разрешить получателям освободить сообщение из карантина**</span><span class="sxs-lookup"><span data-stu-id="06f9d-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="06f9d-160">**Разрешить получателям запрашивать сообщение, которое будет выпущено из карантина**</span><span class="sxs-lookup"><span data-stu-id="06f9d-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="06f9d-161">**Выберите дополнительные действия, которые** получатели могут принимать на карантин сообщения: Выберите некоторые, все или ни одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="06f9d-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="06f9d-162">**удаление**;</span><span class="sxs-lookup"><span data-stu-id="06f9d-162">**Delete**</span></span>
       - <span data-ttu-id="06f9d-163">**Предварительная версия**</span><span class="sxs-lookup"><span data-stu-id="06f9d-163">**Preview**</span></span>
       - <span data-ttu-id="06f9d-164">**Разрешить отправитель**</span><span class="sxs-lookup"><span data-stu-id="06f9d-164">**Allow sender**</span></span>
       - <span data-ttu-id="06f9d-165">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="06f9d-165">**Block sender**</span></span>

   <span data-ttu-id="06f9d-166">Эти разрешения и их влияние на карантинные сообщения и уведомления о нежелательной почте конечных пользователей описаны в разделе Сведения о разрешении тегов карантина в этой статье. [](#quarantine-tag-permission-details)</span><span class="sxs-lookup"><span data-stu-id="06f9d-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="06f9d-167">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="06f9d-168">На странице **Сводка,** которая появится, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="06f9d-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="06f9d-169">Чтобы изменить его, можно нажать **кнопку Изменить** каждый параметр.</span><span class="sxs-lookup"><span data-stu-id="06f9d-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="06f9d-170">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="06f9d-171">Нажмите **кнопку Готово** на странице подтверждения, которая отображается.</span><span class="sxs-lookup"><span data-stu-id="06f9d-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="06f9d-172">Теперь вы готовы назначить карантинный тег функции карантина, как описано в разделе [Шаг 2.](#step-2-assign-a-quarantine-tag-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="06f9d-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="06f9d-173">Создание тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="06f9d-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="06f9d-174">Если вы хотите использовать PowerShell для создания карантиных тегов, подключись к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте командлет **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="06f9d-175">У вас есть два различных метода на выбор:</span><span class="sxs-lookup"><span data-stu-id="06f9d-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="06f9d-176">Используйте параметр _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="06f9d-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="06f9d-177">Используйте параметр _EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="06f9d-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="06f9d-178">Эти методы описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="06f9d-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="06f9d-179">Используйте параметр EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="06f9d-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="06f9d-180">Чтобы создать карантиновый тег с помощью _параметра EndUserQuarantinePermissionsValue,_ используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="06f9d-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="06f9d-181">Параметр _EndUserQuarantinePermissionsValue_ использует десятичное значение, преобразованное из двоичного значения.</span><span class="sxs-lookup"><span data-stu-id="06f9d-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="06f9d-182">Двоичное значение соответствует доступным разрешениям карантина для конечных пользователей в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="06f9d-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="06f9d-183">Для каждого разрешения значение 1 равно True, а значение 0 - false.</span><span class="sxs-lookup"><span data-stu-id="06f9d-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="06f9d-184">Необходимый порядок и значения для каждого отдельного разрешения в предустановленных группах разрешений описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="06f9d-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="06f9d-185">Разрешение</span><span class="sxs-lookup"><span data-stu-id="06f9d-185">Permission</span></span>|<span data-ttu-id="06f9d-186">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="06f9d-186">No access</span></span>|<span data-ttu-id="06f9d-187">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="06f9d-187">Limited access</span></span>|<span data-ttu-id="06f9d-188">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="06f9d-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="06f9d-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="06f9d-189">PermissionToAllowSender</span></span>|<span data-ttu-id="06f9d-190">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-190">0</span></span>|<span data-ttu-id="06f9d-191">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-191">0</span></span>|<span data-ttu-id="06f9d-192">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-192">1</span></span>|
|<span data-ttu-id="06f9d-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="06f9d-193">PermissionToBlockSender</span></span>|<span data-ttu-id="06f9d-194">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-194">0</span></span>|<span data-ttu-id="06f9d-195">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-195">1</span></span>|<span data-ttu-id="06f9d-196">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-196">1</span></span>|
|<span data-ttu-id="06f9d-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="06f9d-197">PermissionToDelete</span></span>|<span data-ttu-id="06f9d-198">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-198">0</span></span>|<span data-ttu-id="06f9d-199">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-199">1</span></span>|<span data-ttu-id="06f9d-200">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-200">1</span></span>|
|<span data-ttu-id="06f9d-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06f9d-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="06f9d-202">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-202">0</span></span>|<span data-ttu-id="06f9d-203">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-203">0</span></span>|<span data-ttu-id="06f9d-204">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-204">0</span></span>|
|<span data-ttu-id="06f9d-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="06f9d-205">PermissionToPreview</span></span>|<span data-ttu-id="06f9d-206">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-206">0</span></span>|<span data-ttu-id="06f9d-207">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-207">1</span></span>|<span data-ttu-id="06f9d-208">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-208">1</span></span>|
|<span data-ttu-id="06f9d-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="06f9d-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="06f9d-210">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-210">0</span></span>|<span data-ttu-id="06f9d-211">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-211">0</span></span>|<span data-ttu-id="06f9d-212">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-212">1</span></span>|
|<span data-ttu-id="06f9d-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="06f9d-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="06f9d-214">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-214">0</span></span>|<span data-ttu-id="06f9d-215">1</span><span class="sxs-lookup"><span data-stu-id="06f9d-215">1</span></span>|<span data-ttu-id="06f9d-216">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-216">0</span></span>|
|<span data-ttu-id="06f9d-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06f9d-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="06f9d-218">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-218">0</span></span>|<span data-ttu-id="06f9d-219">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-219">0</span></span>|<span data-ttu-id="06f9d-220">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-220">0</span></span>|
|<span data-ttu-id="06f9d-221">Двоичное значение</span><span class="sxs-lookup"><span data-stu-id="06f9d-221">Binary value</span></span>|<span data-ttu-id="06f9d-222">00000000</span><span class="sxs-lookup"><span data-stu-id="06f9d-222">00000000</span></span>|<span data-ttu-id="06f9d-223">01101010</span><span class="sxs-lookup"><span data-stu-id="06f9d-223">01101010</span></span>|<span data-ttu-id="06f9d-224">11101100</span><span class="sxs-lookup"><span data-stu-id="06f9d-224">11101100</span></span>|
|<span data-ttu-id="06f9d-225">Десятичная значения для использования</span><span class="sxs-lookup"><span data-stu-id="06f9d-225">Decimal value to use</span></span>|<span data-ttu-id="06f9d-226">0</span><span class="sxs-lookup"><span data-stu-id="06f9d-226">0</span></span>|<span data-ttu-id="06f9d-227">106</span><span class="sxs-lookup"><span data-stu-id="06f9d-227">106</span></span>|<span data-ttu-id="06f9d-228">236</span><span class="sxs-lookup"><span data-stu-id="06f9d-228">236</span></span>|

<span data-ttu-id="06f9d-229"><sup>\*</sup> В настоящее время это значение всегда 0.</span><span class="sxs-lookup"><span data-stu-id="06f9d-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="06f9d-230">Для PermissionToViewHeader значение 0 не скрывает кнопку Заголовок сообщения **View** в подробностях карантиного сообщения (кнопка всегда доступна).</span><span class="sxs-lookup"><span data-stu-id="06f9d-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="06f9d-231"><sup>\*\*</sup> Не устанавливайте оба этих значения до 1.</span><span class="sxs-lookup"><span data-stu-id="06f9d-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="06f9d-232">Установите одно к 1 и другое к 0, или установите оба к 0.</span><span class="sxs-lookup"><span data-stu-id="06f9d-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="06f9d-233">В этом примере создается новое имя тега карантина NoAccess, которое назначает разрешения доступа без доступа, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="06f9d-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="06f9d-234">Для разрешений ограниченного доступа используйте значение 106.</span><span class="sxs-lookup"><span data-stu-id="06f9d-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="06f9d-235">Для разрешений полного доступа используйте значение 236.</span><span class="sxs-lookup"><span data-stu-id="06f9d-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="06f9d-236">Для пользовательских разрешений используйте предыдущую таблицу, чтобы получить двоичное значение, соответствующее нужным разрешениям.</span><span class="sxs-lookup"><span data-stu-id="06f9d-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="06f9d-237">Преобразование двоичного значения в десятичное значение и использование десятичного значения для параметра _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="06f9d-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="06f9d-238">Подробные сведения о синтаксисах и параметрах см. [в new-QuarantineTag.](/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="06f9d-238">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="06f9d-239">Использование параметра EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="06f9d-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="06f9d-240">Чтобы создать карантиновый тег с помощью _параметра EndUserQuarantinePermissionsValue,_ сделайте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="06f9d-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="06f9d-241">О.</span><span class="sxs-lookup"><span data-stu-id="06f9d-241">A.</span></span> <span data-ttu-id="06f9d-242">Храните объект разрешений карантина в переменной с помощью подраздела **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="06f9d-243">B.</span><span class="sxs-lookup"><span data-stu-id="06f9d-243">B.</span></span> <span data-ttu-id="06f9d-244">Используйте переменную в качестве _значения EndUserQuarantinePermissions_ в **команде New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="06f9d-245">Шаг A. Хранение объекта разрешений карантина в переменной</span><span class="sxs-lookup"><span data-stu-id="06f9d-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="06f9d-246">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="06f9d-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="06f9d-247">Значение по умолчанию для любых неиспользимых параметров , поэтому вам нужно использовать только параметры, в которых необходимо установить `$false` значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="06f9d-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="06f9d-248">В следующих примерах покажите, как создавать объекты разрешений, соответствующие заранее:</span><span class="sxs-lookup"><span data-stu-id="06f9d-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="06f9d-249">**Нет доступа:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="06f9d-250">**Ограниченный доступ:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="06f9d-251">**Полный доступ:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="06f9d-252">Чтобы увидеть значения, которые вы установили, запустите имя переменной в качестве команды (например, запустите `$NoAccess` команду).</span><span class="sxs-lookup"><span data-stu-id="06f9d-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="06f9d-253">Для пользовательских разрешений не заданы параметры _PermissionToRelease_ и _PermissionToRequestRelease._ `$true`</span><span class="sxs-lookup"><span data-stu-id="06f9d-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="06f9d-254">Установите одно и `$true` оставьте другое как `$false` , или оставьте оба как `$false` .</span><span class="sxs-lookup"><span data-stu-id="06f9d-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="06f9d-255">Вы также можете изменить существующую переменную объектов разрешений после создания, но перед ее использованием с помощью **cmdlet Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="06f9d-256">Подробные сведения о синтаксисах и параметрах см. в [new-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) и [Set-QuarantinePermissions.](/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="06f9d-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="06f9d-257">Шаг B. Использование переменной в New-QuarantineTag команде</span><span class="sxs-lookup"><span data-stu-id="06f9d-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="06f9d-258">После создания и хранения объекта разрешений в переменной используйте переменную для значения параметра _EndUserQuarantinePermission_ в следующей команде **New-QuarantineTag:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="06f9d-259">В этом примере создается новый карантинный тег с именем LimitedAccess с помощью объекта разрешений, который был описан и создан `$LimitedAccess` на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="06f9d-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="06f9d-260">Подробные сведения о синтаксисах и параметрах см. [в new-QuarantineTag.](/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="06f9d-260">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="06f9d-261">Шаг 2. Назначение тега карантина поддерживаемых компонентов</span><span class="sxs-lookup"><span data-stu-id="06f9d-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="06f9d-262">В _поддерживаемых_ средствах защиты, карантиных сообщениях или файлах (автоматически или в качестве настраиваемого действия), можно назначить карантинный тег доступным карантиным действиям.</span><span class="sxs-lookup"><span data-stu-id="06f9d-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="06f9d-263">Функции карантиных сообщений и наличие тегов карантина описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="06f9d-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="06f9d-264">Функция</span><span class="sxs-lookup"><span data-stu-id="06f9d-264">Feature</span></span>|<span data-ttu-id="06f9d-265">Поддерживаемые теги карантина?</span><span class="sxs-lookup"><span data-stu-id="06f9d-265">Quarantine tags supported?</span></span>|<span data-ttu-id="06f9d-266">Используемые теги карантина по умолчанию</span><span class="sxs-lookup"><span data-stu-id="06f9d-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="06f9d-267">[Политики борьбы со спамом:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="06f9d-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="06f9d-268">**Spam** _(SpamAction)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="06f9d-269">**Высокая достоверность** нежелательной почты _(HighConfidenceSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="06f9d-270">**Фишинговая электронная** _почта (PhishSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="06f9d-271">**Высокая достоверность фишинговой почты** _(HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="06f9d-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="06f9d-272">**Массовая электронная** почта _(BulkSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="06f9d-273">Да</span><span class="sxs-lookup"><span data-stu-id="06f9d-273">Yes</span></span>|<ul><li><span data-ttu-id="06f9d-274">DefaultSpamTag (Полный доступ)</span><span class="sxs-lookup"><span data-stu-id="06f9d-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="06f9d-275">DefaultHighConfSpamTag (Полный доступ)</span><span class="sxs-lookup"><span data-stu-id="06f9d-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="06f9d-276">DefaultPhishTag (Полный доступ)</span><span class="sxs-lookup"><span data-stu-id="06f9d-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="06f9d-277">DefaultHighConfPhishTag (Без доступа)</span><span class="sxs-lookup"><span data-stu-id="06f9d-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="06f9d-278">DefaultBulkTag (Полный доступ)</span><span class="sxs-lookup"><span data-stu-id="06f9d-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="06f9d-279">Политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="06f9d-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="06f9d-280">[Защита от спуф-аналитики](set-up-anti-phishing-policies.md#spoof-settings) _(AuthenticationFailAction)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="06f9d-281">[Защита от обезличения:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06f9d-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="06f9d-282">**Если электронная почта отправляется обезличенным пользователем** _(TargetedUserProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="06f9d-283">**Если электронная почта отправляется с помощью обезличенных доменов** _(TargetedDomainProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="06f9d-284">**Аналитика почтовых ящиков** \> **Если электронная почта отправляется обезличенным пользователем** _(MailboxIntelligenceProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="06f9d-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="06f9d-285">Нет</span><span class="sxs-lookup"><span data-stu-id="06f9d-285">No</span></span>|<span data-ttu-id="06f9d-286">Н/д</span><span class="sxs-lookup"><span data-stu-id="06f9d-286">n/a</span></span>|
|<span data-ttu-id="06f9d-287">[Политики по борьбе с вредоносными](configure-anti-malware-policies.md)программами. Все обнаруженные сообщения всегда находятся на карантине.</span><span class="sxs-lookup"><span data-stu-id="06f9d-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="06f9d-288">Нет</span><span class="sxs-lookup"><span data-stu-id="06f9d-288">No</span></span>|<span data-ttu-id="06f9d-289">Н/д</span><span class="sxs-lookup"><span data-stu-id="06f9d-289">n/a</span></span>|
|[<span data-ttu-id="06f9d-290">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06f9d-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="06f9d-291">Нет</span><span class="sxs-lookup"><span data-stu-id="06f9d-291">No</span></span>|<span data-ttu-id="06f9d-292">Н/д</span><span class="sxs-lookup"><span data-stu-id="06f9d-292">n/a</span></span>|
|<span data-ttu-id="06f9d-293">[Правила потока почты](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (также известные как правила транспорта) с действием: **Доставка** сообщения на карантин(_карантин)._</span><span class="sxs-lookup"><span data-stu-id="06f9d-293">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="06f9d-294">Нет</span><span class="sxs-lookup"><span data-stu-id="06f9d-294">No</span></span>|<span data-ttu-id="06f9d-295">Н/д</span><span class="sxs-lookup"><span data-stu-id="06f9d-295">n/a</span></span>|
|

<span data-ttu-id="06f9d-296"><sup>\*</sup> Параметры защиты от обезличения доступны только в политиках защиты от фишинга в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="06f9d-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="06f9d-297">Если вы довольны разрешениями конечных пользователей, предоставляемыми тегами карантина по умолчанию, вам не нужно ничего делать.</span><span class="sxs-lookup"><span data-stu-id="06f9d-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="06f9d-298">Если вы хотите настроить возможности конечных пользователей (доступные кнопки) в уведомлениях о нежелательной почте конечных пользователей или в карантиновом сообщении, можно назначить настраиваемый тег карантина.</span><span class="sxs-lookup"><span data-stu-id="06f9d-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="06f9d-299">Назначение тегов карантина в политиках защиты от нежелательной почты в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="06f9d-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="06f9d-300">Полные инструкции по созданию и изменению политик борьбы со спамом описаны в настройках политик по борьбе со спамом [в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="06f9d-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="06f9d-301">В Центре & безопасности перейдите к **политике** управления угрозами, а затем выберите службу \>  \> защиты от **нежелательной почты.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="06f9d-302">Или откройте <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="06f9d-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="06f9d-303">Найдите и выберите существующую политику по борьбе со спамом для редактирования или создания новой политики по борьбе со спамом.</span><span class="sxs-lookup"><span data-stu-id="06f9d-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="06f9d-304">В разделе подробные сведения о политике расширите раздел **Спам и массовые** действия.</span><span class="sxs-lookup"><span data-stu-id="06f9d-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="06f9d-305">Если вы выбрали  сообщение карантина для действия решения о фильтрации  нежелательной почты, поле тегов политики применения карантиной политики доступно для выбора тега карантина для этого вердикта.</span><span class="sxs-lookup"><span data-stu-id="06f9d-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="06f9d-306">**Примечание.** При создании новой политики значение пустого карантиного тега для решения о фильтрации нежелательной почты указывает на то, что для этого решения используется карантин по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="06f9d-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="06f9d-307">После редактирования политики пустые значения заменяются фактическими именами карантинными тегами по умолчанию, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="06f9d-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Выбор карантиных тегов в политике борьбы со спамом](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="06f9d-309">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="06f9d-310">Назначение тегов карантина в политиках по борьбе со спамом в PowerShell</span><span class="sxs-lookup"><span data-stu-id="06f9d-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="06f9d-311">Если вы хотите использовать PowerShell для назначения тегов карантина в политиках по борьбе со спамом, подключись к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="06f9d-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="06f9d-312">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-312">**Notes**:</span></span>

- <span data-ttu-id="06f9d-313">Значение по умолчанию для параметра _HighConfidencePhishAction_ — карантин, поэтому не нужно устанавливать действие карантина для обнаружения фишинга с высокой уверенностью в новых политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="06f9d-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="06f9d-314">Для всех остальных приговоров по фильтрации нежелательной почты в новых или существующих политиках по борьбе со нежелательной почтой тег карантина эффективен только в том случае, если значение действия — карантин.</span><span class="sxs-lookup"><span data-stu-id="06f9d-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="06f9d-315">Чтобы увидеть значения действий в существующих политиках по борьбе со спамом, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="06f9d-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="06f9d-316">Сведения о значениях действий по умолчанию и рекомендуемых значениях действий для Standard и Strict см. в параметров политики борьбы со спамом [EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="06f9d-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="06f9d-317">Вердикт фильтрации нежелательной почты без соответствующего [](#step-2-assign-a-quarantine-tag-to-supported-features) параметра карантиного тега означает, что для этого решения используется карантин по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="06f9d-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="06f9d-318">Чтобы изменить возможности конечных пользователей по умолчанию в карантинных сообщениях, необходимо заменить карантиновую метку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="06f9d-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="06f9d-319">Новая политика по борьбе со нежелательной почтой в PowerShell требует политики фильтрации нежелательной почты (параметры) с помощью комлета **New-HostedContentFilterPolicy** и нового правила фильтра нежелательной почты (фильтры получателей) с помощью комлета **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="06f9d-320">Инструкции см. в [инструкции Use PowerShell для создания политик по борьбе со спамом.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="06f9d-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="06f9d-321">В этом примере создается новая политика фильтра нежелательной почты с именем Research Department со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="06f9d-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="06f9d-322">Действие для всех приговоров фильтрации нежелательной почты задавается карантином.</span><span class="sxs-lookup"><span data-stu-id="06f9d-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="06f9d-323">Настраиваемый тег карантина с именем NoAccess, который назначает разрешения на доступ без доступа, заменяет любые теги карантина по умолчанию, которые еще не назначают разрешения доступа по умолчанию.  </span><span class="sxs-lookup"><span data-stu-id="06f9d-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="06f9d-324">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="06f9d-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="06f9d-325">В этом примере изменяется существующая политика фильтрации нежелательной почты с именем Human Resources.</span><span class="sxs-lookup"><span data-stu-id="06f9d-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="06f9d-326">Действие для вердикта карантина нежелательной почты задавается карантином, а настраиваемый карантиный тег с именем NoAccess назначен.</span><span class="sxs-lookup"><span data-stu-id="06f9d-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="06f9d-327">Дополнительные сведения о синтаксисе и параметрах см. в статье [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="06f9d-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="06f9d-328">Настройка глобальных параметров уведомлений о карантине в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="06f9d-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="06f9d-329">Глобальные параметры карантиных тегов позволяют настраивать уведомления о нежелательной почте конечного пользователя, которые отправляются получателям сообщений, которые были карантинными.</span><span class="sxs-lookup"><span data-stu-id="06f9d-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="06f9d-330">Дополнительные сведения об этих уведомлениях см. в сообщении о нежелательной [почте конечных пользователей.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="06f9d-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="06f9d-331">В Центре & безопасности перейдите к  политике управления угрозами и выберите теги \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="06f9d-332">На странице **Теги карантина** выберите **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="06f9d-333">В **открываемом** флаауте параметров уведомлений карантина настройте некоторые или все следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="06f9d-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="06f9d-334">**Используйте логотип моей компании.** Выберите этот параметр, чтобы заменить логотип Microsoft по умолчанию, который используется в верхней части уведомлений о нежелательной почте конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="06f9d-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="06f9d-335">Прежде чем это сделать, необходимо следовать инструкциям в [Настройка темы Microsoft 365](../../admin/setup/customize-your-organization-theme.md) для вашей организации, чтобы загрузить свой пользовательский логотип.</span><span class="sxs-lookup"><span data-stu-id="06f9d-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="06f9d-336">На следующем скриншоте показан настраиваемый логотип в уведомлении о нежелательной почте для конечных пользователей:</span><span class="sxs-lookup"><span data-stu-id="06f9d-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Настраиваемый логотип в уведомлении о нежелательной почте для конечных пользователей](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="06f9d-338">**Выберите язык.** Уведомления о нежелательной почте конечных пользователей уже локализованы в зависимости от параметров языка получателя.</span><span class="sxs-lookup"><span data-stu-id="06f9d-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="06f9d-339">Вы можете указать настраиваемый текст на разных языках для значений **Display и** **Disclaimer.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="06f9d-340">Выберите хотя бы один язык из первого языкового окна и нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="06f9d-341">Вы можете выбрать несколько языков, щелкнув **Добавить** после каждого из них.</span><span class="sxs-lookup"><span data-stu-id="06f9d-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="06f9d-342">В языковом окне раздела показаны все выбранные вами языки:</span><span class="sxs-lookup"><span data-stu-id="06f9d-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Выбранные языки во втором языковом поле в глобальных параметрах уведомлений о карантине тегов карантина](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="06f9d-344">**Отображение имени.** Настройте отображаемого имени отправитель, которое используется в уведомлениях о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="06f9d-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="06f9d-345">Для каждого добавленного языка выберите язык во втором языковом окне (не нажимайте на X) и введите текстовое значение, которое необходимо в поле **Отображайте имя.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="06f9d-346">На следующем скриншоте показано настраиваемого имени отображения в уведомлении о нежелательной почте для конечных пользователей:</span><span class="sxs-lookup"><span data-stu-id="06f9d-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Настраиваемый отправитель отображает имя в уведомлении о нежелательной почте для конечных пользователей](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="06f9d-348">**Отказ от ответственности.** Добавьте настраиваемый отказ в нижней части уведомлений о нежелательной почте конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="06f9d-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="06f9d-349">Локализованный текст , **отказ от организации:** всегда включается в первую очередь, а затем текст, который вы указываете.</span><span class="sxs-lookup"><span data-stu-id="06f9d-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="06f9d-350">Для каждого добавленного языка выберите язык во втором языковом окне (не щелкните X) и введите текстовое значение, которое необходимо в поле **Отказ** от ответственности.</span><span class="sxs-lookup"><span data-stu-id="06f9d-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="06f9d-351">На следующем скриншоте показан настраиваемый отказ в уведомлении о нежелательной почте для конечных пользователей:</span><span class="sxs-lookup"><span data-stu-id="06f9d-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Настраиваемый отказ в нижней части уведомления о нежелательной почте конечного пользователя](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="06f9d-353">Просмотр тегов карантина в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="06f9d-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="06f9d-354">В Центре & безопасности перейдите к  политике управления угрозами и выберите теги \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="06f9d-355">Чтобы просмотреть параметры встроенных или настраиваемого карантиных тегов, выберите карантинный тег из списка (не выберите контрольный ящик).</span><span class="sxs-lookup"><span data-stu-id="06f9d-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="06f9d-356">Чтобы просмотреть глобальные параметры, выберите **параметры Global**</span><span class="sxs-lookup"><span data-stu-id="06f9d-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="06f9d-357">Просмотр тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="06f9d-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="06f9d-358">Если вы хотите использовать PowerShell для просмотра тегов карантина, сделайте любой из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="06f9d-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="06f9d-359">Чтобы просмотреть сводный список всех встроенных или настраиваемых тегов, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="06f9d-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="06f9d-360">Чтобы просмотреть параметры встроенных или настраиваемых карантиных тегов, замените имя тега карантина и запустите \<TagName\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="06f9d-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="06f9d-361">Чтобы просмотреть глобальные параметры, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="06f9d-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="06f9d-362">Дополнительные сведения о синтаксисе и параметрах см. в статье [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="06f9d-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="06f9d-363">Удаление тегов карантина в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="06f9d-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="06f9d-364">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-364">**Notes**:</span></span>

- <span data-ttu-id="06f9d-365">Нельзя удалять встроенные карантинные теги.</span><span class="sxs-lookup"><span data-stu-id="06f9d-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="06f9d-366">Перед удалением настраиваемой карантиной метки убедитесь, что она не используется.</span><span class="sxs-lookup"><span data-stu-id="06f9d-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="06f9d-367">Например, запустите следующую команду в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="06f9d-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="06f9d-368">Если используется карантинный [тег,](#step-2-assign-a-quarantine-tag-to-supported-features) замените назначенную карантиную метку перед ее удалением.</span><span class="sxs-lookup"><span data-stu-id="06f9d-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="06f9d-369">В Центре & безопасности перейдите к  политике управления угрозами и выберите теги \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="06f9d-370">На странице **Теги карантина** выберите настраиваемый тег карантина, который необходимо удалить, и нажмите кнопку **Удалить тег**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="06f9d-371">Нажмите **кнопку Удалить тег** в диалоговом окте подтверждения, который отображается.</span><span class="sxs-lookup"><span data-stu-id="06f9d-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="06f9d-372">Удаление тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="06f9d-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="06f9d-373">Если вы хотите использовать PowerShell для удаления настраиваемого тега карантина, замените имя тега карантина и запустите \<TagName\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="06f9d-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="06f9d-374">Подробные сведения о синтаксисах и параметрах см. в [инструкции Remove-QuarantineTag.](/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="06f9d-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="06f9d-375">Сведения о разрешении тегов карантина</span><span class="sxs-lookup"><span data-stu-id="06f9d-375">Quarantine tag permission details</span></span>

<span data-ttu-id="06f9d-376">В следующих разделах описаны последствия групп предварительного разрешения и отдельных разрешений в подробностях карантиновых сообщений и уведомлений о нежелательной почте конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="06f9d-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="06f9d-377">Группы предустановленных разрешений</span><span class="sxs-lookup"><span data-stu-id="06f9d-377">Preset permissions groups</span></span>

<span data-ttu-id="06f9d-378">Отдельные разрешения, включенные в группы предварительного разрешения, перечислены в таблице в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="06f9d-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="06f9d-379">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="06f9d-379">No access</span></span>

<span data-ttu-id="06f9d-380">Если на карантиновом  теге назначаются разрешения без доступа (без разрешений), пользователи по-прежнему получают некоторые базовые возможности:</span><span class="sxs-lookup"><span data-stu-id="06f9d-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="06f9d-381">**Карантинные сведения о сообщении.** Кнопка **"Просмотр"** всегда доступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Доступные кнопки в карантиновом сообщении, если тег карантина не дает пользователю разрешений на доступ](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="06f9d-383">**Уведомления о нежелательной почте** конечных пользователей: кнопка **Обзор,** которая принимает пользователя к сообщению на карантине, всегда доступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Доступные кнопки в уведомлении о нежелательной почте конечных пользователей, если тег карантина не дает пользователю разрешений на доступ](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="06f9d-385">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="06f9d-385">Limited access</span></span>

<span data-ttu-id="06f9d-386">Если тег карантина назначает  разрешения ограниченного доступа, пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="06f9d-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="06f9d-387">**Сведения о карантинном сообщении:** доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="06f9d-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="06f9d-388">**Выпуск запроса**</span><span class="sxs-lookup"><span data-stu-id="06f9d-388">**Request release**</span></span>
  - <span data-ttu-id="06f9d-389">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-389">**View message header**</span></span>
  - <span data-ttu-id="06f9d-390">**Предварительное сообщение**</span><span class="sxs-lookup"><span data-stu-id="06f9d-390">**Preview message**</span></span>
  - <span data-ttu-id="06f9d-391">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="06f9d-391">**Block sender**</span></span>
  - <span data-ttu-id="06f9d-392">**Удаление из карантина**</span><span class="sxs-lookup"><span data-stu-id="06f9d-392">**Remove from quarantine**</span></span>

  ![Доступные кнопки в карантиновом сообщении, если тег карантина дает пользователю разрешения ограниченного доступа](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="06f9d-394">**Уведомления о нежелательной почте** конечных пользователей: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="06f9d-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="06f9d-395">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="06f9d-395">**Block sender**</span></span>
  - <span data-ttu-id="06f9d-396">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="06f9d-396">**Review**</span></span>

  ![Доступные кнопки в уведомлении о нежелательной почте для конечных пользователей, если тег карантина дает пользователю разрешения ограниченного доступа.](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="06f9d-398">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="06f9d-398">Full access</span></span>

<span data-ttu-id="06f9d-399">Если тег карантина назначает  разрешения полного доступа (все доступные разрешения), пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="06f9d-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="06f9d-400">**Сведения о карантинном сообщении:** доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="06f9d-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="06f9d-401">**Сообщение о выпуске**</span><span class="sxs-lookup"><span data-stu-id="06f9d-401">**Release message**</span></span>
  - <span data-ttu-id="06f9d-402">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="06f9d-402">**View message header**</span></span>
  - <span data-ttu-id="06f9d-403">**Предварительное сообщение**</span><span class="sxs-lookup"><span data-stu-id="06f9d-403">**Preview message**</span></span>
  - <span data-ttu-id="06f9d-404">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="06f9d-404">**Block sender**</span></span>
  - <span data-ttu-id="06f9d-405">**Разрешить отправитель**</span><span class="sxs-lookup"><span data-stu-id="06f9d-405">**Allow sender**</span></span>
  - <span data-ttu-id="06f9d-406">**Удаление из карантина**</span><span class="sxs-lookup"><span data-stu-id="06f9d-406">**Remove from quarantine**</span></span>

  ![Доступные кнопки в карантиновом сообщении, если тег карантина дает пользователю разрешения на полный доступ](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="06f9d-408">**Уведомления о нежелательной почте** конечных пользователей: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="06f9d-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="06f9d-409">**Отправитель блока**</span><span class="sxs-lookup"><span data-stu-id="06f9d-409">**Block sender**</span></span>
  - <span data-ttu-id="06f9d-410">**Выпуск**</span><span class="sxs-lookup"><span data-stu-id="06f9d-410">**Release**</span></span>
  - <span data-ttu-id="06f9d-411">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="06f9d-411">**Review**</span></span>

  ![Доступные кнопки в уведомлении о нежелательной почте для конечных пользователей, если тег карантина дает пользователю разрешения на полный доступ](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="06f9d-413">Отдельные разрешения</span><span class="sxs-lookup"><span data-stu-id="06f9d-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="06f9d-414">Помните, что пользователи всегда получают кнопки, описанные в разделе [Нет доступа.](#no-access)</span><span class="sxs-lookup"><span data-stu-id="06f9d-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="06f9d-415">Эти кнопки не включены в отдельные описания разрешений.</span><span class="sxs-lookup"><span data-stu-id="06f9d-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="06f9d-416">Разрешить разрешение отправитель</span><span class="sxs-lookup"><span data-stu-id="06f9d-416">Allow sender permission</span></span>

<span data-ttu-id="06f9d-417">Разрешение **разрешить отправитель** _(PermissionToAllowSender)_ управляет доступом к кнопке, которая позволяет пользователям удобно добавлять отправитель сообщения, на карантин, в список безопасных отправителей.</span><span class="sxs-lookup"><span data-stu-id="06f9d-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="06f9d-418">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="06f9d-419">**Разрешить разрешение отправитель** включен: **кнопка Разрешить отправитель** доступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="06f9d-420">**Разрешить отключение** разрешения отправитель: кнопка **Разрешить** отправитель недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="06f9d-421">**Уведомления о нежелательной почте конечных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="06f9d-422">Дополнительные сведения о списке "Безопасные отправители" см. в рублях Предотвращение блокировки доверенных отправителей и использование Exchange Online PowerShell для настройки коллекции safelist на [почтовом ящике.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox) [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)</span><span class="sxs-lookup"><span data-stu-id="06f9d-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="06f9d-423">Разрешение отправитель блокировки</span><span class="sxs-lookup"><span data-stu-id="06f9d-423">Block sender permission</span></span>

<span data-ttu-id="06f9d-424">Разрешение **отправителей** блокировки _(PermissionToBlockSender)_ управляет доступом к кнопке, которая позволяет пользователям удобно добавлять отправитель сообщений, на карантин, в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="06f9d-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="06f9d-425">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="06f9d-426">**Включено разрешение отправитель** блока. Кнопка **"Отправитель** блока" доступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="06f9d-427">**Отключено разрешение** отправитель блокировки. Кнопка **"Отправитель** блока" недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="06f9d-428">**Уведомления о нежелательной почте конечных пользователей:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="06f9d-429">**Отключено разрешение** отправитель блокировки. Кнопка **"Отправитель** блока" недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="06f9d-430">**Включено разрешение отправитель** блока. Кнопка **"Отправитель** блока" доступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="06f9d-431">Дополнительные сведения о списке заблокированных отправителей см. в рублях [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and Use Exchange Online [PowerShell to configure the safelist collection on a mailbox.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="06f9d-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="06f9d-432">Разрешения на удаление</span><span class="sxs-lookup"><span data-stu-id="06f9d-432">Delete permission</span></span>

<span data-ttu-id="06f9d-433">Разрешение **Delete** _(PermissionToDelete)_ управляет возможностью пользователей удалять свои сообщения (сообщения, в которых пользователь является получателем) из карантина.</span><span class="sxs-lookup"><span data-stu-id="06f9d-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="06f9d-434">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="06f9d-435">**Удаление** включенного разрешения. Кнопка Удаление из **карантина** доступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="06f9d-436">**Удаление** отключенных разрешений. Кнопка Удалить из **карантина** недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="06f9d-437">**Уведомления о нежелательной почте конечных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="06f9d-438">Разрешение предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="06f9d-438">Preview permission</span></span>

<span data-ttu-id="06f9d-439">Разрешение **Preview** _(PermissionToPreview)_ контролирует возможность предварительного просмотра сообщений пользователями в карантине.</span><span class="sxs-lookup"><span data-stu-id="06f9d-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="06f9d-440">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="06f9d-441">**Включено** разрешение предварительного просмотра: **доступна** кнопка предварительного просмотра сообщения.</span><span class="sxs-lookup"><span data-stu-id="06f9d-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="06f9d-442">**Отключено** разрешение предварительного просмотра. **Кнопка** предварительного просмотра недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="06f9d-443">**Уведомления о нежелательной почте конечных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="06f9d-444">Разрешить получателям освободить сообщение из разрешения карантина</span><span class="sxs-lookup"><span data-stu-id="06f9d-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="06f9d-445">Разрешить **получателям** освободить сообщение из разрешения карантина _(PermissionToRelease)_ контролирует возможность пользователей выпускать свои карантинные сообщения напрямую и без разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="06f9d-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="06f9d-446">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="06f9d-447">Включено разрешение. Доступна кнопка **"Сообщение** о выпуске".</span><span class="sxs-lookup"><span data-stu-id="06f9d-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="06f9d-448">Отключено разрешение. **Кнопка "Сообщение о выпуске"** недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="06f9d-449">**Уведомления о нежелательной почте конечных пользователей:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="06f9d-450">Включено разрешение. Доступна кнопка **Release.**</span><span class="sxs-lookup"><span data-stu-id="06f9d-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="06f9d-451">Отключено разрешение. **Кнопка Выпуска** недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="06f9d-452">Разрешить получателям запрашивать сообщение, которое будет выпущено из разрешения карантина</span><span class="sxs-lookup"><span data-stu-id="06f9d-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="06f9d-453">Разрешить **получателям** запрашивать сообщение, которое будет выпущено из разрешения карантина _(PermissionToRequestRelease)_ контролирует возможность пользователей запрашивать выпуск их карантинов. </span><span class="sxs-lookup"><span data-stu-id="06f9d-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="06f9d-454">Сообщение будет выпущено только после утверждения запроса администратором.</span><span class="sxs-lookup"><span data-stu-id="06f9d-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="06f9d-455">**Сведения о карантине:**</span><span class="sxs-lookup"><span data-stu-id="06f9d-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="06f9d-456">Включено разрешение: **доступна кнопка выпуска** запроса.</span><span class="sxs-lookup"><span data-stu-id="06f9d-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="06f9d-457">Отключено разрешение. **Кнопка выпуска запроса** недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="06f9d-458">**Уведомления о нежелательной почте** конечных пользователей. Кнопка **Выпуска** недоступна.</span><span class="sxs-lookup"><span data-stu-id="06f9d-458">**End-user spam notifications**: The **Release** button is not available.</span></span>