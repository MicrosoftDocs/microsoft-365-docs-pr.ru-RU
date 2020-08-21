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
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="b3368-103">Настройка коллекции виртуальных сертификатов в Exchange Online для проверки S/MIME</span><span class="sxs-lookup"><span data-stu-id="b3368-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="b3368-104">Администратору потребуется настроить коллекцию виртуальных сертификатов в Exchange Online, которая будет использоваться для проверки сертификатов S/MIME.</span><span class="sxs-lookup"><span data-stu-id="b3368-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="b3368-105">Эта коллекция виртуальных сертификатов настроена как хранилище сертификатов с расширением имени файла SST.</span><span class="sxs-lookup"><span data-stu-id="b3368-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="b3368-106">SST-файл содержит все корневые и промежуточные сертификаты, которые используются при проверке сертификата S/MIME.</span><span class="sxs-lookup"><span data-stu-id="b3368-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="b3368-107">Создание и сохранение SST-файла</span><span class="sxs-lookup"><span data-stu-id="b3368-107">Create and save an SST</span></span>

<span data-ttu-id="b3368-108">Можно создать этот файл хранилища сертификатов SST, экспортировав сертификаты с доверенного компьютера с помощью **командлета Export-Certificate** в Windows PowerShell и указав тип значения _sST._</span><span class="sxs-lookup"><span data-stu-id="b3368-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="b3368-109">Инструкции см. в [статье, посвященной Командлету Export-Certificate.](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)</span><span class="sxs-lookup"><span data-stu-id="b3368-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="b3368-110">После создания файла хранилища сертификатов для SST-файла используйте следующий синтаксис в Exchange Online PowerShell, чтобы сохранить содержимое SST-файлов в виртуальном хранилище сертификатов Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b3368-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="b3368-111">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b3368-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="b3368-112">В этом примере импортируется SST-файл C:\My Documents\Exported Certificate Store.sst.</span><span class="sxs-lookup"><span data-stu-id="b3368-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="b3368-113">Дополнительные сведения о синтаксисе и параметрах см. в [статье Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="b3368-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="b3368-114">Проверка действительности сертификата</span><span class="sxs-lookup"><span data-stu-id="b3368-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="b3368-115">В Exchange Online для проверки сертификатов используется только SST.</span><span class="sxs-lookup"><span data-stu-id="b3368-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="b3368-116">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="b3368-116">More Information</span></span>

[<span data-ttu-id="b3368-117">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="b3368-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="b3368-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="b3368-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
