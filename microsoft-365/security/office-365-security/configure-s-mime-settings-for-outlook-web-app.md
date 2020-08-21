---
title: Настройка параметров S/MIME — Exchange Online для Outlook в Интернете
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Краткое описание действий администратора Exchange Online для просмотра и настройки параметров S/MIME в Outlook в Интернете в Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825705"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Настройка параметров S/MIME в Exchange Online для Outlook в Интернете

Как администратор Exchange Online вы можете настроить Outlook в Интернете (прежнее название Outlook Web App) для разрешения отправки и получения сообщений с защитой S/MIME. Просмотр этой функции в Exchange Online PowerShell и управление ими с помощью командлетов **Get-SmimeConfig** и **Set-SmimeConfig.** Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Дополнительные сведения о синтаксисе и параметрах см. в [разделе Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) и [Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Рекомендации по созданию новой версии Microsoft Edge (на основе Chromium)

Чтобы использовать S/MIME в Outlook в Интернете в новом веб-браузере [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) необходимо (или другой администратор) настроить политику браузера Microsoft Edge **с именем ExtensionInstallForcelist, чтобы** установить расширение Microsoft S/MIME в новом Microsoft Edge. Значение `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` политики. Следует отметить, что для применения этой политики требуется присоединенные к домену или Azure AD устройства, поэтому для использования S/MIME в новом браузере Microsoft Edge необходимо присоединенные к домену или Azure AD устройства.

Дополнительные сведения о **политике ExtensionInstallForcelist** см. в [описании значения ExtensionInstallForcelist.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

Этот шаг является необходимым условием для использования новой версии Microsoft Edge; Он не заменяет элемент управления S/MIME, установленный пользователями. Пользователям предлагается загрузить и установить элемент управления S/MIME в Outlook в Интернете во время первого использования S/MIME. Кроме того, пользователи могут заблагоприятно перейти к **s/MIME** в параметрах Outlook в Интернете, чтобы получить ссылку для скачивания для элемента управления.

## <a name="considerations-for-chrome"></a>Рекомендации для Chrome

Чтобы использовать S/MIME в Outlook в Интернете в веб-браузере Google Chrome, необходимо (или другой администратор) настроить политику Chromium **с именем ExtensionInstallForcelist,** чтобы установить расширение Microsoft S/MIME в Chrome. Значение `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` политики. Кроме того, обратите внимание, что для применения этой политики требуется присоединенные к домену компьютеры, поэтому для использования S/MIME в Chrome для эффективного использования компьютеров, присоединенных к домену, требуется компьютеры, присоединенные к домену.

Дополнительные сведения о **политике ExtensionInstallForcelist** см. в [описании значения ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

Этот шаг является необходимым условием для использования Chrome; Он не заменяет элемент управления S/MIME, установленный пользователями. Пользователям предлагается загрузить и установить элемент управления S/MIME в Outlook в Интернете во время первого использования S/MIME. Кроме того, пользователи могут заблагоприятно перейти к **s/MIME** в параметрах Outlook в Интернете, чтобы получить ссылку для скачивания для элемента управления.

## <a name="for-more-information"></a>Дополнительные сведения

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)
