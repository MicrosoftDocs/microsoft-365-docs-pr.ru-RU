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
ms.openlocfilehash: 38614d070f4ac9bfda978301eaeed6029b47e0ca
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406118"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Настройка глобальных параметров безопасных ссылок в Microsoft Defender для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](office-365-atp.md). Если вы домашний пользователь, который ищет сведения о Safelinks в Outlook, см. в Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Безопасные ссылки — это функция [в Microsoft Defender для Office 365,](office-365-atp.md) которая обеспечивает сканирование URL-адресов входящие сообщения электронной почты в потоке почты, а также время проверки URL-адресов и ссылок в сообщениях электронной почты и в других местах. Дополнительные сведения см. в [веб-сайте Безопасные ссылки в Microsoft Defender для Office 365.](atp-safe-links.md)

Большинство параметров безопасных ссылок настраиваются в политиках безопасных ссылок. Инструкции см. в инструкции Настройка политик безопасных ссылок [в Microsoft Defender для Office 365.](set-up-atp-safe-links-policies.md)

Но безопасные ссылки также используют глобальные параметры, применимые к всем пользователям, включенным в любые активные политики безопасных ссылок. Эти глобальные области параметров:

- Блок **следующий список URL-адресов.** Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Защита безопасных ссылок для приложений Office 365. Дополнительные сведения см. в [настройках безопасных ссылок для приложений Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

Вы можете настроить глобальные параметры безопасных ссылок в Центре обеспечения безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с помощью надстройки Microsoft Defender для Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Функции, предоставляемые глобальными настройками безопасных ссылок, применяются только к пользователям, включенным в активные политики безопасных ссылок. Существует не встроенная или по умолчанию политика безопасных ссылок, поэтому необходимо создать по крайней мере одну политику безопасных ссылок, чтобы эти глобальные параметры были активными. Инструкции см. в инструкции Настройка политик безопасных ссылок [в Microsoft Defender для Office 365.](set-up-atp-safe-links-policies.md)

- Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>. Чтобы перейти непосредственно на страницу **Безопасные ссылки,** используйте <https://protection.office.com/safelinksv2> .

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Вам необходимо получить разрешения в **Exchange Online,** прежде чем вы сможете сделать процедуры в этой статье:
  - Чтобы настроить глобальные параметры безопасных ссылок, необходимо быть членом группы ролей **администратора** организации или **администратора** безопасности.
  - Для доступа только для чтения к глобальным настройкам безопасных ссылок необходимо быть членом групп ролей **Global Reader** или **Security Reader.**

  Дополнительные сведения см. в статье [Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Примечания**.

  - Добавление пользователей к соответствующей роли Azure Active Directory в центре администрирования Microsoft  365 дает пользователям необходимые разрешения и разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).
  - Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.

- Рекомендуемые значения для глобальных параметров безопасных ссылок см. в этой [ссылке.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)

- Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.

- [Новые функции постоянно добавляются в Microsoft Defender для Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) При добавлении новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Настройка списка "Блокировка следующих URL-адресов" в Центре & безопасности

В **следующем списке URL-адресов** заблокированы ссылки, которые всегда должны быть заблокированы при сканировании безопасных ссылок в поддерживаемых приложениях. Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)

1. В Центре обеспечения & безопасности перейдите  к политике управления угрозами \>  \> **ATP Safe Links,** а затем щелкните **глобальные параметры**.

2. В политике **безопасных ссылок для организации** вылет, который отображается, перейдите к **блоку следующего URL-адреса.**

3. Настройте одну или несколько записей, как описано в синтаксис Записи, для списка "Блокировать следующие [URL-адреса".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   По завершении нажмите кнопку **Сохранить**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Настройка списка "Блокировка следующих URL-адресов" в PowerShell

Подробные сведения о синтаксисе записи см. в [синтаксис Записи в списке "Заблокировать следующие URL-адреса".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Для просмотра существующих записей в свойстве _BlockURLs_ можно использовать **кодлет Get-AtpPolicyForO365.**

- Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  В этом примере в список добавляются следующие записи:

  - Блокировка домена, поддоменов и путей для fabrikam.com.
  - Заблокируют исследование subdomain, но не родительский домен или другие поддомены в tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Чтобы добавить или удалить значения, не затрагивая другие существующие записи, используйте следующий синтаксис:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  В этом примере добавляется новая запись для adatum.com и удаляется запись для fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Настройка защиты безопасных ссылок для приложений Office 365 в Центре & безопасности

Защита безопасных ссылок для приложений Office 365 применяется к документам в поддерживаемых настольных, мобильных и веб-приложениях Office. Дополнительные сведения см. в [настройках безопасных ссылок для приложений Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

1. В Центре обеспечения & безопасности перейдите  к политике управления угрозами \>  \> **ATP Safe Links,** а затем щелкните **глобальные параметры**.

2. В политике **безопасных ссылок** для организации, которая появится, настройте следующие параметры в разделе Параметры, применимые к контенту, за исключением раздела **электронной** почты:

   - **Приложения Office 365.** Убедитесь, что перегной является правом, чтобы включить безопасные ссылки для поддерживаемых приложений Office 365. ![ ](../../media/scc-toggle-on.png)

   - Не отслеживайте, когда пользователи щелкают "Безопасные ссылки" **(Safe Links:** Move the toggle to the left to track user clicks related to blocked URLs) in supported Office 365 apps: ![ Toggle ](../../media/scc-toggle-off.png) off.

   - **Не позволяйте** пользователям щелкнуть "Безопасные ссылки" на исходный URL-адрес: Убедитесь, что перегородка справа, чтобы пользователи не щелкнули исходный заблокированный URL-адрес в поддерживаемых приложениях Office 365: ![ Toggle on ](../../media/scc-toggle-on.png) .

   По завершении нажмите кнопку **Сохранить**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Настройка защиты безопасных ссылок для приложений Office 365 в PowerShell

Если вы хотите использовать PowerShell для настройки защиты безопасных ссылок для приложений Office 365, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

В этом примере настраиваются следующие параметры защиты безопасных ссылок в приложениях Office 365:

- Включена безопасная связь для приложений Office 365 (мы не используем параметр _EnableSafeLinksForO365Clients,_ а значение по умолчанию $true).
- Отслеживаются клики пользователей, связанные с заблокированными URL-адресами в поддерживаемых приложениях Office 365.
- Пользователям не разрешается щелкнуть исходный заблокированный URL-адрес в поддерживаемых приложениях Office 365 (мы не используем параметр _AllowClickThrough,_ а значение по умолчанию $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что вы успешно настроили глобальные  параметры безопасных ссылок (блокировать следующий список URL-адресов и параметры защиты приложений Office 365), необходимо предпринять следующие действия:

- В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Links,** щелкните Глобальные параметры и проверьте параметры в вылете, который появляется.

- В Exchange Online PowerShell или Exchange Online Protection PowerShell запустите следующую команду и проверьте параметры:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)
