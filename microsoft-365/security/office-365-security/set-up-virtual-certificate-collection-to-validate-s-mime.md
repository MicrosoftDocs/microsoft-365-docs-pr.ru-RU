---
title: Настройка коллекции виртуальных сертификатов — Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Администраторы могут научиться создавать коллекцию виртуальных сертификатов, которая будет использоваться для проверки сертификатов S/MIME в Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16c6d38882a69feb46aa3e8fadccd6e005426304
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825141"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Настройка коллекции виртуальных сертификатов в Exchange Online для проверки S/MIME

Администратору потребуется настроить коллекцию виртуальных сертификатов в Exchange Online, которая будет использоваться для проверки сертификатов S/MIME. Эта коллекция виртуальных сертификатов настроена как хранилище сертификатов с расширением имени файла SST. SST-файл содержит все корневые и промежуточные сертификаты, которые используются при проверке сертификата S/MIME.

## <a name="create-and-save-an-sst"></a>Создание и сохранение SST-файла

Можно создать этот файл хранилища сертификатов SST, экспортировав сертификаты с доверенного компьютера с помощью **командлета Export-Certificate** в Windows PowerShell и указав тип значения _sST._ Инструкции см. в [статье, посвященной Командлету Export-Certificate.](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)

После создания файла хранилища сертификатов для SST-файла используйте следующий синтаксис в Exchange Online PowerShell, чтобы сохранить содержимое SST-файлов в виртуальном хранилище сертификатов Exchange Online. Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

В этом примере импортируется SST-файл C:\My Documents\Exported Certificate Store.sst.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Дополнительные сведения о синтаксисе и параметрах см. в [статье Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="ensuring-a-certificate-is-valid"></a>Проверка действительности сертификата

В Exchange Online для проверки сертификатов используется только SST.

## <a name="more-information"></a>Дополнительная информация

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
