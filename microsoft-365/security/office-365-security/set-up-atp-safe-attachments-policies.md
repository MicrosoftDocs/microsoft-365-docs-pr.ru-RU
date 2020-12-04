---
title: Настройка политик безопасных вложений в защитнике Майкрософт для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Узнайте, как определить политики безопасных вложений, чтобы защитить организацию от вредоносных файлов в электронной почте.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a14f5a22795fc08b76165466d8e44ee38d8a2d81
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572646"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cf999-103">Настройка политик безопасных вложений в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="cf999-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="cf999-104">Эта статья предназначена для корпоративных клиентов, у которых есть [защитник Майкрософт для Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="cf999-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="cf999-105">Если вы являетесь домашним пользователем, который ищет сведения о сканировании вложений в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="cf999-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="cf999-106">"Безопасные вложения" — это функция [защитника Майкрософт для Office 365](office-365-atp.md) , которая использует виртуальную среду для проверки вложений в входящих сообщениях электронной почты после того, как они были проверены с помощью [защиты от вредоносных программ в Exchange Online Protection (EOP)](anti-malware-protection.md), но перед доставкой получателям.</span><span class="sxs-lookup"><span data-stu-id="cf999-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="cf999-107">Дополнительные сведения см в разделе [безопасные вложения в защитнике Майкрософт для Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="cf999-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="cf999-108">Встроенная политика или политика безопасных вложений отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cf999-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="cf999-109">Чтобы получать безопасные вложения при сканировании вложений в сообщениях электронной почты, необходимо создать одну или несколько политик безопасных вложений, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cf999-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="cf999-110">Политики безопасных вложений можно настраивать в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для подходящих организаций Microsoft 365 с почтовыми ящиками в Exchange Online; изолированная оболочка EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с помощью защитника для Office 365 подписки на надстройки).</span><span class="sxs-lookup"><span data-stu-id="cf999-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="cf999-111">Основные элементы политики безопасных вложений:</span><span class="sxs-lookup"><span data-stu-id="cf999-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="cf999-112">**Политика безопасных вложений**: определяет действия для неизвестных обнаружений вредоносных программ, как отправлять сообщения с вложениями вредоносных программ по указанному адресу электронной почты, а также следует ли доставлять сообщения, если сканирование безопасных вложений не может быть завершено.</span><span class="sxs-lookup"><span data-stu-id="cf999-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="cf999-113">**Правило "безопасное вложение**" определяет приоритет и фильтры получателей (к которым применяется политика).</span><span class="sxs-lookup"><span data-stu-id="cf999-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="cf999-114">Различия между этими двумя элементами не очевидны при управлении политиками безопасных вложений в центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="cf999-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="cf999-115">При создании политики безопасных вложений фактически создается правило безопасных вложений и связанная политика безопасных вложений с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="cf999-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="cf999-116">При изменении политики безопасных вложений параметры, связанные с фильтрами имени, приоритета, включенного или отключенного, и получателей, изменяют правило безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="cf999-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="cf999-117">Все остальные параметры изменяют связанную политику безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="cf999-118">При удалении политики безопасных вложений удаляется правило безопасных вложений и связанная политика безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="cf999-119">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="cf999-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="cf999-120">Более подробную информацию можно узнать в разделе [использование Exchange Online PowerShell или изолированной EOP PowerShell для настройки политик безопасных вложений](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cf999-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="cf999-121">В области Глобальные параметры параметров безопасных вложений вы настраиваете компоненты, которые не зависят от политик безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="cf999-122">Инструкции: [включить ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) и [безопасные документы в Microsoft 365](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="cf999-122">For instructions see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cf999-123">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="cf999-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cf999-124">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="cf999-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cf999-125">Чтобы перейти непосредственно к странице " **безопасные вложения** ", используйте <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="cf999-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="cf999-126">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cf999-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cf999-127">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="cf999-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cf999-128">Прежде чем выполнять процедуры, описанные в этой статье, необходимо назначить разрешения в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cf999-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cf999-129">Чтобы создавать, изменять и удалять политики безопасных вложений, необходимо быть членом группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="cf999-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="cf999-130">Для доступа только для чтения к политикам безопасных вложений необходимо быть членом группы ролей " **глобальный читатель** " или " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="cf999-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="cf999-131">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="cf999-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="cf999-132">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="cf999-132">**Notes**:</span></span>

  - <span data-ttu-id="cf999-133">Добавление пользователей в соответствующую роль Azure Active Directory в центре администрирования Microsoft 365 предоставляет пользователям необходимые разрешения в центре безопасности & соответствия требованиям _и_ разрешениях для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf999-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cf999-134">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="cf999-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="cf999-135">Группа ролей **Управление организацией только для просмотра** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ к компоненту только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cf999-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="cf999-136">Рекомендуемые параметры политик безопасных вложений приведены в разделе [Параметры безопасных вложений](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="cf999-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="cf999-137">Разрешить применение новой или обновленной политики до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="cf999-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="cf999-138">Использование центра безопасности & соответствия требованиям для создания политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="cf999-139">При создании настраиваемой политики безопасных вложений в центре безопасности & соответствия требованиям создается правило безопасного вложения и сопоставленная политика безопасных вложений с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="cf999-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="cf999-140">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="cf999-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="cf999-141">На странице **безопасные вложения** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="cf999-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="cf999-142">Откроется мастер **создания политики безопасных вложений** .</span><span class="sxs-lookup"><span data-stu-id="cf999-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="cf999-143">На странице " **назвать политику** " настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="cf999-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="cf999-144">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="cf999-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="cf999-145">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="cf999-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="cf999-146">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf999-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="cf999-147">На открывшейся странице **Параметры** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="cf999-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cf999-148">**Безопасных вложений неизвестный отклик от вредоносных программ**: выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="cf999-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="cf999-149">**Отключение**: как правило, это значение не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="cf999-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="cf999-150">**Монитор**</span><span class="sxs-lookup"><span data-stu-id="cf999-150">**Monitor**</span></span>
     - <span data-ttu-id="cf999-151">**Block**: это значение по умолчанию и рекомендуемое значение в стандартном и ограниченном [установленных политиках безопасности](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cf999-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="cf999-152">**Replace**</span><span class="sxs-lookup"><span data-stu-id="cf999-152">**Replace**</span></span>
     - <span data-ttu-id="cf999-153">**Динамическая доставка (функция предварительной версии)**</span><span class="sxs-lookup"><span data-stu-id="cf999-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="cf999-154">Эти значения описаны в разделах [Параметры политики безопасных вложений](atp-safe-attachments.md#safe-attachments-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="cf999-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="cf999-155">**Отправьте вложение на следующий адрес электронной почты**: для **блокировки** значений действий, **отслеживания** или **замены** можно выбрать параметр **включить перенаправление** для отправки сообщений, которые содержат вложения вредоносных программ, на указанный внутренний или внешний адрес электронной почты для анализа и расследования.</span><span class="sxs-lookup"><span data-stu-id="cf999-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="cf999-156">Рекомендация по стандартным и жестким параметрам политики состоит в включении перенаправления.</span><span class="sxs-lookup"><span data-stu-id="cf999-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="cf999-157">Дополнительные сведения [см.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="cf999-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="cf999-158">**Применить вышеуказанный вариант при превышении времени ожидания для обнаружения вредоносных программ или при возникновении ошибки**: действие, заданное **безопасными вложениями неизвестными ответами на вредоносные программы** , применяется к сообщениям даже в том случае, если сканирование</span><span class="sxs-lookup"><span data-stu-id="cf999-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="cf999-159">Всегда выбирайте этот параметр, если выбран параметр **включить перенаправление**.</span><span class="sxs-lookup"><span data-stu-id="cf999-159">Always select this option if you select **Enabled redirect**.</span></span> <span data-ttu-id="cf999-160">В противном случае сообщения могут быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="cf999-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="cf999-161">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf999-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="cf999-162">На появившейся странице " **применено к** " определите внутренних получателей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="cf999-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="cf999-163">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="cf999-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="cf999-164">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="cf999-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="cf999-165">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="cf999-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="cf999-166">Нажмите кнопку **Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="cf999-166">Click **Add a condition**.</span></span> <span data-ttu-id="cf999-167">В появившемся раскрывающемся меню выберите условие **применено, если**:</span><span class="sxs-lookup"><span data-stu-id="cf999-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="cf999-168">**Получатель**: указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в Организации.</span><span class="sxs-lookup"><span data-stu-id="cf999-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="cf999-169">**Получатель является участником**: указывает одну или несколько групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="cf999-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="cf999-170">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cf999-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="cf999-171">После выбора условия появится соответствующее раскрывающийся список с **одним из этих** полей.</span><span class="sxs-lookup"><span data-stu-id="cf999-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="cf999-172">Щелкните поле и прокрутите список выбираемых значений.</span><span class="sxs-lookup"><span data-stu-id="cf999-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="cf999-173">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="cf999-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="cf999-174">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="cf999-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="cf999-175">Чтобы удалить отдельные записи, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " на значении.</span><span class="sxs-lookup"><span data-stu-id="cf999-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="cf999-176">Чтобы удалить условие целиком, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " в условии.</span><span class="sxs-lookup"><span data-stu-id="cf999-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="cf999-177">Чтобы добавить дополнительное условие, щелкните **Добавить условие** и выберите оставшееся значение в разделе **применено, если**.</span><span class="sxs-lookup"><span data-stu-id="cf999-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="cf999-178">Чтобы добавить исключения, щелкните **Добавить условие** и выберите исключение в разделе **за исключением if**.</span><span class="sxs-lookup"><span data-stu-id="cf999-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="cf999-179">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="cf999-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="cf999-180">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf999-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="cf999-181">На открывшейся странице **Проверьте параметры** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="cf999-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="cf999-182">Для изменения каждого параметра можно нажать кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="cf999-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="cf999-183">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cf999-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="cf999-184">Использование центра безопасности & соответствия требованиям для просмотра политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="cf999-185">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="cf999-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="cf999-186">На странице **безопасные вложения** выберите политику из списка и щелкните ее (не устанавливая флажок).</span><span class="sxs-lookup"><span data-stu-id="cf999-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="cf999-187">Сведения о политике отображаются на лету</span><span class="sxs-lookup"><span data-stu-id="cf999-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="cf999-188">Использование центра безопасности & соответствия требованиям для изменения политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="cf999-189">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="cf999-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="cf999-190">На странице **безопасные вложения** выберите политику из списка и щелкните ее (не устанавливая флажок).</span><span class="sxs-lookup"><span data-stu-id="cf999-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="cf999-191">В появившемся окне сведения о политике выберите **изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="cf999-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="cf999-192">Доступные параметры отображаются в виде, идентичном приведенным в разделе [Использование центра безопасности & соответствия требованиям для создания раздела политики безопасных вложений](#use-the-security--compliance-center-to-create-safe-attachments-policies) .</span><span class="sxs-lookup"><span data-stu-id="cf999-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="cf999-193">Чтобы включить или отключить политику или настроить порядок приоритетов политики, ознакомьтесь со следующими разделами.</span><span class="sxs-lookup"><span data-stu-id="cf999-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="cf999-194">Включение и отключение политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="cf999-195">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="cf999-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="cf999-196">Обратите внимание на значение в столбце **состояние** :</span><span class="sxs-lookup"><span data-stu-id="cf999-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="cf999-197">Перемещение переключателя влево</span><span class="sxs-lookup"><span data-stu-id="cf999-197">Move the toggle to the left</span></span> ![Отключение политики](../../media/scc-toggle-off.png) <span data-ttu-id="cf999-199">для отключения политики.</span><span class="sxs-lookup"><span data-stu-id="cf999-199">to disable the policy.</span></span>

   - <span data-ttu-id="cf999-200">Перемещение переключателя вправо</span><span class="sxs-lookup"><span data-stu-id="cf999-200">Move the toggle to the right</span></span> ![Включение политики](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) <span data-ttu-id="cf999-202">для включения политики.</span><span class="sxs-lookup"><span data-stu-id="cf999-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="cf999-203">Установка приоритета политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="cf999-204">По умолчанию политикам надежных вложений назначен приоритет, основанный на порядке, в котором они были созданы (более новые политики имеют более низкий приоритет, чем старые политики).</span><span class="sxs-lookup"><span data-stu-id="cf999-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="cf999-205">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="cf999-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="cf999-206">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="cf999-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="cf999-207">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="cf999-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="cf999-208">Политики безопасных вложений отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="cf999-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="cf999-209">**Note**: в центре безопасности & соответствия требованиям можно изменить приоритет политики безопасных вложений после ее создания.</span><span class="sxs-lookup"><span data-stu-id="cf999-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="cf999-210">В PowerShell можно переопределить приоритет по умолчанию при создании правила безопасного вложения (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="cf999-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="cf999-211">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="cf999-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="cf999-212">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="cf999-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="cf999-213">На странице **безопасные вложения** выберите политику из списка и щелкните ее (не устанавливая флажок).</span><span class="sxs-lookup"><span data-stu-id="cf999-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="cf999-214">В появившемся окне сведения о политике нажмите кнопку доступный приоритет.</span><span class="sxs-lookup"><span data-stu-id="cf999-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="cf999-215">Политика безопасных вложений со значением **приоритета** **0** имеет только кнопку " **уменьшить приоритет** ".</span><span class="sxs-lookup"><span data-stu-id="cf999-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="cf999-216">Для политики безопасных вложений с наименьшим значением **приоритета** (например, **3**) доступна только кнопка **повышения приоритета** .</span><span class="sxs-lookup"><span data-stu-id="cf999-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="cf999-217">Если у вас есть три или более политики безопасных вложений, политики между максимальным и минимальным значениями приоритетов имеют доступные кнопки **повышение приоритет** и **понижение приоритета** .</span><span class="sxs-lookup"><span data-stu-id="cf999-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="cf999-218">Щелкните **увеличить** или **уменьшить** приоритет, чтобы изменить значение **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="cf999-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="cf999-219">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="cf999-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="cf999-220">Использование центра безопасности & соответствия требованиям для удаления политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="cf999-221">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="cf999-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="cf999-222">На странице **безопасные вложения** выберите политику из списка и щелкните ее (не устанавливая флажок).</span><span class="sxs-lookup"><span data-stu-id="cf999-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="cf999-223">В появившемся окне сведения о политике выберите **удалить политику**, а затем нажмите кнопку **Да** в появившемся диалоговом окне предупреждения.</span><span class="sxs-lookup"><span data-stu-id="cf999-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="cf999-224">Настройка политик безопасных вложений с помощью Exchange Online PowerShell или изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf999-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="cf999-225">Как было сказано ранее, политика безопасных вложений состоит из политики безопасных вложений и правила безопасного вложения.</span><span class="sxs-lookup"><span data-stu-id="cf999-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="cf999-226">В PowerShell различия между политиками безопасного вложения и правилами безопасного вложения очевидны.</span><span class="sxs-lookup"><span data-stu-id="cf999-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="cf999-227">Политики безопасных вложений управляются с помощью командлетов **\* – safeattachmentpolicy используется** и управление правилами безопасных вложений осуществляется с помощью командлетов **\* – safeattachmentrule используется** .</span><span class="sxs-lookup"><span data-stu-id="cf999-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="cf999-228">В PowerShell сначала создается политика безопасных вложений, а затем создается правило безопасного вложения, идентифицирующее политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="cf999-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="cf999-229">В PowerShell вы изменяете параметры политики безопасных вложений и правила безопасного вложения отдельно.</span><span class="sxs-lookup"><span data-stu-id="cf999-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="cf999-230">При удалении политики безопасных вложений из PowerShell соответствующее правило безопасных вложений не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="cf999-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="cf999-231">Создание политик безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf999-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="cf999-232">Процесс создания политики безопасных вложений в PowerShell состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="cf999-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="cf999-233">Создайте политику безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="cf999-234">Создайте правило безопасного вложения, которое определяет политику безопасных вложений, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="cf999-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="cf999-235">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="cf999-235">**Notes**:</span></span>

- <span data-ttu-id="cf999-236">Вы можете создать новое правило для безопасного вложения и назначить для него существующую, несвязанную политику безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="cf999-237">Правило безопасного вложения невозможно связать с несколькими политиками безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="cf999-238">Вы можете настроить следующие параметры для новых политик безопасных вложений в PowerShell, которые недоступны в центре безопасности & соответствия требованиям, пока не будет создана политика:</span><span class="sxs-lookup"><span data-stu-id="cf999-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="cf999-239">Создайте новую политику как отключенную (_включена_ `$false` в командлете **New-safeattachmentrule используется** ).</span><span class="sxs-lookup"><span data-stu-id="cf999-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="cf999-240">Задайте приоритет политики при создании (_приоритет_ _\<Number\>_ ) для командлета **New-safeattachmentrule используется** .</span><span class="sxs-lookup"><span data-stu-id="cf999-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="cf999-241">Новая политика безопасных вложений, созданная в PowerShell, не отображается в центре безопасности & соответствия требованиям, пока вы не назначите политику для правила "безопасное вложение".</span><span class="sxs-lookup"><span data-stu-id="cf999-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="cf999-242">Шаг 1: использование PowerShell для создания политики безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="cf999-243">Чтобы создать политику безопасных вложений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="cf999-244">В этом примере создается политика безопасных вложений с именем Contoso ALL со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="cf999-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="cf999-245">Блокировать сообщения, которые содержат вредоносные программы, с помощью безопасной проверки документов (мы не используем параметр _Action_ , а значение по умолчанию — `Block` ).</span><span class="sxs-lookup"><span data-stu-id="cf999-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="cf999-246">Перенаправление включено, а сообщения, которые содержат вредоносные программы, отправляются в sec-ops@contoso.com для анализа и исследования.</span><span class="sxs-lookup"><span data-stu-id="cf999-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="cf999-247">Если сканирование безопасных вложений недоступно или обнаружены ошибки, не доставлять сообщение (мы не используем параметр _актиононеррор_ , а значение по умолчанию — `$true` ).</span><span class="sxs-lookup"><span data-stu-id="cf999-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="cf999-248">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – safeattachmentpolicy используется](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="cf999-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="cf999-249">Шаг 2: использование PowerShell для создания правила безопасного вложения</span><span class="sxs-lookup"><span data-stu-id="cf999-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="cf999-250">Чтобы создать правило для безопасного вложения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="cf999-251">В этом примере создается правило безопасного вложения с именем Contoso ALL со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="cf999-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="cf999-252">Правило связано с политикой безопасных вложений с именем Contoso ALL.</span><span class="sxs-lookup"><span data-stu-id="cf999-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="cf999-253">Правило применяется ко всем получателям в домене contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cf999-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="cf999-254">Так как мы не используем параметр _Priority_ , используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf999-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="cf999-255">Правило включено (параметр _Enabled_ не используется, а значение по умолчанию — `$true` ).</span><span class="sxs-lookup"><span data-stu-id="cf999-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="cf999-256">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – safeattachmentrule используется](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="cf999-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="cf999-257">Использование PowerShell для просмотра политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="cf999-258">Чтобы просмотреть существующие политики безопасных вложений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="cf999-259">В этом примере возвращается сводный список всех политик безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="cf999-260">В этом примере возвращаются подробные сведения о политике безопасных вложений с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="cf999-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="cf999-261">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – safeattachmentpolicy используется](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="cf999-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="cf999-262">Использование PowerShell для просмотра правил безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="cf999-263">Чтобы просмотреть существующие правила безопасных вложений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="cf999-264">В этом примере возвращается сводный список всех правил безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="cf999-265">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="cf999-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="cf999-266">В этом примере возвращаются подробные сведения о правиле "безопасное вложение" с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="cf999-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="cf999-267">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – safeattachmentrule используется](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="cf999-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="cf999-268">Использование PowerShell для изменения политик безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="cf999-269">Вы не можете переименовать политику безопасных вложений в PowerShell (командлет **Set-safeattachmentpolicy используется** не имеет параметра _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="cf999-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="cf999-270">При переименовании политики безопасных вложений в центре безопасности & соответствия требованиям Вы переименовываете только _правило_ безопасных вложений.</span><span class="sxs-lookup"><span data-stu-id="cf999-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="cf999-271">В противном случае те же параметры доступны при создании политики безопасных вложений, как описано в [шаге 1: с помощью PowerShell создайте раздел "политика безопасных вложений](#step-1-use-powershell-to-create-a-safe-attachment-policy) " ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cf999-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="cf999-272">Чтобы изменить политику безопасных вложений, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="cf999-273">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – safeattachmentpolicy используется](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="cf999-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="cf999-274">Использование PowerShell для изменения правил безопасных вложений</span><span class="sxs-lookup"><span data-stu-id="cf999-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="cf999-275">Единственный параметр, недоступный при изменении правила безопасного вложения в PowerShell, это параметр _Enabled_ , позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="cf999-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="cf999-276">Чтобы включить или отключить существующие правила безопасных вложений, ознакомьтесь со статьей в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="cf999-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="cf999-277">В противном случае те же параметры доступны при создании правила, как описано в [шаге 2: используйте PowerShell, чтобы создать раздел "безопасные правила вложения](#step-2-use-powershell-to-create-a-safe-attachment-rule) " ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cf999-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="cf999-278">Чтобы изменить правило безопасного вложения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="cf999-279">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – safeattachmentrule используется](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="cf999-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="cf999-280">Включение и отключение правил безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf999-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="cf999-281">Включение или отключение правила безопасного вложения в PowerShell включает или отключает политику "все безопасные вложения" (правило безопасного вложения и назначенная политика безопасных вложений).</span><span class="sxs-lookup"><span data-stu-id="cf999-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="cf999-282">Чтобы включить или отключить правило для безопасного вложения в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="cf999-283">В этом примере отключается правило безопасного вложения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="cf999-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="cf999-284">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="cf999-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="cf999-285">Подробные сведения о синтаксисе и параметрах можно найти в статье [Enable – safeattachmentrule используется](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable – safeattachmentrule используется](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="cf999-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="cf999-286">Настройка приоритета правил безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf999-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="cf999-287">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="cf999-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="cf999-288">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="cf999-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="cf999-289">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="cf999-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="cf999-290">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="cf999-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="cf999-291">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="cf999-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="cf999-292">Чтобы задать приоритет правила безопасного вложения в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="cf999-p124">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="cf999-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="cf999-295">**Примечание**. чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ в командлете **New – safeattachmentrule используется** .</span><span class="sxs-lookup"><span data-stu-id="cf999-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="cf999-296">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – safeattachmentrule используется](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="cf999-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="cf999-297">Удаление политик безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf999-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="cf999-298">При использовании PowerShell для удаления политики безопасных вложений соответствующее правило не удаляется.</span><span class="sxs-lookup"><span data-stu-id="cf999-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="cf999-299">Чтобы удалить политику безопасных вложений в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="cf999-300">В этом примере удаляется политика безопасных вложений с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="cf999-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="cf999-301">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – safeattachmentpolicy используется](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="cf999-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="cf999-302">Удаление правил безопасных вложений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf999-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="cf999-303">При использовании PowerShell для удаления правила безопасного вложения соответствующая политика безопасных вложений не удаляется.</span><span class="sxs-lookup"><span data-stu-id="cf999-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="cf999-304">Чтобы удалить правило безопасных вложений в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cf999-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="cf999-305">В этом примере удаляется правило безопасного вложения с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="cf999-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="cf999-306">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – safeattachmentrule используется](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="cf999-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="cf999-307">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="cf999-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="cf999-308">Чтобы проверить, успешно ли созданы, изменены или удалены политики безопасных вложений, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="cf999-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="cf999-309">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**.</span><span class="sxs-lookup"><span data-stu-id="cf999-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="cf999-310">Проверьте список политик, их значения **состояния** и значения **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="cf999-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="cf999-311">Чтобы просмотреть дополнительные сведения, выберите политику из списка и просмотрите сведения в разделе "вылет".</span><span class="sxs-lookup"><span data-stu-id="cf999-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="cf999-312">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените на \<Name\> имя политики или правила, выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="cf999-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="cf999-313">Чтобы убедиться, что безопасные вложения проверяют сообщения, просмотрите доступные защитники для Office 365 отчеты.</span><span class="sxs-lookup"><span data-stu-id="cf999-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="cf999-314">Дополнительные сведения см. в статье [Просмотр отчетов для защитника для Office 365](view-reports-for-atp.md) и [Использование проводника в центре безопасности & соответствия требованиям](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="cf999-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
