---
title: Включим выход на пенсию определения для антивирусная программа в Microsoft Defender
description: Включим выход на пенсию определения для антивирусная программа в Microsoft Defender.
keywords: антивирусная программа в Microsoft Defender, antimalware, security, defender, definition retirement
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903808"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="85254-104">Включив выход на пенсию определения</span><span class="sxs-lookup"><span data-stu-id="85254-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="85254-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="85254-105">**Applies to:**</span></span>

- [<span data-ttu-id="85254-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="85254-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="85254-107">Вы можете настроить определение выхода на пенсию с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="85254-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="85254-108">Определение выхода на пенсию проверяет, есть ли на компьютере необходимые обновления безопасности, необходимые для защиты от определенной уязвимости.</span><span class="sxs-lookup"><span data-stu-id="85254-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="85254-109">Если система не уязвима для эксплойтов, обнаруженных определением, то это определение является "отмененным".</span><span class="sxs-lookup"><span data-stu-id="85254-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="85254-110">Если все сведения о безопасности для заданного протокола будут отменены, этот протокол больше не будет размыт.</span><span class="sxs-lookup"><span data-stu-id="85254-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="85254-111">Включение этой функции помогает повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="85254-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="85254-112">На компьютере, который обновляется со всеми последними обновлениями безопасности, защита сети не повлияет на производительность сети.</span><span class="sxs-lookup"><span data-stu-id="85254-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="85254-113">Использование групповой политики для настройки выхода на пенсию определения</span><span class="sxs-lookup"><span data-stu-id="85254-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="85254-114">На конечной точке управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="85254-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="85254-115">Перейдите **к административным** шаблонам конфигурации  >    >  **компьютера Windows компонентов**  >  **антивирусная программа в Microsoft Defender**  >  **сетевой системы проверки.**</span><span class="sxs-lookup"><span data-stu-id="85254-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="85254-116">Выберите **включив выход на пенсию определения.**</span><span class="sxs-lookup"><span data-stu-id="85254-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="85254-117">По умолчанию эта политика включена.</span><span class="sxs-lookup"><span data-stu-id="85254-117">By default, this policy is enabled.</span></span> <span data-ttu-id="85254-118">Если набор **не настроен,** включено определение выхода на пенсию.</span><span class="sxs-lookup"><span data-stu-id="85254-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="85254-119">Чтобы изменить политику, выберите ссылку **параметра политики** редактирования.</span><span class="sxs-lookup"><span data-stu-id="85254-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="85254-120">Выберите **включено,** а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="85254-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="85254-121">Развертывание обновленного объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="85254-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="85254-122">См. [консоль управления групповой политикой.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="85254-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="85254-123">Вы используете объекты групповой политики в помещениях?</span><span class="sxs-lookup"><span data-stu-id="85254-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="85254-124">Узнайте, как они переводятся в облаке.</span><span class="sxs-lookup"><span data-stu-id="85254-124">See how they translate in the cloud.</span></span> <span data-ttu-id="85254-125">[Анализ объектов локальной групповой политики](/mem/intune/configuration/group-policy-analytics)с помощью аналитики групповой политики в Microsoft Endpoint Manager - Preview .</span><span class="sxs-lookup"><span data-stu-id="85254-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
