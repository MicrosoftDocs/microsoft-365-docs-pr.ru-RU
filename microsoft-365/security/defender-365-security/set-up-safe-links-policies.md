---
title: Настройка политик безопасных ссылок в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться просматривать, создавать, изменять и удалять политики безопасных ссылок и глобальные параметры безопасных ссылок в Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8b2cb8b57dcf630b3e07ac387e96ab099ca7403
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072565"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cd6de-103">Настройка политик безопасных ссылок в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="cd6de-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cd6de-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="cd6de-104">**Applies to**</span></span>
- [<span data-ttu-id="cd6de-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="cd6de-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cd6de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd6de-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="cd6de-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="cd6de-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="cd6de-108">Если вы домашний пользователь, который ищет сведения о Safelinks в Outlook, см. в Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="cd6de-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="cd6de-109">Безопасные ссылки — это функция [в Microsoft Defender для Office 365,](defender-for-office-365.md) которая обеспечивает сканирование URL-адресов входящие сообщения электронной почты в потоке почты, а также время проверки URL-адресов и ссылок в сообщениях электронной почты и в других местах.</span><span class="sxs-lookup"><span data-stu-id="cd6de-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="cd6de-110">Дополнительные сведения см. в [веб-сайте Безопасные ссылки в Microsoft Defender для Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="cd6de-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="cd6de-111">Не существует встроенной или по умолчанию политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="cd6de-112">Чтобы получить сканирование URL-адресов безопасных ссылок, необходимо создать одну или несколько политик безопасных ссылок, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cd6de-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="cd6de-113">Настройка глобальных параметров защиты безопасных ссылок за **пределами** политик безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="cd6de-114">Инструкции см. в [инструкции Configure global settings for Safe Links in Microsoft Defender for Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="cd6de-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="cd6de-115">Политики безопасных ссылок можно настроить в Центре обеспечения безопасности & или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономных EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с помощью надстройки Microsoft Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="cd6de-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="cd6de-116">Основные элементы политики безопасных ссылок:</span><span class="sxs-lookup"><span data-stu-id="cd6de-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="cd6de-117">Политика безопасных ссылок: включайте защиту безопасных ссылок, включайте сканирование URL-адресов в режиме реального времени, укажите, следует ли ждать завершения сканирования в режиме реального времени перед доставкой сообщения, включить сканирование внутренних сообщений, указать, следует ли отслеживать щелчки пользователя по URL-адресам, а также указать, следует ли разрешить пользователям щелкнуть корыто на исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="cd6de-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="cd6de-118">**Правило безопасных ссылок:** указывает фильтры приоритета и получателя (к кому применяется политика).</span><span class="sxs-lookup"><span data-stu-id="cd6de-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="cd6de-119">Разница между этими двумя элементами не очевидна при управлении полицией безопасных ссылок в Центре & безопасности:</span><span class="sxs-lookup"><span data-stu-id="cd6de-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="cd6de-120">При создании политики безопасных ссылок создается правило безопасных ссылок и связанная политика безопасных ссылок одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="cd6de-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="cd6de-121">При изменении политики безопасных ссылок параметры, связанные с именем, приоритетом, включенной или отключенной, и фильтры получателей изменяют правило безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="cd6de-122">Все остальные параметры изменяют связанную политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="cd6de-123">При удалении политики безопасных ссылок правило безопасных ссылок и связанная политика безопасных ссылок удаляются.</span><span class="sxs-lookup"><span data-stu-id="cd6de-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="cd6de-124">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="cd6de-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="cd6de-125">Дополнительные сведения см. в разделе Use Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) для настройки политики безопасных ссылок в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cd6de-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cd6de-126">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="cd6de-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cd6de-127">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="cd6de-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cd6de-128">Чтобы перейти непосредственно на страницу **Безопасные ссылки,** используйте <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="cd6de-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="cd6de-129">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cd6de-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cd6de-130">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="cd6de-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cd6de-131">Прежде чем делать процедуры в этой статье, необходимо получить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="cd6de-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cd6de-132">Чтобы создать, изменить и удалить политики безопасных ссылок, необходимо быть  членом группы ролей управления организацией или администратором безопасности  в Центре соответствия требованиям & безопасности и членом группы ролей управления организацией в Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="cd6de-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="cd6de-133">Для доступа только для чтения к политикам безопасных ссылок необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="cd6de-134">Дополнительные сведения см. [в веб-сайте Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="cd6de-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="cd6de-135">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd6de-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cd6de-136">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cd6de-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="cd6de-137">.</span><span class="sxs-lookup"><span data-stu-id="cd6de-137">.</span></span> <span data-ttu-id="cd6de-138">— Группа **ролей управления** только для просмотра организации в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="cd6de-138">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="cd6de-139">Рекомендуемые параметры для политик безопасных ссылок см. в этой [ссылке.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="cd6de-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="cd6de-140">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="cd6de-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="cd6de-141">[Новые функции постоянно добавляются в Microsoft Defender для Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="cd6de-141">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="cd6de-142">При добавлении новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="cd6de-143">Используйте Центр & безопасности для создания политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="cd6de-144">Создание настраиваемой политики безопасных ссылок в Центре & безопасности создает правило безопасных ссылок и связанную политику безопасных ссылок одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="cd6de-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="cd6de-145">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="cd6de-146">На странице **Безопасные ссылки** нажмите **кнопку Создать**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="cd6de-147">Откроется мастер политики "Новые **безопасные** ссылки".</span><span class="sxs-lookup"><span data-stu-id="cd6de-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="cd6de-148">На странице **Имя политики** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="cd6de-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="cd6de-149">**Имя**. Укажите уникальное, понятное имя политики.</span><span class="sxs-lookup"><span data-stu-id="cd6de-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="cd6de-150">**Описание**. Укажите необязательное описание политики.</span><span class="sxs-lookup"><span data-stu-id="cd6de-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="cd6de-151">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="cd6de-152">На **странице Параметры,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="cd6de-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cd6de-153">**Выберите действие для неизвестных** потенциально вредоносных URL-адресов в сообщениях: **Выберите** On, чтобы включить защиту безопасных ссылок для ссылок в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cd6de-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="cd6de-154">**Выберите действие для неизвестных или** потенциально вредоносных URL-адресов в Microsoft Teams: **Выберите** On, чтобы включить защиту безопасных ссылок для ссылок в Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6de-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="cd6de-155">**Применение сканирования URL-адресов** в режиме реального времени для подозрительных ссылок и ссылок, которые указывают на файлы: Выберите этот параметр, чтобы включить сканирование ссылок в электронной почте в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="cd6de-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="cd6de-156">**Дождись завершения** сканирования URL-адресов перед доставкой сообщения. Выберите этот параметр, чтобы дождаться завершения сканирования URL-адресов в режиме реального времени перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="cd6de-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="cd6de-157">**Применение безопасных ссылок** к сообщениям электронной почты, отправленным в организации: Выберите этот параметр, чтобы применить политику безопасных ссылок к сообщениям между внутренними отправителями и внутренними получателями.</span><span class="sxs-lookup"><span data-stu-id="cd6de-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="cd6de-158">**Не отслеживайте щелчки** пользователя: оставьте этот параметр незасеченным, чтобы включить щелчки пользователя отслеживания url-адресов в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cd6de-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="cd6de-159">**Не позволяйте пользователям** щелкнуть исходный URL-адрес: Выберите этот параметр, чтобы заблокировать доступ пользователей к исходному URL-адресу на страницах [с предупреждением.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="cd6de-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="cd6de-160">**Не переописывайте** следующие URL-адреса: позволяет получить доступ к указанным URL-адресам, которые в противном случае будут заблокированы с помощью безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="cd6de-161">В поле введите НУЖНЫЙ URL-адрес или значение, а затем нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="cd6de-161">In the box, type the URL or value that you want, and then click</span></span> ![Добавление значка кнопки](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="cd6de-163">.</span><span class="sxs-lookup"><span data-stu-id="cd6de-163">.</span></span>

     <span data-ttu-id="cd6de-164">Чтобы удалить существующую запись, выберите ее и нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="cd6de-164">To remove an existing entry, select it and then click</span></span> ![Удаление значка кнопки](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="cd6de-166">.</span><span class="sxs-lookup"><span data-stu-id="cd6de-166">.</span></span>

     <span data-ttu-id="cd6de-167">Синтаксис записи см. в синтаксис Записи в списке "Не переписать следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="cd6de-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="cd6de-168">Подробные сведения об этих параметрах см. в настройках [Безопасные](safe-links.md#safe-links-settings-for-email-messages) ссылки для сообщений электронной почты и [параметры безопасных](safe-links.md#safe-links-settings-for-microsoft-teams)ссылок для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd6de-168">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="cd6de-169">Дополнительные рекомендуемые значения для стандартных и строгих параметров политики см. в дополнительных параметрах [политики безопасных ссылок.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="cd6de-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="cd6de-170">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="cd6de-171">На странице **Applied to** page, которая появится, определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="cd6de-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="cd6de-172">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="cd6de-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="cd6de-173">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="cd6de-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="cd6de-174">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="cd6de-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="cd6de-175">Нажмите **кнопку Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-175">Click **Add a condition**.</span></span> <span data-ttu-id="cd6de-176">В отсеве, которое появится, выберите условие в **applied, если**:</span><span class="sxs-lookup"><span data-stu-id="cd6de-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="cd6de-177">**Получатель:** указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="cd6de-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="cd6de-178">**Получатель является членом**: указывает одну или несколько групп в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cd6de-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="cd6de-179">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cd6de-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="cd6de-180">После выбора условия в любом из этих поле появится соответствующее **отсев.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="cd6de-181">Щелкните в поле и прокрутите список значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="cd6de-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="cd6de-182">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="cd6de-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="cd6de-183">Чтобы добавить дополнительные значения, щелкните в пустой области в поле.</span><span class="sxs-lookup"><span data-stu-id="cd6de-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="cd6de-184">Чтобы удалить отдельные записи, **нажмите кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) значение.</span><span class="sxs-lookup"><span data-stu-id="cd6de-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="cd6de-185">Чтобы удалить все условие, нажмите **кнопку Удалить значок Удалить** ![ в ](../../media/scc-remove-icon.png) состоянии.</span><span class="sxs-lookup"><span data-stu-id="cd6de-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="cd6de-186">Чтобы добавить дополнительное условие, нажмите **кнопку Добавить условие** и выберите оставшееся значение **в applied if**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="cd6de-187">Чтобы добавить исключения, нажмите **кнопку Добавить условие** и выберите исключение в соответствии **с исключением, если**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="cd6de-188">Параметры и поведение полностью идентичны условиям.</span><span class="sxs-lookup"><span data-stu-id="cd6de-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="cd6de-189">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="cd6de-190">На странице **Обзор параметров,** которая отображается, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="cd6de-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="cd6de-191">Чтобы изменить его, можно нажать **кнопку Изменить** каждый параметр.</span><span class="sxs-lookup"><span data-stu-id="cd6de-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="cd6de-192">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="cd6de-193">Используйте Центр & безопасности для просмотра политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="cd6de-194">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="cd6de-195">На странице **Безопасные ссылки** выберите политику из списка и нажмите на нее (не выберите поле).</span><span class="sxs-lookup"><span data-stu-id="cd6de-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="cd6de-196">Сведения о политике отображаются в вылете</span><span class="sxs-lookup"><span data-stu-id="cd6de-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="cd6de-197">Используйте Центр & безопасности для изменения политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="cd6de-198">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="cd6de-199">На странице **Безопасные ссылки** выберите политику из списка и нажмите на нее (не выберите поле).</span><span class="sxs-lookup"><span data-stu-id="cd6de-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="cd6de-200">В появились сведения о политике, нажмите **кнопку Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="cd6de-201">Доступные параметры в вылете, которые появляются, идентичны тем, которые описаны в разделе Use the Security & Compliance Center для создания политик [безопасных ссылок.](#use-the-security--compliance-center-to-create-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="cd6de-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="cd6de-202">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="cd6de-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="cd6de-203">Включить или отключить политики безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="cd6de-204">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="cd6de-205">Обратите внимание на значение в **столбце Состояние:**</span><span class="sxs-lookup"><span data-stu-id="cd6de-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="cd6de-206">Чтобы отключить политику, переместите переключатель влево:</span><span class="sxs-lookup"><span data-stu-id="cd6de-206">Move the toggle to the left to disable the policy:</span></span> ![Отключение политики](../../media/scc-toggle-off.png)<span data-ttu-id="cd6de-208">.</span><span class="sxs-lookup"><span data-stu-id="cd6de-208">.</span></span>

   - <span data-ttu-id="cd6de-209">Чтобы включить политику, переместите переключатель вправо:</span><span class="sxs-lookup"><span data-stu-id="cd6de-209">Move the toggle to the right to enable the policy:</span></span> ![Включаем политику](../../media/scc-toggle-on.png)<span data-ttu-id="cd6de-211">.</span><span class="sxs-lookup"><span data-stu-id="cd6de-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="cd6de-212">Заорит приоритет политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="cd6de-213">По умолчанию политикам безопасных ссылок предоставляется приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="cd6de-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="cd6de-214">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="cd6de-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="cd6de-215">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="cd6de-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="cd6de-216">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="cd6de-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="cd6de-217">Политики безопасных ссылок отображаются в порядке их обработки (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="cd6de-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="cd6de-218">В Центре & безопасности можно изменить приоритет политики безопасных ссылок только после ее создания.</span><span class="sxs-lookup"><span data-stu-id="cd6de-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="cd6de-219">В PowerShell можно переопредить приоритет по умолчанию при создании правила безопасных ссылок (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="cd6de-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="cd6de-220">Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).</span><span class="sxs-lookup"><span data-stu-id="cd6de-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="cd6de-221">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="cd6de-222">На странице **Безопасные ссылки** выберите политику из списка и нажмите на нее (не выберите поле).</span><span class="sxs-lookup"><span data-stu-id="cd6de-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="cd6de-223">В появились сведения о политике, щелкните доступную кнопку приоритета:</span><span class="sxs-lookup"><span data-stu-id="cd6de-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="cd6de-224">Политика безопасных ссылок со **значением Приоритет** **0** имеет только доступную кнопку **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="cd6de-225">Политика безопасных ссылок с **наименьшим** значением приоритета (например, **3)** имеет только доступную кнопку **Увеличение приоритета.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="cd6de-226">Если у вас есть три или более политик безопасных ссылок, политики между  самыми высокими и самыми низкими значениями приоритетов имеют доступные кнопки "Увеличение приоритета" и **"Уменьшение** приоритетов".</span><span class="sxs-lookup"><span data-stu-id="cd6de-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="cd6de-227">Щелкните **Увеличить приоритет или** уменьшить **приоритет,** чтобы изменить **значение Priority.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="cd6de-228">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="cd6de-229">С помощью Центра & безопасности для удаления политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="cd6de-230">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="cd6de-231">На странице **Безопасные ссылки** выберите политику из списка и нажмите на нее (не выберите поле).</span><span class="sxs-lookup"><span data-stu-id="cd6de-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="cd6de-232">В появились сведения о политике, нажмите кнопку **Удалить** политику, а затем нажмите **кнопку Да** в диалоговом окте предупреждения, который появится.</span><span class="sxs-lookup"><span data-stu-id="cd6de-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="cd6de-233">Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="cd6de-234">Как описано выше, политика безопасных ссылок состоит из политики безопасных ссылок и правила безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="cd6de-235">В PowerShell очевидна разница между политиками безопасных ссылок и правилами безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="cd6de-236">Вы управляете политиками безопасных ссылок с помощью **\* кодлетов -SafeLinksPolicy** и управляете правилами безопасных ссылок с помощью **\* cmdlets-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="cd6de-237">В PowerShell сначала создается политика безопасных ссылок, а затем создается правило безопасных ссылок, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="cd6de-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="cd6de-238">В PowerShell параметры политики безопасных ссылок и правила безопасных ссылок изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="cd6de-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="cd6de-239">При удалении политики безопасных ссылок из PowerShell соответствующее правило безопасных ссылок не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="cd6de-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="cd6de-240">Использование PowerShell для создания политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="cd6de-241">Создание политики безопасных ссылок в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="cd6de-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="cd6de-242">Создание политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="cd6de-243">Создайте правило безопасных ссылок, которое указывает политику безопасных ссылок, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="cd6de-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="cd6de-244">Можно создать новое правило безопасных ссылок и назначить к ней существующую политику безопасных ссылок без связи.</span><span class="sxs-lookup"><span data-stu-id="cd6de-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="cd6de-245">Правило безопасных ссылок не может быть связано с более чем одной политикой безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="cd6de-246">Вы можете настроить следующие параметры для новых политик безопасных ссылок в PowerShell, недоступных в Центре обеспечения безопасности & до момента создания политики:</span><span class="sxs-lookup"><span data-stu-id="cd6de-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="cd6de-247">Создайте новую политику как отключенную _(включена_ `$false` в **комлете New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="cd6de-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="cd6de-248">Задай приоритет политики во время создания _(priority)_ в _\<Number\>_ **комлете New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="cd6de-249">Новая политика безопасных ссылок, которую вы создаете в PowerShell, не отображается в Центре & безопасности, пока не назначите политику правилу безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="cd6de-250">Шаг 1. Использование PowerShell для создания политики безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="cd6de-251">Чтобы создать политику безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="cd6de-252">Подробные сведения о синтаксисе записи, используемом для параметра _DoNotRewriteUrls,_ см. в материале Запись синтаксиса для списка "Не переписывай следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="cd6de-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="cd6de-253">Дополнительный синтаксис, который можно использовать для параметра _DoNotRewriteUrls_ при изменении существующих политик безопасных ссылок с помощью комлета **Set-SafeLinksPolicy,** см. в разделе [Использование PowerShell](#use-powershell-to-modify-safe-links-policies) для изменения политик безопасных ссылок в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cd6de-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="cd6de-254">В этом примере создается политика безопасных ссылок с именем Contoso All со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="cd6de-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="cd6de-255">Включайте сканирование URL-адресов и переписывание в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cd6de-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="cd6de-256">Включив сканирование URL-адресов в Teams (только для предварительного просмотра TAP).</span><span class="sxs-lookup"><span data-stu-id="cd6de-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="cd6de-257">Включайте сканирование url-адресов в режиме реального времени, в том числе щелкнув ссылки, которые указывают на файлы.</span><span class="sxs-lookup"><span data-stu-id="cd6de-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="cd6de-258">Дождись завершения сканирования URL-адресов перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="cd6de-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="cd6de-259">Включи сканирование URL-адресов и переописывание внутренних сообщений.</span><span class="sxs-lookup"><span data-stu-id="cd6de-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="cd6de-260">Отслеживайте щелчки пользователей, связанные с защитой безопасных ссылок (мы не используем параметр _DoNotTrackUserClicks,_ а значение по умолчанию $false, что означает отслеживание кликов пользователей).</span><span class="sxs-lookup"><span data-stu-id="cd6de-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="cd6de-261">Не позволяйте пользователям щелкнуть исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="cd6de-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="cd6de-262">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SafeLinksPolicy.](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="cd6de-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="cd6de-263">Шаг 2. Использование PowerShell для создания правила безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="cd6de-264">Чтобы создать правило безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="cd6de-265">В этом примере создается правило безопасных ссылок с именем Contoso All со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="cd6de-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="cd6de-266">Правило связано с политикой безопасных ссылок с именем Contoso All.</span><span class="sxs-lookup"><span data-stu-id="cd6de-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="cd6de-267">Правило применяется ко всем получателям в contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="cd6de-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="cd6de-268">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cd6de-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="cd6de-269">Правило включено (мы не используем параметр _Включен,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cd6de-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="cd6de-270">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SafeLinksRule.](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="cd6de-270">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="cd6de-271">Использование PowerShell для просмотра политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="cd6de-272">Чтобы просмотреть существующие политики безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="cd6de-273">В этом примере возвращается сводный список всех политик безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="cd6de-274">В этом примере возвращаются подробные сведения о политике безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="cd6de-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="cd6de-275">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SafeLinksPolicy.](/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="cd6de-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="cd6de-276">Использование PowerShell для просмотра правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="cd6de-277">Чтобы просмотреть существующие правила безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="cd6de-278">В этом примере возвращается сводный список всех правил безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="cd6de-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="cd6de-279">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="cd6de-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="cd6de-280">В этом примере возвращается подробная информация для правила безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="cd6de-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="cd6de-281">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SafeLinksRule.](/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="cd6de-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="cd6de-282">Использование PowerShell для изменения политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="cd6de-283">В PowerShell нельзя переименовать политику безопасных ссылок (в **комлете Set-SafeLinksPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="cd6de-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="cd6de-284">При переименовании политики безопасных ссылок в Центре & безопасности вы только переименовывать правило безопасных _ссылок._</span><span class="sxs-lookup"><span data-stu-id="cd6de-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="cd6de-285">Единственным дополнительным фактором для изменения политик безопасных ссылок в PowerShell является доступный синтаксис для параметра _DoNotRewriteUrls_ (список "Не переписать следующие [URL-адреса"):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="cd6de-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="cd6de-286">Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="cd6de-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="cd6de-287">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="cd6de-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="cd6de-288">В противном случае те же параметры доступны при создании политики безопасных ссылок, как описано в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) для создания раздела политики безопасных ссылок ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cd6de-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="cd6de-289">Чтобы изменить политику безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="cd6de-290">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksPolicy.](/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="cd6de-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="cd6de-291">Использование PowerShell для изменения правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="cd6de-292">Единственным параметром, недоступным при изменении правила безопасных ссылок  в PowerShell, является параметр Включен, который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="cd6de-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="cd6de-293">Чтобы включить или отключить существующие правила безопасных ссылок, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="cd6de-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="cd6de-294">В противном случае те же параметры доступны при создании правила, описанного в шаге [2: Использование PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) для создания раздела правила безопасных ссылок в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="cd6de-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="cd6de-295">Чтобы изменить правило безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="cd6de-296">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="cd6de-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="cd6de-297">Использование PowerShell для включения или отключения правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="cd6de-298">Включение или отключение правила безопасных ссылок в PowerShell включает или отключает всю политику безопасных ссылок (правило безопасных ссылок и назначенную политику безопасных ссылок).</span><span class="sxs-lookup"><span data-stu-id="cd6de-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="cd6de-299">Чтобы включить или отключить правило безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="cd6de-300">В этом примере отключает правило безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="cd6de-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="cd6de-301">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="cd6de-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="cd6de-302">Подробные сведения о синтаксисах и параметрах см. в [рублях Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) и [Disable-SafeLinksRule.](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="cd6de-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="cd6de-303">Используйте PowerShell, чтобы установить приоритет правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="cd6de-304">Максимальный приоритет, который можно задать для правила, — 0.</span><span class="sxs-lookup"><span data-stu-id="cd6de-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="cd6de-305">Минимальное значение зависит от количества правил.</span><span class="sxs-lookup"><span data-stu-id="cd6de-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="cd6de-306">Например, если у вас есть пять правил, вы можете использовать значения 0–4.</span><span class="sxs-lookup"><span data-stu-id="cd6de-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="cd6de-307">Изменение приоритета существующего правила оказывает каскадное влияние на другие правила.</span><span class="sxs-lookup"><span data-stu-id="cd6de-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="cd6de-308">Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="cd6de-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="cd6de-309">Чтобы установить приоритет правила безопасных ссылок в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="cd6de-p123">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="cd6de-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="cd6de-312">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="cd6de-313">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="cd6de-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="cd6de-314">Использование PowerShell для удаления политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="cd6de-315">При удалении политики безопасных ссылок с помощью PowerShell соответствующее правило безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="cd6de-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="cd6de-316">Чтобы удалить политику безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="cd6de-317">В этом примере удаляется политика безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="cd6de-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="cd6de-318">Подробные сведения о синтаксисах и параметрах см. в этой ссылке [Remove-SafeLinksPolicy.](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="cd6de-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="cd6de-319">Использование PowerShell для удаления правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="cd6de-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="cd6de-320">При удалении правила безопасных ссылок с помощью PowerShell соответствующая политика безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="cd6de-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="cd6de-321">Чтобы удалить правило безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cd6de-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="cd6de-322">В этом примере удаляется правило безопасных ссылок с именем Отдел маркетинга.</span><span class="sxs-lookup"><span data-stu-id="cd6de-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="cd6de-323">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-SafeLinksRule.](/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="cd6de-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="cd6de-324">Чтобы убедиться, что безопасные ссылки сканирует сообщения, ознакомьтесь с доступными отчетами Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd6de-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="cd6de-325">Дополнительные сведения см. в обзоре отчетов [для Defender для Office 365](view-reports-for-mdo.md) и Use Explorer в Центре & [безопасности.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="cd6de-325">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="cd6de-326">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="cd6de-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="cd6de-327">Чтобы убедиться, что вы успешно создали, изменили или удалили политики безопасных ссылок, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cd6de-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="cd6de-328">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="cd6de-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="cd6de-329">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="cd6de-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="cd6de-330">Чтобы просмотреть дополнительные сведения, выберите политику из списка и просмотреть сведения в поле вылета.</span><span class="sxs-lookup"><span data-stu-id="cd6de-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="cd6de-331">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="cd6de-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```