---
title: Совместимость антивируса Microsoft Defender с Защитником для конечной точки
description: Узнайте, как Защитник Windows с Microsoft Defender для endpoint и как он функционирует при работе с сторонним клиентом антивирусных программ.
keywords: Совместимость защитника Windows, защитника, защитника Microsoft atp, защитника конечной точки, антивируса, mde
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165963"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="c5101-104">Совместимость антивируса Microsoft Defender с Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c5101-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c5101-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c5101-105">**Applies to:**</span></span>
- [<span data-ttu-id="c5101-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c5101-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c5101-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5101-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="c5101-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c5101-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c5101-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c5101-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="c5101-110">Агент Microsoft Defender для конечной точки зависит от антивируса Microsoft Defender для некоторых возможностей, таких как сканирование файлов.</span><span class="sxs-lookup"><span data-stu-id="c5101-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c5101-111">Защитник для конечной точки не придерживается параметров исключения антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c5101-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="c5101-112">Необходимо настроить обновления аналитики безопасности на устройствах Defender для конечных точек независимо от того, является ли антивирус Microsoft Defender активным антивирусом или нет.</span><span class="sxs-lookup"><span data-stu-id="c5101-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="c5101-113">Дополнительные сведения см. в [веб-сайте Управление обновлениями антивирусного](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)антивируса Microsoft Defender и применение базовых данных.</span><span class="sxs-lookup"><span data-stu-id="c5101-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c5101-114">Если бортовые устройства защищены сторонним клиентом антивирусных программ, антивирус Microsoft Defender на этой конечной точке вступает в пассивный режим.</span><span class="sxs-lookup"><span data-stu-id="c5101-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="c5101-115">Антивирус Microsoft Defender будет по-прежнему получать  обновления, и процессmspeng.exeбудет указан как запущенная служба, но она не будет выполнять проверки и не заменит запущенный сторонний клиент антивирусного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c5101-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="c5101-116">Антивирусный интерфейс Microsoft Defender будет отключен, а пользователи на устройстве не смогут использовать антивирус Microsoft Defender для выполнения проверки по запросу или настройки большинства параметров.</span><span class="sxs-lookup"><span data-stu-id="c5101-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="c5101-117">Дополнительные сведения см. в разделе [Антивирус Microsoft Defender и Defender для конечной точки совместимости.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="c5101-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>