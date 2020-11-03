---
title: Настройка политик безопасных ссылок в защитнике Майкрософт для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как просматривать, создавать, изменять и удалять политики безопасных ссылок и параметры глобальных безопасных ссылок в защитнике Майкрософт для Office 365.
ms.openlocfilehash: ed95c72c98e0c9d59b9860e89843c5f9b4970c8e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846440"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c2401-103">Настройка политик безопасных ссылок в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="c2401-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="c2401-104">Эта статья предназначена для корпоративных клиентов, у которых есть [защитник Майкрософт для Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c2401-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="c2401-105">Если вы являетесь домашним пользователем, который ищет сведения о Сафелинкс в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="c2401-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="c2401-106">"Безопасные ссылки" — это функция [защитника Microsoft для Office 365](office-365-atp.md) , которая обеспечивает сканирование URL-адресов входящих сообщений электронной почты в почтовом ящике, а также время нажатия проверки URL-адресов и ссылок в сообщениях электронной почты и других расположениях.</span><span class="sxs-lookup"><span data-stu-id="c2401-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="c2401-107">Для получения дополнительных сведений см [в разделе безопасные ссылки в защитнике Майкрософт для Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="c2401-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="c2401-108">Отсутствует встроенная политика безопасных ссылок или политика по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c2401-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="c2401-109">Чтобы получать безопасные ссылки на проверку URL-адресов, необходимо создать одну или несколько политик безопасных ссылок, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c2401-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="c2401-110">Политики безопасных ссылок можно настроить в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для допустимых организаций Microsoft 365 с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с помощью защитника Майкрософт для Office 365 подписки на надстройки).</span><span class="sxs-lookup"><span data-stu-id="c2401-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="c2401-111">Основные элементы политики безопасных ссылок:</span><span class="sxs-lookup"><span data-stu-id="c2401-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="c2401-112">**Политика безопасных ссылок** : включить защиту безопасных ссылок, включить сканирование URL-адресов в режиме реального времени, указать, следует ли ожидать завершения сканирования в режиме реального времени перед доставкой сообщения, включить сканирование для внутренних сообщений, указать, следует ли отслеживать щелчки по URL-адресам, и указать, следует ли разрешить пользователям щелкать траугх по исходному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="c2401-112">**The safe links policy** : Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="c2401-113">**Правило "безопасные ссылки** " определяет приоритет и фильтры получателей (к которым применяется политика).</span><span class="sxs-lookup"><span data-stu-id="c2401-113">**The safe links rule** : Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="c2401-114">Различия между этими двумя элементами не очевидны при управлении политиками безопасных ссылок в центре безопасности & соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="c2401-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c2401-115">При создании политики безопасных ссылок вы фактически создаете правило безопасных ссылок и связанную политику безопасных ссылок одновременно с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="c2401-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="c2401-116">При изменении политики безопасных ссылок параметры, связанные с фильтрами имен, приоритетов, включенных или отключенных и получателей, изменяют правило безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="c2401-117">Все остальные параметры изменяют связанную политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="c2401-118">При удалении политики безопасных ссылок удаляется правило безопасных ссылок и связанная политика безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="c2401-119">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="c2401-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="c2401-120">Для получения дополнительных сведений обратитесь к разделу [использование Exchange Online PowerShell или изолированной EOP PowerShell для настройки политик безопасных ссылок](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c2401-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="c2401-121">Вы настраиваете глобальные параметры для защиты безопасных ссылок **вне** политик безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="c2401-122">Инструкции приведены в разделе [Настройка глобальных параметров для безопасных ссылок в защитнике Майкрософт для Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="c2401-122">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c2401-123">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c2401-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c2401-124">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c2401-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c2401-125">Чтобы перейти непосредственно на страницу " **безопасные ссылки** ", используйте <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="c2401-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="c2401-126">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c2401-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c2401-127">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c2401-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c2401-128">Чтобы просматривать, создавать, изменять и удалять политики безопасных ссылок, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="c2401-128">To view, create, modify, and delete Safe Links policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="c2401-129">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c2401-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="c2401-130">**Управление организацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c2401-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="c2401-131">Рекомендуемые параметры политик безопасных ссылок приведены в разделе [Параметры политики](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-131">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="c2401-132">Разрешить применение новой или обновленной политики до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="c2401-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="c2401-133">[Новые функции постоянно добавляются в защитник Майкрософт для Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="c2401-133">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="c2401-134">По мере добавления новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-134">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="c2401-135">Использование центра безопасности & соответствия требованиям для создания политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-135">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="c2401-136">Создание настраиваемой политики безопасных ссылок в центре безопасности & соответствия требованиям создает правило безопасных ссылок и связанную политику безопасных ссылок одновременно с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="c2401-136">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="c2401-137">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**.</span><span class="sxs-lookup"><span data-stu-id="c2401-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c2401-138">На странице **безопасные ссылки** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="c2401-138">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="c2401-139">Откроется мастер **Новая политика безопасных ссылок** .</span><span class="sxs-lookup"><span data-stu-id="c2401-139">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="c2401-140">На странице " **назвать политику** " настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c2401-140">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="c2401-141">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="c2401-141">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="c2401-142">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="c2401-142">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="c2401-143">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2401-143">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c2401-144">На открывшейся странице **Параметры** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c2401-144">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c2401-145">**Выберите действие для неизвестных потенциально вредоносных URL-адресов в сообщениях**. Выберите включить, чтобы включить защиту безопасных **ссылок для ссылок** в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c2401-145">**Select the action for unknown potentially malicious URLs in messages** : Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="c2401-146">**Выберите действие для неизвестных или потенциально вредоносных URL-адресов в Microsoft Teams** : выберите Включить, чтобы включить защиту безопасных **ссылок для ссылок** в Teams.</span><span class="sxs-lookup"><span data-stu-id="c2401-146">**Select the action for unknown or potentially malicious URLs within Microsoft Teams** : Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="c2401-147">**Применить сканирование URL-адресов в режиме реального времени для подозрительных ссылок и ссылок, указывающих на файлы** : Выберите этот параметр, чтобы включить сканирование ссылок в сообщениях электронной почты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c2401-147">**Apply real-time URL scanning for suspicious links and links that point to files** : Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="c2401-148">**Дождитесь завершения сканирования URL-адреса перед доставкой сообщения** : Выберите этот параметр, чтобы дождаться завершения сканирования URL-адресов в режиме реального времени перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="c2401-148">**Wait for URL scanning to complete before delivering the message** : Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="c2401-149">**Применение безопасных ссылок к сообщениям электронной почты, отправленным в Организации** : Выберите этот параметр, чтобы применить политику безопасных ссылок к сообщениям между внутренними отправителями и внутренними получателями.</span><span class="sxs-lookup"><span data-stu-id="c2401-149">**Apply Safe Links to email messages sent within the organization** : Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="c2401-150">**Не Отслеживайте щелчков пользователя** : Оставьте этот параметр отключенным, чтобы разрешить пользователям отслеживания щелкать по URL-адресам в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c2401-150">**Do not track user clicks** : Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="c2401-151">**Не разрешать пользователям щелкать по исходному URL-адресу** : Выберите этот параметр, чтобы запретить пользователям щелкать по исходному URL-адресу на [страницах с предупреждениями](atp-safe-links.md#warning-pages-from-safe-links).</span><span class="sxs-lookup"><span data-stu-id="c2401-151">**Do not allow users to click through to original URL** : Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="c2401-152">**Не перезаписывайте следующие URL-адреса** : разрешает доступ к указанным URL-адресам, которые в противном случае будут заблокированы с помощью безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-152">**Do not rewrite the following URLs** : Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="c2401-153">В поле введите нужный URL-адрес или значение, а затем нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="c2401-153">In the box, type the URL or value that you want, and then click</span></span> ![Значок кнопки "Добавить"](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="c2401-155">.</span><span class="sxs-lookup"><span data-stu-id="c2401-155">.</span></span>

     <span data-ttu-id="c2401-156">Чтобы удалить существующую запись, выберите ее и нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="c2401-156">To remove an existing entry, select it and then click</span></span> ![Значок кнопки "Удалить"](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="c2401-158">.</span><span class="sxs-lookup"><span data-stu-id="c2401-158">.</span></span>

     <span data-ttu-id="c2401-159">Синтаксис для записей приведен [в разделе синтаксис записи для списка "не переопределять следующие URL-адреса"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="c2401-159">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="c2401-160">Подробные сведения об этих параметрах приведены в разделе [Параметры безопасных ссылок для сообщений электронной почты](atp-safe-links.md#safe-links-settings-for-email-messages) и [параметров безопасных ссылок для Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="c2401-160">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="c2401-161">Для получения дополнительных рекомендуемых значений для стандартных и строго параметров политики, ознакомьтесь со статьей [Параметры политики безопасных ссылок](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="c2401-161">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="c2401-162">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2401-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c2401-163">На появившейся странице " **применено к** " определите внутренних получателей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="c2401-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="c2401-164">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="c2401-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="c2401-165">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="c2401-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="c2401-166">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="c2401-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="c2401-167">Нажмите кнопку **Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="c2401-167">Click **Add a condition**.</span></span> <span data-ttu-id="c2401-168">В появившемся раскрывающемся меню выберите условие **применено, если** :</span><span class="sxs-lookup"><span data-stu-id="c2401-168">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="c2401-169">**Получатель** : указывает один или несколько почтовых ящиков, почтовых пользователей или почтовых контактов в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2401-169">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="c2401-170">**Получатель является участником** : указывает одну или несколько групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2401-170">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="c2401-171">**Домен получателя** : Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c2401-171">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="c2401-172">После выбора условия появится соответствующее раскрывающийся список с **одним из этих** полей.</span><span class="sxs-lookup"><span data-stu-id="c2401-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="c2401-173">Щелкните поле и прокрутите список выбираемых значений.</span><span class="sxs-lookup"><span data-stu-id="c2401-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="c2401-174">Щелкните поле и начните ввод текста, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="c2401-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="c2401-175">Чтобы добавить дополнительные значения, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="c2401-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="c2401-176">Чтобы удалить отдельные записи, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " на значении.</span><span class="sxs-lookup"><span data-stu-id="c2401-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="c2401-177">Чтобы удалить условие целиком, нажмите кнопку **Удалить** ![ значок "удалить ](../../media/scc-remove-icon.png) " в условии.</span><span class="sxs-lookup"><span data-stu-id="c2401-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="c2401-178">Чтобы добавить дополнительное условие, щелкните **Добавить условие** и выберите оставшееся значение в разделе **применено, если**.</span><span class="sxs-lookup"><span data-stu-id="c2401-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="c2401-179">Чтобы добавить исключения, щелкните **Добавить условие** и выберите исключение в разделе **за исключением if**.</span><span class="sxs-lookup"><span data-stu-id="c2401-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="c2401-180">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="c2401-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="c2401-181">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2401-181">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c2401-182">На открывшейся странице **Проверьте параметры** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="c2401-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="c2401-183">Для изменения каждого параметра можно нажать кнопку **изменить** .</span><span class="sxs-lookup"><span data-stu-id="c2401-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="c2401-184">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c2401-184">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="c2401-185">Использование центра безопасности & соответствия требованиям для просмотра политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-185">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="c2401-186">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**.</span><span class="sxs-lookup"><span data-stu-id="c2401-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c2401-187">На странице **безопасные ссылки** выберите политику из списка и щелкните ее (не устанавливая флажок).</span><span class="sxs-lookup"><span data-stu-id="c2401-187">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="c2401-188">Сведения о политике отображаются на лету</span><span class="sxs-lookup"><span data-stu-id="c2401-188">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="c2401-189">Использование центра безопасности & соответствия требованиям для изменения политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-189">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="c2401-190">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**.</span><span class="sxs-lookup"><span data-stu-id="c2401-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c2401-191">На странице **безопасные ссылки** выберите политику из списка и щелкните ее (не устанавливая флажок).</span><span class="sxs-lookup"><span data-stu-id="c2401-191">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c2401-192">В появившемся окне сведения о политике выберите **изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="c2401-192">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="c2401-193">Доступные параметры отображаются в виде, идентичном приведенным в разделе [Использование центра соответствия & безопасности для создания раздела политики безопасных ссылок](#use-the-security--compliance-center-to-create-safe-links-policies) .</span><span class="sxs-lookup"><span data-stu-id="c2401-193">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="c2401-194">Чтобы включить или отключить политику или настроить порядок приоритетов политики, ознакомьтесь со следующими разделами.</span><span class="sxs-lookup"><span data-stu-id="c2401-194">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="c2401-195">Включение и отключение политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-195">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="c2401-196">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**.</span><span class="sxs-lookup"><span data-stu-id="c2401-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c2401-197">Обратите внимание на значение в столбце **состояние** :</span><span class="sxs-lookup"><span data-stu-id="c2401-197">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="c2401-198">Чтобы отключить политику, переместите переключатель влево:</span><span class="sxs-lookup"><span data-stu-id="c2401-198">Move the toggle to the left to disable the policy:</span></span> ![Отключение политики](../../media/scc-toggle-off.png)<span data-ttu-id="c2401-200">.</span><span class="sxs-lookup"><span data-stu-id="c2401-200">.</span></span>

   - <span data-ttu-id="c2401-201">Чтобы включить политику, переместите переключатель вправо:</span><span class="sxs-lookup"><span data-stu-id="c2401-201">Move the toggle to the right to enable the policy:</span></span> ![Включение политики](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c2401-203">.</span><span class="sxs-lookup"><span data-stu-id="c2401-203">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="c2401-204">Установка приоритета политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-204">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="c2401-205">По умолчанию политикам безопасных ссылок назначен приоритет, основанный на порядке, в котором они были созданы (более новые политики имеют более низкий приоритет, чем старые политики).</span><span class="sxs-lookup"><span data-stu-id="c2401-205">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="c2401-206">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="c2401-206">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="c2401-207">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="c2401-207">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="c2401-208">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="c2401-208">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="c2401-209">Политики безопасных ссылок отображаются в том порядке, в котором они обрабатываются (первая политика имеет значение **приоритета** 0).</span><span class="sxs-lookup"><span data-stu-id="c2401-209">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="c2401-210">**Note** : в центре безопасности & соответствия требованиям можно изменить приоритет политики безопасных ссылок после ее создания.</span><span class="sxs-lookup"><span data-stu-id="c2401-210">**Note** : In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="c2401-211">В PowerShell вы можете переопределить приоритет по умолчанию при создании правила "безопасные ссылки" (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="c2401-211">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="c2401-212">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет** ).</span><span class="sxs-lookup"><span data-stu-id="c2401-212">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="c2401-213">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**.</span><span class="sxs-lookup"><span data-stu-id="c2401-213">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c2401-214">На странице **безопасные ссылки** выберите политику из списка и щелкните ее (не устанавливая флажок).</span><span class="sxs-lookup"><span data-stu-id="c2401-214">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c2401-215">В появившемся окне сведения о политике нажмите кнопку доступный приоритет:</span><span class="sxs-lookup"><span data-stu-id="c2401-215">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="c2401-216">Политика безопасных ссылок со значением **приоритета** **0** имеет только кнопку " **уменьшить приоритет** ".</span><span class="sxs-lookup"><span data-stu-id="c2401-216">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="c2401-217">Политика безопасных ссылок с наименьшим значением **приоритета** (например, **3** ) имеет только кнопку **повышения приоритета** .</span><span class="sxs-lookup"><span data-stu-id="c2401-217">The Safe Links policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="c2401-218">Если у вас есть три или более политики безопасных ссылок, политики между самыми высокими и минимальными значениями приоритетов имеют доступные кнопки **повышение приоритет** и **понижение приоритета** .</span><span class="sxs-lookup"><span data-stu-id="c2401-218">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="c2401-219">Щелкните **увеличить** или **уменьшить** приоритет, чтобы изменить значение **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="c2401-219">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="c2401-220">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c2401-220">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="c2401-221">Использование центра безопасности & соответствия требованиям для удаления политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-221">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="c2401-222">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**.</span><span class="sxs-lookup"><span data-stu-id="c2401-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="c2401-223">На странице **безопасные ссылки** выберите политику из списка и щелкните ее (не устанавливая флажок).</span><span class="sxs-lookup"><span data-stu-id="c2401-223">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="c2401-224">В появившемся окне сведения о политике выберите **удалить политику** , а затем нажмите кнопку **Да** в появившемся диалоговом окне предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c2401-224">In the policy details fly out that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="c2401-225">Настройка политик безопасных ссылок с помощью Exchange Online PowerShell или изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2401-225">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="c2401-226">Как было сказано ранее, политика безопасных ссылок состоит из политики безопасных ссылок и правила безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-226">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="c2401-227">В PowerShell разница между политиками безопасных ссылок и правил безопасных ссылок очевидна.</span><span class="sxs-lookup"><span data-stu-id="c2401-227">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="c2401-228">Управлять политиками безопасных ссылок можно с помощью командлетов **\* safelinkspolicy позволяет** , а также управлять правилами безопасных ссылок с помощью командлетов **\* – SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="c2401-228">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="c2401-229">В PowerShell сначала создается политика безопасных ссылок, а затем создается правило безопасных ссылок, которое определяет политику, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="c2401-229">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="c2401-230">В PowerShell параметры политики безопасных ссылок и правила безопасных ссылок можно изменить отдельно.</span><span class="sxs-lookup"><span data-stu-id="c2401-230">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="c2401-231">При удалении политики безопасных ссылок из PowerShell соответствующее правило безопасных ссылок не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="c2401-231">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="c2401-232">Создание политик безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2401-232">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="c2401-233">Процесс создания политики безопасных ссылок в PowerShell состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="c2401-233">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="c2401-234">Создайте политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-234">Create the safe links policy.</span></span>
2. <span data-ttu-id="c2401-235">Создайте правило безопасных ссылок, которое определяет политику безопасных ссылок, к которой применяется правило.</span><span class="sxs-lookup"><span data-stu-id="c2401-235">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="c2401-236">**Примечания** :</span><span class="sxs-lookup"><span data-stu-id="c2401-236">**Notes** :</span></span>

- <span data-ttu-id="c2401-237">Вы можете создать новое правило безопасных ссылок и присвоить ему существующую, несвязанную политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-237">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="c2401-238">Правило безопасных ссылок невозможно связать с несколькими политиками безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-238">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="c2401-239">Вы можете настроить следующие параметры для новых политик безопасных ссылок в PowerShell, которые недоступны в центре безопасности & соответствия требованиям, пока не будет создана политика:</span><span class="sxs-lookup"><span data-stu-id="c2401-239">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="c2401-240">Создайте новую политику как отключенную ( _включена_ `$false` в командлете **New-SafeLinksRule** ).</span><span class="sxs-lookup"><span data-stu-id="c2401-240">Create the new policy as disabled ( _Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="c2401-241">Задайте приоритет политики при создании ( _приоритет_ _\<Number\>_ ) для командлета **New-SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="c2401-241">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="c2401-242">Новая политика безопасных ссылок, созданная в PowerShell, не отображается в центре безопасности & безопасности до тех пор, пока политика не будет назначена правилу безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-242">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="c2401-243">Шаг 1: использование PowerShell для создания политики безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-243">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="c2401-244">Чтобы создать политику безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-244">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="c2401-245">**Примечания** :</span><span class="sxs-lookup"><span data-stu-id="c2401-245">**Notes** :</span></span>

- <span data-ttu-id="c2401-246">Для получения подробных сведений о синтаксисе элементов, используемых для параметра _донотревритеурлс_ , обратитесь к разделу [синтаксис записи для списка "не переопределять следующие URL-адреса"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="c2401-246">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="c2401-247">Дополнительные сведения о синтаксисе, который можно использовать для параметра _донотревритеурлс_ при изменении существующих политик безопасных ссылок с помощью командлета **Set – safelinkspolicy позволяет** , можно найти в разделе [Использование PowerShell для изменения политик безопасных ссылок](#use-powershell-to-modify-safe-links-policies) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c2401-247">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="c2401-248">В этом примере создается политика безопасных ссылок с именем Contoso ALL со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="c2401-248">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="c2401-249">Включение сканирования и перезаписи URL-адресов в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c2401-249">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="c2401-250">Включите сканирование URL-адресов в Teams (нажмите только просмотр).</span><span class="sxs-lookup"><span data-stu-id="c2401-250">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="c2401-251">Включите сканирование в режиме реального времени по щелчку URL-адресов, включая ссылки, указывающие на файлы.</span><span class="sxs-lookup"><span data-stu-id="c2401-251">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="c2401-252">Дождитесь завершения сканирования URL-адресов перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="c2401-252">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="c2401-253">Включение сканирования и перезаписи URL-адресов для внутренних сообщений.</span><span class="sxs-lookup"><span data-stu-id="c2401-253">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="c2401-254">Отслеживание щелчков пользователя, связанных с защитой безопасных ссылок (мы не используем параметр _доноттраккусеркликкс_ , а значение по умолчанию — $false, что означает, что пользователь щелкает элемент отслеживается).</span><span class="sxs-lookup"><span data-stu-id="c2401-254">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="c2401-255">Не разрешать пользователям щелкать по исходному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="c2401-255">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="c2401-256">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – safelinkspolicy позволяет](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="c2401-256">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="c2401-257">Шаг 2: использование PowerShell для создания правила безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-257">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="c2401-258">Чтобы создать правило безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-258">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="c2401-259">В этом примере создается правило безопасных ссылок с именем Contoso ALL со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="c2401-259">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="c2401-260">Правило связано с политикой безопасных ссылок с именем Contoso ALL.</span><span class="sxs-lookup"><span data-stu-id="c2401-260">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="c2401-261">Правило применяется ко всем получателям в домене contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c2401-261">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="c2401-262">Так как мы не используем параметр _Priority_ , используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c2401-262">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="c2401-263">Правило включено (параметр _Enabled_ не используется, а значение по умолчанию — `$true` ).</span><span class="sxs-lookup"><span data-stu-id="c2401-263">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="c2401-264">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c2401-264">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="c2401-265">Использование PowerShell для просмотра политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-265">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="c2401-266">Чтобы просмотреть существующие политики безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-266">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c2401-267">В этом примере возвращается сводный список всех политик безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-267">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="c2401-268">В этом примере возвращаются подробные сведения о политике безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="c2401-268">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="c2401-269">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – safelinkspolicy позволяет](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="c2401-269">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="c2401-270">Использование PowerShell для просмотра правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-270">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="c2401-271">Чтобы просмотреть существующие правила безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-271">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c2401-272">В этом примере возвращается сводный список всех правил безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-272">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="c2401-273">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="c2401-273">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="c2401-274">В этом примере возвращаются подробные сведения о правиле безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="c2401-274">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="c2401-275">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c2401-275">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="c2401-276">Использование PowerShell для изменения политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-276">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="c2401-277">Вы не можете переименовать политику безопасных ссылок в PowerShell (командлет **Set-safelinkspolicy позволяет** не имеет параметра _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="c2401-277">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="c2401-278">При переименовании политики безопасных ссылок в центре безопасности & соответствия требованиям Вы переименовываете _правило_ безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="c2401-278">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="c2401-279">Единственным дополнительным вопросом при изменении политик безопасных ссылок в PowerShell является доступный синтаксис для параметра _донотревритеурлс_ ( [список "не переопределять следующие URL-адреса"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="c2401-279">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="c2401-280">Чтобы добавить значения, которые будут заменять все существующие записи, используйте следующий синтаксис: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="c2401-280">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="c2401-281">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="c2401-281">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="c2401-282">В противном случае одни и те же параметры будут доступны при создании политики безопасных ссылок, как описано в [шаге 1: с помощью PowerShell создайте раздел "безопасные ссылки](#step-1-use-powershell-to-create-a-safe-links-policy) ", приведенный ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c2401-282">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="c2401-283">Чтобы изменить политику безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-283">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="c2401-284">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – safelinkspolicy позволяет](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="c2401-284">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="c2401-285">Использование PowerShell для изменения правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="c2401-285">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="c2401-286">Единственный параметр, недоступный при изменении правила безопасных ссылок в PowerShell, это параметр _Enabled_ , позволяющий создать отключенное правило.</span><span class="sxs-lookup"><span data-stu-id="c2401-286">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="c2401-287">Чтобы включить или отключить существующие правила безопасных ссылок, ознакомьтесь со статьей в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="c2401-287">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="c2401-288">В противном случае те же параметры доступны при создании правила, как описано в [шаге 2: используйте PowerShell, чтобы создать раздел "безопасные ссылки](#step-2-use-powershell-to-create-a-safe-links-rule) " ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c2401-288">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="c2401-289">Чтобы изменить правило безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-289">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="c2401-290">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c2401-290">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="c2401-291">Включение и отключение правил безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2401-291">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="c2401-292">Включение или отключение правила безопасных ссылок в PowerShell включает или отключает политику "все безопасные ссылки" (правило безопасных ссылок и назначенная политика безопасных ссылок).</span><span class="sxs-lookup"><span data-stu-id="c2401-292">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="c2401-293">Чтобы включить или отключить правило безопасных ссылок в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-293">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="c2401-294">В этом примере отключается правило безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="c2401-294">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c2401-295">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="c2401-295">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c2401-296">Подробные сведения о синтаксисе и параметрах можно найти в статье [Enable – SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable – SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c2401-296">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="c2401-297">Настройка приоритета правил безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2401-297">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="c2401-298">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="c2401-298">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="c2401-299">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="c2401-299">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="c2401-300">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="c2401-300">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="c2401-301">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="c2401-301">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="c2401-302">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="c2401-302">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="c2401-303">Чтобы задать приоритет правила безопасных ссылок в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-303">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="c2401-p122">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="c2401-p122">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="c2401-306">**Примечание**. чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ в командлете **New – SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="c2401-306">**Note** : To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="c2401-307">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c2401-307">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="c2401-308">Удаление политик безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2401-308">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="c2401-309">При использовании PowerShell для удаления политики безопасных ссылок соответствующее правило не удаляется.</span><span class="sxs-lookup"><span data-stu-id="c2401-309">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="c2401-310">Чтобы удалить политику безопасных ссылок в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-310">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="c2401-311">В этом примере удаляется политика безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="c2401-311">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="c2401-312">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – safelinkspolicy позволяет](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="c2401-312">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="c2401-313">Удаление правил безопасных ссылок с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2401-313">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="c2401-314">Если вы используете PowerShell для удаления правила безопасных ссылок, соответствующая политика безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="c2401-314">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="c2401-315">Чтобы удалить правило безопасных ссылок в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c2401-315">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="c2401-316">В этом примере удаляется правило безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="c2401-316">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="c2401-317">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="c2401-317">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="c2401-318">Чтобы убедиться, что безопасные ссылки проверяют сообщения, просмотрите доступные отчеты Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="c2401-318">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="c2401-319">Дополнительные сведения см. в статье [Просмотр отчетов для защитника для Office 365](view-reports-for-atp.md) и [Использование проводника в центре безопасности & соответствия требованиям](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="c2401-319">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c2401-320">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="c2401-320">How do you know these procedures worked?</span></span>

<span data-ttu-id="c2401-321">Чтобы проверить успешность создания, изменения или удаления политик безопасных ссылок, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="c2401-321">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="c2401-322">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**.</span><span class="sxs-lookup"><span data-stu-id="c2401-322">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="c2401-323">Проверьте список политик, их значения **состояния** и значения **приоритета** .</span><span class="sxs-lookup"><span data-stu-id="c2401-323">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="c2401-324">Чтобы просмотреть дополнительные сведения, выберите политику из списка и просмотрите сведения в разделе "вылет".</span><span class="sxs-lookup"><span data-stu-id="c2401-324">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="c2401-325">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените на \<Name\> имя политики или правила, выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="c2401-325">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
