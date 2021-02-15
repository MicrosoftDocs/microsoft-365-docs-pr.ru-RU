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
description: Администраторы могут узнать, как использовать теги карантина для управления тем, что пользователи могут делать с их сообщениями на карантине.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f18ad6ce1c8b12d38aef377ab663ca679a703e5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928906"
---
# <a name="quarantine-tags"></a><span data-ttu-id="c76f4-103">Теги карантина</span><span class="sxs-lookup"><span data-stu-id="c76f4-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="c76f4-104">Функции, описанные в этой статье, в настоящее время доступны в предварительной версии, доступны не всем и могут быть измениться.</span><span class="sxs-lookup"><span data-stu-id="c76f4-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="c76f4-105">Теги карантина в Exchange Online Protection (EOP) позволяют администраторам контролировать, что пользователи могут делать с их сообщениями на карантине в зависимости от того, как сообщение было в карантине.</span><span class="sxs-lookup"><span data-stu-id="c76f4-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="c76f4-106">В EOP традиционно разрешены или запрещены определенные [](find-and-release-quarantined-messages-as-a-user.md) уровни интерактивности для сообщений в карантине и уведомлениях конечных пользователей о [нежелательной почте.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c76f4-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="c76f4-107">Например, конечные пользователи могут просматривать и освободить сообщения, которые были на карантине путем фильтрации нежелательной почты как спама или массовой рассылки, но не могут просматривать или освободить сообщения, которые были на карантине, как фишинговые сообщения с высокой достоверности.</span><span class="sxs-lookup"><span data-stu-id="c76f4-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="c76f4-108">Для [](#step-2-assign-a-quarantine-tag-to-supported-features)поддерживаемых функций защиты теги карантина указывают, что пользователям разрешено делать в уведомлениях о нежелательной почте конечных пользователей и в их сообщениях на карантине (сообщениях, получателем которых является пользователь).</span><span class="sxs-lookup"><span data-stu-id="c76f4-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="c76f4-109">Теги карантина по умолчанию автоматически назначены для применения исторических возможностей для конечных пользователей в сообщениях, на карантине.</span><span class="sxs-lookup"><span data-stu-id="c76f4-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="c76f4-110">Также можно создать и назначить настраиваемые теги карантина, чтобы разрешить или запретить конечным пользователям выполнять определенные действия с сообщениями в карантине.</span><span class="sxs-lookup"><span data-stu-id="c76f4-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="c76f4-111">Отдельные разрешения объединяются в следующие предустановленные группы разрешений:</span><span class="sxs-lookup"><span data-stu-id="c76f4-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="c76f4-112">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="c76f4-112">No access</span></span>
- <span data-ttu-id="c76f4-113">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="c76f4-113">Limited access</span></span>
- <span data-ttu-id="c76f4-114">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="c76f4-114">Full access</span></span>

<span data-ttu-id="c76f4-115">Доступные отдельные разрешения и включенные или не включенные в предустановленные группы разрешений описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="c76f4-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="c76f4-116">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c76f4-116">Permission</span></span>|<span data-ttu-id="c76f4-117">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="c76f4-117">No access</span></span>|<span data-ttu-id="c76f4-118">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="c76f4-118">Limited access</span></span>|<span data-ttu-id="c76f4-119">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="c76f4-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="c76f4-120">**Разрешить отправитель** (_PermissionToAllowSender)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="c76f4-122">**Block sender** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="c76f4-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="c76f4-125">**Delete** (_PermissionToDelete)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-125">**Delete** (_PermissionToDelete_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="c76f4-128">**Preview** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="c76f4-128">**Preview** (_PermissionToPreview_)</span></span>||![Флажок](../../media/checkmark.png)|![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="c76f4-131">**Разрешить получателям освободить сообщение из карантина** (_PermissionToRelease)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Флажок](../../media/checkmark.png)|
|<span data-ttu-id="c76f4-133">**Разрешить получателям запрашивать сообщение для освобождения** из карантина (_PermissionToRequestRelease)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Флажок](../../media/checkmark.png)||
|

<span data-ttu-id="c76f4-135">Если вам не нравится использование разрешений по умолчанию в предустановленных группах разрешений, можно использовать настраиваемые разрешения при создании или изменении настраиваемой теги карантина.</span><span class="sxs-lookup"><span data-stu-id="c76f4-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="c76f4-136">Дополнительные сведения о том, что [](#quarantine-tag-permission-details) делает каждое разрешение, см. в разделе о разрешении тега карантина далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c76f4-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="c76f4-137">Теги карантина создаются и назначаются в Центре безопасности и & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками Exchange Online; автономный EOP PowerShell в организациях EOP без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="c76f4-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c76f4-138">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c76f4-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c76f4-139">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c76f4-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c76f4-140">Чтобы перейти непосредственно на страницу **тегов карантина,** откройте <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="c76f4-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="c76f4-141">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c76f4-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c76f4-142">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c76f4-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c76f4-143">Чтобы просматривать, создавать, изменять или удалять теги карантина, необходимо  быть  участником ролей "Управление организацией" или "Администратор безопасности" в Центре безопасности [& соответствия требованиям.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="c76f4-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="c76f4-144">Шаг 1. Создание тегов карантина в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c76f4-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="c76f4-145">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами и выберите теги \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="c76f4-146">На странице **"Теги карантина"** выберите **"Добавить настраиваемый тег".**</span><span class="sxs-lookup"><span data-stu-id="c76f4-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="c76f4-147">Откроется **мастер новых** тегов.</span><span class="sxs-lookup"><span data-stu-id="c76f4-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="c76f4-148">На странице **"Имя тега"** введите краткое, но уникальное имя в **поле "Имя** тега".</span><span class="sxs-lookup"><span data-stu-id="c76f4-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="c76f4-149">Вам потребуется идентифицировать и выбрать тег по имени в предстоящих действиях.</span><span class="sxs-lookup"><span data-stu-id="c76f4-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="c76f4-150">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76f4-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c76f4-151">На странице **доступа к сообщению получателя** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c76f4-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="c76f4-152">**Нет доступа**</span><span class="sxs-lookup"><span data-stu-id="c76f4-152">**No access**</span></span>
   - <span data-ttu-id="c76f4-153">**Ограниченный доступ**</span><span class="sxs-lookup"><span data-stu-id="c76f4-153">**Limited access**</span></span>
   - <span data-ttu-id="c76f4-154">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="c76f4-154">**Full access**</span></span>

   <span data-ttu-id="c76f4-155">Отдельные разрешения, включенные в эти группы разрешений, описаны ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c76f4-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="c76f4-156">Чтобы указать пользовательские разрешения, выберите "Задать **определенный доступ (расширенный")** и настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c76f4-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="c76f4-157">**Выберите параметр действия выпуска:** выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c76f4-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="c76f4-158">**Нет действия по выпуску:** это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c76f4-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="c76f4-159">**Разрешение получателям освободить сообщение из карантина**</span><span class="sxs-lookup"><span data-stu-id="c76f4-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="c76f4-160">**Разрешение получателям запрашивать сообщение для освобождения из карантина**</span><span class="sxs-lookup"><span data-stu-id="c76f4-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="c76f4-161">**Выберите дополнительные действия, которые** получатели могут делать с сообщениями в карантине: выберите некоторые, все или ни одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c76f4-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="c76f4-162">**удаление**;</span><span class="sxs-lookup"><span data-stu-id="c76f4-162">**Delete**</span></span>
       - <span data-ttu-id="c76f4-163">**Предварительная версия**</span><span class="sxs-lookup"><span data-stu-id="c76f4-163">**Preview**</span></span>
       - <span data-ttu-id="c76f4-164">**Разрешить отправитель**</span><span class="sxs-lookup"><span data-stu-id="c76f4-164">**Allow sender**</span></span>
       - <span data-ttu-id="c76f4-165">**Блокировать отправитель**</span><span class="sxs-lookup"><span data-stu-id="c76f4-165">**Block sender**</span></span>

   <span data-ttu-id="c76f4-166">Эти разрешения и их влияние на сообщения в карантине и уведомления конечных [](#quarantine-tag-permission-details) пользователей о нежелательной почте описаны в разделе сведений о разрешении тега карантина далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c76f4-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="c76f4-167">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c76f4-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c76f4-168">На странице **"Сводка"** просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="c76f4-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="c76f4-169">Вы можете **нажать кнопку "Изменить"** для каждого параметра, чтобы изменить его.</span><span class="sxs-lookup"><span data-stu-id="c76f4-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="c76f4-170">По завершению нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="c76f4-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="c76f4-171">Нажмите **кнопку "Готово"** на странице подтверждения.</span><span class="sxs-lookup"><span data-stu-id="c76f4-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="c76f4-172">Теперь можно назначить тег карантина функции карантина, как описано в разделе ["Шаг 2".](#step-2-assign-a-quarantine-tag-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="c76f4-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="c76f4-173">Создание тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76f4-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="c76f4-174">Если вы хотите использовать PowerShell для создания тегов карантина, подключите Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте командлет **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="c76f4-175">У вас есть два разных способа выбора:</span><span class="sxs-lookup"><span data-stu-id="c76f4-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="c76f4-176">Используйте параметр _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="c76f4-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="c76f4-177">Используйте параметр _EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="c76f4-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="c76f4-178">Эти методы описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c76f4-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="c76f4-179">Использование параметра EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="c76f4-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="c76f4-180">Чтобы создать тег карантина с помощью параметра _EndUserQuarantinePermissionsValue,_ используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c76f4-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="c76f4-181">Параметр _EndUserQuarantinePermissionsValue_ использует десятичное значение, преобразованное из двоичного значения.</span><span class="sxs-lookup"><span data-stu-id="c76f4-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="c76f4-182">Двоичное значение соответствует доступным разрешениям на карантин конечных пользователей в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="c76f4-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="c76f4-183">Для каждого разрешения значение 1 равно True, а значение 0 равно False.</span><span class="sxs-lookup"><span data-stu-id="c76f4-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="c76f4-184">Необходимый порядок и значения для каждого отдельного разрешения в предустановленных группах разрешений описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="c76f4-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="c76f4-185">Разрешение</span><span class="sxs-lookup"><span data-stu-id="c76f4-185">Permission</span></span>|<span data-ttu-id="c76f4-186">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="c76f4-186">No access</span></span>|<span data-ttu-id="c76f4-187">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="c76f4-187">Limited access</span></span>|<span data-ttu-id="c76f4-188">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="c76f4-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="c76f4-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="c76f4-189">PermissionToAllowSender</span></span>|<span data-ttu-id="c76f4-190">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-190">0</span></span>|<span data-ttu-id="c76f4-191">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-191">0</span></span>|<span data-ttu-id="c76f4-192">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-192">1</span></span>|
|<span data-ttu-id="c76f4-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="c76f4-193">PermissionToBlockSender</span></span>|<span data-ttu-id="c76f4-194">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-194">0</span></span>|<span data-ttu-id="c76f4-195">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-195">1</span></span>|<span data-ttu-id="c76f4-196">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-196">1</span></span>|
|<span data-ttu-id="c76f4-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="c76f4-197">PermissionToDelete</span></span>|<span data-ttu-id="c76f4-198">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-198">0</span></span>|<span data-ttu-id="c76f4-199">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-199">1</span></span>|<span data-ttu-id="c76f4-200">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-200">1</span></span>|
|<span data-ttu-id="c76f4-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c76f4-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="c76f4-202">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-202">0</span></span>|<span data-ttu-id="c76f4-203">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-203">0</span></span>|<span data-ttu-id="c76f4-204">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-204">0</span></span>|
|<span data-ttu-id="c76f4-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="c76f4-205">PermissionToPreview</span></span>|<span data-ttu-id="c76f4-206">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-206">0</span></span>|<span data-ttu-id="c76f4-207">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-207">1</span></span>|<span data-ttu-id="c76f4-208">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-208">1</span></span>|
|<span data-ttu-id="c76f4-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="c76f4-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="c76f4-210">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-210">0</span></span>|<span data-ttu-id="c76f4-211">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-211">0</span></span>|<span data-ttu-id="c76f4-212">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-212">1</span></span>|
|<span data-ttu-id="c76f4-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="c76f4-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="c76f4-214">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-214">0</span></span>|<span data-ttu-id="c76f4-215">1 </span><span class="sxs-lookup"><span data-stu-id="c76f4-215">1</span></span>|<span data-ttu-id="c76f4-216">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-216">0</span></span>|
|<span data-ttu-id="c76f4-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c76f4-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="c76f4-218">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-218">0</span></span>|<span data-ttu-id="c76f4-219">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-219">0</span></span>|<span data-ttu-id="c76f4-220">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-220">0</span></span>|
|<span data-ttu-id="c76f4-221">Двоичное значение</span><span class="sxs-lookup"><span data-stu-id="c76f4-221">Binary value</span></span>|<span data-ttu-id="c76f4-222">00000000</span><span class="sxs-lookup"><span data-stu-id="c76f4-222">00000000</span></span>|<span data-ttu-id="c76f4-223">01101010</span><span class="sxs-lookup"><span data-stu-id="c76f4-223">01101010</span></span>|<span data-ttu-id="c76f4-224">11101100</span><span class="sxs-lookup"><span data-stu-id="c76f4-224">11101100</span></span>|
|<span data-ttu-id="c76f4-225">Десятичная затметь для использования</span><span class="sxs-lookup"><span data-stu-id="c76f4-225">Decimal value to use</span></span>|<span data-ttu-id="c76f4-226">0</span><span class="sxs-lookup"><span data-stu-id="c76f4-226">0</span></span>|<span data-ttu-id="c76f4-227">106</span><span class="sxs-lookup"><span data-stu-id="c76f4-227">106</span></span>|<span data-ttu-id="c76f4-228">236</span><span class="sxs-lookup"><span data-stu-id="c76f4-228">236</span></span>|

<span data-ttu-id="c76f4-229"><sup>\*</sup> В настоящее время это значение всегда 0.</span><span class="sxs-lookup"><span data-stu-id="c76f4-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="c76f4-230">Для PermissionToViewHeader значение 0 не скрывает  кнопку "Просмотреть заголовок сообщения" в сведениях о сообщении на карантине (кнопка всегда доступна).</span><span class="sxs-lookup"><span data-stu-id="c76f4-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="c76f4-231"><sup>\*\*</sup> Не устанавливайте для обоих этих значений значение 1.</span><span class="sxs-lookup"><span data-stu-id="c76f4-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="c76f4-232">Установите для одного из них 1, а другого 0 или установите для обоих 0.</span><span class="sxs-lookup"><span data-stu-id="c76f4-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="c76f4-233">В этом примере создается новый тег карантина NoAccess, который назначает разрешения "Нет доступа", как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="c76f4-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="c76f4-234">Для разрешений на ограниченный доступ используйте значение 106.</span><span class="sxs-lookup"><span data-stu-id="c76f4-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="c76f4-235">Для разрешений "Полный доступ" используйте значение 236.</span><span class="sxs-lookup"><span data-stu-id="c76f4-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="c76f4-236">Для пользовательских разрешений используйте предыдущую таблицу, чтобы получить двоичное значение, соответствующее нужным разрешениям.</span><span class="sxs-lookup"><span data-stu-id="c76f4-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="c76f4-237">Преобразуем двоичное значение в десятичное и используйте десятичное значение для _параметра EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="c76f4-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="c76f4-238">Подробные сведения о синтаксисах и параметрах см. в описании [New-QuarantineTag.](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="c76f4-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="c76f4-239">Использование параметра EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="c76f4-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="c76f4-240">Чтобы создать тег карантина с помощью параметра _EndUserQuarantinePermissionsValue,_ сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c76f4-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="c76f4-241">О.</span><span class="sxs-lookup"><span data-stu-id="c76f4-241">A.</span></span> <span data-ttu-id="c76f4-242">Храните объект разрешений карантина в переменной с помощью **cmdlet New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="c76f4-243">B.</span><span class="sxs-lookup"><span data-stu-id="c76f4-243">B.</span></span> <span data-ttu-id="c76f4-244">Используйте переменную в качестве _значения EndUserQuarantinePermissions_ в команде **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="c76f4-245">Шаг А. Хранение объекта разрешений карантина в переменной</span><span class="sxs-lookup"><span data-stu-id="c76f4-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="c76f4-246">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="c76f4-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="c76f4-247">По умолчанию для любых неиспользимых параметров используется значение , поэтому вам нужно использовать только параметры, для которых требуется `$false` установить значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="c76f4-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="c76f4-248">В следующих примерах покажите, как создавать объекты разрешений, соответствующие предварительно заранее.</span><span class="sxs-lookup"><span data-stu-id="c76f4-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="c76f4-249">**Нет доступа:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="c76f4-250">**Ограниченный доступ:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="c76f4-251">**Полный доступ:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="c76f4-252">Чтобы увидеть установленные значения, запустите имя переменной в качестве команды (например, запустите `$NoAccess` команду).</span><span class="sxs-lookup"><span data-stu-id="c76f4-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="c76f4-253">Для пользовательских разрешений не устанавливайте для параметров _PermissionToRelease_ и _PermissionToRequestRelease_ параметры `$true` .</span><span class="sxs-lookup"><span data-stu-id="c76f4-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="c76f4-254">Установите одно из `$true` них и оставьте другое как `$false` , или оставьте оба как `$false` .</span><span class="sxs-lookup"><span data-stu-id="c76f4-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="c76f4-255">Вы также можете изменить существующую объектную переменную разрешений после создания, но перед ее использованием с помощью cmdlet **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="c76f4-256">Подробные сведения о синтаксисах и параметрах см. в описании [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) и [Set-QuarantinePermissions.](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="c76f4-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="c76f4-257">Шаг Б. Использование переменной в команде New-QuarantineTag командной New-QuarantineTag</span><span class="sxs-lookup"><span data-stu-id="c76f4-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="c76f4-258">После создания и хранения объекта разрешений в переменной используйте переменную для значения параметра _EndUserQuarantinePermission_ в следующей команде **New-QuarantineTag:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="c76f4-259">В этом примере создается новый тег карантина с именем LimitedAccess с помощью объекта разрешений, который был описан и создан на предыдущем `$LimitedAccess` шаге.</span><span class="sxs-lookup"><span data-stu-id="c76f4-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="c76f4-260">Подробные сведения о синтаксисах и параметрах см. в описании [New-QuarantineTag.](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="c76f4-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="c76f4-261">Шаг 2. Назначение тега карантина поддерживаемых функций</span><span class="sxs-lookup"><span data-stu-id="c76f4-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="c76f4-262">В _поддерживаемых_ средствах защиты, которые карантин сообщений или файлов (автоматически или в качестве настраиваемого действия) можно назначить тег карантина доступным действиям карантина.</span><span class="sxs-lookup"><span data-stu-id="c76f4-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="c76f4-263">Функции карантина сообщений и доступность тегов карантина описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="c76f4-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="c76f4-264">Возможность</span><span class="sxs-lookup"><span data-stu-id="c76f4-264">Feature</span></span>|<span data-ttu-id="c76f4-265">Поддерживаемые теги карантина?</span><span class="sxs-lookup"><span data-stu-id="c76f4-265">Quarantine tags supported?</span></span>|<span data-ttu-id="c76f4-266">Используемые теги карантина по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c76f4-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="c76f4-267">[Политики нежелательной почты:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c76f4-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="c76f4-268">**Spam** _(SpamAction)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="c76f4-269">**Нежелательное сообщение с** высокой достоверности (_HighConfidenceSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="c76f4-270">**Фишинговое сообщение** электронной почты (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="c76f4-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="c76f4-271">**Фишинговое сообщение с высокой** достоверности (_HighConfidencePhishAction)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="c76f4-272">**Массовая рассылка** _(BulkSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="c76f4-273">Да</span><span class="sxs-lookup"><span data-stu-id="c76f4-273">Yes</span></span>|<ul><li><span data-ttu-id="c76f4-274">DefaultSpamTag (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="c76f4-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="c76f4-275">DefaultHighConfSpamTag (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="c76f4-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="c76f4-276">DefaultPhishTag (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="c76f4-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="c76f4-277">DefaultHighConfPhishTag (Нет доступа)</span><span class="sxs-lookup"><span data-stu-id="c76f4-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="c76f4-278">DefaultBulkTag (полный доступ)</span><span class="sxs-lookup"><span data-stu-id="c76f4-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="c76f4-279">Политики защиты от фишинга:</span><span class="sxs-lookup"><span data-stu-id="c76f4-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="c76f4-280">[Защита от спуфинговой аналитики](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="c76f4-281">[Защита от подмикания:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c76f4-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="c76f4-282">**Если сообщение отправляется ненастоящем пользователем** (_TargetedUserProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="c76f4-283">**Если электронная почта отправляется подмененным доменом** (_TargetedDomainProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="c76f4-284">**Аналитика почтовых ящиков** \> **Если сообщение отправляется** ненастоящем пользователем (_MailboxIntelligenceProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="c76f4-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="c76f4-285">Нет</span><span class="sxs-lookup"><span data-stu-id="c76f4-285">No</span></span>|<span data-ttu-id="c76f4-286">н/д</span><span class="sxs-lookup"><span data-stu-id="c76f4-286">n/a</span></span>|
|<span data-ttu-id="c76f4-287">[Политики борьбы с вредоносными программами:](configure-anti-malware-policies.md)все обнаруженные сообщения всегда находятся в карантине.</span><span class="sxs-lookup"><span data-stu-id="c76f4-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="c76f4-288">Нет</span><span class="sxs-lookup"><span data-stu-id="c76f4-288">No</span></span>|<span data-ttu-id="c76f4-289">н/д</span><span class="sxs-lookup"><span data-stu-id="c76f4-289">n/a</span></span>|
|[<span data-ttu-id="c76f4-290">Безопасные вложения для SharePoint, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c76f4-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="c76f4-291">Нет</span><span class="sxs-lookup"><span data-stu-id="c76f4-291">No</span></span>|<span data-ttu-id="c76f4-292">н/д</span><span class="sxs-lookup"><span data-stu-id="c76f4-292">n/a</span></span>|
|<span data-ttu-id="c76f4-293">[Правила потока почты](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (также известные как правила транспорта) с действием: **доставка** сообщения в карантин, на который отправлено сообщение (_карантин)._</span><span class="sxs-lookup"><span data-stu-id="c76f4-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="c76f4-294">Нет</span><span class="sxs-lookup"><span data-stu-id="c76f4-294">No</span></span>|<span data-ttu-id="c76f4-295">н/д</span><span class="sxs-lookup"><span data-stu-id="c76f4-295">n/a</span></span>|
|

<span data-ttu-id="c76f4-296"><sup>\*</sup> Параметры защиты от фишинга доступны только в политиках защиты от фишинга в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="c76f4-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="c76f4-297">Если вы довольны разрешениями конечных пользователей, предоставляемыми тегами карантина по умолчанию, вам не нужно ничего делать.</span><span class="sxs-lookup"><span data-stu-id="c76f4-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="c76f4-298">Если вы хотите настроить возможности конечных пользователей (доступные кнопки) в уведомлениях о нежелательной почте конечных пользователей или в сведениях о сообщении в карантине, можно назначить настраиваемый тег карантина.</span><span class="sxs-lookup"><span data-stu-id="c76f4-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="c76f4-299">Назначение тегов карантина в политиках защиты от нежелательной почты в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c76f4-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="c76f4-300">Полные инструкции по созданию и изменению политик борьбы с нежелательной почтой описаны в описании настройки политик нежелательной почты [в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c76f4-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="c76f4-301">В Центре безопасности & соответствия требованиям  перейдите в политику управления угрозами, а затем выберите \>  \> **"Anti-spam".**</span><span class="sxs-lookup"><span data-stu-id="c76f4-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="c76f4-302">Или откройте <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="c76f4-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="c76f4-303">Найдите и выберите существующую политику для изменения или создайте новую политику.</span><span class="sxs-lookup"><span data-stu-id="c76f4-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="c76f4-304">Во flyout сведений о политике расширите раздел **"Спам и массовые действия".**</span><span class="sxs-lookup"><span data-stu-id="c76f4-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="c76f4-305">Если вы выбрали  сообщение "Карантин" для действия решения о  доступной фильтрации нежелательной почты, вы можете выбрать тег карантина в поле "Применить политику карантина".</span><span class="sxs-lookup"><span data-stu-id="c76f4-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="c76f4-306">**Примечание.** При создании новой политики пустое значение тега карантина для решения фильтрации нежелательной почты указывает используемый по умолчанию тег карантина для этого решения.</span><span class="sxs-lookup"><span data-stu-id="c76f4-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="c76f4-307">При дальнейшем редактировании политики пустые значения заменяются фактическими именами тегов карантина по умолчанию, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="c76f4-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Выбор тегов карантина в политике нежелательной почты](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="c76f4-309">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c76f4-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="c76f4-310">Назначение тегов карантина в политиках нежелательной почты в PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76f4-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="c76f4-311">Если вы хотите назначить теги карантина в политиках защиты от нежелательной почты с помощью PowerShell, подключись к Exchange Online PowerShell или Exchange Online Protection PowerShell и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c76f4-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="c76f4-312">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="c76f4-312">**Notes**:</span></span>

- <span data-ttu-id="c76f4-313">По умолчанию параметр _HighConfidencePhishAction_ имеет значение Quarantine, поэтому вам не нужно устанавливать действие карантина для обнаружения фишинга с высокой достоверности в новых политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c76f4-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="c76f4-314">Для всех остальных результатов фильтрации нежелательной почты в новых или существующих политиках нежелательной почты тег карантина будет действовать только в том случае, если действие имеет значение "Карантин".</span><span class="sxs-lookup"><span data-stu-id="c76f4-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="c76f4-315">Чтобы увидеть значения действий в существующих политиках борьбы с нежелательной почтой, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c76f4-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="c76f4-316">Сведения о значениях действий по умолчанию и рекомендуемых значениях действий для Standard и Strict см. в параметрах политики [EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="c76f4-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="c76f4-317">Решение фильтра нежелательной почты без соответствующего [](#step-2-assign-a-quarantine-tag-to-supported-features) параметра тега карантина означает, что для этого решения используется тег карантина по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c76f4-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="c76f4-318">Тег карантина по умолчанию необходимо заменить на настраиваемый тег карантина, только если вы хотите изменить возможности конечных пользователей по умолчанию для сообщений в карантине.</span><span class="sxs-lookup"><span data-stu-id="c76f4-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="c76f4-319">Для новой политики фильтрации нежелательной почты в PowerShell требуется политика фильтрации нежелательной почты (параметры) с использованием параметра **New-HostedContentFilterPolicy** и новое правило фильтрации нежелательной почты (фильтры получателей) с помощью этого параметра. </span><span class="sxs-lookup"><span data-stu-id="c76f4-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="c76f4-320">Инструкции см. в инструкциях по созданию политик нежелательной почты с [помощью PowerShell.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="c76f4-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="c76f4-321">В этом примере создается новая политика фильтрации нежелательной почты Research Department со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="c76f4-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="c76f4-322">Действие для всех оглавлений фильтрации нежелательной почты установлено в карантине.</span><span class="sxs-lookup"><span data-stu-id="c76f4-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="c76f4-323">Настраиваемый тег карантина NoAccess,  который не назначает разрешения на доступ, заменяет все теги карантина по умолчанию, которые еще не назначили разрешения на доступ по умолчанию. </span><span class="sxs-lookup"><span data-stu-id="c76f4-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="c76f4-324">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c76f4-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="c76f4-325">В этом примере изменяется существующая политика фильтрации нежелательной почты с именем Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c76f4-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="c76f4-326">Действие для решения карантина нежелательной почты установлено на карантин, и настраиваемый тег карантина NoAccess назначен.</span><span class="sxs-lookup"><span data-stu-id="c76f4-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="c76f4-327">Дополнительные сведения о синтаксисе и параметрах см. в статье [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c76f4-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="c76f4-328">Настройка параметров уведомлений глобального карантина в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c76f4-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="c76f4-329">Глобальные параметры тегов карантина позволяют настраивать уведомления конечного пользователя о нежелательной почте, которые отправляются получателям сообщений, которые были отправлены на карантин.</span><span class="sxs-lookup"><span data-stu-id="c76f4-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="c76f4-330">Дополнительные сведения об этих уведомлениях см. в уведомлениях конечных пользователей [о нежелательной почте.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c76f4-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="c76f4-331">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами и выберите теги \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="c76f4-332">На странице **"Теги карантина"** выберите **"Глобальные параметры".**</span><span class="sxs-lookup"><span data-stu-id="c76f4-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="c76f4-333">В **открываемом окне** параметров уведомлений карантина настройте некоторые или все следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c76f4-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="c76f4-334">**Используйте логотип компании:** выберите этот параметр, чтобы заменить логотип Майкрософт по умолчанию, который используется в верхней части уведомлений пользователя о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="c76f4-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="c76f4-335">Прежде чем сделать это, следуйте инструкциям в настройке [темы Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) для вашей организации, чтобы отправить пользовательский логотип.</span><span class="sxs-lookup"><span data-stu-id="c76f4-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="c76f4-336">На следующем снимке экрана показан пользовательский логотип в уведомлении пользователя о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="c76f4-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Настраиваемый логотип в уведомлении пользователя о нежелательной почте](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="c76f4-338">**Выберите язык:** уведомления конечных пользователей о нежелательной почте уже локализованы в зависимости от языковых параметров получателя.</span><span class="sxs-lookup"><span data-stu-id="c76f4-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="c76f4-339">Для отображаемых имен и значений  заявления об отказе можно указать настраиваемый текст на разных **языках.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="c76f4-340">Выберите хотя бы один язык в первом языковом поле и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="c76f4-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="c76f4-341">Можно выбрать несколько языков, нажав кнопку **"Добавить"** после каждого из них.</span><span class="sxs-lookup"><span data-stu-id="c76f4-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="c76f4-342">В поле "Язык раздела" показаны все выбранные языки:</span><span class="sxs-lookup"><span data-stu-id="c76f4-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Выбранные языки во втором языковом поле в глобальных параметрах уведомлений карантина тегов карантина](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="c76f4-344">**Отображаемые** имена: настройте отображаемые имена отправитель, которые используются в уведомлениях о нежелательной почте конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c76f4-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="c76f4-345">Для каждого добавленного языка выберите язык во втором языковом поле (не щелкайте X) и введите нужное текстовое значение в поле отображаемого **имени.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="c76f4-346">На следующем снимке экрана показано настраиваемого отображаемого имени в уведомлении пользователя о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="c76f4-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Отображаемого имени настроенного отправитель в уведомлении о нежелательной почте для пользователя](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="c76f4-348">**Заявление об отказе:** добавьте пользовательское заявление об отказе в конец уведомлений пользователя о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="c76f4-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="c76f4-349">Локализованный текст , заявление об отказе от ответственности из **организации:** всегда включается первым, за которым следует текст, который вы указали.</span><span class="sxs-lookup"><span data-stu-id="c76f4-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="c76f4-350">Для каждого добавленного языка выберите язык во втором языковом поле (не щелкайте X) и введите нужное текстовое значение в поле заявления об **отказе.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="c76f4-351">На следующем снимке экрана показано настроенное заявление об отказе в уведомлении пользователя о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="c76f4-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Настраиваемая оговорка в нижней части уведомления конечного пользователя о нежелательной почте](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="c76f4-353">Просмотр тегов карантина в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c76f4-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="c76f4-354">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами и выберите теги \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="c76f4-355">Чтобы просмотреть параметры встроенных или настраиваемые теги карантина, выберите тег карантина в списке (не устанавливайте этот параметр).</span><span class="sxs-lookup"><span data-stu-id="c76f4-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="c76f4-356">Чтобы просмотреть глобальные параметры, выберите глобальные **параметры**</span><span class="sxs-lookup"><span data-stu-id="c76f4-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="c76f4-357">Просмотр тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76f4-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="c76f4-358">Если вы хотите использовать PowerShell для просмотра тегов карантина, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c76f4-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="c76f4-359">Чтобы просмотреть сводный список всех встроенных или пользовательских тегов, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c76f4-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="c76f4-360">Чтобы просмотреть параметры встроенных или настраиваемые теги карантина, замените имя тега карантина и запустите \<TagName\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c76f4-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="c76f4-361">Чтобы просмотреть глобальные параметры, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c76f4-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="c76f4-362">Дополнительные сведения о синтаксисе и параметрах см. в статье [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="c76f4-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="c76f4-363">Удаление тегов карантина в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c76f4-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="c76f4-364">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="c76f4-364">**Notes**:</span></span>

- <span data-ttu-id="c76f4-365">Встроенные теги карантина удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="c76f4-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="c76f4-366">Перед удалением настраиваемой метки карантина убедитесь, что он не используется.</span><span class="sxs-lookup"><span data-stu-id="c76f4-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="c76f4-367">Например, в PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c76f4-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="c76f4-368">Если используется тег карантина, [](#step-2-assign-a-quarantine-tag-to-supported-features) замените соответствующий тег карантина перед его удалением.</span><span class="sxs-lookup"><span data-stu-id="c76f4-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="c76f4-369">В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами и выберите теги \>  **карантина.**</span><span class="sxs-lookup"><span data-stu-id="c76f4-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="c76f4-370">На странице **"Теги карантина"** выберите настраиваемый тег карантина, который нужно удалить, и нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="c76f4-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="c76f4-371">Нажмите **кнопку "Удалить"** в диалоговом окле подтверждения.</span><span class="sxs-lookup"><span data-stu-id="c76f4-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="c76f4-372">Удаление тегов карантина в PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76f4-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="c76f4-373">Если вы хотите удалить настраиваемый тег карантина с помощью PowerShell, замените имя тега карантина и запустите \<TagName\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c76f4-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="c76f4-374">Подробные сведения о синтаксисах и параметрах см. в описании [Remove-QuarantineTag.](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="c76f4-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="c76f4-375">Сведения о разрешении тега карантина</span><span class="sxs-lookup"><span data-stu-id="c76f4-375">Quarantine tag permission details</span></span>

<span data-ttu-id="c76f4-376">В следующих разделах описываются последствия предварительно заранее заявив о последствиях для сообщений на карантине и уведомлений пользователей о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="c76f4-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="c76f4-377">Предустановленные группы разрешений</span><span class="sxs-lookup"><span data-stu-id="c76f4-377">Preset permissions groups</span></span>

<span data-ttu-id="c76f4-378">Отдельные разрешения, включенные в предустановленные группы разрешений, перечислены в таблице в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="c76f4-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="c76f4-379">Нет доступа</span><span class="sxs-lookup"><span data-stu-id="c76f4-379">No access</span></span>

<span data-ttu-id="c76f4-380">Если тег карантина назначает  разрешения "Нет доступа" (без разрешений), пользователи по-прежнему получают некоторые базовые возможности:</span><span class="sxs-lookup"><span data-stu-id="c76f4-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="c76f4-381">**Сведения о сообщении в карантине:** кнопка "Просмотр **сообщения"** всегда доступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Доступные кнопки в сведениях о сообщении на карантине, если тег карантина предоставляет пользователю разрешения на доступ](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="c76f4-383">**Уведомления конечных пользователей о** нежелательной почте: кнопка "Обзор", которая перенабирает пользователя к сообщению в карантине, всегда доступна. </span><span class="sxs-lookup"><span data-stu-id="c76f4-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет пользователю разрешения на доступ](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="c76f4-385">Ограниченный доступ</span><span class="sxs-lookup"><span data-stu-id="c76f4-385">Limited access</span></span>

<span data-ttu-id="c76f4-386">Если тег карантина назначает  разрешения на ограниченный доступ, пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="c76f4-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="c76f4-387">**Сведения о сообщении в карантине:** доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="c76f4-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="c76f4-388">**Выпуск запроса**</span><span class="sxs-lookup"><span data-stu-id="c76f4-388">**Request release**</span></span>
  - <span data-ttu-id="c76f4-389">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="c76f4-389">**View message header**</span></span>
  - <span data-ttu-id="c76f4-390">**Предварительный просмотр сообщения**</span><span class="sxs-lookup"><span data-stu-id="c76f4-390">**Preview message**</span></span>
  - <span data-ttu-id="c76f4-391">**Блокировать отправитель**</span><span class="sxs-lookup"><span data-stu-id="c76f4-391">**Block sender**</span></span>
  - <span data-ttu-id="c76f4-392">**Удаление из карантина**</span><span class="sxs-lookup"><span data-stu-id="c76f4-392">**Remove from quarantine**</span></span>

  ![Доступные кнопки в сведениях о сообщении на карантине, если тег карантина предоставляет пользователю разрешения на ограниченный доступ](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="c76f4-394">**Уведомления конечных пользователей о нежелательной** почте: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="c76f4-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="c76f4-395">**Блокировать отправитель**</span><span class="sxs-lookup"><span data-stu-id="c76f4-395">**Block sender**</span></span>
  - <span data-ttu-id="c76f4-396">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="c76f4-396">**Review**</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет пользователю разрешения на ограниченный доступ](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="c76f4-398">Полный доступ</span><span class="sxs-lookup"><span data-stu-id="c76f4-398">Full access</span></span>

<span data-ttu-id="c76f4-399">Если тег карантина назначает  разрешения полного доступа (все доступные разрешения), пользователи получают следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="c76f4-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="c76f4-400">**Сведения о сообщении в карантине:** доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="c76f4-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="c76f4-401">**Сообщение о выпуске**</span><span class="sxs-lookup"><span data-stu-id="c76f4-401">**Release message**</span></span>
  - <span data-ttu-id="c76f4-402">**Просмотр заголовка сообщения**.</span><span class="sxs-lookup"><span data-stu-id="c76f4-402">**View message header**</span></span>
  - <span data-ttu-id="c76f4-403">**Предварительный просмотр сообщения**</span><span class="sxs-lookup"><span data-stu-id="c76f4-403">**Preview message**</span></span>
  - <span data-ttu-id="c76f4-404">**Блокировать отправитель**</span><span class="sxs-lookup"><span data-stu-id="c76f4-404">**Block sender**</span></span>
  - <span data-ttu-id="c76f4-405">**Разрешить отправитель**</span><span class="sxs-lookup"><span data-stu-id="c76f4-405">**Allow sender**</span></span>
  - <span data-ttu-id="c76f4-406">**Удаление из карантина**</span><span class="sxs-lookup"><span data-stu-id="c76f4-406">**Remove from quarantine**</span></span>

  ![Доступные кнопки в сведениях о сообщении на карантине, если тег карантина предоставляет пользователю разрешения на полный доступ](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="c76f4-408">**Уведомления конечных пользователей о нежелательной** почте: доступны следующие кнопки:</span><span class="sxs-lookup"><span data-stu-id="c76f4-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="c76f4-409">**Блокировать отправитель**</span><span class="sxs-lookup"><span data-stu-id="c76f4-409">**Block sender**</span></span>
  - <span data-ttu-id="c76f4-410">**Выпуск**</span><span class="sxs-lookup"><span data-stu-id="c76f4-410">**Release**</span></span>
  - <span data-ttu-id="c76f4-411">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="c76f4-411">**Review**</span></span>

  ![Доступные кнопки в уведомлении пользователя о нежелательной почте, если тег карантина предоставляет пользователю разрешения на полный доступ](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="c76f4-413">Индивидуальные разрешения</span><span class="sxs-lookup"><span data-stu-id="c76f4-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="c76f4-414">Помните, что пользователи всегда получают кнопки, описанные в разделе ["Нет доступа".](#no-access)</span><span class="sxs-lookup"><span data-stu-id="c76f4-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="c76f4-415">Эти кнопки не включаются в отдельные описания разрешений.</span><span class="sxs-lookup"><span data-stu-id="c76f4-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="c76f4-416">Разрешение отправитель</span><span class="sxs-lookup"><span data-stu-id="c76f4-416">Allow sender permission</span></span>

<span data-ttu-id="c76f4-417">Разрешение **"Разрешить** отправителю"_(PermissionToAllowSender)_ управляет доступом к кнопке, которая позволяет пользователям удобно добавлять отправителей сообщений в карантин в список надежных отправителей.</span><span class="sxs-lookup"><span data-stu-id="c76f4-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="c76f4-418">**Сведения о сообщении в карантине:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c76f4-419">**Разрешение "Разрешить отправитель"** включено: доступна **кнопка** "Разрешить отправитель".</span><span class="sxs-lookup"><span data-stu-id="c76f4-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="c76f4-420">**Разрешение "Разрешить отправитель"** отключено: кнопка "Разрешить **отправитель"** недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="c76f4-421">**Уведомления конечных пользователей о нежелательной почте:** без эффекта.</span><span class="sxs-lookup"><span data-stu-id="c76f4-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="c76f4-422">Дополнительные сведения о списке надежных отправителей см. в подстроке "Запретить блокировку надежных отправителей" и настройке коллекции списков надежных отправителей для почтового ящика с помощью [Exchange Online PowerShell.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox) [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)</span><span class="sxs-lookup"><span data-stu-id="c76f4-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="c76f4-423">Разрешение блокировки отправитель</span><span class="sxs-lookup"><span data-stu-id="c76f4-423">Block sender permission</span></span>

<span data-ttu-id="c76f4-424">Разрешение **"Отправитель** блока"_(PermissionToBlockSender)_ управляет доступом к кнопке, которая позволяет пользователям удобно добавлять отправителей сообщений в карантин в список заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="c76f4-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="c76f4-425">**Сведения о сообщении в карантине:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c76f4-426">**Разрешение блокировки отправитель** включено: кнопка **"Блокировать отправитель"** доступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="c76f4-427">**Разрешение блокировки отправитель** отключено: кнопка **"Заблокировать** отправитель" недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="c76f4-428">**Уведомления конечных пользователей о нежелательной почте:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="c76f4-429">**Разрешение блокировки отправитель** отключено: кнопка **"Заблокировать** отправитель" недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="c76f4-430">**Разрешение блокировки отправитель** включено: кнопка **"Блокировать отправитель"** доступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="c76f4-431">Дополнительные сведения о списке заблокированных [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) отправителей см. в подстроке "Блокировка сообщений от кого-либо" и использовании Exchange Online PowerShell для настройки коллекции списков надежных отправителей [для почтового ящика.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="c76f4-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="c76f4-432">Разрешения на удаление</span><span class="sxs-lookup"><span data-stu-id="c76f4-432">Delete permission</span></span>

<span data-ttu-id="c76f4-433">Разрешение **на** удаление _(PermissionToDelete)_ управляет возможностью пользователей удалять свои сообщения (сообщения, в которых пользователь является получателем) из карантина.</span><span class="sxs-lookup"><span data-stu-id="c76f4-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="c76f4-434">**Сведения о сообщении в карантине:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c76f4-435">**Разрешение на** удаление включено: доступна кнопка "Удалить из **карантина".**</span><span class="sxs-lookup"><span data-stu-id="c76f4-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="c76f4-436">**Удаление** разрешения отключено: **кнопка "Удалить из карантина"** недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="c76f4-437">**Уведомления конечных пользователей о нежелательной почте:** без эффекта.</span><span class="sxs-lookup"><span data-stu-id="c76f4-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="c76f4-438">Разрешение предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="c76f4-438">Preview permission</span></span>

<span data-ttu-id="c76f4-439">Разрешение **preview** _(PermissionToPreview)_ управляет возможностью пользователей предварительно просматривать свои сообщения в карантине.</span><span class="sxs-lookup"><span data-stu-id="c76f4-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="c76f4-440">**Сведения о сообщении в карантине:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c76f4-441">**Разрешение предварительного** просмотра включено: доступна кнопка **"Предварительный** просмотр сообщения".</span><span class="sxs-lookup"><span data-stu-id="c76f4-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="c76f4-442">**Разрешение** предварительного просмотра отключено: кнопка **"Предварительный** просмотр сообщения" недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="c76f4-443">**Уведомления конечных пользователей о нежелательной почте:** без эффекта.</span><span class="sxs-lookup"><span data-stu-id="c76f4-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="c76f4-444">Разрешение получателям освободить сообщение из разрешения карантина</span><span class="sxs-lookup"><span data-stu-id="c76f4-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="c76f4-445">Разрешение **на** освобождение сообщения из разрешения карантина _(PermissionToRelease)_ позволяет пользователям освободить свои сообщения на карантине напрямую и без утверждения администратора.</span><span class="sxs-lookup"><span data-stu-id="c76f4-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="c76f4-446">**Сведения о сообщении в карантине:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c76f4-447">Разрешение включено: доступна **кнопка** "Освободить сообщение".</span><span class="sxs-lookup"><span data-stu-id="c76f4-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="c76f4-448">Разрешение отключено: **кнопка "Освободить сообщение"** недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="c76f4-449">**Уведомления конечных пользователей о нежелательной почте:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="c76f4-450">Разрешение включено: доступна **кнопка** "Выпуск".</span><span class="sxs-lookup"><span data-stu-id="c76f4-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="c76f4-451">Разрешение отключено: **кнопка "Выпуск"** недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="c76f4-452">Разрешение получателям запрашивать освобождения сообщения из разрешения на карантин</span><span class="sxs-lookup"><span data-stu-id="c76f4-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="c76f4-453">Разрешение **получателям** запрашивать освобождение сообщения из карантина _(PermissionToRequestRelease)_ управляет  возможностью пользователей запрашивать освобождение своих сообщений на карантине.</span><span class="sxs-lookup"><span data-stu-id="c76f4-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="c76f4-454">Сообщение будет освобождено только после того, как администратор утвердит запрос.</span><span class="sxs-lookup"><span data-stu-id="c76f4-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="c76f4-455">**Сведения о сообщении в карантине:**</span><span class="sxs-lookup"><span data-stu-id="c76f4-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="c76f4-456">Разрешение включено: доступна **кнопка выпуска** запроса.</span><span class="sxs-lookup"><span data-stu-id="c76f4-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="c76f4-457">Разрешение отключено: **кнопка выпуска запроса** недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="c76f4-458">**Уведомления конечных пользователей о нежелательной почте:** кнопка **"Освободить"** недоступна.</span><span class="sxs-lookup"><span data-stu-id="c76f4-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
