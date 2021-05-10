---
title: Укажите дополнительные наборы определений для проверки сетевого трафика для антивирусная программа в Microsoft Defender
description: Укажите дополнительные наборы определений для проверки сетевого трафика для антивирусная программа в Microsoft Defender.
keywords: антивирусная программа в Microsoft Defender, антивирусное программное обеспечение, безопасность, защитник, проверка сетевого трафика
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300259"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="a0823-104">Укажите дополнительные наборы определений для проверки сетевого трафика</span><span class="sxs-lookup"><span data-stu-id="a0823-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0823-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a0823-105">**Applies to:**</span></span>

- [<span data-ttu-id="a0823-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a0823-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a0823-107">Дополнительные наборы определений для проверки сетевого трафика можно указать с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="a0823-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="a0823-108">Использование групповой политики для указания дополнительных наборов определений для проверки сетевого трафика</span><span class="sxs-lookup"><span data-stu-id="a0823-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="a0823-109">На конечной точке управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="a0823-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="a0823-110">Перейдите **Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **сетевой системы проверки.**</span><span class="sxs-lookup"><span data-stu-id="a0823-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="a0823-111">Выберите **укажите дополнительные наборы определений для проверки сетевого трафика.**</span><span class="sxs-lookup"><span data-stu-id="a0823-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="a0823-112">По умолчанию эта политика настроена как **Not configured**.</span><span class="sxs-lookup"><span data-stu-id="a0823-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="a0823-113">Чтобы изменить политику, выберите ссылку **параметра политики** редактирования.</span><span class="sxs-lookup"><span data-stu-id="a0823-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="a0823-114">Выберите **включено,** а затем в разделе **Параметры** выберите **Показать ...**.</span><span class="sxs-lookup"><span data-stu-id="a0823-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="a0823-115">Добавьте записи в список и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="a0823-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="a0823-116">Каждая запись должна быть указана в качестве пары значения имени, где имя представляет строку представления guID набора определений.</span><span class="sxs-lookup"><span data-stu-id="a0823-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="a0823-117">Например, набор guID определения, позволяющий включить анализ безопасности тестирования, определяется как: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` .</span><span class="sxs-lookup"><span data-stu-id="a0823-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="a0823-118">Значение не используется, поэтому мы рекомендуем установить `0` его.</span><span class="sxs-lookup"><span data-stu-id="a0823-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="a0823-119">Выберите **ОК** и разверните обновленный объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="a0823-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="a0823-120">См. [консоль управления групповой политикой.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="a0823-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="a0823-121">Вы используете объекты групповой политики в помещениях?</span><span class="sxs-lookup"><span data-stu-id="a0823-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="a0823-122">Узнайте, как они переводятся в облаке.</span><span class="sxs-lookup"><span data-stu-id="a0823-122">See how they translate in the cloud.</span></span> <span data-ttu-id="a0823-123">[Анализ объектов локальной групповой политики](/mem/intune/configuration/group-policy-analytics)с помощью аналитики групповой политики в Microsoft Endpoint Manager - Preview .</span><span class="sxs-lookup"><span data-stu-id="a0823-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="a0823-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a0823-124">Related articles</span></span>

- [<span data-ttu-id="a0823-125">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="a0823-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="a0823-126">Включение облачной защиты</span><span class="sxs-lookup"><span data-stu-id="a0823-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="a0823-127">Создание и развертывание политик противомалярийных программ: служба облачной защиты</span><span class="sxs-lookup"><span data-stu-id="a0823-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)