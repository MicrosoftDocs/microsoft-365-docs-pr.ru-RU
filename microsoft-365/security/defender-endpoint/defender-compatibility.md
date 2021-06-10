---
title: Совместимость антивирусного решения с Защитником для конечной точки
description: Узнайте, как Защитник Windows с Microsoft Defender для конечной точки и как он функционирует при работе с сторонним клиентом противомалярийных программ.
keywords: совместимость защитника windows, защитника, защитника Microsoft для конечной точки, защитника конечной точки, антивируса, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782889"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="523ea-104">Совместимость антивирусных решений с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="523ea-104">Antivirus solution compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="523ea-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="523ea-105">**Applies to:**</span></span>
- [<span data-ttu-id="523ea-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="523ea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="523ea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="523ea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="523ea-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="523ea-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="523ea-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="523ea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="523ea-110">Агент Microsoft Defender для конечной точки зависит от антивирусная программа в Microsoft Defender некоторых возможностей, таких как сканирование файлов.</span><span class="sxs-lookup"><span data-stu-id="523ea-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="523ea-111">Defender for Endpoint не придерживается параметров антивирусная программа в Microsoft Defender исключений.</span><span class="sxs-lookup"><span data-stu-id="523ea-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="523ea-112">Необходимо настроить обновления аналитики безопасности на устройствах Defender для конечных точек независимо антивирусная программа в Microsoft Defender является активным антивирусом или нет.</span><span class="sxs-lookup"><span data-stu-id="523ea-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="523ea-113">Дополнительные сведения см. в [антивирусная программа в Microsoft Defender обновления и применение базовых показателей.](manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="523ea-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="523ea-114">Если бортовые устройства защищены сторонним клиентом противомалярийных программ, антивирусная программа в Microsoft Defender на этой конечной точке вступает в пассивный режим.</span><span class="sxs-lookup"><span data-stu-id="523ea-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="523ea-115">антивирусная программа в Microsoft Defender будет продолжать получать обновления, и  процессmspeng.exeбудет указан как запущенная служба, но она не будет выполнять проверки и не заменит запущенный сторонний клиент антивирусного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="523ea-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="523ea-116">Интерфейс антивирусная программа в Microsoft Defender будет отключен, а пользователи на устройстве не смогут использовать антивирусная программа в Microsoft Defender для выполнения сканов по запросу или настройки большинства параметров.</span><span class="sxs-lookup"><span data-stu-id="523ea-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="523ea-117">Дополнительные сведения см. в [разделе антивирусная программа в Microsoft Defender и Defender для конечной точки совместимости.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="523ea-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](microsoft-defender-antivirus-compatibility.md).</span></span>
