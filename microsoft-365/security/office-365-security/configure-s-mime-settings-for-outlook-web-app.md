---
title: Настройка параметров S/MIME в Exchange Online для Outlook в Интернете
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Краткое описание администраторов Exchange Online, необходимых для просмотра и настройки параметров S/MIME в Outlook в Интернете в Exchange Online.
ms.openlocfilehash: 6e390e377369dc0de73d5e063a6a21fd549c3bef
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091331"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Настройка параметров S/MIME в Exchange Online для Outlook в Интернете

В качестве администратора Exchange Online можно настроить Outlook в Интернете (прежнее название — Outlook Web App), чтобы разрешить отправку и получение сообщений, защищенных с помощью S/MIME. Используйте командлеты **Get-SmimeConfig** и **Set-SmimeConfig** для просмотра и управления этой функцией в Exchange Online PowerShell. Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) и [Set/SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).

## <a name="considerations-for-chrome"></a>Рекомендации для Chrome

Чтобы использовать S/MIME в Outlook в Интернете в веб-браузере Google Chrome, вы (или другой администратор) должны настроить и настроить политику Чромиум с именем **екстенсионинсталлфорцелист** , чтобы установить расширение Microsoft S/MIME в Chrome. Значение политики — `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. Обратите внимание, что для применения этой политики требуются компьютеры, присоединенные к домену, поэтому для эффективного использования S/MIME в Chrome необходимы компьютеры, присоединенные к домену.

Подробные сведения о политике **екстенсионинсталлфорцелист** можно найти в статье [екстенсионинсталлфорцелист](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).

Этот шаг является необходимым условием для использования Chrome; Он не заменяет элемент управления S/MIME, установленный пользователями. При первом использовании S/MIME пользователям предлагается скачать и установить элемент управления S/MIME в Outlook в Интернете. Кроме того, пользователи могут активно перейти к параметру **S/MIME** в Outlook в Интернете, чтобы получить ссылку для скачивания этого элемента управления.

## <a name="for-more-information"></a>Дополнительные сведения

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)
