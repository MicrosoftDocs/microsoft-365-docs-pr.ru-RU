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
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Сводка: сведения о устойчивости данных в Microsoft Office 365.'
ms.openlocfilehash: 5b22584e677dd4815b991b4e95b5ad59feb2fbc2
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799549"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="28616-103">Шифрование служб Office 365</span><span class="sxs-lookup"><span data-stu-id="28616-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="28616-104">В дополнение к использованию шифрования на уровне тома, Exchange Online, Skype для бизнеса, SharePoint Online и OneDrive для бизнеса также следует использовать шифрование службы для шифрования данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="28616-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="28616-105">Шифрование службы позволяет использовать два параметра управления ключами:</span><span class="sxs-lookup"><span data-stu-id="28616-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="28616-106">Корпорация Майкрософт управляет всеми ключами шифрования.</span><span class="sxs-lookup"><span data-stu-id="28616-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="28616-107">(В настоящее время этот параметр доступен в SharePoint Online, OneDrive для бизнеса и Skype для бизнеса.)</span><span class="sxs-lookup"><span data-stu-id="28616-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="28616-108">Клиент предоставляет корневые ключи, используемые с шифрованием служб, а клиент управляет этими ключами с помощью Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="28616-108">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault.</span></span> <span data-ttu-id="28616-109">Корпорация Майкрософт управляет всеми остальными ключами.</span><span class="sxs-lookup"><span data-stu-id="28616-109">Microsoft manages all other keys.</span></span> <span data-ttu-id="28616-110">Этот параметр называется ключом клиента и в настоящее время доступен для Exchange Online, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="28616-110">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="28616-111">(Ранее называлось расширенным шифрованием с БЙОК.</span><span class="sxs-lookup"><span data-stu-id="28616-111">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="28616-112">Ознакомьтесь со статьей [улучшение прозрачности и управления для пользователей Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) для первоначального объявления.)</span><span class="sxs-lookup"><span data-stu-id="28616-112">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="28616-113">Шифрование службы предоставляет несколько преимуществ.</span><span class="sxs-lookup"><span data-stu-id="28616-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="28616-114">Например, ключ клиента:</span><span class="sxs-lookup"><span data-stu-id="28616-114">For example, Customer Key:</span></span>

- <span data-ttu-id="28616-115">Предоставляет функции защиты и управления правами на основе надежной защиты шифрования.</span><span class="sxs-lookup"><span data-stu-id="28616-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="28616-116">Включает в себя ключ клиента, который позволяет службам, поддерживающим несколько клиентов, обеспечивать управление ключами клиентов.</span><span class="sxs-lookup"><span data-stu-id="28616-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="28616-117">Обеспечивает разделение администраторов операционной системы Windows от доступа к данным клиентов, хранящимся или обрабатываемым операционной системой.</span><span class="sxs-lookup"><span data-stu-id="28616-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="28616-118">Расширяет возможности Office 365 для удовлетворения требований клиентов, имеющих требования по обеспечению соответствия требованиям для шифрования.</span><span class="sxs-lookup"><span data-stu-id="28616-118">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="28616-119">Ключ клиента</span><span class="sxs-lookup"><span data-stu-id="28616-119">Customer Key</span></span>

<span data-ttu-id="28616-120">С помощью ключа клиента вы можете создавать собственные криптографические ключи с помощью локального модуля службы оборудования (HSM) или Azure Key Vault (АКВ).</span><span class="sxs-lookup"><span data-stu-id="28616-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="28616-121">Независимо от того, как вы создаете ключ, вы можете использовать АКВ для управления ключами шифрования, используемыми в Office 365, и управления ими.</span><span class="sxs-lookup"><span data-stu-id="28616-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="28616-122">После сохранения ключей в АКВ их можно использовать в качестве корня одного из кэйчаинс, который шифрует данные почтовых ящиков или файлы.</span><span class="sxs-lookup"><span data-stu-id="28616-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="28616-123">Еще одним преимуществом ключа клиента является элемент управления, получающий возможность обработки данных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="28616-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="28616-124">Если вы хотите удалить данные из Office 365, например, если вы хотите прерывать обслуживание с корпорацией Майкрософт или удалить часть данных, хранящихся в облаке, вы можете использовать ключ клиента в качестве технического контроля.</span><span class="sxs-lookup"><span data-stu-id="28616-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="28616-125">Это гарантирует, что никто, включая Майкрософт, сможет получить доступ к данным или обработать их.</span><span class="sxs-lookup"><span data-stu-id="28616-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="28616-126">Ключ клиента является дополнительным и дополнительным абонентским ящиком, используемым для управления доступом к данным сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="28616-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="28616-127">Сведения о том, как настроить ключ клиента для Office 365 для Exchange Online, Skype для бизнеса, SharePoint Online, включая сайты групп и OneDrive для бизнеса, приведены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="28616-127">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="28616-128">Шифрование службы с помощью ключа клиента в Office 365</span><span class="sxs-lookup"><span data-stu-id="28616-128">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="28616-129">Настройка ключа клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="28616-129">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="28616-130">Управление ключом клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="28616-130">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="28616-131">Вращение или поворот ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="28616-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="28616-132">Общие сведения о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="28616-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 