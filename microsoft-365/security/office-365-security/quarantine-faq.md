---
title: Quarantined messages FAQ
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
description: Администраторы могут просматривать часто задаваемые вопросы и ответы о сообщениях на карантине в Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8496ae4f1702bb63328be0c494d8829c9ddd8cf2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289405"
---
# <a name="quarantined-messages-faq"></a>Quarantined messages FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В этом разделе даны вопросы и ответы о сообщениях электронной почты, отправленных на карантин, для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.

Вопросы и ответы о защите от нежелательной почты см. в вопросах о защите от нежелательной [почты.](anti-spam-protection-faq.md)

Вопросы и ответы о защите от вредоносных программ см. в вопросах о защите от [вредоносных программ.](anti-malware-protection-faq-eop.md)

Вопросы и ответы о защите от спуфинга см. в ответах на вопросы о защите от [спуфинга.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Как управлять сообщениями, которые были на карантине для вредоносных программ?

Управлять сообщениями, которые были на карантине для вредоносных программ, могут только администраторы. Дополнительные сведения см. в под управлением сообщений и файлов на карантине от [имени администратора.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>Как сделать карантин нежелательной почты?

По умолчанию сообщения, классифицированные как спам или массовая рассылка с помощью фильтрации нежелательной почты, доставляются в почтовый ящик пользователя и перемещаются в папку нежелательной почты. Однако вместо этого можно создать и настроить политики нежелательной почты для карантина нежелательной почты или массовых сообщений электронной почты. Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Как предоставить пользователям доступ к карантину?

Для доступа к собственным сообщениям в карантине у пользователя должна быть действительная учетная запись. Автономный EOP требует, чтобы пользователи были представлены в EOP как почтовые пользователи (вручную созданные или созданные с помощью синхронизации каталогов). Дополнительные сведения об управлении пользователями в автономных средах EOP см. в подсети ["Управление почтовыми пользователями в EOP".](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Какие сообщения могут быть доступны конечным пользователям в карантине?

Пользователи могут получать доступ к нежелательным, массовым рассылкам и (в апреле 2020 г.) фишинговыми сообщениями, в которых они являются получателями. Конечные пользователи не могут получить доступ к вредоносным программам, которые были отправлены  на карантин, фишингу с высокой достоверности или сообщениям, которые были отправлены в карантин из-за действия "Доставить сообщение в карантин" в правилах потока почты (также известных как правила транспорта). Дополнительные сведения о пользователях, которые имеют доступ к сообщениям на карантине, см. в подсети "Поиск и освобождение сообщений на карантине" в [качестве пользователя.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Как долго сообщения хранятся в карантине?

С помощью политик защиты от нежелательной почты вы можете настроить срок, в течение который нежелательные, фишинговые и массовые сообщения электронной почты будут храниться в карантине. Значение по умолчанию — 30 дней, что также является максимальным значением. Дополнительные сведения см. в подстроке "Настройка политик [нежелательной почты" в EOP](configure-your-spam-filter-policies.md)

Для сообщений, которые были отправлены в карантин действием правила потока почты **Доставить** сообщение в почтовый карантин, сообщения хранятся в карантине в течение 30 дней. Этот срок настроить нельзя.

По истечении этого периода сообщения удаляются и не могут быть восстановлены.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Можно ли освободить одновременно несколько сообщений, помещенных на карантин, или сообщить о них?

В Центре & соответствия требованиям можно выбрать и освободить до 100 сообщений одновременно.

Администраторы могут использовать [](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) в Exchange Online PowerShell [](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) или автономных EOP PowerShell для массового поиска и освобождения сообщений из карантина и массовой рассылки сообщений в карантине и массового сообщения о ложных срабатываниях.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Поддерживаются ли подстановочные знаки при поиске сообщений, помещенных на карантин? Можно ли искать помещенные на карантин сообщения для определенного домена?

Wildcards aren't supported in the Security & Compliance Center. Например, при поиске отправители необходимо указать полный адрес электронной почты. Но вы можете использовать поддиапные знаки в Exchange Online PowerShell или в автономных EOP PowerShell.

Например, скопируйте следующий код PowerShell в Блокнот и сохраните файл как PS1 в расположении, которое легко найти (например, C:\Data\QuarantineRelease.ps1).

После подключения к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) или [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)запустите следующую команду, чтобы запустить сценарий:

```powershell
& C:\Data\QuarantineRelease.ps1
```

Сценарий делает следующие действия:

- Найдите невысланные сообщения, которые были на карантине как спам от всех отправителей в домене fabrikam. Максимальное число результатов — 50 000 (50 страниц из 1000 результатов).
- Сохраните результаты в CSV-файле.
- Отпустите совпадающие сообщения на карантине для всех исходных получателей.

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

После освобождения сообщения вы не сможете освободить его снова.
