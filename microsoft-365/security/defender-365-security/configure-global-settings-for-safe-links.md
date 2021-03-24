---
title: Настройка глобальных параметров для параметров безопасных ссылок в Defender для Office 365
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как просматривать и настраивать глобальные параметры (список "Блокировка следующих URL-адресов" и защита приложений Office 365) для безопасных ссылок в Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 390177a24648cf860a78ab831d5dfe334b2c9590
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073421"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="03807-103">Настройка глобальных параметров безопасных ссылок в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="03807-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="03807-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="03807-104">**Applies to**</span></span>
- [<span data-ttu-id="03807-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="03807-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="03807-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03807-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="03807-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="03807-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="03807-108">Если вы домашний пользователь, который ищет сведения о Safelinks в Outlook, см. в Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="03807-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="03807-109">Безопасные ссылки — это функция [в Microsoft Defender для Office 365,](defender-for-office-365.md) которая обеспечивает сканирование URL-адресов входящие сообщения электронной почты в потоке почты, а также время проверки URL-адресов и ссылок в сообщениях электронной почты и в других местах.</span><span class="sxs-lookup"><span data-stu-id="03807-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="03807-110">Дополнительные сведения см. в [веб-сайте Безопасные ссылки в Microsoft Defender для Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="03807-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="03807-111">Большинство параметров безопасных ссылок настраиваются в политиках безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="03807-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="03807-112">Инструкции см. в инструкции Настройка политик безопасных ссылок [в Microsoft Defender для Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="03807-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="03807-113">Но безопасные ссылки также используют глобальные параметры, применимые к всем пользователям, включенным в любые активные политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="03807-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="03807-114">Эти глобальные области параметров:</span><span class="sxs-lookup"><span data-stu-id="03807-114">These global settings area:</span></span>

- <span data-ttu-id="03807-115">Блок **следующий список URL-адресов.**</span><span class="sxs-lookup"><span data-stu-id="03807-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="03807-116">Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="03807-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="03807-117">Защита безопасных ссылок для приложений Office 365.</span><span class="sxs-lookup"><span data-stu-id="03807-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="03807-118">Дополнительные сведения см. в [настройках безопасных ссылок для приложений Office 365.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="03807-118">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="03807-119">Вы можете настроить глобальные параметры безопасных ссылок в Центре обеспечения безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с помощью надстройки Microsoft Defender для Office 365).</span><span class="sxs-lookup"><span data-stu-id="03807-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="03807-120">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="03807-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="03807-121">Функции, предоставляемые глобальными настройками безопасных ссылок, применяются только к пользователям, включенным в активные политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="03807-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="03807-122">Существует не встроенная или по умолчанию политика безопасных ссылок, поэтому необходимо создать по крайней мере одну политику безопасных ссылок, чтобы эти глобальные параметры были активными.</span><span class="sxs-lookup"><span data-stu-id="03807-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="03807-123">Инструкции см. в инструкции Настройка политик безопасных ссылок [в Microsoft Defender для Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="03807-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="03807-124">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="03807-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="03807-125">Чтобы перейти непосредственно на страницу **Безопасные ссылки,** используйте <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="03807-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="03807-126">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="03807-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="03807-127">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="03807-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="03807-128">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="03807-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="03807-129">Чтобы настроить глобальные параметры безопасных ссылок, необходимо быть членом группы ролей **администратора** организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="03807-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="03807-130">Для доступа только для чтения к глобальным настройкам безопасных ссылок необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="03807-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="03807-131">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="03807-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="03807-132">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="03807-132">**Notes**:</span></span>

  - <span data-ttu-id="03807-133">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03807-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="03807-134">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="03807-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="03807-135">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="03807-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="03807-136">Рекомендуемые значения для глобальных параметров безопасных ссылок см. в этой [ссылке.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="03807-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="03807-137">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="03807-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="03807-138">[Новые функции постоянно добавляются в Microsoft Defender для Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="03807-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="03807-139">При добавлении новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="03807-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="03807-140">Настройка списка "Блокировка следующих URL-адресов" в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="03807-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="03807-141">В **следующем списке URL-адресов** заблокированы ссылки, которые всегда должны быть заблокированы при сканировании безопасных ссылок в поддерживаемых приложениях.</span><span class="sxs-lookup"><span data-stu-id="03807-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="03807-142">Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок.](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="03807-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="03807-143">В Центре обеспечения & безопасности перейдите  к политике управления угрозами \>  \> **ATP Safe Links,** а затем щелкните **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="03807-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="03807-144">В политике **безопасных ссылок для организации** вылет, который отображается, перейдите к **блоку следующего URL-адреса.**</span><span class="sxs-lookup"><span data-stu-id="03807-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="03807-145">Настройте одну или несколько записей, как описано в синтаксис Записи, для списка "Блокировать следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="03807-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="03807-146">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="03807-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="03807-147">Настройка списка "Блокировка следующих URL-адресов" в PowerShell</span><span class="sxs-lookup"><span data-stu-id="03807-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="03807-148">Подробные сведения о синтаксисе записи см. в [синтаксис Записи в списке "Заблокировать следующие URL-адреса".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="03807-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="03807-149">Для просмотра существующих записей в свойстве _BlockURLs_ можно использовать **кодлет Get-AtpPolicyForO365.**</span><span class="sxs-lookup"><span data-stu-id="03807-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="03807-150">Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03807-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="03807-151">В этом примере в список добавляются следующие записи:</span><span class="sxs-lookup"><span data-stu-id="03807-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="03807-152">Блокировка домена, поддоменов и путей для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="03807-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="03807-153">Заблокируют исследование subdomain, но не родительский домен или другие поддомены в tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="03807-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="03807-154">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="03807-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="03807-155">В этом примере добавляется новая запись для adatum.com и удаляется запись для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="03807-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="03807-156">Настройка защиты безопасных ссылок для приложений Office 365 в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="03807-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="03807-157">Защита безопасных ссылок для приложений Office 365 применяется к документам в поддерживаемых настольных, мобильных и веб-приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="03807-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="03807-158">Дополнительные сведения см. в [настройках безопасных ссылок для приложений Office 365.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="03807-158">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="03807-159">В Центре обеспечения & безопасности перейдите  к политике управления угрозами \>  \> **ATP Safe Links,** а затем щелкните **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="03807-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="03807-160">В политике **безопасных ссылок** для организации, которая появится, настройте следующие параметры в разделе Параметры, применимые к контенту, за исключением раздела **электронной** почты:</span><span class="sxs-lookup"><span data-stu-id="03807-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="03807-161">**Приложения Office 365.** Убедитесь, что перегной является правом, чтобы включить безопасные ссылки для поддерживаемых приложений Office 365. ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="03807-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="03807-162">Не отслеживайте, когда пользователи щелкают "Безопасные ссылки" **(Safe Links:** Move the toggle to the left to track user clicks related to blocked URLs) in supported Office 365 apps: ![ Toggle ](../../media/scc-toggle-off.png) off.</span><span class="sxs-lookup"><span data-stu-id="03807-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="03807-163">**Не позволяйте** пользователям щелкнуть "Безопасные ссылки" на исходный URL-адрес: Убедитесь, что перегородка справа, чтобы пользователи не щелкнули исходный заблокированный URL-адрес в поддерживаемых приложениях Office 365: ![ Toggle on ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="03807-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="03807-164">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="03807-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="03807-165">Настройка защиты безопасных ссылок для приложений Office 365 в PowerShell</span><span class="sxs-lookup"><span data-stu-id="03807-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="03807-166">Если вы хотите использовать PowerShell для настройки защиты безопасных ссылок для приложений Office 365, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03807-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="03807-167">В этом примере настраиваются следующие параметры защиты безопасных ссылок в приложениях Office 365:</span><span class="sxs-lookup"><span data-stu-id="03807-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="03807-168">Включена безопасная связь для приложений Office 365 (мы не используем параметр _EnableSafeLinksForO365Clients,_ а значение по умолчанию $true).</span><span class="sxs-lookup"><span data-stu-id="03807-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="03807-169">Отслеживаются клики пользователей, связанные с заблокированными URL-адресами в поддерживаемых приложениях Office 365.</span><span class="sxs-lookup"><span data-stu-id="03807-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="03807-170">Пользователям не разрешается щелкнуть исходный заблокированный URL-адрес в поддерживаемых приложениях Office 365 (мы не используем параметр _AllowClickThrough,_ а значение по умолчанию $false).</span><span class="sxs-lookup"><span data-stu-id="03807-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="03807-171">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="03807-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="03807-172">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="03807-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="03807-173">Чтобы убедиться, что вы успешно настроили глобальные  параметры безопасных ссылок (блокировать следующий список URL-адресов и параметры защиты приложений Office 365), необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="03807-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="03807-174">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links,** щелкните Глобальные параметры и проверьте параметры в вылете, который появляется.</span><span class="sxs-lookup"><span data-stu-id="03807-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="03807-175">В Exchange Online PowerShell или Exchange Online Protection PowerShell запустите следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="03807-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="03807-176">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="03807-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>