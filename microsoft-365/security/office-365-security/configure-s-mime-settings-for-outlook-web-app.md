---
title: Настройка параметров S/MIME — Exchange Online для Outlook в Интернете
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Краткое описание того, что необходимо сделать администраторам Exchange Online для просмотра и настройки параметров S/MIME в Outlook в Интернете в Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ccadfc46e42713601b115c18a119e48dcfdcbf4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290037"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Настройка параметров S/MIME в Exchange Online для Outlook в Интернете

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Администратор Exchange Online может настроить Outlook в Интернете (прежнее название — Outlook Web App), чтобы разрешить отправку и получение сообщений с защитой S/MIME. Используйте **get-SmimeConfig** и **Set-SmimeConfig** для просмотра и управления этой функцией в Exchange Online PowerShell. Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Подробные сведения о синтаксисах и параметрах см. в описании [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) и [Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Вопросы, которые следует учитывать при новых решениях Microsoft Edge (на основе Chromium)

Чтобы использовать S/MIME в Outlook в Интернете в новом веб-браузере [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) необходимо установить и настроить политику браузера Microsoft Edge с именем **ExtensionInstallForcelist,** чтобы установить расширение Microsoft S/MIME в новом Microsoft Edge. Значение политики: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Обратите внимание, что для применения этой политики требуются устройства, которые присоединяются к домену или к Azure AD, поэтому для использования S/MIME в новом браузере Microsoft Edge фактически требуются устройства, которые присоединяются к домену или к Azure AD.

Подробные сведения о **политике ExtensionInstallForcelist** см. в [списке ExtensionInstallForcelist.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

Это необходимое условие для использования нового Microsoft Edge; Он не заменяет установленный пользователями контроль S/MIME. При первом использовании S/MIME пользователям будет предложено скачать и установить в Outlook в Интернете контроль S/MIME. Кроме того, пользователи могут заблаговременно перейти к **S/MIME** в своих параметрах Outlook в Интернете, чтобы получить ссылку для скачивания для этого управления.

## <a name="considerations-for-chrome"></a>Вопросы, которые следует учитывать при chrome

Чтобы использовать S/MIME в Outlook в Интернете в веб-браузере Google Chrome, вам (или другому администратору) необходимо установить расширение Microsoft S/MIME в Chrome и настроить политику Chromium с именем **ExtensionInstallForcelist.** Значение политики: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Обратите внимание, что для применения этой политики требуются компьютеры, присоединимые к домену, поэтому для использования S/MIME в Chrome фактически требуются компьютеры, присоединимые к домену.

Подробные сведения о **политике ExtensionInstallForcelist** см. в [списке ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

Это необходимое условие для использования Chrome; Он не заменяет установленный пользователями контроль S/MIME. При первом использовании S/MIME пользователям будет предложено скачать и установить в Outlook в Интернете контроль S/MIME. Кроме того, пользователи могут заблаговременно перейти к **S/MIME** в своих параметрах Outlook в Интернете, чтобы получить ссылку для скачивания для этого управления.

## <a name="for-more-information"></a>Дополнительные сведения

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)
