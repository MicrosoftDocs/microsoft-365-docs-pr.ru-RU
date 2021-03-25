---
title: Microsoft Threat Experts
ms.reviewer: ''
description: Эксперты microsoft Threat предоставляют дополнительный уровень знаний для Microsoft Defender для конечной точки.
keywords: служба управляемой охоты на угрозы, управляемый поиск угроз, служба управляемого обнаружения и реагирования (MDR), MTE, Эксперты microsoft Threat, MTE-TAN, целевое уведомление об атаке, уведомление о целевой атаке
search.product: Windows 10
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 466e67bb4649f8cf87e4152a07122d57c5071b79
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185579"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="21338-104">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="21338-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="21338-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="21338-105">**Applies to:**</span></span>
- [<span data-ttu-id="21338-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="21338-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="21338-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21338-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="21338-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="21338-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="21338-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="21338-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="21338-110">Microsoft Threat Experts — это служба управляемой охоты на угрозы, которая предоставляет вашим центрам операций безопасности (SOCs) мониторинг и анализ на уровне экспертов, чтобы обеспечить, чтобы критические угрозы в уникальных средах не пропускались.</span><span class="sxs-lookup"><span data-stu-id="21338-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="21338-111">Эта служба управляемой охоты на угрозы предоставляет экспертные сведения и данные с помощью этих двух возможностей: целевого уведомления об атаке и доступа к экспертам по запросу.</span><span class="sxs-lookup"><span data-stu-id="21338-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="21338-112">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="21338-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="21338-113">Обсудите требования к требованиям с поставщиком технической службы Майкрософт и командой учетных записей перед тем, как примениться к службе управляемой охоты на угрозы.</span><span class="sxs-lookup"><span data-stu-id="21338-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="21338-114">Если вы клиент Microsoft Defender для конечных точек, вам необходимо обратиться к **экспертам microsoft Threat Experts - Targeted Attack Notifications,** чтобы получить специальные сведения и анализ, которые помогут определить наиболее важные угрозы в вашей среде, чтобы вы могли быстро реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="21338-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly</span></span>

<span data-ttu-id="21338-115">Чтобы зарегистрироваться в Microsoft Threat Experts - targeted Attack Notifications benefits, перейдите в параметры Общие расширенные функции   >    >    >  **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span><span class="sxs-lookup"><span data-stu-id="21338-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="21338-116">После его принятие вы получите преимущества уведомлений о целевых атаках.</span><span class="sxs-lookup"><span data-stu-id="21338-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="21338-117">Свяжитесь с командой учетных записей или представителем Майкрософт, чтобы подписаться на **экспертов Microsoft Threat Experts - Experts on Demand,** чтобы проконсультироваться с нашими экспертами по угрозам по соответствующим обнаружениям и противникам, с которыми сталкивается ваша организация.</span><span class="sxs-lookup"><span data-stu-id="21338-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="21338-118">Подробнее [см. в материале "Настройка](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) возможностей экспертов по угрозам Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="21338-118">See [Configure Microsoft Threat Experts capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="21338-119">Эксперты по угрозам Microsoft — целевое уведомление об атаке</span><span class="sxs-lookup"><span data-stu-id="21338-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="21338-120">Эксперты по угрозам Microsoft . Целевое уведомление об атаке обеспечивает активную охоту на наиболее важные угрозы для вашей сети, включая вторжение противника, атаки на клавиатуре или расширенные атаки, такие как кибершпионаж.</span><span class="sxs-lookup"><span data-stu-id="21338-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="21338-121">Эти уведомления показываются как новое оповещение.</span><span class="sxs-lookup"><span data-stu-id="21338-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="21338-122">Служба управляемой охоты включает в себя:</span><span class="sxs-lookup"><span data-stu-id="21338-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="21338-123">Мониторинг и анализ угроз, сокращение времени и риска для бизнеса</span><span class="sxs-lookup"><span data-stu-id="21338-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="21338-124">Искусственный интеллект, обученный охотником, для обнаружения и расстановки приоритетов как известных, так и неизвестных атак</span><span class="sxs-lookup"><span data-stu-id="21338-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="21338-125">Определение наиболее важных рисков, помогая soCs увеличить время и энергию</span><span class="sxs-lookup"><span data-stu-id="21338-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="21338-126">Область компрометации и максимальное количество контекста, которые можно быстро доставить для быстрого реагирования SOC.</span><span class="sxs-lookup"><span data-stu-id="21338-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="21338-127">Эксперты по угрозам Майкрософт — эксперты по запросу</span><span class="sxs-lookup"><span data-stu-id="21338-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="21338-128">Клиенты могут привлекать наших экспертов по безопасности непосредственно из Центра безопасности Защитника Майкрософт для быстрого и точного ответа.</span><span class="sxs-lookup"><span data-stu-id="21338-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="21338-129">Эксперты предоставляют сведения, необходимые для лучшего понимания сложных угроз, затрагивающих организацию, от запросов оповещений, потенциально скомпрометных устройств, первопричины подозрительного сетевого подключения до дополнительных сведений об угрозах в отношении текущих расширенных кампаний сохраняющихся угроз.</span><span class="sxs-lookup"><span data-stu-id="21338-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="21338-130">С помощью этой возможности можно:</span><span class="sxs-lookup"><span data-stu-id="21338-130">With this capability, you can:</span></span>
- <span data-ttu-id="21338-131">Дополнительные разъяснения по оповещениям, включая корневую причину или область инцидента</span><span class="sxs-lookup"><span data-stu-id="21338-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="21338-132">Получение ясности в подозрительном поведении устройства и последующих действиях, если вы столкнулись с расширенным злоумышленником</span><span class="sxs-lookup"><span data-stu-id="21338-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="21338-133">Определение рисков и защиты в отношении субъектов угроз, кампаний или формирующихся методов злоумышленников</span><span class="sxs-lookup"><span data-stu-id="21338-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="21338-134">Возможность **проконсультироваться с экспертом** по угрозам доступна в нескольких местах на портале, чтобы вы могли взаимодействовать со специалистами в контексте вашего расследования:</span><span class="sxs-lookup"><span data-stu-id="21338-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="21338-135"><i>**Меню справки и поддержки**</i></span><span class="sxs-lookup"><span data-stu-id="21338-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="21338-136">![Снимок экрана параметра меню MTE-EOD](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="21338-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="21338-137"><i>**Меню действий страницы устройства**</i></span><span class="sxs-lookup"><span data-stu-id="21338-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="21338-138">![Снимок экрана параметра действия страницы действий для устройства MTE-EOD](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="21338-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="21338-139"><i>**Оповещает меню действий страницы**</i></span><span class="sxs-lookup"><span data-stu-id="21338-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="21338-140">![Снимок экрана меню действия страницы оповещения MTE-EOD](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="21338-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="21338-141"><i>**Меню действий страницы файлов**</i></span><span class="sxs-lookup"><span data-stu-id="21338-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="21338-142">![Снимок экрана параметра действия страницы действий страницы файлов MTE-EOD](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="21338-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="21338-143">Если вы хотите отслеживать состояние дел "Эксперты по запросу" с помощью Центра служб Майкрософт, перенаправление в диспетчер технической учетной записи.</span><span class="sxs-lookup"><span data-stu-id="21338-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="21338-144">Просмотрите это видео для краткого обзора центра служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="21338-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="21338-145">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="21338-145">Related topic</span></span>
- [<span data-ttu-id="21338-146">Настройка возможностей экспертов по угрозам Майкрософт</span><span class="sxs-lookup"><span data-stu-id="21338-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)