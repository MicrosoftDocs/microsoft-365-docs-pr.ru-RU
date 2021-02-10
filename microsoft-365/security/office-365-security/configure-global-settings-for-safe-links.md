---
title: Настройка глобальных параметров для параметров безопасных ссылок в Защитнике Office 365
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
description: Администраторы могут узнать, как просматривать и настраивать глобальные параметры (список "Блокировать следующие URL-адреса" и защиту приложений Office 365) для безопасных ссылок в Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165731"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Настройка глобальных параметров безопасных ссылок в Microsoft Defender для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](office-365-atp.md). Если вы — домашний пользователь, который ищет сведения о безопасных ссылках в Outlook, см. дополнительные Outlook.com [безопасности.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Функция "Безопасные ссылки" — это функция в Microsoft Defender для [Office 365,](office-365-atp.md) которая обеспечивает сканирование URL-адресов входящие сообщения электронной почты в потоке почты и время проверки URL-адресов и ссылок в сообщениях электронной почты и других расположениях. Дополнительные сведения см. в [веб-сайте "Безопасные ссылки" в Microsoft Defender для Office 365.](atp-safe-links.md)

Большинство параметров безопасных ссылок настраиваются в политиках безопасных ссылок. Инструкции см. в [настройках политик безопасных ссылок в Microsoft Defender для Office 365.](set-up-atp-safe-links-policies.md)

Однако безопасные ссылки также используют глобальные параметры, которые применяются для всех пользователей, включенных в активные политики безопасных ссылок. Область глобальных параметров:

- Список **заблокированных URL-адресов.** Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Защита безопасных ссылок для приложений Office 365. Дополнительные сведения см. в параметрах безопасных [ссылок для приложений Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

Глобальные параметры безопасных ссылок можно настроить в Центре безопасности и & соответствия требованиям или в PowerShell (Exchange Online PowerShell для соответствующих организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online, но с подписками на надстройки Microsoft Defender для Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Функции, предоставляемые глобальными настройками безопасных ссылок, применяются только к пользователям, включенным в активные политики безопасных ссылок. Встроенная или стандартная политика безопасных ссылок не существует, поэтому необходимо создать по крайней мере одну политику безопасных ссылок, чтобы эти глобальные параметры были активными. Инструкции см. в [настройках политик безопасных ссылок в Microsoft Defender для Office 365.](set-up-atp-safe-links-policies.md)

- Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>. Чтобы перейти непосредственно на страницу **"Безопасные ссылки",** используйте <https://protection.office.com/safelinksv2> .

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:
  - Чтобы настроить глобальные параметры для функции "Безопасные ссылки", необходимо быть членом группы ролей "Управление организацией" или **"Администратор** безопасности". 
  - Для доступа только для чтения к глобальным настройкам безопасных ссылок необходимо  быть участником группы ролей **"Глобальное** чтение" или "Читатель безопасности".

  Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

  **Примечания**.

  - Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.

- Рекомендуемые значения глобальных параметров для безопасных ссылок см. в параметрах [безопасных ссылок.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)

- Позволяет применять новую или обновленную политику в течение 30 минут.

- [Новые функции постоянно добавляются в Microsoft Defender для Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) При добавлении новых функций может потребоваться внести изменения в существующие политики безопасных ссылок.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Настройка списка "Блокировать следующие URL-адреса" в Центре безопасности & соответствия требованиям

В **списке "Блокировать следующие** URL-адреса" указаны ссылки, которые всегда должны блокироваться при сканировании безопасных ссылок в поддерживаемых приложениях. Дополнительные сведения см. в [списке "Блокировка следующих URL-адресов" для безопасных ссылок.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)

1. В Центре безопасности & соответствия требованиям  перейдите в центр безопасных ссылок ATP политики управления угрозами, а затем щелкните \>  \>  **"Глобальные параметры".**

2. В **окне "Политика безопасных ссылок"** для организации перейдите к окну **"Блокировать следующие URL-адреса".**

3. Настройте одну или несколько записей, как описано в синтаксис записи для [списка "Блокировать следующие URL-адреса".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   По завершении нажмите кнопку **Сохранить**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Настройка списка "Блокировать следующие URL-адреса" в PowerShell

Подробные сведения о синтаксисах записей см. в синтаксису записей в списке ["Блокировать следующие URL-адреса".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Для просмотра существующих записей в свойстве _BlockURLs_ можно использовать cmdlet **Get-AtpPolicyForO365.**

- Чтобы добавить значения, которые заменят существующие записи, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  В этом примере в список добавляются следующие записи:

  - Блокировка домена, поддоменов и путей для fabrikam.com.
  - Блокировать исследования поддоменов, но не родительский домен или другие поддомены в tailspintoys.com

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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Настройка защиты безопасных ссылок для приложений Office 365 в Центре безопасности & соответствия требованиям

Защита безопасных ссылок для приложений Office 365 применяется к документам в поддерживаемых классических, мобильных и веб-приложениях Office. Дополнительные сведения см. в параметрах безопасных [ссылок для приложений Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

1. В Центре безопасности & соответствия требованиям  перейдите в центр безопасных ссылок ATP политики управления угрозами, а затем щелкните \>  \>  **"Глобальные параметры".**

2. В политике **безопасных ссылок** для организации настройте следующие параметры в параметрах, которые применяются к контенту, кроме раздела **"Электронная** почта":

   - **Приложения Office 365:** убедитесь, что этот переладок находится справа, чтобы включить безопасные ссылки для поддерживаемых приложений Office 365: включить. ![ ](../../media/scc-toggle-on.png)

   - **Не отслеживайте,** когда пользователи нажимают кнопку "Безопасные ссылки": переключение влево для отслеживания переходов пользователей, связанных с заблокированными URL-адресами в поддерживаемых приложениях Office 365: выключение. ![ ](../../media/scc-toggle-off.png)

   - Не позволяйте пользователям перейдите по ссылке "Безопасные ссылки" на исходный URL-адрес: убедитесь, что перейдите справа, чтобы запретить пользователям перенажимать исходный заблокированный URL-адрес в поддерживаемых приложениях Office 365: "Нажать кнопку". ![ ](../../media/scc-toggle-on.png)

   По завершении нажмите кнопку **Сохранить**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Настройка защиты безопасных ссылок для приложений Office 365 в PowerShell

Если вы хотите использовать PowerShell для настройки защиты безопасных ссылок для приложений Office 365, используйте следующий синтаксис в Exchange Online PowerShell или Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

В этом примере настраиваются следующие параметры защиты безопасных ссылок в приложениях Office 365:

- Безопасные ссылки для приложений Office 365 включены (мы не используем параметр _EnableSafeLinksForO365Clients,_ а значение по умолчанию — $true).
- Щелчки пользователей, связанные с заблокированными URL-адресами в поддерживаемых приложениях Office 365, отслеживаются.
- Пользователям не разрешено перебор исходного заблокированного URL-адреса в поддерживаемых приложениях Office 365 (мы не используем параметр _AllowClickThrough,_ а значение по умолчанию — $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Подробные сведения о синтаксис и параметрах см. в описании [Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

Чтобы убедиться, что вы успешно настроили глобальные  параметры безопасных ссылок (список "Блокировать следующие URL-адреса" и параметры защиты приложений Office 365), сделайте следующее:

- In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links,** click **Global settings**, and verify the settings in the fly out that appears.

- В Exchange Online PowerShell или Exchange Online Protection PowerShell запустите следующую команду и проверьте параметры:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Подробные сведения о синтаксисах и параметрах см. в описании [get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)
