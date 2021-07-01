---
title: Настройка шифрования в Office 365 корпоративный
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: С Office 365 некоторые возможности шифрования включены по умолчанию; другие возможности можно настроить для соответствия определенным требованиям или требованиям законодательства.
ms.openlocfilehash: a9a3170fdb99a4acfec8cf4d3b03ab9b584197bd
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228475"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Настройка шифрования в Office 365 корпоративный

Шифрование может защитить содержимое от чтения несанкционированными пользователями. Поскольку [шифрование в Office 365](encryption.md) можно сделать с помощью различных технологий и методов, нет ни одного места, где можно включить или настроить шифрование. В этой статье содержится информация о различных способах настройки или настройки шифрования в рамках стратегии защиты информации.

> [!TIP]
> Если вы ищете дополнительные технические сведения о шифровании, см. в материале [Technical reference details about encryption in Office 365.](technical-reference-details-about-encryption.md)

С Office 365 по умолчанию доступны несколько возможностей шифрования. Дополнительные возможности шифрования можно настроить для соответствия определенным требованиям или требованиям законодательства. В следующей таблице описано несколько методов шифрования для различных сценариев.

<br>

****

|Сценарий|Методы шифрования|
|---|---|
|Файлы сохраняются на Windows компьютерах|Шифрование на уровне компьютера можно сделать с помощью BitLocker на Windows устройствах. В качестве администратора предприятия или ИТ-Pro это можно настроить с помощью службы развертывания Microsoft набор средств (MDT). См. [в настройках MDT для BitLocker.](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)|
|Файлы сохраняются на мобильных устройствах|Некоторые виды мобильных устройств шифруют файлы, которые сохраняются на этих устройствах по умолчанию. С [помощью возможностей](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)встроенной Управление мобильными устройствами для Office 365 можно установить политики, определяя, следует ли разрешить мобильным устройствам доступ к данным в Office 365. Например, можно установить политику, которая позволяет только устройствам, шифруя контент, получать доступ Office 365 данным. См. [в руб. Создание и развертывание политик безопасности устройств.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6) <p> Дополнительный контроль за взаимодействием мобильных устройств с Office 365 можно добавить [Microsoft Intune.](/mem/intune/fundamentals/setup-steps)|
|Необходим контроль над ключами шифрования, используемыми для шифрования данных в центрах обработки данных Майкрософт|Будучи администратором Office 365, вы можете управлять ключами шифрования организации, а затем Office 365 использовать их для шифрования данных в центрах обработки данных Майкрософт. <p> [Шифрование службы с помощью ключа клиента в Office 365](customer-key-overview.md)|
|Люди общаются по электронной почте (Exchange Online)|Как администратор Exchange Online, у вас есть несколько вариантов настройки шифрования электронной почты. Эти решения перечислены ниже. <ul><li>Использование [Office 365 шифрования сообщений (OME)](set-up-new-message-encryption-capabilities.md) с помощью Azure Rights Management (Azure RMS), чтобы позволить пользователям отправлять зашифрованные сообщения в организации или за ее пределами.</li><li>Использование [S/MIME для](/exchange/security-and-compliance/smime-exo/smime-exo) шифрования и цифрового подписания сообщений электронной почты</li><li>Использование TLS для [настроить соединители для безопасного потока почты с другой организацией](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> См. [в Office 365.](./email-encryption.md)|
|Доступ к файлам из сайтов группы или библиотек документов (OneDrive для бизнеса или SharePoint Online)|При работе с файлами, сохраненными для OneDrive для бизнеса или SharePoint Online, используются подключения TLS. Это встроено в Office 365 автоматически. См. [в OneDrive для бизнеса и SharePoint Online.](./data-encryption-in-odb-and-spo.md)|
|Файлы делятся в онлайн-собраниях и чатах (Skype для бизнеса Online)|Когда люди работают с файлами с Skype для бизнеса Online, для подключения используется TLS. Это встроено в Office 365 автоматически. См. в интернете службы [безопасности и архива (Skype для бизнеса Online).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)|
|Файлы делятся в онлайн-собраниях и беседах по чату (Microsoft Teams)|Когда люди работают с файлами с Microsoft Teams, для подключения используется TLS. Это встроено в Office 365 автоматически. Microsoft Teams в настоящее время не поддерживает отрисовку зашифрованной электронной почты. Чтобы зашифрованная электронная почта не приземлилась в Microsoft Teams как зашифрованная, см. в [faq шифрования сообщений.](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)|
|

## <a name="additional-information"></a>Дополнительные сведения

Дополнительные материалы о решениях защиты файлов, которые включают параметры шифрования, см. в [Office 365.](https://www.microsoft.com/download/details.aspx?id=55523)
