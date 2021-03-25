---
title: FaQ сообщений в карантине
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут просматривать часто задаваемые вопросы и ответы о карантинных сообщениях в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 342f6b7f27c99352c4e5906799ce463b658e0c87
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206628"
---
# <a name="quarantined-messages-faq"></a>FaQ сообщений в карантине

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В этом разделе часто задавались вопросы и ответы о карантинных сообщениях электронной почты для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.

Вопросы и ответы о защите от нежелательной почты см. в [faq anti-spam protection.](anti-spam-protection-faq.md)

Вопросы и ответы о защите от вредоносных программ см. в faq [anti-malware protection.](anti-malware-protection-faq-eop.md)

Вопросы и ответы о защите от подмены см. в [faq anti-spoofing protection.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Как управлять сообщениями, которые были карантинными для вредоносных программ?

Только администраторы могут управлять сообщениями, которые были карантин для вредоносных программ. Дополнительные сведения см. в [статью Управление карантинными сообщениями и файлами в качестве администратора.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>Как сделать карантин нежелательной почты?

По умолчанию сообщения, классифицируются как спам или массовая фильтрация нежелательной почты, доставляются в почтовый ящик пользователя и перемещаются в папку нежелательной почты. Но вместо этого можно создавать и настраивать политики по борьбе со спамом для карантиного спама или массовых сообщений электронной почты. Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Как предоставить пользователям доступ к карантину?

Пользователь должен иметь допустимую учетную запись, чтобы получить доступ к собственным сообщениям в карантине. Автономный EOP требует, чтобы пользователи представлялись пользователями почты в EOP (вручную созданные или созданные с помощью синхронизации каталогов). Дополнительные сведения об управлении пользователями в автономных средах EOP см. в рублях Управление пользователями [почты в EOP.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Какие сообщения могут закончить доступ пользователей к карантину?

Пользователи могут получать доступ к спаму, массовой электронной почте и (по данным на апрель 2020 г.) фишинговых сообщений, в которых они являются получателем. Конечные пользователи не могут получить доступ к карантинным вредоносным программам, высокой достоверности фишинга или сообщений, которые были на карантине из-за доставки сообщения в действие на карантин в правилах потока почты (также известные как правила транспорта).  Дополнительные сведения о доступе пользователей к карантинным сообщениям см. в тексте [Find and release quarantined messages as a user.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Как долго сообщения хранятся в карантине?

Вы можете настроить, как долго спам, фишинг и массовые сообщения электронной почты хранятся в карантине с помощью политики защиты от нежелательной почты. По умолчанию — 30 дней, что также является максимальным значением. Дополнительные сведения см. в [сообщении Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)

Для сообщений, которые были карантин в действие правила потока почты **Доставить** сообщение на принимающий карантин, сообщения хранятся в карантине в течение 30 дней. Вы не можете настроить эту продолжительность.

По истечении периода времени сообщения удаляются и не могут быть восстановлены.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Можно ли освободить одновременно несколько сообщений, помещенных на карантин, или сообщить о них?

В Центре & безопасности можно выбрать и выпустить до 100 сообщений одновременно.

Администраторы могут использовать [комлеты Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) и [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) в Exchange Online PowerShell или автономные EOP PowerShell для поиска и выпуска карантиных сообщений оптом, а также для массовой рассылки ложных срабатывающих сообщений.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Поддерживаются ли подстановочные знаки при поиске сообщений, помещенных на карантин? Можно ли искать помещенные на карантин сообщения для определенного домена?

Поддиальды не поддерживаются в Центре & безопасности. Например, при поиске отправители необходимо указать полный адрес электронной почты. Но вы можете использовать подкарды в Exchange Online PowerShell или автономный EOP PowerShell.

Например, скопируйте следующий код PowerShell в NotePad и сохраните файл как .ps1 в удобном для вас расположении (например, C:\Data\QuarantineRelease.ps1).

После подключения к [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) или [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)запустите следующую команду для запуска сценария:

```powershell
& C:\Data\QuarantineRelease.ps1
```

Сценарий делает следующие действия:

- Найдите неоформленные сообщения, которые были на карантине как спам от всех отправителей в домене fabrikam. Максимальное число результатов — 50 000 (50 страниц из 1000 результатов).
- Сохраните результаты в CSV-файле.
- Отпустите соответствие карантинному сообщению всем исходным получателям.

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

После выпуска сообщения вы не сможете выпустить его снова.