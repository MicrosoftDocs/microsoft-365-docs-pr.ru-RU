---
title: Общие сведения о пилотных результатах проекта Microsoft Threat protection
description: Завершите пилотный проект Microsoft Threat Protection, выполнив систему показателей, анализируя результаты отчета и принимая решение о том, как перемещаться вперед.
keywords: Пилотный проект по защите от угроз Майкрософт, выберите дальнейшие действия после пробного развертывания Microsoft Threat Protection, что делать после оценки защиты от угроз Майкрософт в рабочей среде, перехода от пилотной системы защиты от угроз Майкрософт к развертыванию, безопасности кибератак, расширенной постоянной угрозе, корпоративной безопасности, устройств, устройств, удостоверений, пользователей, данных, приложений, инцидентов, автоматизированного исследования и исправления
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: d820b360f189425cc3913c6d92afc8965a7d1eee
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333633"
---
# <a name="closing-and-summarizing-your-microsoft-threat-protection-pilot"></a><span data-ttu-id="f6aa9-104">Заключение и подведение итогов для пилотной программы Майкрософт по защите от угроз</span><span class="sxs-lookup"><span data-stu-id="f6aa9-104">Closing and summarizing your Microsoft Threat Protection pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f6aa9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f6aa9-105">**Applies to:**</span></span>
- <span data-ttu-id="f6aa9-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f6aa9-106">Microsoft Threat Protection</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Планирование пилотного проекта Microsoft Threat protection" />
      <br/><span data-ttu-id="f6aa9-108">Планирование </a></span><span class="sxs-lookup"><span data-stu-id="f6aa9-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Подготовка пробной лаборатории или пилотной среды Майкрософт для защиты от угроз" />
      <br/><span data-ttu-id="f6aa9-110">Подготовка </a></span><span class="sxs-lookup"><span data-stu-id="f6aa9-110">Prepare </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Запуск эмуляции атак Майкрософт для защиты от угроз" />
      <br/><span data-ttu-id="f6aa9-112">Имитация атаки </a></span><span class="sxs-lookup"><span data-stu-id="f6aa9-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Закрываете и обобщает свой пилотный проект Майкрософт по защите от угроз." />
      <br/><span data-ttu-id="f6aa9-114">Закрытие и подведение итогов </a></span><span class="sxs-lookup"><span data-stu-id="f6aa9-114">Close and summarize </a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="f6aa9-115">В настоящее время вы находитесь на этапе закрытия и создания итогов.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-115">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="f6aa9-116">Вы только что настроили расширенную атаку "только для памяти", которая выполняла код удаленно на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-116">You’ve just simulated an advanced memory-only attack that executed code remotely on a domain controller.</span></span> <span data-ttu-id="f6aa9-117">Вы узнали, как обнаружение и оповещение защитником Майкрософт и Azure ATP при стеалси вредоносных действиях.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-117">You’ve seen how Microsoft Defender ATP and Azure ATP detects and alerts on stealthy malicious activity.</span></span> <span data-ttu-id="f6aa9-118">Вы также видели, как оповещения из различных источников доставляются вместе с другими контекстными сведениями в один инцидент на портале Центра безопасности Microsoft 365, позволяя аналитикам SOC исследовать и выполнять необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-118">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal, enabling SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="f6aa9-119">Вы также создали Расширенный запрос поиска, который определит входящие сообщения электронной почты, в которых пользователь открыл или сохранил вложение и создал обнаружение на основе этого запроса.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-119">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="f6aa9-120">Вы достигли конца процесса после завершения всех тестов.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-120">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="f6aa9-121">Ниже приведен полный результат.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-121">The final output should be:</span></span>

- <span data-ttu-id="f6aa9-122">Завершенная система показателей</span><span class="sxs-lookup"><span data-stu-id="f6aa9-122">A completed scorecard</span></span>
- <span data-ttu-id="f6aa9-123">Подробный отчет о результатах пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="f6aa9-123">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="f6aa9-124">Решение о перемещении вперед</span><span class="sxs-lookup"><span data-stu-id="f6aa9-124">A decision on how to move forward</span></span>

<span data-ttu-id="f6aa9-125">Эти сведения должны быть представлены как для внутренних заинтересованных лиц (которые определены на этапе [подготовки](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) ), так и для контактов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-125">This information should be presented to both internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="f6aa9-126">Это гарантирует, что любые отзывы можно использовать для усовершенствования продуктов и документации.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-126">This ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="f6aa9-127">Мы надеемся, что вы довольны этой имитацией и готовы приступить к внедрению того, что вы узнали.</span><span class="sxs-lookup"><span data-stu-id="f6aa9-127">We hope you enjoyed this simulation and are encouraged to start implementing what you've learned.</span></span>

## <a name="next-step"></a><span data-ttu-id="f6aa9-128">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="f6aa9-128">Next step</span></span>
<span data-ttu-id="f6aa9-129">Узнайте больше о базовых средствах защиты от угроз Майкрософт с помощью следующих интерактивных руководств:</span><span class="sxs-lookup"><span data-stu-id="f6aa9-129">Learn more about the Microsoft Threat Protection pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="f6aa9-130">Защита Организации с помощью защитника Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="f6aa9-130">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="f6aa9-131">Обнаружение подозрительных действий и потенциальных атак с помощью защитника Майкрософт для удостоверения</span><span class="sxs-lookup"><span data-stu-id="f6aa9-131">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="f6aa9-132">Обнаружение угроз и Управление оповещениями с помощью Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f6aa9-132">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="f6aa9-133">Исследование и исправление угроз с помощью защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f6aa9-133">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
