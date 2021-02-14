---
title: Как Exchange Online защищает секреты вашей электронной почты
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Помимо центра управления безопасностью Office 365, который предоставляет сведения о безопасности, конфиденциальности и соответствии требованиям для Microsoft 365, вам может потребоваться узнать, как Майкрософт помогает защитить секреты, хранимые в центрах обработки данных. Мы используем технологию под названием Распределенный диспетчер ключей (DKM).
ms.openlocfilehash: 17a7fbbd54a725edcd87681f011ddc6633a1f4aa
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615983"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="0a9cc-104">Как Exchange Online защищает секреты вашей электронной почты</span><span class="sxs-lookup"><span data-stu-id="0a9cc-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="0a9cc-105">В этой статье описывается, как корпорация Майкрософт защищает вашу электронную почту в своих центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="0a9cc-106">Как мы защищаем секретные сведения, предоставленные вами?</span><span class="sxs-lookup"><span data-stu-id="0a9cc-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="0a9cc-107">Помимо центра управления безопасностью Office 365, который предоставляет сведения о безопасности, конфиденциальности и соответствии требованиям для [Office 365,](https://go.microsoft.com/fwlink/?linkid=874644)вам может потребоваться узнать, как Майкрософт помогает защитить секреты, которые вы предоставляете в своих центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Microsoft helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="0a9cc-108">Мы используем технологию под названием Распределенный диспетчер ключей (DKM).</span><span class="sxs-lookup"><span data-stu-id="0a9cc-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="0a9cc-109">[Диспетчер распределенных ключей](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) — это клиентская функция, которая использует набор секретных ключей для шифрования и расшифровки информации.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="0a9cc-110">Только члены определенной группы безопасности в доменных службах Active Directory могут получать доступ к этим ключам для расшифровки данных, зашифрованных DKM.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="0a9cc-111">В Exchange Online только некоторые учетные записи служб, под которыми выполняются процессы Exchange, входят в эту группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="0a9cc-112">В рамках стандартной процедуры в центре обработки данных ни один человек не получает учетные данные, включенные в эту группу безопасности, и поэтому ни один человек не получает доступ к ключам, которые могут расшифровать эти секреты.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="0a9cc-p104">Для отладки, устранения неполадок и аудита администратор центра обработки данных должен запросить повышенные права доступа для получения временных учетных данных, которые входят в группу безопасности. Для этого процесса требуется несколько уровней юридического утверждения. Если доступ предоставлен, все действия заносятся в журнал и проходят аудиторскую проверку. Кроме того, доступ предоставляется только в течение заданного интервала, после чего он автоматически отключается.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-p104">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group. This process requires multiple levels of legal approval. If access is granted, all activity is logged and audited. In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="0a9cc-117">Для дополнительной защиты технология DKM использует автоматический откат и архивацию ключей.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="0a9cc-118">Это также гарантирует, что вы сможете получить доступ к старому контенту, не используя все время один и тот же ключ.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="0a9cc-119">Где Exchange Online использует DKM?</span><span class="sxs-lookup"><span data-stu-id="0a9cc-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="0a9cc-120">Корпорация Майкрософт использует [диспетчер распределенных](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) ключей для шифрования секретов в центрах обработки данных Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="0a9cc-121">Например:</span><span class="sxs-lookup"><span data-stu-id="0a9cc-121">For example:</span></span>
  
- <span data-ttu-id="0a9cc-122">Учетные данные для подключенных учетных записей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="0a9cc-123">Подключенные учетные записи — это сторонние учетные записи, такие как Hotmail, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="0a9cc-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="0a9cc-124">и Gmail.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-124">mail accounts.</span></span>

- <span data-ttu-id="0a9cc-125">Ключ клиента.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-125">Customer key.</span></span> <span data-ttu-id="0a9cc-126">Если вы используете шифрование [службы с ключом](customer-key-overview.md)клиента, вы будете использовать [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) для защиты секретов.</span><span class="sxs-lookup"><span data-stu-id="0a9cc-126">If you are using [Service encryption with Customer Key](customer-key-overview.md), you'll use [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a9cc-127">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="0a9cc-127">Related topics</span></span>

[<span data-ttu-id="0a9cc-128">Шифрование в Office 365</span><span class="sxs-lookup"><span data-stu-id="0a9cc-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="0a9cc-129">Технические сведения о шифровании</span><span class="sxs-lookup"><span data-stu-id="0a9cc-129">Technical reference details about encryption</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="0a9cc-130">Контроль службы в Центре соответствия &amp; требованиям безопасности</span><span class="sxs-lookup"><span data-stu-id="0a9cc-130">Service assurance in the Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

