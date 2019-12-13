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
ms.openlocfilehash: 708ae0965eadd453ad4a8fd1dd7c29231cb07916
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911537"
---
# <a name="microsoft-threat-protection-data-security-and-privacy"></a><span data-ttu-id="84bea-104">Безопасность данных и конфиденциальность в службе защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="84bea-104">Microsoft Threat Protection data security and privacy</span></span>

<span data-ttu-id="84bea-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="84bea-105">**Applies to:**</span></span>
- <span data-ttu-id="84bea-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="84bea-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="84bea-107">Используя предварительную версию службы защиты от угроз (Майкрософт), вы соглашаетесь со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="84bea-107">By using the Microsoft Threat Protection preview you consent to the following terms:</span></span>

<span data-ttu-id="84bea-108">Ваши соответствующие данные клиента (определенные в условиях использования веб-служб (OST)) будут передаваться из других служб Майкрософт в службу защиты от угроз (Майкрософт) и в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="84bea-108">Your applicable Customer Data (as defined in the Online Service Terms ("OST")) will be transferred from other Microsoft services into Microsoft Threat Protection and from Microsoft Threat Protection back to applicable Microsoft services.</span></span> <span data-ttu-id="84bea-109">Во время применения этой предварительной версии данные клиента в службе защиты от угроз (Майкрософт) будут использоваться в соответствии со стандартами и обязательствами расширенной защиты от угроз в Microsoft Defender (ATP в Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="84bea-109">For the duration of this preview, use of your Customer Data in Microsoft Threat Protection will follow the data handling standards and commitments for Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP).</span></span> <span data-ttu-id="84bea-110">Вы соглашаетесь, что такие обязательства могут отличаться в зависимости от служб, из которых передаются данные клиента.</span><span class="sxs-lookup"><span data-stu-id="84bea-110">You acknowledge that such commitments may differ from the services from which that Customer Data is transferred.</span></span> <span data-ttu-id="84bea-111">Кроме того, данные клиента, сохраняемые в службе защиты от угроз (Майкрософт), будут храниться в географическом расположении, выбранном вами в качестве хранилища для данных клиента ATP в Microsoft Defender, которое может отличаться от географического расположения, выбранного в отношении других служб.</span><span class="sxs-lookup"><span data-stu-id="84bea-111">Further, Customer Data stored in Microsoft Threat Protection will be stored at rest in the Geo you selected for storage of your Microsoft Defender ATP Customer Data, which may differ from the Geo you selected in connection with other services.</span></span> <span data-ttu-id="84bea-112">Корпорация Майкрософт не будет переносить данные клиента за пределы этого географического расположения, кроме случаев, указанных в разделе "Расположение данных", находящемся в [центре управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="84bea-112">Microsoft will not transfer the Customer Data outside of such Geo except as noted in the "Data Location" section of the Microsoft Trust Center located at [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span>

<span data-ttu-id="84bea-113">Кроме того, хотя вы определяете, какие пользователи могут получить доступ к службе защиты от угроз (Майкрософт), она в настоящее время не поддерживает управление доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="84bea-113">Further, while you determine which of your users may access Microsoft Threat Protection, Microsoft Threat Protection does not currently allow for role-based access control ("RBAC").</span></span> <span data-ttu-id="84bea-114">Вы соглашаетесь, что если служба защиты от угроз (Майкрософт) получает данные от службы Майкрософт, поддерживающей RBAC, уровни доступа в этой службе не применяются к службе защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="84bea-114">You acknowledge that to the extent Microsoft Threat Protection receives data from a Microsoft service that does support RBAC, access levels in that service will not apply in Microsoft Threat Protection.</span></span>


<span data-ttu-id="84bea-115">Дополнительные сведения о хранении данных и конфиденциальности для определенных продуктов см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="84bea-115">For more information on the data storage and privacy information of the specific products see:</span></span>
- [<span data-ttu-id="84bea-116">Хранение и конфиденциальность данных Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="84bea-116">Microsoft Defender ATP data storage and privacy</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [<span data-ttu-id="84bea-117">Безопасность и конфиденциальность данных в Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="84bea-117">Microsoft Cloud App Security data security and privacy</span></span>](https://docs.microsoft.com/cloud-app-security/cas-compliance-trust)
- [<span data-ttu-id="84bea-118">Конфиденциальность, безопасность и прозрачность в Office 365</span><span class="sxs-lookup"><span data-stu-id="84bea-118">Office 365 privacy, security, and transparency</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/privacy-security-and-transparency#advanced-threat-protection)