---
title: Настройка параметров S/MIME - Exchange Online для Outlook в Интернете
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
ms.openlocfilehash: 6ab1aaabf0e7651a5a84642c178c28961430eea0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906484"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Настройка параметров S/MIME в Exchange Online для Outlook в Интернете

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В качестве администратора Exchange Online можно настроить Outlook в Интернете (ранее известный как Outlook Web App), чтобы разрешить отправку и получение сообщений, защищенных S/MIME. Для просмотра и управления этой функцией в Exchange Online PowerShell используйте комлеты **Get-SmimeConfig** и **Set-SmimeConfig.** Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Подробные сведения о синтаксисах и параметрах см. в [сведениях Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) и [Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Соображения для нового Microsoft Edge (на основе хрома)

Чтобы использовать S/MIME в Outlook в Интернете в новом веб-браузере [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) вам (или другому администратору) необходимо установить и настроить политику браузера Microsoft Edge с именем **ExtensionInstallForcelist** для установки расширения Microsoft S/MIME в новом Microsoft Edge. Значение политики `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Обратите внимание, что для применения этой политики требуются устройства, присоединившись к домену или к Azure AD, поэтому для использования S/MIME в новом браузере Microsoft Edge эффективно требуются устройства, присоединившись к домену или к Azure AD.

Сведения о политике **ExtensionInstallForcelist** см. в [материале ExtensionInstallForcelist.](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

Этот шаг является обязательным условием для использования нового Microsoft Edge; он не заменяет установленный пользователями контроль S/MIME. Пользователям предложено скачать и установить управление S/MIME в Outlook в Интернете во время первого использования S/MIME. Или пользователи могут упреждающим образом перейти в **S/MIME** в Outlook на веб-параметры, чтобы получить ссылку на скачивание для управления.

## <a name="considerations-for-chrome"></a>Соображения для Chrome

Чтобы использовать S/MIME в Outlook в веб-браузере Google Chrome, вам (или другому администратору) необходимо установить и настроить политику Chromium с именем **ExtensionInstallForcelist** для установки расширения Microsoft S/MIME в Chrome. Значение политики `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . И обратите внимание, что для применения этой политики требуются компьютеры, присоединившись к домену, поэтому для использования S/MIME в Chrome эффективно требуются компьютеры, присоединившись к домену.

Сведения о политике **ExtensionInstallForcelist** см. в [материале ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

Этот шаг является обязательным условием для использования Chrome; он не заменяет установленный пользователями контроль S/MIME. Пользователям предложено скачать и установить управление S/MIME в Outlook в Интернете во время первого использования S/MIME. Или пользователи могут упреждающим образом перейти в **S/MIME** в Outlook на веб-параметры, чтобы получить ссылку на скачивание для управления.

## <a name="for-more-information"></a>Дополнительные сведения

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)