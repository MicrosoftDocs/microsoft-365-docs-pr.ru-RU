---
title: Настройка параметров S/MIME — Exchange Online для Outlook в Интернете
f1.keywords:
- NOCSH
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9f4e6c33369640ad66956568959dd02b01c4fb9
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517489"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Настройка параметров S/MIME в Exchange Online для Outlook в Интернете

В качестве администратора Exchange Online можно настроить Outlook в Интернете (прежнее название — Outlook Web App), чтобы разрешить отправку и получение сообщений, защищенных с помощью S/MIME. Используйте командлеты **Get-SmimeConfig** и **Set-SmimeConfig** для просмотра и управления этой функцией в Exchange Online PowerShell. Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) и [Set/SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Рекомендации по новым Microsoft EDGE (на основе Чромиум)

Чтобы использовать S/MIME в Outlook в Интернете в новом веб-браузере [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) , вы (или другой администратор) должны установить и настроить политику браузера Microsoft Edge с именем **екстенсионинсталлфорцелист** , чтобы установить расширение Microsoft S/MIME в новой Microsoft Edge. Значение политики — `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Обратите внимание, что для применения этой политики необходимо присоединение к домену или устройства, присоединенные к Azure AD, поэтому для эффективного использования S/MIME в новом обозревателе Microsoft Edge необходимо присоединение к домену или устройства, присоединенные к Azure AD.

Подробные сведения о политике **екстенсионинсталлфорцелист** можно найти в статье [екстенсионинсталлфорцелист](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Этот шаг является необходимым условием для использования новых Microsoft Edge; Он не заменяет элемент управления S/MIME, установленный пользователями. При первом использовании S/MIME пользователям предлагается скачать и установить элемент управления S/MIME в Outlook в Интернете. Кроме того, пользователи могут активно перейти к параметру **S/MIME** в Outlook в Интернете, чтобы получить ссылку для скачивания этого элемента управления.

## <a name="considerations-for-chrome"></a>Рекомендации для Chrome

Чтобы использовать S/MIME в Outlook в Интернете в веб-браузере Google Chrome, вы (или другой администратор) должны настроить и настроить политику Чромиум с именем **екстенсионинсталлфорцелист** , чтобы установить расширение Microsoft S/MIME в Chrome. Значение политики — `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Обратите внимание, что для применения этой политики требуются компьютеры, присоединенные к домену, поэтому для эффективного использования S/MIME в Chrome необходимы компьютеры, присоединенные к домену.

Подробные сведения о политике **екстенсионинсталлфорцелист** можно найти в статье [екстенсионинсталлфорцелист](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Этот шаг является необходимым условием для использования Chrome; Он не заменяет элемент управления S/MIME, установленный пользователями. При первом использовании S/MIME пользователям предлагается скачать и установить элемент управления S/MIME в Outlook в Интернете. Кроме того, пользователи могут активно перейти к параметру **S/MIME** в Outlook в Интернете, чтобы получить ссылку для скачивания этого элемента управления.

## <a name="for-more-information"></a>Дополнительные сведения

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)
