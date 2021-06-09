---
title: Шифрование служб
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
description: Сводка. Понимание устойчивости данных в Microsoft Office 365.
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058552"
---
# <a name="service-encryption"></a><span data-ttu-id="9ccae-103">Шифрование служб</span><span class="sxs-lookup"><span data-stu-id="9ccae-103">Service Encryption</span></span>

<span data-ttu-id="9ccae-104">В дополнение к использованию шифрования на уровне тома, Exchange Online, Microsoft Teams, SharePoint Online и OneDrive для бизнеса шифрование служб для шифрования данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="9ccae-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="9ccae-105">Шифрование служб позволяет использовать два ключевых варианта управления:</span><span class="sxs-lookup"><span data-stu-id="9ccae-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="9ccae-106">Клавиши с управлением Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9ccae-106">Microsoft-managed keys</span></span>
<span data-ttu-id="9ccae-107">Корпорация Майкрософт управляет всеми криптографическими ключами, включая корневые ключи шифрования службы.</span><span class="sxs-lookup"><span data-stu-id="9ccae-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="9ccae-108">Этот параметр в настоящее время включен по умолчанию для Exchange Online, SharePoint Online, OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9ccae-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="9ccae-109">Управляемые Microsoft ключи обеспечивают шифрование служб по умолчанию, если только вы не решите использовать ключ клиента на борту.</span><span class="sxs-lookup"><span data-stu-id="9ccae-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="9ccae-110">Если позднее вы решите прекратить использование ключа клиента, не следуя пути очистки данных, ваши данные будут зашифрованы с помощью ключей, управляемых Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9ccae-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="9ccae-111">Ваши данные всегда шифруются на этом уровне по умолчанию как минимум.</span><span class="sxs-lookup"><span data-stu-id="9ccae-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="9ccae-112">Ключ клиента</span><span class="sxs-lookup"><span data-stu-id="9ccae-112">Customer Key</span></span>
<span data-ttu-id="9ccae-113">Вы поставляете корневые ключи, используемые с шифрованием службы, и управляете этими ключами с помощью Хранилища ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="9ccae-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="9ccae-114">Корпорация Майкрософт управляет всеми другими ключами.</span><span class="sxs-lookup"><span data-stu-id="9ccae-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="9ccae-115">Этот параметр называется Ключ клиента, и в настоящее время он доступен для Exchange Online, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9ccae-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="9ccae-116">(Ранее именуемая расширенным шифрованием с ПОМОЩЬЮ BYOK.</span><span class="sxs-lookup"><span data-stu-id="9ccae-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="9ccae-117">См. [в сообщении](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) Об усилении прозрачности и управления для Office 365 клиентов для исходного объявления.)</span><span class="sxs-lookup"><span data-stu-id="9ccae-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="9ccae-118">Шифрование службы предоставляет несколько преимуществ:</span><span class="sxs-lookup"><span data-stu-id="9ccae-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="9ccae-119">Обеспечивает дополнительный уровень защиты поверх BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9ccae-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="9ccae-120">Обеспечивает разделение администраторов Windows операционной системы от доступа к данным приложений, хранимым или обрабатываемых операционной системой.</span><span class="sxs-lookup"><span data-stu-id="9ccae-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="9ccae-121">Включает параметр "Ключ клиента", который позволяет нескольким клиентам предоставлять управление ключами для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="9ccae-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="9ccae-122">Повышает возможности Microsoft 365 для удовлетворения требований клиентов с определенными требованиями к шифрованию.</span><span class="sxs-lookup"><span data-stu-id="9ccae-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="9ccae-123">С помощью ключа клиента можно создавать собственные криптографические ключи с помощью локального модуля службы оборудования (HSM) или хранилища ключей Azure (AKV).</span><span class="sxs-lookup"><span data-stu-id="9ccae-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="9ccae-124">Независимо от того, как вы создаете ключ, вы используете AKV для управления криптографическими ключами, используемыми Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ccae-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="9ccae-125">После хранения ключей в AKV они могут использоваться в качестве корневого ключа, шифруемого данными или файлами почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="9ccae-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="9ccae-126">Еще одним преимуществом клиентского ключа является контроль над возможностью Корпорации Майкрософт обрабатывать данные.</span><span class="sxs-lookup"><span data-stu-id="9ccae-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="9ccae-127">Если вы хотите удалить данные из Office 365, например, если вы хотите прекратить службу с Microsoft или удалить часть данных, хранимых в облаке, вы можете сделать это и использовать ключ клиента в качестве технического управления.</span><span class="sxs-lookup"><span data-stu-id="9ccae-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="9ccae-128">Удаление данных гарантирует, что никто, включая Корпорацию Майкрософт, не сможет получить доступ к данным или обработать их.</span><span class="sxs-lookup"><span data-stu-id="9ccae-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="9ccae-129">Ключ клиента дополняется клиентской блокировкой, которую вы используете для управления доступом к данным сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9ccae-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="9ccae-130">Чтобы узнать, как настроить ключ клиента для Microsoft 365 для Exchange Online, Microsoft Teams, SharePoint Online, включая сайты команд и OneDrive для бизнеса, см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="9ccae-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="9ccae-131">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="9ccae-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="9ccae-132">Настройка ключа клиента</span><span class="sxs-lookup"><span data-stu-id="9ccae-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="9ccae-133">Управление ключом клиента</span><span class="sxs-lookup"><span data-stu-id="9ccae-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="9ccae-134">Roll или rotate a customer key or an availability key</span><span class="sxs-lookup"><span data-stu-id="9ccae-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="9ccae-135">Понимание ключа доступности</span><span class="sxs-lookup"><span data-stu-id="9ccae-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
