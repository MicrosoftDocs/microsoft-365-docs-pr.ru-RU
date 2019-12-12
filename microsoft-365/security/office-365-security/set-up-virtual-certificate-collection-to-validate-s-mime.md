---
title: Настройка коллекции виртуальных сертификатов в Exchange Online для проверки S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Администраторы могут узнать, как создать коллекцию виртуальных сертификатов, которая будет использоваться для проверки сертификатов S/MIME в Exchange Online.
ms.openlocfilehash: f7ccd9995c51385c2d3152bdecc7b9e51ed7456b
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970125"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="7e843-103">Настройка коллекции виртуальных сертификатов в Exchange Online для проверки S/MIME</span><span class="sxs-lookup"><span data-stu-id="7e843-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="7e843-104">В качестве администратора вам потребуется настроить виртуальную коллекцию сертификатов в Exchange Online, которая будет использоваться для проверки сертификатов S/MIME.</span><span class="sxs-lookup"><span data-stu-id="7e843-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="7e843-105">Эта коллекция виртуальных сертификатов настроена как хранилище сертификатов с расширением имени файла SST.</span><span class="sxs-lookup"><span data-stu-id="7e843-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="7e843-106">SST-файл содержит все корневые и промежуточные сертификаты, которые используются при проверке сертификата S/MIME.</span><span class="sxs-lookup"><span data-stu-id="7e843-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="7e843-107">Создание и сохранение SST-файла</span><span class="sxs-lookup"><span data-stu-id="7e843-107">Create and save an SST</span></span>

<span data-ttu-id="7e843-108">Вы можете создать SST файл хранилища сертификатов, экспортировав сертификаты с доверенного компьютера, используя командлет **Export/Certificate** в Windows PowerShell, и указав _тип_ значения SST.</span><span class="sxs-lookup"><span data-stu-id="7e843-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="7e843-109">Инструкции можно найти в разделе [Export/Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="7e843-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="7e843-110">Когда у вас будет файл хранилища сертификатов SST, используйте следующий синтаксис в Exchange Online PowerShell, чтобы сохранить содержимое SST-файла в виртуальном хранилище сертификатов Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7e843-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="7e843-111">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7e843-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="7e843-112">В этом примере импортируется SST файл с параметром Documents\exported Rules Certificate Store. SST. SST.</span><span class="sxs-lookup"><span data-stu-id="7e843-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="7e843-113">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="7e843-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="7e843-114">Проверка действительности сертификата</span><span class="sxs-lookup"><span data-stu-id="7e843-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="7e843-115">В Exchange Online для проверки сертификата используется только SST.</span><span class="sxs-lookup"><span data-stu-id="7e843-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="7e843-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7e843-116">More Information</span></span>

[<span data-ttu-id="7e843-117">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="7e843-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="7e843-118">Get — SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="7e843-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig)
