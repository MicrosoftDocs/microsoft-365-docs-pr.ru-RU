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
ms.openlocfilehash: 5b1bcdaf92412b17b231e3f4849bae8aab72f292
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878536"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Настройка глобальных параметров для Сейф ссылок в Microsoft Defender для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](defender-for-office-365.md). Если вы домашний пользователь, который ищет сведения о Safelinks в Outlook, см. в [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Сейф Ссылки — это функция в Microsoft Defender для Office 365, которая обеспечивает сканирование [URL-адресов](defender-for-office-365.md) входящие сообщения электронной почты в потоке почты, а также время проверки URL-адресов и ссылок в сообщениях электронной почты и в других местах. Дополнительные сведения см. [в Сейф Ссылки в Microsoft Defender для Office 365.](safe-links.md)

Большинство параметров Сейф ссылок в Сейф ссылки. Инструкции см. в Сейф ссылки в [Microsoft Defender для Office 365.](set-up-safe-links-policies.md)

Но Сейф ссылки также используют следующие глобальные параметры, которые вы настраиваете за пределами самих политик Сейф ссылки:

- Блок **следующий список URL-адресов.** Этот параметр применяется ко всем пользователям, включенным в активные политики Сейф ссылки. Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов"](safe-links.md#block-the-following-urls-list-for-safe-links) для Сейф ссылки
- Сейф Защита ссылок для Office 365 приложений. Эти параметры применяются для всех пользователей в организации, которые имеют лицензию на defender для Office 365, независимо от того, включены ли пользователи в активные политики Сейф ссылки или нет. Дополнительные сведения см. [в Сейф ссылки для Office 365 приложений.](safe-links.md#safe-links-settings-for-office-365-apps)

Параметры глобальных ссылок Сейф можно настроить на портале Microsoft 365 Defender или в PowerShell (Exchange Online PowerShell для подходящих Microsoft 365 организаций с почтовыми ящиками в Exchange Online; автономные EOP PowerShell для организаций без Exchange Online почтовых ящиков, но с Microsoft Defender для Office 365 надстройки).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Политика встроенных или Сейф ссылок по умолчанию не существует, поэтому для активной блокировки следующего  списка URL-адресов необходимо создать по крайней мере одну политику Сейф links. Инструкции см. в Сейф ссылки в [Microsoft Defender для Office 365.](set-up-safe-links-policies.md)

- Вы открываете портал Microsoft 365 Defender по <https://security.microsoft.com> ссылке . Чтобы перейти непосредственно **на страницу Сейф ссылки,** используйте <https://security.microsoft.com/safelinksv2> .

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:
  - Чтобы настроить глобальные параметры для Сейф ссылок, необходимо быть членом  группы ролей администратора организации или **администратора** безопасности.
  - Для доступа только для чтения к глобальным настройкам для Сейф ссылок необходимо быть членом групп ролей **Global Reader** или **Security Reader.**

  Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Примечания**.

  - Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).
  - Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.

- Рекомендуемые значения для глобальных параметров для Сейф ссылки см. в Сейф [Ссылки.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- Разрешить до 30 минут для новой или обновленной политики, которая будет применяться.

- [Новые функции постоянно добавляются в Microsoft Defender для](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 . При добавлении новых функций может потребоваться внести изменения в существующие политики Сейф ссылки.

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>Настройка списка "Блокировка следующих URL-адресов" на портале Microsoft 365 Defender

В **списке Блок следующих** URL-адресов указаны ссылки, которые всегда должны быть заблокированы с помощью Сейф ссылок в поддерживаемых приложениях. Дополнительные сведения см. в [списке "Блокировать следующие URL-адреса" для Сейф ссылки.](safe-links.md#block-the-following-urls-list-for-safe-links)

1. На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы Сейф \>  \>  \>  \> **ссылки**.

2. На странице **Сейф Ссылки** щелкните **Глобальные параметры**. В политике **Сейф ссылки** для организации вылет, который отображается, перейдите к **блоку следующего URL-адреса.**

3. Настройте одну или несколько записей, как описано в синтаксис Записи, для списка "Блокировать следующие [URL-адреса".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Выполнив необходимые действия, нажмите кнопку **Сохранить**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Настройка списка "Блокировка следующих URL-адресов" в PowerShell

Подробные сведения о синтаксисе записи см. в [синтаксис Записи в списке "Заблокировать следующие URL-адреса".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a>Настройка Сейф ссылок для Office 365 приложений на портале Microsoft 365 Defender

Сейф Защита ссылок для Office 365 приложений применяется к документам в поддерживаемых Office, мобильных и веб-приложениях. Дополнительные сведения см. [в Сейф ссылки для Office 365 приложений.](safe-links.md#safe-links-settings-for-office-365-apps)

1. На портале Microsoft 365 Defender перейдите в раздел Политики **совместной** & электронной почты & политики угрозы Сейф \>  \>  \>  \> **ссылки**.

2. На странице **Сейф Ссылки** щелкните **Глобальные параметры**. В **политике Сейф ссылки** для организации вылет, который появляется, настройте следующие параметры в Параметры, которые применяются к контенту в поддерживаемом разделе **Office 365** приложений:

   - **Используйте Сейф ссылки** в Office 365 приложениях. Убедитесь, что справа нужно включить Сейф ссылки для поддерживаемых Office 365 приложений: переналадка. ![ ](../../media/scc-toggle-on.png)

   - **Не отслеживайте,** когда пользователи щелкают защищенные ссылки в Office 365 приложениях: переместите очки влево, чтобы отслеживать щелчки пользователей, связанные с заблокированными URL-адресами в поддерживаемых Office 365 ![ приложениях. ](../../media/scc-toggle-off.png)

   - Не позволяйте пользователям щелкнуть исходный **URL-адрес** в Office 365 приложениях: убедитесь, что перегной является правой кнопкой, чтобы пользователи не щелкнули исходный заблокированный URL-адрес в поддерживаемых Office 365 приложениях: ![ Toggle on ](../../media/scc-toggle-on.png) .

   Выполнив необходимые действия, нажмите кнопку **Сохранить**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Настройка Сейф ссылок для Office 365 приложений в PowerShell

Если вы хотите использовать PowerShell для настройки защиты Сейф ссылок для Office 365 приложений, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

В этом примере настраиваются следующие параметры защиты Сейф ссылок в Office 365 приложениях:

- Сейф Включена ссылка Office 365 приложений (мы не используем параметр _EnableSafeLinksForO365Clients,_ и значение по умолчанию $true).
- Клики пользователей, связанные с заблокированными URL-адресами в поддерживаемых Office 365 отслеживаются.
- Пользователям не разрешается щелкнуть исходный заблокированный URL-адрес в поддерживаемых Office 365 приложениях (мы не используем параметр _AllowClickThrough,_ а значение по умолчанию $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что вы успешно настроены глобальные параметры для  ссылок Сейф (блок следующий список URL-адресов и параметры защиты Office 365 приложения), сделайте все следующие действия:

- На портале Microsoft 365 Defender перейдите  в раздел Политики & совместной работы & Правила политики \>  \>  \>  \> **угрозы Сейф Ссылки** \> нажмите глобальные параметры и проверьте параметры в вылете, который появляется.

- В Exchange Online PowerShell или Exchange Online Protection PowerShell запустите следующую команду и проверьте параметры:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)
