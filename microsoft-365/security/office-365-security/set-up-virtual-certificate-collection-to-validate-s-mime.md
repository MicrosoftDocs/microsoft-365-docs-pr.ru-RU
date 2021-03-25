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
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="44a9b-103">Настройка виртуальной коллекции сертификатов в Exchange Online для проверки S/MIME</span><span class="sxs-lookup"><span data-stu-id="44a9b-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="44a9b-104">В качестве администратора необходимо настроить виртуальную коллекцию сертификатов в Exchange Online, которая будет использоваться для проверки сертификатов S/MIME.</span><span class="sxs-lookup"><span data-stu-id="44a9b-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="44a9b-105">Эта виртуальная коллекция сертификатов настроена как хранилище сертификатов с расширением SST-файла.</span><span class="sxs-lookup"><span data-stu-id="44a9b-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="44a9b-106">SST-файл содержит все корневые и промежуточные сертификаты, которые используются при проверке сертификата S/MIME.</span><span class="sxs-lookup"><span data-stu-id="44a9b-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="44a9b-107">Создание и сохранение SST-файла</span><span class="sxs-lookup"><span data-stu-id="44a9b-107">Create and save an SST</span></span>

<span data-ttu-id="44a9b-108">Этот файл хранения сертификатов SST можно создать, экспортив  сертификаты из доверенного компьютера с помощью Windows PowerShell экспорта и указав значение _Type_ as SST.</span><span class="sxs-lookup"><span data-stu-id="44a9b-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="44a9b-109">Инструкции см. в [справке Экспорт-Сертификат.](/powershell/module/pkiclient/export-certificate)</span><span class="sxs-lookup"><span data-stu-id="44a9b-109">For instructions, see [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="44a9b-110">Если у вас есть файл магазина сертификатов SST, используйте следующий синтаксис в Exchange Online PowerShell для сохранения содержимого SST-файлов в виртуальном хранилище сертификатов Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="44a9b-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="44a9b-111">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="44a9b-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="44a9b-112">В этом примере импортируется SST-файл C:\My Documents\Exported Certificate Store.sst.</span><span class="sxs-lookup"><span data-stu-id="44a9b-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="44a9b-113">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="44a9b-113">For detailed syntax and parameter information, see [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="44a9b-114">Проверка действительности сертификата</span><span class="sxs-lookup"><span data-stu-id="44a9b-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="44a9b-115">В Exchange Online для проверки сертификатов используется только SST.</span><span class="sxs-lookup"><span data-stu-id="44a9b-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="44a9b-116">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="44a9b-116">More Information</span></span>

[<span data-ttu-id="44a9b-117">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="44a9b-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="44a9b-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="44a9b-118">Get-SmimeConfig</span></span>](/powershell/module/exchange/get-smimeconfig)