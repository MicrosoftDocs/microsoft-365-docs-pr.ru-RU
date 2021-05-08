---
title: Настройка глобальных параметров для параметров Сейф ссылок в Defender для Office 365
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
description: Администраторы могут узнать, как просматривать и настраивать глобальные параметры (список "Блокировка следующих URL-адресов" и защита для Office 365 приложений) для Сейф ссылок в Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11544953bf348c47e697b3210da709cccdb31a7e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245844"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1be16-103">Настройка глобальных параметров для Сейф ссылок в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="1be16-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1be16-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="1be16-104">**Applies to**</span></span>
- [<span data-ttu-id="1be16-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="1be16-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1be16-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1be16-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="1be16-107">Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1be16-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="1be16-108">Если вы домашний пользователь, который ищет сведения о Safelinks в Outlook, см. в [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="1be16-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="1be16-109">Сейф Ссылки — это функция в Microsoft Defender для Office 365, которая обеспечивает сканирование [URL-адресов](defender-for-office-365.md) входящие сообщения электронной почты в потоке почты, а также время проверки URL-адресов и ссылок в сообщениях электронной почты и в других местах.</span><span class="sxs-lookup"><span data-stu-id="1be16-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="1be16-110">Дополнительные сведения см. [в Сейф Ссылки в Microsoft Defender для Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="1be16-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="1be16-111">Большинство параметров Сейф ссылок в Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="1be16-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="1be16-112">Инструкции см. в Сейф ссылки в [Microsoft Defender для Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1be16-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="1be16-113">Но Сейф ссылки также используют следующие глобальные параметры, которые вы настраиваете за пределами самих политик Сейф ссылки:</span><span class="sxs-lookup"><span data-stu-id="1be16-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="1be16-114">Блок **следующий список URL-адресов.**</span><span class="sxs-lookup"><span data-stu-id="1be16-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="1be16-115">Этот параметр применяется ко всем пользователям, включенным в активные политики Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="1be16-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="1be16-116">Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов"](safe-links.md#block-the-following-urls-list-for-safe-links) для Сейф ссылки</span><span class="sxs-lookup"><span data-stu-id="1be16-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="1be16-117">Сейф Защита ссылок для Office 365 приложений.</span><span class="sxs-lookup"><span data-stu-id="1be16-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="1be16-118">Эти параметры применяются для всех пользователей в организации, которые имеют лицензию на defender для Office 365, независимо от того, включены ли пользователи в активные политики Сейф ссылки или нет.</span><span class="sxs-lookup"><span data-stu-id="1be16-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="1be16-119">Дополнительные сведения см. [в Сейф ссылки для Office 365 приложений.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="1be16-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="1be16-120">Можно настроить параметры глобальных ссылок Сейф в Центре обеспечения безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для подходящих Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономных EOP PowerShell для организаций без Exchange Online почтовых ящиков, но с Microsoft Defender для Office 365 надстройки).</span><span class="sxs-lookup"><span data-stu-id="1be16-120">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1be16-121">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="1be16-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1be16-122">Политика встроенных или Сейф ссылок по умолчанию не существует, поэтому для активной блокировки следующего  списка URL-адресов необходимо создать по крайней мере одну политику Сейф links.</span><span class="sxs-lookup"><span data-stu-id="1be16-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="1be16-123">Инструкции см. в Сейф ссылки в [Microsoft Defender для Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1be16-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="1be16-124">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1be16-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1be16-125">Чтобы перейти непосредственно **на страницу Сейф ссылки,** используйте <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="1be16-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="1be16-126">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1be16-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1be16-127">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1be16-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1be16-128">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="1be16-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1be16-129">Чтобы настроить глобальные параметры для Сейф ссылок, необходимо быть членом  группы ролей администратора организации или **администратора** безопасности.</span><span class="sxs-lookup"><span data-stu-id="1be16-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="1be16-130">Для доступа только для чтения к глобальным настройкам для Сейф ссылок необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="1be16-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="1be16-131">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="1be16-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="1be16-132">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="1be16-132">**Notes**:</span></span>

  - <span data-ttu-id="1be16-133">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1be16-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1be16-134">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1be16-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="1be16-135">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="1be16-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="1be16-136">Рекомендуемые значения для глобальных параметров для Сейф ссылки см. в Сейф [Ссылки.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="1be16-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="1be16-137">Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.</span><span class="sxs-lookup"><span data-stu-id="1be16-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="1be16-138">[Новые функции постоянно добавляются в Microsoft Defender для](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 .</span><span class="sxs-lookup"><span data-stu-id="1be16-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="1be16-139">При добавлении новых функций может потребоваться внести изменения в существующие политики Сейф ссылки.</span><span class="sxs-lookup"><span data-stu-id="1be16-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="1be16-140">Настройка списка "Блокировка следующих URL-адресов" в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="1be16-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="1be16-141">В **списке Блок следующих** URL-адресов указаны ссылки, которые всегда должны быть заблокированы с помощью Сейф ссылок в поддерживаемых приложениях.</span><span class="sxs-lookup"><span data-stu-id="1be16-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="1be16-142">Дополнительные сведения см. в [списке "Блокировать следующие URL-адреса" для Сейф ссылки.](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="1be16-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="1be16-143">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Сейф ссылки,** а затем нажмите **параметры Global**.</span><span class="sxs-lookup"><span data-stu-id="1be16-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="1be16-144">В политике **Сейф ссылки** для организации вылет, который отображается, перейдите к **блоку следующего URL-адреса.**</span><span class="sxs-lookup"><span data-stu-id="1be16-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="1be16-145">Настройте одну или несколько записей, как описано в синтаксис Записи, для списка "Блокировать следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="1be16-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="1be16-146">Когда закончите, нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1be16-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="1be16-147">Настройка списка "Блокировка следующих URL-адресов" в PowerShell</span><span class="sxs-lookup"><span data-stu-id="1be16-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="1be16-148">Подробные сведения о синтаксисе записи см. в [синтаксис Записи в списке "Заблокировать следующие URL-адреса".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="1be16-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="1be16-149">Для просмотра существующих записей в свойстве _BlockURLs_ можно использовать **кодлет Get-AtpPolicyForO365.**</span><span class="sxs-lookup"><span data-stu-id="1be16-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="1be16-150">Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1be16-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="1be16-151">В этом примере в список добавляются следующие записи:</span><span class="sxs-lookup"><span data-stu-id="1be16-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="1be16-152">Блокировка домена, поддоменов и путей для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1be16-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="1be16-153">Заблокируют исследование subdomain, но не родительский домен или другие поддомены в tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="1be16-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="1be16-154">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1be16-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="1be16-155">В этом примере добавляется новая запись для adatum.com и удаляется запись для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1be16-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="1be16-156">Настройка Сейф ссылок для Office 365 приложений в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="1be16-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="1be16-157">Сейф Защита ссылок для Office 365 приложений применяется к документам в поддерживаемых Office, мобильных и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="1be16-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="1be16-158">Дополнительные сведения см. [в Сейф ссылки для Office 365 приложений.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="1be16-158">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="1be16-159">В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Сейф ссылки,** а затем нажмите **параметры Global**.</span><span class="sxs-lookup"><span data-stu-id="1be16-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="1be16-160">В политике **Сейф ссылки** для организации вылет, который появляется, настройте следующие параметры в Параметры, которые применяются к контенту, за исключением раздела **электронной** почты:</span><span class="sxs-lookup"><span data-stu-id="1be16-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="1be16-161">**Office 365** приложений: Убедитесь, что перегной является правом, чтобы включить ссылки Сейф для поддерживаемых Office 365 приложений: ![ торгуться ](../../media/scc-toggle-on.png) на .</span><span class="sxs-lookup"><span data-stu-id="1be16-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="1be16-162">**Не отслеживайте,** когда пользователи щелкают Сейф ссылки: переместите переключение влево для отслеживания щелчков пользователей, связанных с заблокированными URL-адресами в поддерживаемых Office 365 ![ приложениях. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="1be16-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="1be16-163">Не позволяйте пользователям щелкнуть **Сейф** ссылки на исходный URL-адрес: Убедитесь, что перегородка находится справа, чтобы пользователи не щелкнули исходный заблокированный URL-адрес в поддерживаемых Office 365 приложениях: ![ Toggle on ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="1be16-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="1be16-164">Когда закончите, нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1be16-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="1be16-165">Настройка Сейф ссылок для Office 365 приложений в PowerShell</span><span class="sxs-lookup"><span data-stu-id="1be16-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="1be16-166">Если вы хотите использовать PowerShell для настройки защиты Сейф ссылок для Office 365 приложений, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1be16-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="1be16-167">В этом примере настраиваются следующие параметры защиты Сейф ссылок в Office 365 приложениях:</span><span class="sxs-lookup"><span data-stu-id="1be16-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="1be16-168">Сейф Включена ссылка Office 365 приложений (мы не используем параметр _EnableSafeLinksForO365Clients,_ и значение по умолчанию $true).</span><span class="sxs-lookup"><span data-stu-id="1be16-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="1be16-169">Клики пользователей, связанные с заблокированными URL-адресами в поддерживаемых Office 365 отслеживаются.</span><span class="sxs-lookup"><span data-stu-id="1be16-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="1be16-170">Пользователям не разрешается щелкнуть исходный заблокированный URL-адрес в поддерживаемых Office 365 приложениях (мы не используем параметр _AllowClickThrough,_ а значение по умолчанию $false).</span><span class="sxs-lookup"><span data-stu-id="1be16-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="1be16-171">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="1be16-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1be16-172">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="1be16-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="1be16-173">Чтобы убедиться, что вы успешно настроены глобальные параметры для  ссылок Сейф (блок следующий список URL-адресов и параметры защиты Office 365 приложения), сделайте все следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1be16-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="1be16-174">В Центре & безопасности перейдите в  центр политики управления угрозами \>  \> **ATP Сейф Ссылки,** щелкните глобальные параметры и проверьте параметры в вылете, который появляется.</span><span class="sxs-lookup"><span data-stu-id="1be16-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="1be16-175">В Exchange Online PowerShell или Exchange Online Protection PowerShell запустите следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="1be16-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="1be16-176">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="1be16-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
