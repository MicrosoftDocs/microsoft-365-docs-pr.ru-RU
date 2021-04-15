---
title: Укажите уровень облачной защиты антивируса Microsoft Defender
description: Установите уровень облачной защиты для антивируса Microsoft Defender.
keywords: Антивирус Microsoft Defender, антивирусные программы, безопасность, защита, облако, агрессивность, уровень защиты
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: a0c73c8dd341c4940e3eddd4ede75240e57502d6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764125"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="585cb-104">Указать уровень облачной защиты</span><span class="sxs-lookup"><span data-stu-id="585cb-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="585cb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="585cb-105">**Applies to:**</span></span>

- [<span data-ttu-id="585cb-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="585cb-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="585cb-107">Уровень облачной защиты, предлагаемый антивирусом Microsoft Defender, можно указать с помощью Microsoft Endpoint Manager (рекомендуется) или групповой политики.</span><span class="sxs-lookup"><span data-stu-id="585cb-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="585cb-108">Облачная защита — это не просто защита файлов, хранимых в облаке.</span><span class="sxs-lookup"><span data-stu-id="585cb-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="585cb-109">Облачная служба антивирусных программ Microsoft Defender — это механизм доставки обновленной защиты на сеть и устройства (также называемые конечными точками).</span><span class="sxs-lookup"><span data-stu-id="585cb-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="585cb-110">Облачная защита с помощью антивируса Microsoft Defender использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, значительно более быстрой, чем традиционные обновления сведений о безопасности.</span><span class="sxs-lookup"><span data-stu-id="585cb-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="585cb-111">Microsoft Intune и Microsoft Endpoint Manager теперь являются частью [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview)</span><span class="sxs-lookup"><span data-stu-id="585cb-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="585cb-112">Используйте Microsoft Endpoint Manager, чтобы указать уровень облачной защиты</span><span class="sxs-lookup"><span data-stu-id="585cb-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="585cb-113">Перейдите в центр администрирования конечной точки Microsoft Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="585cb-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="585cb-114">Выберите **антивирус безопасности**  >  **конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="585cb-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="585cb-115">Выберите антивирусный профиль.</span><span class="sxs-lookup"><span data-stu-id="585cb-115">Select an antivirus profile.</span></span> <span data-ttu-id="585cb-116">(Если у вас еще нет его или вы хотите создать новый профиль, см. параметры ограничения устройств в [Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="585cb-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="585cb-117">Выбор **свойств**.</span><span class="sxs-lookup"><span data-stu-id="585cb-117">Select **Properties**.</span></span> <span data-ttu-id="585cb-118">Затем, рядом с **настройками конфигурации,** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="585cb-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="585cb-119">**Расширив** защиту облака, а затем в **списке** уровней защиты с доставкой в облаке выберите один из следующих:</span><span class="sxs-lookup"><span data-stu-id="585cb-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="585cb-120">**High**: применяет высокий уровень обнаружения.</span><span class="sxs-lookup"><span data-stu-id="585cb-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="585cb-121">**Высокий плюс:** использует **высокий** уровень и применяет дополнительные меры защиты (может повлиять на производительность клиента).</span><span class="sxs-lookup"><span data-stu-id="585cb-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="585cb-122">**Нулевая толерантность.** Блокирует все неизвестные исполняемые.</span><span class="sxs-lookup"><span data-stu-id="585cb-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="585cb-123">Выберите **Обзор + сохранение,** а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="585cb-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="585cb-124">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="585cb-124">Need some help?</span></span> <span data-ttu-id="585cb-125">См. следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="585cb-125">See the following resources:</span></span>
> - [<span data-ttu-id="585cb-126">Настройка защиты конечных точек</span><span class="sxs-lookup"><span data-stu-id="585cb-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="585cb-127">Добавление параметров защиты конечных точек в Intune</span><span class="sxs-lookup"><span data-stu-id="585cb-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="585cb-128">Использование групповой политики для указания уровня облачной защиты</span><span class="sxs-lookup"><span data-stu-id="585cb-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="585cb-129">На компьютере управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="585cb-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="585cb-130">Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="585cb-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="585cb-131">В **редакторе управления групповой политикой** перейдите к **шаблонам администрирования конфигурации**  >  **компьютеров.**</span><span class="sxs-lookup"><span data-stu-id="585cb-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="585cb-132">Расширь дерево до **компонентов Windows** Microsoft  >  **Defender Antivirus**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="585cb-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="585cb-133">Дважды щелкните **параметр Выберите параметр уровня облачной защиты** и установите его **включено.**</span><span class="sxs-lookup"><span data-stu-id="585cb-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="585cb-134">Выберите уровень защиты:</span><span class="sxs-lookup"><span data-stu-id="585cb-134">Select the level of protection:</span></span>
    - <span data-ttu-id="585cb-135">**Уровень блокировки по** умолчанию обеспечивает сильное обнаружение без увеличения риска обнаружения законных файлов.</span><span class="sxs-lookup"><span data-stu-id="585cb-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="585cb-136">**Умеренный уровень блокировки** обеспечивает умеренный уровень только для обнаружения высокой уверенности</span><span class="sxs-lookup"><span data-stu-id="585cb-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="585cb-137">**Высокий уровень блокировки** применяет высокий уровень обнаружения при оптимизации производительности клиента (но также может дать вам больше шансов на ложные срабатывания).</span><span class="sxs-lookup"><span data-stu-id="585cb-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="585cb-138">**Высокий + уровень блокировки** применяет дополнительные меры защиты (может повлиять на производительность клиента и повысить вероятность ложных срабатывавай).</span><span class="sxs-lookup"><span data-stu-id="585cb-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="585cb-139">**Уровень блокировки нулевой толерантности** блокирует все неизвестные исполняемые.</span><span class="sxs-lookup"><span data-stu-id="585cb-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="585cb-140">Хотя это маловероятно, установка этого переключателя на **High** или **High +** может привести к обнаружению некоторых законных файлов (хотя у вас будет возможность разблокировать или оспорить это обнаружение).</span><span class="sxs-lookup"><span data-stu-id="585cb-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="585cb-141">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="585cb-141">Click **OK**.</span></span>

7. <span data-ttu-id="585cb-142">Развертывание обновленного объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="585cb-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="585cb-143">См. [консоль управления групповой политикой](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="585cb-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="585cb-144">Вы используете объекты групповой политики в помещениях?</span><span class="sxs-lookup"><span data-stu-id="585cb-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="585cb-145">Узнайте, как они переводятся в облаке.</span><span class="sxs-lookup"><span data-stu-id="585cb-145">See how they translate in the cloud.</span></span> <span data-ttu-id="585cb-146">[Анализ объектов локальной групповой политики с помощью аналитики групповой](/mem/intune/configuration/group-policy-analytics)политики в Microsoft Endpoint Manager .</span><span class="sxs-lookup"><span data-stu-id="585cb-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="585cb-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="585cb-147">Related articles</span></span>

- [<span data-ttu-id="585cb-148">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="585cb-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="585cb-149">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="585cb-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="585cb-150">Создание и развертывание политик противомалярийных программ: служба облачной защиты</span><span class="sxs-lookup"><span data-stu-id="585cb-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)