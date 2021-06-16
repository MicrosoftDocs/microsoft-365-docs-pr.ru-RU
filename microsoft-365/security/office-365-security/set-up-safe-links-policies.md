---
title: Настройка политик Сейф ссылок в Microsoft Defender для Office 365
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
description: Администраторы могут научиться просматривать, создавать, изменять и удалять Сейф ссылки и глобальные Сейф ссылки в Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40ae52cfce53c3fa14253a94e72f1a2bccda9a86
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929831"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="036e9-103">Настройка политик Сейф ссылок в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="036e9-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="036e9-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="036e9-104">**Applies to**</span></span>
- [<span data-ttu-id="036e9-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="036e9-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="036e9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="036e9-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="036e9-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="036e9-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="036e9-108">Если вы домашний пользователь, который ищет сведения о Safelinks в Outlook, см. в [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="036e9-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="036e9-109">Сейф Ссылки — это функция в Microsoft Defender для Office 365, которая обеспечивает сканирование [URL-адресов](defender-for-office-365.md) входящие сообщения электронной почты в потоке почты, а также время проверки URL-адресов и ссылок в сообщениях электронной почты и в других местах.</span><span class="sxs-lookup"><span data-stu-id="036e9-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="036e9-110">Дополнительные сведения см. [в Сейф Ссылки в Microsoft Defender для Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="036e9-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="036e9-111">Не существует политики встроенных или Сейф ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="036e9-112">Чтобы получить Сейф ссылки для сканирования URL-адресов, необходимо создать одну или несколько Сейф ссылок, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="036e9-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="036e9-113">Вы настраивает глобальные параметры защиты Сейф **ссылок** за пределами политик Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="036e9-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="036e9-114">Инструкции см. в перенастройке глобальных [параметров для Сейф ссылок в Microsoft Defender для Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="036e9-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="036e9-115">Политики ссылок Сейф можно настроить на портале Microsoft 365 Defender или в PowerShell (Exchange Online PowerShell для подходящих Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без Exchange Online почтовых ящиков, но с Microsoft Defender для Office 365 надстройки).</span><span class="sxs-lookup"><span data-stu-id="036e9-115">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="036e9-116">Основные элементы политики Сейф ссылки:</span><span class="sxs-lookup"><span data-stu-id="036e9-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="036e9-117">Политика безопасных ссылок: включайте защиту Сейф ссылок, включайте сканирование URL-адресов в режиме реального времени, укажите, следует ли ждать завершения сканирования в режиме реального времени перед доставкой сообщения, включить сканирование внутренних сообщений, указать, следует ли отслеживать клики пользователя по URL-адресам, а также указать, следует ли разрешить пользователям щелкнуть корыто на исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="036e9-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="036e9-118">**Правило безопасных ссылок:** указывает фильтры приоритета и получателя (к кому применяется политика).</span><span class="sxs-lookup"><span data-stu-id="036e9-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="036e9-119">Администраторы должны учитывать различные параметры конфигурации для SafeLinks.</span><span class="sxs-lookup"><span data-stu-id="036e9-119">Admins should consider the different configuration settings for SafeLinks.</span></span> <span data-ttu-id="036e9-120">Один из доступных вариантов — включить идентифицируемые сведения пользователей в SafeLinks.</span><span class="sxs-lookup"><span data-stu-id="036e9-120">One of the available options is to include user identifiable information in SafeLinks.</span></span> <span data-ttu-id="036e9-121">Эта функция позволяет *командам security Ops* исследовать потенциальный пользовательский компромисс, принимать меры по исправлению и ограничивать дорогостоящие нарушения.</span><span class="sxs-lookup"><span data-stu-id="036e9-121">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="036e9-122">Разница между этими двумя элементами не очевидна при управлении Сейф ссылками на портале Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="036e9-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="036e9-123">При создании политики Сейф ссылки создается правило безопасных ссылок и связанная политика безопасных ссылок одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="036e9-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="036e9-124">При изменении политики Сейф ссылки параметры, связанные с именем, приоритетом, включенной или отключенной, а также фильтры получателей изменяют правило безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="036e9-125">Все остальные параметры изменяют связанную политику безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="036e9-126">При удалении политики Сейф ссылки правило безопасных ссылок и связанная политика безопасных ссылок удаляются.</span><span class="sxs-lookup"><span data-stu-id="036e9-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="036e9-127">В Exchange Online PowerShell или автономном EOP PowerShell вы управляете политикой и правилом отдельно.</span><span class="sxs-lookup"><span data-stu-id="036e9-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="036e9-128">Дополнительные сведения см. в разделе Использование Exchange Online PowerShell или автономный [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) для настройки Сейф ссылок далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="036e9-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="036e9-129">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="036e9-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="036e9-130">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="036e9-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="036e9-131">Чтобы перейти непосредственно **на страницу Сейф ссылки,** используйте <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="036e9-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="036e9-132">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="036e9-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="036e9-133">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="036e9-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="036e9-134">Прежде чем делать процедуры в этой статье, необходимо получить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="036e9-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="036e9-135">Чтобы создать, изменить и удалить политики Сейф ссылки, необходимо быть членом группы  ролей управления организацией или администратором  безопасности на портале Microsoft 365 Defender и членом группы ролей управления организацией в Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="036e9-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="036e9-136">Для доступа только для чтения к политикам Сейф ссылки необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="036e9-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="036e9-137">Дополнительные сведения см. [в см.](permissions-in-the-security-and-compliance-center.md) в Microsoft 365 портале Defender и [разрешениях в Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="036e9-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="036e9-138">Добавление пользователей к соответствующей роли Azure Active Directory в центре администрирования Microsoft 365 предоставляет пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения на другие функции в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="036e9-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="036e9-139">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="036e9-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="036e9-140">.</span><span class="sxs-lookup"><span data-stu-id="036e9-140">.</span></span> <span data-ttu-id="036e9-141">— Группа **ролей для** управления только для просмотра организации в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="036e9-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="036e9-142">Рекомендуемые параметры для политик Сейф ссылки см. в Сейф [параметров политики ссылок.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="036e9-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="036e9-143">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="036e9-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="036e9-144">[Новые функции постоянно добавляются в Microsoft Defender для](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="036e9-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="036e9-145">При добавлении новых функций может потребоваться внести изменения в существующие политики Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="036e9-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="036e9-146">Используйте портал Microsoft 365 Defender для создания политик Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="036e9-147">Создание настраиваемой политики Сейф ссылок на портале Microsoft 365 Defender создает правило безопасных ссылок и связанную политику безопасных ссылок одновременно с использованием одного и того же имени для обоих.</span><span class="sxs-lookup"><span data-stu-id="036e9-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="036e9-148">На портале Microsoft 365 Defender перейдите к политике & **правила** политики \>  \> **угрозы Сейф ссылки**.</span><span class="sxs-lookup"><span data-stu-id="036e9-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="036e9-149">На странице **Сейф ссылки** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="036e9-149">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="036e9-150">Откроется **мастер политики Сейф** ссылки.</span><span class="sxs-lookup"><span data-stu-id="036e9-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="036e9-151">На странице **Имя политики** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="036e9-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="036e9-152">**Имя**. Укажите уникальное, описательное имя политики.</span><span class="sxs-lookup"><span data-stu-id="036e9-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="036e9-153">**Описание**. По желанию введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="036e9-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="036e9-154">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="036e9-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="036e9-155">На **Параметры,** которая появится, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="036e9-155">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="036e9-156">**Выберите действие для неизвестных** потенциально вредоносных URL-адресов в сообщениях: Выберите On, чтобы включить защиту Сейф ссылок для ссылок в сообщениях электронной почты. </span><span class="sxs-lookup"><span data-stu-id="036e9-156">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="036e9-157">**Выберите действие для** неизвестных или потенциально вредоносных URL-адресов в Microsoft Teams : **Выберите** on, чтобы включить защиту Сейф ссылок для ссылок в Teams.</span><span class="sxs-lookup"><span data-stu-id="036e9-157">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="036e9-158">**Применение сканирования URL-адресов** в режиме реального времени для подозрительных ссылок и ссылок, которые указывают на файлы: Выберите этот параметр, чтобы включить сканирование ссылок в электронной почте в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="036e9-158">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="036e9-159">**Дождись завершения** сканирования URL-адресов перед доставкой сообщения. Выберите этот параметр, чтобы дождаться завершения сканирования URL-адресов в режиме реального времени перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="036e9-159">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="036e9-160">**Применяйте Сейф** ссылки на сообщения электронной почты, отправленные в организации: Выберите этот параметр, чтобы применить политику Сейф ссылок к сообщениям между внутренними отправителями и внутренними получателями.</span><span class="sxs-lookup"><span data-stu-id="036e9-160">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="036e9-161">**Не отслеживайте щелчки** пользователя: оставьте этот параметр незасеченным, чтобы включить щелчки пользователя отслеживания url-адресов в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="036e9-161">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="036e9-162">**Не позволяйте пользователям** щелкнуть исходный URL-адрес: Выберите этот параметр, чтобы заблокировать доступ пользователей к исходному URL-адресу на страницах [с предупреждением.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="036e9-162">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="036e9-163">**Не переписать** следующие URL-адреса: разрешить доступ к указанным URL-адресам, которые в противном случае будут заблокированы Сейф ссылками.</span><span class="sxs-lookup"><span data-stu-id="036e9-163">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="036e9-164">В поле введите НУЖНЫЙ URL-адрес или значение, а затем нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="036e9-164">In the box, type the URL or value that you want, and then click</span></span> ![Добавление значка кнопки](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="036e9-166">.</span><span class="sxs-lookup"><span data-stu-id="036e9-166">.</span></span>

     <span data-ttu-id="036e9-167">Чтобы удалить существующую запись, выберите ее и нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="036e9-167">To remove an existing entry, select it and then click</span></span> ![Удаление значка кнопки](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="036e9-169">.</span><span class="sxs-lookup"><span data-stu-id="036e9-169">.</span></span>

     <span data-ttu-id="036e9-170">Синтаксис записи см. в синтаксис Записи в списке "Не переписать следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="036e9-170">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="036e9-171">Подробные сведения об этих параметрах см. в [Сейф ссылки](safe-links.md#safe-links-settings-for-email-messages) на сообщения электронной почты и [Сейф ссылки для Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="036e9-171">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="036e9-172">Дополнительные рекомендуемые значения для параметров стандартной и строгой политики см. в [Сейф параметров политики ссылок.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="036e9-172">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="036e9-173">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="036e9-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="036e9-174">На странице **Applied to** page, которая появится, определите внутренних получателей, к которые применяется политика.</span><span class="sxs-lookup"><span data-stu-id="036e9-174">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="036e9-175">Условие или исключение можно использовать только один раз, но можно указать для них несколько значений.</span><span class="sxs-lookup"><span data-stu-id="036e9-175">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="036e9-176">Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="036e9-176">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="036e9-177">Между разными условиями и исключениями используется оператор AND (например, _\<recipient1\>_ and _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="036e9-177">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="036e9-178">Нажмите **кнопку Добавить условие**.</span><span class="sxs-lookup"><span data-stu-id="036e9-178">Click **Add a condition**.</span></span> <span data-ttu-id="036e9-179">В отсеве, которое появится, выберите условие в **applied, если**:</span><span class="sxs-lookup"><span data-stu-id="036e9-179">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="036e9-180">**Получатель:** указывает один или несколько почтовых ящиков, пользователей почты или почтовых контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="036e9-180">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="036e9-181">**Получатель является членом**: указывает одну или несколько групп в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="036e9-181">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="036e9-182">**Домен получателя**: Указывает получателей в одном или нескольких настроенных принятых доменов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="036e9-182">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="036e9-183">После выбора условия в любом из этих поле появится соответствующее **отсев.**</span><span class="sxs-lookup"><span data-stu-id="036e9-183">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="036e9-184">Щелкните в поле и прокрутите список значений для выбора.</span><span class="sxs-lookup"><span data-stu-id="036e9-184">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="036e9-185">Щелкните в поле и начните печатать, чтобы отфильтровать список и выбрать значение.</span><span class="sxs-lookup"><span data-stu-id="036e9-185">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="036e9-186">Чтобы добавить дополнительные значения, щелкните в пустой области в поле.</span><span class="sxs-lookup"><span data-stu-id="036e9-186">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="036e9-187">Чтобы удалить отдельные записи, **нажмите кнопку Удалить** ![ значок Удалить ](../../media/scc-remove-icon.png) значение.</span><span class="sxs-lookup"><span data-stu-id="036e9-187">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="036e9-188">Чтобы удалить все условие, нажмите **кнопку Удалить значок Удалить** ![ в ](../../media/scc-remove-icon.png) состоянии.</span><span class="sxs-lookup"><span data-stu-id="036e9-188">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="036e9-189">Чтобы добавить дополнительное условие, нажмите **кнопку Добавить условие** и выберите оставшееся значение **в applied if**.</span><span class="sxs-lookup"><span data-stu-id="036e9-189">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="036e9-190">Чтобы добавить исключения, нажмите **кнопку Добавить условие** и выберите исключение в соответствии **с исключением, если**.</span><span class="sxs-lookup"><span data-stu-id="036e9-190">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="036e9-191">Настройки и поведение такие же, как в разделе условий.</span><span class="sxs-lookup"><span data-stu-id="036e9-191">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="036e9-192">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="036e9-192">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="036e9-193">На странице **Обзор параметров,** которая отображается, просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="036e9-193">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="036e9-194">Чтобы изменить его, можно нажать **кнопку Изменить** каждый параметр.</span><span class="sxs-lookup"><span data-stu-id="036e9-194">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="036e9-195">Закончив, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="036e9-195">When you're finished, click **Finish**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="036e9-196">Используйте портал Microsoft 365 Defender для просмотра Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-196">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="036e9-197">На портале Microsoft 365 Defender перейдите к политике & **правила** политики \>  \> **угрозы Сейф ссылки**.</span><span class="sxs-lookup"><span data-stu-id="036e9-197">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="036e9-198">На странице **Сейф ссылки** выберите политику из списка и нажмите на нее (не выберите шажок).</span><span class="sxs-lookup"><span data-stu-id="036e9-198">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="036e9-199">Сведения о политике отображаются в вылете</span><span class="sxs-lookup"><span data-stu-id="036e9-199">The policy details appear in a fly out</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="036e9-200">Используйте портал Microsoft 365 Defender для изменения Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-200">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="036e9-201">На портале Microsoft 365 Defender перейдите к \* Политики &**политики** угрозы \>  \> **Сейф ссылки**.</span><span class="sxs-lookup"><span data-stu-id="036e9-201">In the Microsoft 365 Defender portal, go to \***Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="036e9-202">На странице **Сейф ссылки** выберите политику из списка и нажмите на нее (не выберите шажок).</span><span class="sxs-lookup"><span data-stu-id="036e9-202">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="036e9-203">В появились сведения о политике, нажмите **кнопку Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="036e9-203">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="036e9-204">Доступные параметры в вылете идентичны тем, которые описаны на портале Use the Microsoft 365 Defender для создания [Сейф ссылок.](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="036e9-204">The available settings in the fly out that appears are identical to those described in the [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="036e9-205">Чтобы включить или отключить политику или установить порядок приоритета политики, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="036e9-205">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="036e9-206">Включить или отключить Сейф ссылки</span><span class="sxs-lookup"><span data-stu-id="036e9-206">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="036e9-207">На портале Microsoft 365 Defender перейдите к политике & **правила** политики \>  \> **угрозы Сейф ссылки**.</span><span class="sxs-lookup"><span data-stu-id="036e9-207">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="036e9-208">Обратите внимание на значение в **столбце Состояние:**</span><span class="sxs-lookup"><span data-stu-id="036e9-208">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="036e9-209">Чтобы отключить политику, переместите переключатель влево:</span><span class="sxs-lookup"><span data-stu-id="036e9-209">Move the toggle to the left to disable the policy:</span></span> ![Отключение политики](../../media/scc-toggle-off.png)<span data-ttu-id="036e9-211">.</span><span class="sxs-lookup"><span data-stu-id="036e9-211">.</span></span>

   - <span data-ttu-id="036e9-212">Чтобы включить политику, переместите переключатель вправо:</span><span class="sxs-lookup"><span data-stu-id="036e9-212">Move the toggle to the right to enable the policy:</span></span> ![Включаем политику](../../media/scc-toggle-on.png)<span data-ttu-id="036e9-214">.</span><span class="sxs-lookup"><span data-stu-id="036e9-214">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="036e9-215">Установите приоритет политик Сейф ссылки</span><span class="sxs-lookup"><span data-stu-id="036e9-215">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="036e9-216">По умолчанию политикам Сейф ссылки дается приоритет, основанный на порядке, в который они были созданы (более новые политики имеют более низкий приоритет по сравнению с более старыми политиками).</span><span class="sxs-lookup"><span data-stu-id="036e9-216">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="036e9-217">Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом).</span><span class="sxs-lookup"><span data-stu-id="036e9-217">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="036e9-218">Никакие две политики не могут иметь одинаковый приоритет, и обработка политики прекращается после применения первой политики.</span><span class="sxs-lookup"><span data-stu-id="036e9-218">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="036e9-219">Дополнительные сведения о приоритетах, а также оценке и применении нескольких политик см. в статье [Порядок и приоритет защиты электронной почты](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="036e9-219">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="036e9-220">Сейф Политики ссылок отображаются в порядке их обработки (первая политика имеет значение **Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="036e9-220">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="036e9-221">На портале Microsoft 365 Defender можно изменить приоритет политики Сейф ссылок после ее создания.</span><span class="sxs-lookup"><span data-stu-id="036e9-221">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="036e9-222">В PowerShell можно переопредить приоритет по умолчанию при создании правила безопасных ссылок (которое может повлиять на приоритет существующих правил).</span><span class="sxs-lookup"><span data-stu-id="036e9-222">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="036e9-223">Чтобы изменить приоритет политики, переместийте политику вверх или вниз в списке (вы не можете напрямую изменить номер **Priority** на портале Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="036e9-223">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span>

1. <span data-ttu-id="036e9-224">На портале Microsoft 365 Defender перейдите к политике & **правила** политики \>  \> **угрозы Сейф ссылки**.</span><span class="sxs-lookup"><span data-stu-id="036e9-224">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="036e9-225">На странице **Сейф ссылки** выберите политику из списка и нажмите на нее (не выберите шажок).</span><span class="sxs-lookup"><span data-stu-id="036e9-225">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="036e9-226">В появились сведения о политике, щелкните доступную кнопку приоритета:</span><span class="sxs-lookup"><span data-stu-id="036e9-226">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="036e9-227">Политика Сейф ссылок с **значением Приоритет** **0** имеет только доступную кнопку **Приоритет уменьшения.**</span><span class="sxs-lookup"><span data-stu-id="036e9-227">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="036e9-228">Политика Сейф ссылок с наименьшим значением Приоритет (например, **3)** имеет только доступную кнопку  **Увеличение** приоритета.</span><span class="sxs-lookup"><span data-stu-id="036e9-228">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="036e9-229">Если у вас есть три или более Сейф политик ссылок, политики между самыми  высокими  и самыми низкими значениями приоритетов имеют доступные кнопки "Увеличение приоритета" и "Уменьшение приоритетов".</span><span class="sxs-lookup"><span data-stu-id="036e9-229">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="036e9-230">Щелкните **Увеличить приоритет или** уменьшить **приоритет,** чтобы изменить **значение Priority.**</span><span class="sxs-lookup"><span data-stu-id="036e9-230">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="036e9-231">Когда закончите, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="036e9-231">When you're finished, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="036e9-232">Использование портала Microsoft 365 Defender для удаления Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-232">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="036e9-233">На портале Microsoft 365 Defender перейдите к политике & **правила** политики \>  \> **угрозы Сейф ссылки**.</span><span class="sxs-lookup"><span data-stu-id="036e9-233">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="036e9-234">На странице **Сейф ссылки** выберите политику из списка и нажмите на нее (не выберите шажок).</span><span class="sxs-lookup"><span data-stu-id="036e9-234">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="036e9-235">В появились сведения о политике, нажмите кнопку **Удалить** политику, а затем нажмите **кнопку Да** в диалоговом окте предупреждения, который появится.</span><span class="sxs-lookup"><span data-stu-id="036e9-235">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="036e9-236">Для настройки Сейф ссылок используйте Exchange Online PowerShell или автономный EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="036e9-236">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="036e9-237">Как описано выше, политика Сейф ссылок состоит из политики безопасных ссылок и правила безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-237">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="036e9-238">В PowerShell очевидна разница между политиками безопасных ссылок и правилами безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-238">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="036e9-239">Вы управляете политиками безопасных ссылок с помощью **\* кодлетов -SafeLinksPolicy** и управляете правилами безопасных ссылок с помощью **\* cmdlets-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="036e9-239">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="036e9-240">В PowerShell сначала создается политика безопасных ссылок, а затем создается правило безопасных ссылок, которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="036e9-240">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="036e9-241">В PowerShell параметры политики безопасных ссылок и правила безопасных ссылок изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="036e9-241">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="036e9-242">При удалении политики безопасных ссылок из PowerShell соответствующее правило безопасных ссылок не удаляется автоматически, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="036e9-242">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="036e9-243">Использование PowerShell для создания Сейф ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-243">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="036e9-244">Создание политики Сейф ссылок в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="036e9-244">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="036e9-245">Создание политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-245">Create the safe links policy.</span></span>
2. <span data-ttu-id="036e9-246">Создайте правило безопасных ссылок, которое указывает политику безопасных ссылок, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="036e9-246">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="036e9-247">Можно создать новое правило безопасных ссылок и назначить к ней существующую политику безопасных ссылок без связи.</span><span class="sxs-lookup"><span data-stu-id="036e9-247">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="036e9-248">Правило безопасных ссылок не может быть связано с более чем одной политикой безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-248">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="036e9-249">Вы можете настроить следующие параметры для новых политик безопасных ссылок в PowerShell, недоступных на портале Microsoft 365 Defender до создания политики:</span><span class="sxs-lookup"><span data-stu-id="036e9-249">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="036e9-250">Создайте новую политику как отключенную _(включена_ `$false` в **комлете New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="036e9-250">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="036e9-251">Задай приоритет политики во время создания _(priority)_ в _\<Number\>_ **комлете New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="036e9-251">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="036e9-252">Новая политика безопасных ссылок, которую вы создаете в PowerShell, не отображается на портале Microsoft 365 Defender, пока не назначите политику правилу безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-252">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="036e9-253">Шаг 1. Использование PowerShell для создания политики безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-253">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="036e9-254">Чтобы создать политику безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-254">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="036e9-255">Подробные сведения о синтаксисе записи, используемом для параметра _DoNotRewriteUrls,_ см. в материале Запись синтаксиса для списка "Не переписывай следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="036e9-255">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="036e9-256">Дополнительный синтаксис, который можно использовать для параметра _DoNotRewriteUrls_ при изменении существующих политик безопасных ссылок с помощью комлета **Set-SafeLinksPolicy,** см. в разделе [Использование PowerShell](#use-powershell-to-modify-safe-links-policies) для изменения политик безопасных ссылок в этой статье.</span><span class="sxs-lookup"><span data-stu-id="036e9-256">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="036e9-257">В этом примере создается политика безопасных ссылок с именем Contoso All со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="036e9-257">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="036e9-258">Включайте сканирование URL-адресов и переписывание в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="036e9-258">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="036e9-259">Включив сканирование URL Teams в режиме Teams (только для предварительного просмотра TAP).</span><span class="sxs-lookup"><span data-stu-id="036e9-259">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="036e9-260">Включайте сканирование url-адресов в режиме реального времени, в том числе щелкнув ссылки, которые указывают на файлы.</span><span class="sxs-lookup"><span data-stu-id="036e9-260">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="036e9-261">Дождись завершения сканирования URL-адресов перед доставкой сообщения.</span><span class="sxs-lookup"><span data-stu-id="036e9-261">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="036e9-262">Включи сканирование URL-адресов и переописывание внутренних сообщений.</span><span class="sxs-lookup"><span data-stu-id="036e9-262">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="036e9-263">Отслеживайте щелчки пользователей, связанные с защитой Сейф ссылок (мы не используем параметр _DoNotTrackUserClicks,_ а значение по умолчанию $false, что означает отслеживание кликов пользователей).</span><span class="sxs-lookup"><span data-stu-id="036e9-263">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="036e9-264">Не позволяйте пользователям щелкнуть исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="036e9-264">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="036e9-265">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SafeLinksPolicy.](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="036e9-265">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="036e9-266">Шаг 2. Использование PowerShell для создания правила безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-266">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="036e9-267">Чтобы создать правило безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-267">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="036e9-268">В этом примере создается правило безопасных ссылок с именем Contoso All со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="036e9-268">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="036e9-269">Правило связано с политикой безопасных ссылок с именем Contoso All.</span><span class="sxs-lookup"><span data-stu-id="036e9-269">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="036e9-270">Правило применяется ко всем получателям в contoso.com домене.</span><span class="sxs-lookup"><span data-stu-id="036e9-270">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="036e9-271">Так как мы не используем параметр _Priority,_ используется приоритет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="036e9-271">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="036e9-272">Правило включено (мы не используем параметр _Включен,_ а значение по `$true` умолчанию).</span><span class="sxs-lookup"><span data-stu-id="036e9-272">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="036e9-273">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SafeLinksRule.](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="036e9-273">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="036e9-274">Использование PowerShell для просмотра политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-274">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="036e9-275">Чтобы просмотреть существующие политики безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-275">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="036e9-276">В этом примере возвращается сводный список всех политик безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-276">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="036e9-277">В этом примере возвращаются подробные сведения о политике безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="036e9-277">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="036e9-278">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SafeLinksPolicy.](/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="036e9-278">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="036e9-279">Использование PowerShell для просмотра правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-279">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="036e9-280">Чтобы просмотреть существующие правила безопасных ссылок, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-280">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="036e9-281">В этом примере возвращается сводный список всех правил безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="036e9-281">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="036e9-282">Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="036e9-282">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="036e9-283">В этом примере возвращается подробная информация для правила безопасных ссылок с именем Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="036e9-283">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="036e9-284">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SafeLinksRule.](/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="036e9-284">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="036e9-285">Использование PowerShell для изменения политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-285">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="036e9-286">В PowerShell нельзя переименовать политику безопасных ссылок (в **комлете Set-SafeLinksPolicy** нет _параметра Name)._</span><span class="sxs-lookup"><span data-stu-id="036e9-286">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="036e9-287">При переименовании политики Сейф ссылок на портале Microsoft 365 Defender можно переименовать только правило безопасных _ссылок._</span><span class="sxs-lookup"><span data-stu-id="036e9-287">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="036e9-288">Единственным дополнительным фактором для изменения политик безопасных ссылок в PowerShell является доступный синтаксис для параметра _DoNotRewriteUrls_ (список "Не переписать следующие [URL-адреса"):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="036e9-288">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="036e9-289">Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="036e9-289">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="036e9-290">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="036e9-290">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="036e9-291">В противном случае те же параметры доступны при создании политики безопасных ссылок, как описано в шаге [1: Использование PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) для создания раздела политики безопасных ссылок ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="036e9-291">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="036e9-292">Чтобы изменить политику безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-292">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="036e9-293">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksPolicy.](/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="036e9-293">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="036e9-294">Использование PowerShell для изменения правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-294">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="036e9-295">Единственным параметром, недоступным при изменении правила безопасных ссылок  в PowerShell, является параметр Включен, который позволяет создать правило отключения.</span><span class="sxs-lookup"><span data-stu-id="036e9-295">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="036e9-296">Чтобы включить или отключить существующие правила безопасных ссылок, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="036e9-296">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="036e9-297">В противном случае те же параметры доступны при создании правила, описанного в шаге [2: Использование PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) для создания раздела правила безопасных ссылок в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="036e9-297">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="036e9-298">Чтобы изменить правило безопасных ссылок, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-298">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="036e9-299">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="036e9-299">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="036e9-300">Использование PowerShell для включения или отключения правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-300">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="036e9-301">Включение или отключение правила безопасных ссылок в PowerShell включает или отключает всю политику Сейф ссылок (правило безопасных ссылок и назначенную политику безопасных ссылок).</span><span class="sxs-lookup"><span data-stu-id="036e9-301">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="036e9-302">Чтобы включить или отключить правило безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-302">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="036e9-303">В этом примере отключает правило безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="036e9-303">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="036e9-304">В этом примере включается то же правило.</span><span class="sxs-lookup"><span data-stu-id="036e9-304">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="036e9-305">Подробные сведения о синтаксисах и параметрах см. в [рублях Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) и [Disable-SafeLinksRule.](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="036e9-305">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="036e9-306">Используйте PowerShell, чтобы установить приоритет правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-306">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="036e9-p123">Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0-4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="036e9-p123">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="036e9-312">Чтобы установить приоритет правила безопасных ссылок в PowerShell, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-312">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="036e9-p124">В этом примере для правила Marketing Department задается приоритет 2. Все правила с приоритетом не больше 2 понижаются на один ранг (значения приоритета увеличиваются на 1).</span><span class="sxs-lookup"><span data-stu-id="036e9-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="036e9-315">Чтобы установить приоритет нового правила при его создании, используйте параметр _Priority_ в **комлете New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="036e9-315">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="036e9-316">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="036e9-316">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="036e9-317">Использование PowerShell для удаления политик безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-317">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="036e9-318">При удалении политики безопасных ссылок с помощью PowerShell соответствующее правило безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="036e9-318">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="036e9-319">Чтобы удалить политику безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-319">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="036e9-320">В этом примере удаляется политика безопасных ссылок с именем Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="036e9-320">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="036e9-321">Подробные сведения о синтаксисах и параметрах см. в этой ссылке [Remove-SafeLinksPolicy.](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="036e9-321">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="036e9-322">Использование PowerShell для удаления правил безопасных ссылок</span><span class="sxs-lookup"><span data-stu-id="036e9-322">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="036e9-323">При удалении правила безопасных ссылок с помощью PowerShell соответствующая политика безопасных ссылок не удаляется.</span><span class="sxs-lookup"><span data-stu-id="036e9-323">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="036e9-324">Чтобы удалить правило безопасных ссылок в PowerShell, используйте этот синтаксис:</span><span class="sxs-lookup"><span data-stu-id="036e9-324">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="036e9-325">В этом примере удаляется правило безопасных ссылок с именем Отдел маркетинга.</span><span class="sxs-lookup"><span data-stu-id="036e9-325">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="036e9-326">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-SafeLinksRule.](/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="036e9-326">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="036e9-327">Чтобы убедиться, Сейф ссылки — это сканирование сообщений, проверьте доступные microsoft Defender для Office 365 отчетов.</span><span class="sxs-lookup"><span data-stu-id="036e9-327">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="036e9-328">Дополнительные сведения см. в [обзоре](view-reports-for-mdo.md) отчетов defender for Office 365 и Use Explorer на [портале Microsoft 365 Defender.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="036e9-328">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="036e9-329">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="036e9-329">How do you know these procedures worked?</span></span>

<span data-ttu-id="036e9-330">Чтобы убедиться, что вы успешно создали, изменили или удалили Сейф ссылки, сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="036e9-330">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="036e9-331">На портале Microsoft 365 Defender перейдите к **политикам & правила политики** \>  \> **угрозы Сейф ссылки**.</span><span class="sxs-lookup"><span data-stu-id="036e9-331">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="036e9-332">Проверка списка политик, их значений **состояния** и **их значений приоритета.**</span><span class="sxs-lookup"><span data-stu-id="036e9-332">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="036e9-333">Чтобы просмотреть дополнительные сведения, выберите политику из списка и просмотреть сведения в поле вылета.</span><span class="sxs-lookup"><span data-stu-id="036e9-333">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="036e9-334">В Exchange Online PowerShell или Exchange Online Protection PowerShell замените имя политики или правила, запустите следующую команду и проверьте \<Name\> параметры:</span><span class="sxs-lookup"><span data-stu-id="036e9-334">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```