---
title: Шифрование службы
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
ms.openlocfilehash: e69d35f08070e1fe092ca8a9b4aef6d179711121
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717350"
---
# <a name="service-encryption"></a><span data-ttu-id="8f93d-103">Шифрование службы</span><span class="sxs-lookup"><span data-stu-id="8f93d-103">Service Encryption</span></span>

<span data-ttu-id="8f93d-104">В дополнение к использованию шифрования на уровне тома, Exchange Online, Skype для бизнеса, SharePoint Online и OneDrive для бизнеса также следует использовать шифрование службы для шифрования данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="8f93d-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="8f93d-105">Шифрование службы позволяет использовать два параметра управления ключами:</span><span class="sxs-lookup"><span data-stu-id="8f93d-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="8f93d-106">Управляемые клавиши Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="8f93d-106">Microsoft managed keys:</span></span> 
<span data-ttu-id="8f93d-107">Корпорация Майкрософт управляет всеми ключами шифрования, в том числе корневыми ключами для шифрования службы.</span><span class="sxs-lookup"><span data-stu-id="8f93d-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="8f93d-108">В настоящее время этот параметр доступен в SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8f93d-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="8f93d-109">Для Exchange Online в данный момент выполняется развертывание этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8f93d-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="8f93d-110">Управляемые ключи корпорации Майкрософт предоставляют шифрование службы по умолчанию, если вы не решили использовать ключ клиента.</span><span class="sxs-lookup"><span data-stu-id="8f93d-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="8f93d-111">Если позднее вы решили прекратить использование ключа клиента без указания пути очистки данных, данные будут зашифрованы с использованием управляемых ключей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f93d-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="8f93d-112">Данные по умолчанию всегда шифруются на этом уровне по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8f93d-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="8f93d-113">Ключ клиента:</span><span class="sxs-lookup"><span data-stu-id="8f93d-113">Customer Key:</span></span> 
<span data-ttu-id="8f93d-114">Вы предоставляете корневые ключи, используемые с шифрованием служб, и управляете этими ключами с помощью Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="8f93d-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="8f93d-115">Корпорация Майкрософт управляет всеми остальными ключами.</span><span class="sxs-lookup"><span data-stu-id="8f93d-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="8f93d-116">Этот параметр называется ключом клиента и в настоящее время доступен для Exchange Online, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8f93d-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="8f93d-117">(Ранее называлось расширенным шифрованием с БЙОК.</span><span class="sxs-lookup"><span data-stu-id="8f93d-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="8f93d-118">Ознакомьтесь со статьей [улучшение прозрачности и управления для пользователей Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) для первоначального объявления.)</span><span class="sxs-lookup"><span data-stu-id="8f93d-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="8f93d-119">Шифрование службы предоставляет несколько преимуществ.</span><span class="sxs-lookup"><span data-stu-id="8f93d-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="8f93d-120">Например, ключ клиента:</span><span class="sxs-lookup"><span data-stu-id="8f93d-120">For example, Customer Key:</span></span>

- <span data-ttu-id="8f93d-121">Предоставляет функции защиты и управления правами на основе надежной защиты шифрования.</span><span class="sxs-lookup"><span data-stu-id="8f93d-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="8f93d-122">Включает в себя ключ клиента, который позволяет службам, поддерживающим несколько клиентов, обеспечивать управление ключами клиентов.</span><span class="sxs-lookup"><span data-stu-id="8f93d-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="8f93d-123">Обеспечивает разделение администраторов операционной системы Windows от доступа к данным клиентов, хранящимся или обрабатываемым операционной системой.</span><span class="sxs-lookup"><span data-stu-id="8f93d-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="8f93d-124">Расширяет возможности Microsoft 365 для удовлетворения требований клиентов, имеющих требования по обеспечению соответствия требованиям для шифрования.</span><span class="sxs-lookup"><span data-stu-id="8f93d-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="8f93d-125">С помощью ключа клиента вы можете создавать собственные криптографические ключи с помощью локального модуля службы оборудования (HSM) или Azure Key Vault (АКВ).</span><span class="sxs-lookup"><span data-stu-id="8f93d-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="8f93d-126">Независимо от того, как вы создаете ключ, вы можете использовать АКВ для управления ключами шифрования, используемыми в Office 365, и управления ими.</span><span class="sxs-lookup"><span data-stu-id="8f93d-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="8f93d-127">После сохранения ключей в АКВ их можно использовать в качестве корня одного из кэйчаинс, который шифрует данные почтовых ящиков или файлы.</span><span class="sxs-lookup"><span data-stu-id="8f93d-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="8f93d-128">Еще одним преимуществом ключа клиента является элемент управления, получающий возможность обработки данных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f93d-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="8f93d-129">Если вы хотите удалить данные из Office 365, например, если вы хотите прерывать обслуживание с корпорацией Майкрософт или удалить часть данных, хранящихся в облаке, вы можете использовать ключ клиента в качестве технического контроля.</span><span class="sxs-lookup"><span data-stu-id="8f93d-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="8f93d-130">Это гарантирует, что никто, включая Майкрософт, сможет получить доступ к данным или обработать их.</span><span class="sxs-lookup"><span data-stu-id="8f93d-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="8f93d-131">Ключ клиента является дополнительным и дополнительным абонентским ящиком, используемым для управления доступом к данным сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8f93d-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="8f93d-132">Сведения о том, как настроить ключ клиента для Microsoft 365 для Exchange Online, Skype для бизнеса, SharePoint Online, включая сайты групп и OneDrive для бизнеса, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="8f93d-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="8f93d-133">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="8f93d-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="8f93d-134">Настройка ключа клиента</span><span class="sxs-lookup"><span data-stu-id="8f93d-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="8f93d-135">Управление ключом клиента</span><span class="sxs-lookup"><span data-stu-id="8f93d-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="8f93d-136">Вращение или поворот ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="8f93d-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="8f93d-137">Общие сведения о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="8f93d-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

