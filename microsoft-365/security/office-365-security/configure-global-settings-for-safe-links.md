---
title: Настройка глобальных параметров для параметров безопасных ссылок в Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как просматривать и настраивать глобальные параметры (список "блокировать следующие URL-адреса" и "Защита для приложений Office 365") для безопасных ссылок в Office 365 Advanced Threat protection (ATP).
ms.openlocfilehash: 6ca18bfb555419a8f4a61b55715f328ed7da5e88
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328565"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a><span data-ttu-id="57db5-103">Настройка глобальных параметров для безопасных ссылок в Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="57db5-103">Configure global settings for Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="57db5-104">Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="57db5-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="57db5-105">Если вы являетесь домашним пользователем, который ищет сведения о Сафелинкс в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="57db5-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="57db5-106">"Безопасные ссылки" это функция в [Office 365 Advanced Threat protection (ATP)](office-365-atp.md) , которая обеспечивает сканирование URL-адресов входящих сообщений электронной почты в почтовом ящике и время нажатия проверки URL-адресов и ссылок в сообщениях электронной почты и других расположениях.</span><span class="sxs-lookup"><span data-stu-id="57db5-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="57db5-107">Дополнительные сведения см в статье [безопасные ссылки в Office 365 ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="57db5-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="57db5-108">Большинство параметров безопасных ссылок настраиваются в политиках безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="57db5-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="57db5-109">Инструкции приведены в разделе [Настройка политик безопасных ссылок в Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57db5-109">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="57db5-110">Однако безопасные ссылки также используют глобальные параметры, которые применяются ко всем пользователям, включенным в активные политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="57db5-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="57db5-111">Область глобальных параметров:</span><span class="sxs-lookup"><span data-stu-id="57db5-111">These global settings area:</span></span>

- <span data-ttu-id="57db5-112">**Заблокируйте следующий список URL-адресов** .</span><span class="sxs-lookup"><span data-stu-id="57db5-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="57db5-113">Для получения дополнительных сведений см. [список "Блокировка следующих URL-адресов" для безопасных ссылок](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="57db5-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="57db5-114">Защита безопасных ссылок для приложений Office 365.</span><span class="sxs-lookup"><span data-stu-id="57db5-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="57db5-115">Дополнительные сведения приведены в разделе [Параметры безопасных ссылок для приложений Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="57db5-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="57db5-116">Параметры глобальных безопасных ссылок можно настроить в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для подходящих организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономная оболочка EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с подписками на надстройки Office 365 для Office).</span><span class="sxs-lookup"><span data-stu-id="57db5-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="57db5-117">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="57db5-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="57db5-118">Функции, предоставляемые глобальными параметрами для безопасных ссылок, применяются только к пользователям, включенным в активные политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="57db5-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="57db5-119">Встроенной политики или безопасной ссылки по умолчанию нет, поэтому необходимо создать хотя бы одну политику безопасных ссылок, чтобы активировать эти глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="57db5-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="57db5-120">Инструкции приведены в разделе [Настройка политик безопасных ссылок в Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57db5-120">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="57db5-121">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="57db5-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="57db5-122">Чтобы перейти непосредственно на страницу " **безопасные ссылки" ATP** , используйте <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="57db5-122">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="57db5-123">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="57db5-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="57db5-124">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="57db5-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="57db5-125">Чтобы просмотреть и настроить глобальные параметры для безопасных ссылок, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="57db5-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="57db5-126">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="57db5-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="57db5-127">**Управление организацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="57db5-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="57db5-128">Для наших рекомендуемых значений глобальных параметров для безопасных ссылок в разделе [Параметры](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="57db5-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="57db5-129">Разрешить применение новой или обновленной политики до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="57db5-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="57db5-130">[Новые функции постоянно добавляются в ATP](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="57db5-130">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="57db5-131">По мере добавления новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.</span><span class="sxs-lookup"><span data-stu-id="57db5-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="57db5-132">Настройте список "блокировать следующие URL-адреса" в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="57db5-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="57db5-133">В списке **блокировать следующие URL-адреса** указываются ссылки, которые должны всегда блокироваться с помощью поиска безопасных ссылок в поддерживаемых приложениях.</span><span class="sxs-lookup"><span data-stu-id="57db5-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="57db5-134">Для получения дополнительных сведений см. [список "Блокировка следующих URL-адресов" для безопасных ссылок](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="57db5-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="57db5-135">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**и выберите **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="57db5-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="57db5-136">Когда откроется **Политика безопасных ссылок** , перейдите к полю **блокировать следующие URL-адреса** .</span><span class="sxs-lookup"><span data-stu-id="57db5-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="57db5-137">Настройте одну или несколько записей, как описано в разделе [синтаксис записи для списка "Блокировка следующих URL-адресов"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="57db5-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="57db5-138">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="57db5-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="57db5-139">Настройка списка "блокировать следующие URL-адреса" в PowerShell</span><span class="sxs-lookup"><span data-stu-id="57db5-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="57db5-140">Для получения дополнительных сведений о синтаксисе записей обратитесь к разделу ["Блокировка следующих URL-адресов"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="57db5-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="57db5-141">С помощью командлета **Get – AtpPolicyForO365** можно просматривать существующие записи в свойстве _блоккурлс_ .</span><span class="sxs-lookup"><span data-stu-id="57db5-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="57db5-142">Чтобы добавить значения, которые будут заменять все существующие записи, используйте следующий синтаксис в Exchange Online PowerShell или PowerShell Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="57db5-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="57db5-143">В этом примере в список добавляются следующие записи:</span><span class="sxs-lookup"><span data-stu-id="57db5-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="57db5-144">Блокировать домен, дочерние домены и пути для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="57db5-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="57db5-145">Блокировка исследований поддоменов, но не родительского домена или других поддоменов в tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="57db5-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="57db5-146">Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="57db5-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="57db5-147">В этом примере добавляется новая запись для adatum.com и удаляется запись для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="57db5-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="57db5-148">Настройка защиты безопасных ссылок для приложений Office 365 в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="57db5-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="57db5-149">Защита безопасных ссылок для приложений Office 365. применяется к документам в поддерживаемых приложениях Office для настольных ПК, мобильных устройств и веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="57db5-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="57db5-150">Дополнительные сведения приведены в разделе [Параметры безопасных ссылок для приложений Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="57db5-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="57db5-151">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**и выберите **глобальные параметры**.</span><span class="sxs-lookup"><span data-stu-id="57db5-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="57db5-152">В разделе **Политика безопасных ссылок для своей организации** необходимо настроить следующие параметры в **параметрах, которые применяются к содержимому, кроме раздела Электронная почта** :</span><span class="sxs-lookup"><span data-stu-id="57db5-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="57db5-153">**Приложения office 365**: установите флажок справа, чтобы включить безопасные ссылки для поддерживаемых приложений Office 365: ![ вкл ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="57db5-153">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="57db5-154">**Не Отслеживайте, когда пользователи щелкают ссылки "безопасные ссылки**": перемещение переключателя влево для отслеживания нажатий кнопок, связанных с заблокированными URL-адресами в поддерживаемых приложениях Office 365: ![ вкл ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="57db5-154">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="57db5-155">**Не разрешать пользователям щелкать ссылки по безопасному URL-адресу**: Проверьте переключатель справа, чтобы запретить пользователям переходить к исходному заблокированному URL-адресу в поддерживаемых приложениях Office 365: ![ включить ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="57db5-155">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="57db5-156">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="57db5-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="57db5-157">Настройка защиты безопасных ссылок для приложений Office 365 в PowerShell</span><span class="sxs-lookup"><span data-stu-id="57db5-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="57db5-158">Если вы предпочитаете использовать PowerShell для настройки защиты безопасных ссылок для приложений Office 365, используйте следующий синтаксис в Exchange Online PowerShell или PowerShell Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="57db5-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="57db5-159">В этом примере настраиваются следующие параметры для защиты безопасных ссылок в приложениях Office 365:</span><span class="sxs-lookup"><span data-stu-id="57db5-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="57db5-160">Безопасные ссылки для приложений Office 365 включены (мы не используем параметр _EnableSafeLinksForO365Clients_ , а значение по умолчанию — $true).</span><span class="sxs-lookup"><span data-stu-id="57db5-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="57db5-161">Отслеживаются нажатия клавиш, связанные с заблокированными URL-адресами в поддерживаемых приложениях Office 365.</span><span class="sxs-lookup"><span data-stu-id="57db5-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="57db5-162">Пользователям запрещено щелкать по исходному заблокированному URL-адресу в поддерживаемых приложениях Office 365 (мы не используем параметр _алловкликксраугх_ , а значение по умолчанию — $false).</span><span class="sxs-lookup"><span data-stu-id="57db5-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="57db5-163">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="57db5-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="57db5-164">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="57db5-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="57db5-165">Чтобы убедиться, что вы успешно настроили глобальные параметры для "безопасные ссылки" ( **блокировать следующий список URL-адресов** и параметры защиты приложений Office 365), выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="57db5-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="57db5-166">В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасных ссылок ATP**, щелкните **глобальные параметры**и проверьте, отображаются ли параметры на лету.</span><span class="sxs-lookup"><span data-stu-id="57db5-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="57db5-167">В PowerShell Exchange Online или Exchange Online Protection выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="57db5-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="57db5-168">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="57db5-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
