---
title: Шифрование служб Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Сводка. сведения о шифровании данных на уровне службы в Microsoft Office 365.
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193465"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="3c427-103">Шифрование служб Office 365</span><span class="sxs-lookup"><span data-stu-id="3c427-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="3c427-104">В дополнение к использованию BitLocker для шифрования на уровне тома, Exchange Online, Skype для бизнеса, SharePoint Online, OneDrive для бизнеса и Teams также используют шифрование служб для шифрования данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="3c427-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="3c427-105">Шифрование службы позволяет использовать два параметра управления ключами:</span><span class="sxs-lookup"><span data-stu-id="3c427-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="3c427-106">Корпорация Майкрософт управляет всеми ключами шифрования.</span><span class="sxs-lookup"><span data-stu-id="3c427-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="3c427-107">В настоящее время этот параметр доступен в SharePoint Online, OneDrive для бизнеса, Skype для бизнеса и командах чата.</span><span class="sxs-lookup"><span data-stu-id="3c427-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="3c427-108">По умолчанию данные шифруются с помощью управляемых ключей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3c427-108">Your data is encrypted by default with Microsoft managed keys.</span></span>

- <span data-ttu-id="3c427-109">Ваша организация предоставляет корневые ключи.</span><span class="sxs-lookup"><span data-stu-id="3c427-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="3c427-110">Управление этими ключами осуществляется с помощью Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="3c427-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="3c427-111">Этот параметр называется ключом клиента.</span><span class="sxs-lookup"><span data-stu-id="3c427-111">This option is called Customer Key.</span></span> <span data-ttu-id="3c427-112">В настоящее время ключ клиента доступен для файлов Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса и Teams.</span><span class="sxs-lookup"><span data-stu-id="3c427-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="3c427-113">Если вы используете ключ клиента, эти ключи заменяют управляемые ключи Майкрософт для шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="3c427-113">If you use Customer Key, these keys replace Microsoft managed keys to encrypt your data.</span></span>

<span data-ttu-id="3c427-114">Независимо от выбранного варианта шифрование службы предоставляет несколько преимуществ:</span><span class="sxs-lookup"><span data-stu-id="3c427-114">Regardless of the option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="3c427-115">Обеспечивает проверку подлинности пользователей для получения и расшифровки данных, запрашиваемых авторизованным пользователем.</span><span class="sxs-lookup"><span data-stu-id="3c427-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="3c427-116">Обеспечивает разделение администраторов операционной системы Windows от доступа к данным клиентов, хранящимся или обрабатываемым операционной системой.</span><span class="sxs-lookup"><span data-stu-id="3c427-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="3c427-117">Расширяет возможности Office 365 для удовлетворения требований клиентов, имеющих требования по обеспечению соответствия требованиям для шифрования.</span><span class="sxs-lookup"><span data-stu-id="3c427-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="3c427-118">Сведения о том, как настроить ключ клиента для Office 365 для Exchange Online, Skype для бизнеса, SharePoint Online, OneDrive для бизнеса и файлов Teams, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="3c427-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="3c427-119">Шифрование службы с помощью ключа клиента в Office 365</span><span class="sxs-lookup"><span data-stu-id="3c427-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="3c427-120">Настройка ключа клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c427-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="3c427-121">Управление ключом клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="3c427-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="3c427-122">Вращение или поворот ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="3c427-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="3c427-123">Общие сведения о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="3c427-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
