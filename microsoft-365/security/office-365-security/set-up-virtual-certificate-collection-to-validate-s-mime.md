---
title: Настройка виртуальной коллекции сертификатов - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Администраторы могут узнать, как создать виртуальную коллекцию сертификатов, которая будет использоваться для проверки сертификатов S/MIME в Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206807"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Настройка виртуальной коллекции сертификатов в Exchange Online для проверки S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


В качестве администратора необходимо настроить виртуальную коллекцию сертификатов в Exchange Online, которая будет использоваться для проверки сертификатов S/MIME. Эта виртуальная коллекция сертификатов настроена как хранилище сертификатов с расширением SST-файла. SST-файл содержит все корневые и промежуточные сертификаты, которые используются при проверке сертификата S/MIME.

## <a name="create-and-save-an-sst"></a>Создание и сохранение SST-файла

Этот файл хранения сертификатов SST можно создать, экспортив  сертификаты из доверенного компьютера с помощью Windows PowerShell экспорта и указав значение _Type_ as SST. Инструкции см. в [справке Экспорт-Сертификат.](/powershell/module/pkiclient/export-certificate)

Если у вас есть файл магазина сертификатов SST, используйте следующий синтаксис в Exchange Online PowerShell для сохранения содержимого SST-файлов в виртуальном хранилище сертификатов Exchange Online. Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

В этом примере импортируется SST-файл C:\My Documents\Exported Certificate Store.sst.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)

## <a name="ensuring-a-certificate-is-valid"></a>Проверка действительности сертификата

В Exchange Online для проверки сертификатов используется только SST.

## <a name="more-information"></a>Дополнительная информация

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)