---
title: Опыт Microsoft Defender для конечной точки с помощью имитации атак
description: Запустите предоставленные имитации сценариев атак, чтобы узнать, как Microsoft Defender для конечной точки может обнаруживать, исследовать и реагировать на нарушения.
keywords: тест, сценарий, атака, моделирование, имитация, diy, Microsoft Defender для конечной точки
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 9a56167f0025ec42f4fd441886f83026c1bf23d6
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339542"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="33d6c-104">Опыт Microsoft Defender для конечной точки с помощью имитации атак</span><span class="sxs-lookup"><span data-stu-id="33d6c-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33d6c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="33d6c-105">**Applies to:**</span></span>
- [<span data-ttu-id="33d6c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="33d6c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="33d6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33d6c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="33d6c-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="33d6c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33d6c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="33d6c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="33d6c-110">Узнайте о последних улучшениях в Microsoft Defender для конечной точки: что нового в [Defender для конечной точки?.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="33d6c-110">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="33d6c-111">Defender for Endpoint в недавней оценке MITRE продемонстрировал ведущие в отрасли возможности оптики и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="33d6c-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="33d6c-112">Read: Аналитика из оценки [ATT MITRE&на](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)основе CK .</span><span class="sxs-lookup"><span data-stu-id="33d6c-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="33d6c-113">Может потребоваться испытать Defender для конечной точки, прежде чем вы на борту более нескольких устройств в службу.</span><span class="sxs-lookup"><span data-stu-id="33d6c-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="33d6c-114">Для этого можно выполнить управляемые имитации атак на нескольких тестовых устройствах.</span><span class="sxs-lookup"><span data-stu-id="33d6c-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="33d6c-115">После запуска смоделированных атак вы можете просмотреть, как Defender для конечной точки просматривает вредоносную активность и изучите, как она позволяет эффективно отвечать.</span><span class="sxs-lookup"><span data-stu-id="33d6c-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="33d6c-116">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="33d6c-116">Before you begin</span></span>

<span data-ttu-id="33d6c-117">Для запуска любого из предоставленных симуляций необходимо по крайней мере [одно бортовом устройстве.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="33d6c-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="33d6c-118">Ознакомьтесь с документом по погона, который содержит каждый сценарий атаки.</span><span class="sxs-lookup"><span data-stu-id="33d6c-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="33d6c-119">Каждый документ содержит требования к ОС и приложениям, а также подробные инструкции, которые относятся к сценарию атаки.</span><span class="sxs-lookup"><span data-stu-id="33d6c-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="33d6c-120">Запуск моделирования</span><span class="sxs-lookup"><span data-stu-id="33d6c-120">Run a simulation</span></span>

1. <span data-ttu-id="33d6c-121">В **endpoints** Assessment & учебники & моделирования , выберите, какой из доступных сценариев атаки вы хотели бы  >    >  имитировать:</span><span class="sxs-lookup"><span data-stu-id="33d6c-121">In **Endpoints** > **Evaluation & tutorials** > **Tutorials & simulations**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="33d6c-122">**Сценарий 1. Отбрасыватель** документа — имитирует доставку социально разработанного документа-приманки.</span><span class="sxs-lookup"><span data-stu-id="33d6c-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="33d6c-123">В документе запускается специально созданный backdoor, который дает злоумышленникам контроль.</span><span class="sxs-lookup"><span data-stu-id="33d6c-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="33d6c-124">**Сценарий 2. Сценарий PowerShell** в без файловой атаке — имитирует без файловую атаку, которая опирается на PowerShell, демонстрацию уменьшения поверхности атаки и обнаружение вредоносных действий памяти на устройстве.</span><span class="sxs-lookup"><span data-stu-id="33d6c-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="33d6c-125">**Сценарий 3.** Автоматизированная реакция на инциденты — запускает автоматическое расследование, которое автоматически охотится за артефактами нарушений и устраняет их для масштабирования емкости реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="33d6c-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="33d6c-126">Скачайте и прочитайте соответствующий документ по погонам, предоставленный в выбранном сценарии.</span><span class="sxs-lookup"><span data-stu-id="33d6c-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="33d6c-127">Скачайте файл моделирования или скопируйте сценарий моделирования, перенавигав для **справки**&  >  **руководства.**</span><span class="sxs-lookup"><span data-stu-id="33d6c-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="33d6c-128">Вы можете скачать файл или скрипт на тестовом устройстве, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="33d6c-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="33d6c-129">Запустите файл или сценарий моделирования на тестовом устройстве, как поручено в документе по поручению.</span><span class="sxs-lookup"><span data-stu-id="33d6c-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="33d6c-130">Файлы или сценарии моделирования имитируют действия атаки, но на самом деле являются доброкачественными и не наносят вреда тестовом устройству.</span><span class="sxs-lookup"><span data-stu-id="33d6c-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="33d6c-131">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="33d6c-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33d6c-132">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="33d6c-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="33d6c-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="33d6c-133">Related topics</span></span>

- [<span data-ttu-id="33d6c-134">Подключение устройств</span><span class="sxs-lookup"><span data-stu-id="33d6c-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="33d6c-135">Подключение устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="33d6c-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
