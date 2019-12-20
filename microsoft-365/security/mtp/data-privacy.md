---
title: Безопасность данных и конфиденциальность в службе защиты от угроз (Майкрософт)
description: В этой статье описаны конфиденциальность и безопасность данных службы.
keywords: конфиденциальность, данные, безопасность, центр управления безопасностью, сбор сведений
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 49574f17abee645943becc8403bef01951d31924
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806948"
---
# <a name="microsoft-threat-protection-data-security-and-privacy"></a><span data-ttu-id="6e54b-104">Безопасность данных и конфиденциальность в службе защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="6e54b-104">Microsoft Threat Protection data security and privacy</span></span>

<span data-ttu-id="6e54b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6e54b-105">**Applies to:**</span></span>
- <span data-ttu-id="6e54b-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="6e54b-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6e54b-107">Используя предварительную версию службы защиты от угроз (Майкрософт), вы соглашаетесь со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="6e54b-107">By using the Microsoft Threat Protection preview you consent to the following terms:</span></span>

<span data-ttu-id="6e54b-108">Ваши соответствующие данные клиента (определенные в условиях использования веб-служб (OST)) будут передаваться из других служб Майкрософт в службу защиты от угроз (Майкрософт) и в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="6e54b-108">Your applicable Customer Data (as defined in the Online Service Terms ("OST")) will be transferred from other Microsoft services into Microsoft Threat Protection and from Microsoft Threat Protection back to applicable Microsoft services.</span></span> <span data-ttu-id="6e54b-109">Во время применения этой предварительной версии данные клиента в службе защиты от угроз (Майкрософт) будут использоваться в соответствии со стандартами и обязательствами расширенной защиты от угроз в Microsoft Defender (ATP в Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="6e54b-109">For the duration of this preview, use of your Customer Data in Microsoft Threat Protection will follow the data handling standards and commitments for Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP).</span></span> <span data-ttu-id="6e54b-110">Вы соглашаетесь, что такие обязательства могут отличаться в зависимости от служб, из которых передаются данные клиента.</span><span class="sxs-lookup"><span data-stu-id="6e54b-110">You acknowledge that such commitments may differ from the services from which that Customer Data is transferred.</span></span> <span data-ttu-id="6e54b-111">Кроме того, данные клиента, сохраняемые в службе защиты от угроз (Майкрософт), будут храниться в географическом расположении, выбранном вами в качестве хранилища для данных клиента ATP в Microsoft Defender, которое может отличаться от географического расположения, выбранного в отношении других служб.</span><span class="sxs-lookup"><span data-stu-id="6e54b-111">Further, Customer Data stored in Microsoft Threat Protection will be stored at rest in the Geo you selected for storage of your Microsoft Defender ATP Customer Data, which may differ from the Geo you selected in connection with other services.</span></span> <span data-ttu-id="6e54b-112">Корпорация Майкрософт не будет переносить данные клиента за пределы этого географического расположения, кроме случаев, указанных в разделе "Расположение данных", находящемся в [центре управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="6e54b-112">Microsoft will not transfer the Customer Data outside of such Geo except as noted in the "Data Location" section of the Microsoft Trust Center located at [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span>

<span data-ttu-id="6e54b-113">Кроме того, хотя вы определяете, какие пользователи могут получить доступ к службе защиты от угроз (Майкрософт), она в настоящее время не поддерживает управление доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="6e54b-113">Further, while you determine which of your users may access Microsoft Threat Protection, Microsoft Threat Protection does not currently allow for role-based access control ("RBAC").</span></span> <span data-ttu-id="6e54b-114">Вы соглашаетесь, что если служба защиты от угроз (Майкрософт) получает данные от службы Майкрософт, поддерживающей RBAC, уровни доступа в этой службе не применяются к службе защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="6e54b-114">You acknowledge that to the extent Microsoft Threat Protection receives data from a Microsoft service that does support RBAC, access levels in that service will not apply in Microsoft Threat Protection.</span></span>


<span data-ttu-id="6e54b-115">Дополнительные сведения о хранении данных и конфиденциальности для определенных продуктов см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="6e54b-115">For more information on the data storage and privacy information of the specific products see:</span></span>
- [<span data-ttu-id="6e54b-116">Хранение и конфиденциальность данных Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="6e54b-116">Microsoft Defender ATP data storage and privacy</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [<span data-ttu-id="6e54b-117">Безопасность и конфиденциальность данных в Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6e54b-117">Microsoft Cloud App Security data security and privacy</span></span>](https://docs.microsoft.com/cloud-app-security/cas-compliance-trust)
- [<span data-ttu-id="6e54b-118">Конфиденциальность, безопасность и прозрачность в Office 365</span><span class="sxs-lookup"><span data-stu-id="6e54b-118">Office 365 privacy, security, and transparency</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/privacy-security-and-transparency#advanced-threat-protection)