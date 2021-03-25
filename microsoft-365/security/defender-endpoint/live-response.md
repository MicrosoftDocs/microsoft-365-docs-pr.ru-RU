---
title: Исследование сущностями на устройствах с использованием живого ответа в ATP Защитника Майкрософт
description: Доступ к устройству с использованием безопасного удаленного подключения к оболочке для следственных действий и немедленного реагирования на устройство в режиме реального времени.
keywords: удаленный, оболочка, подключение, живой, ответ, в режиме реального времени, команда, сценарий, исправление, охота, экспорт, журнал, падение, скачивание, файл,
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 784e73467efc114f05ebdfca9bc4034e2d75f6c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185711"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="211df-104">Исследование сущностями на устройствах с использованием живого ответа</span><span class="sxs-lookup"><span data-stu-id="211df-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="211df-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="211df-105">**Applies to:**</span></span>
- [<span data-ttu-id="211df-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="211df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="211df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="211df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="211df-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="211df-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="211df-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="211df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="211df-110">Живой ответ предоставляет группам операций безопасности мгновенный доступ к устройству (также именуемого машиной) с помощью удаленного подключения к оболочке.</span><span class="sxs-lookup"><span data-stu-id="211df-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="211df-111">Это позволяет вам делать углубленные следственные действия и принимать срочные меры реагирования для оперативного сдерживания выявленных угроз в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="211df-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="211df-112">Live response предназначен для повышения эффективности расследований, позволяя группе операций безопасности собирать судебные данные, запускать сценарии, отправлять подозрительные объекты для анализа, устранения угроз и активной охоты на возникающие угрозы.</span><span class="sxs-lookup"><span data-stu-id="211df-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="211df-113">При живом отклике аналитики могут выполнять все следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="211df-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="211df-114">Запустите базовые и расширенные команды, чтобы выполнить следственные работы на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="211df-115">Скачайте файлы, такие как образцы вредоносных программ и результаты скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="211df-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="211df-116">Скачайте файлы в фоновом режиме (новые!).</span><span class="sxs-lookup"><span data-stu-id="211df-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="211df-117">Загрузите сценарий PowerShell или исполняемый в библиотеку и запустите его на устройстве с уровня клиента.</span><span class="sxs-lookup"><span data-stu-id="211df-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="211df-118">Принять или отменить действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="211df-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="211df-119">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="211df-119">Before you begin</span></span>

<span data-ttu-id="211df-120">Прежде чем инициировать сеанс на устройстве, выполните следующие требования:</span><span class="sxs-lookup"><span data-stu-id="211df-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="211df-121">**Убедитесь, что вы работаете с поддерживаемой версией Windows.**</span><span class="sxs-lookup"><span data-stu-id="211df-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="211df-122">Устройства должны запускать одну из следующих версий Windows</span><span class="sxs-lookup"><span data-stu-id="211df-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="211df-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="211df-123">**Windows 10**</span></span>
    - <span data-ttu-id="211df-124">[Версия 1909 или](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) более поздней версии</span><span class="sxs-lookup"><span data-stu-id="211df-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="211df-125">[Версия 1903 с](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="211df-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="211df-126">[Версия 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) с [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="211df-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="211df-127">[Версия 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) с [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="211df-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="211df-128">[Версия 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) с [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="211df-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="211df-129">**Windows Server 2019 — применимо только для предварительного просмотра для общего просмотра**</span><span class="sxs-lookup"><span data-stu-id="211df-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="211df-130">Версия 1903 или (с [KB4515384)](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)позже</span><span class="sxs-lookup"><span data-stu-id="211df-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="211df-131">Версия 1809 (с [KB4537818)](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="211df-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="211df-132">**Включить живой ответ со страницы расширенных параметров.**</span><span class="sxs-lookup"><span data-stu-id="211df-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="211df-133">Необходимо включить функцию живого ответа на странице [Параметры расширенных функций.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="211df-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="211df-134">Изменить эти параметры могут только пользователи, у которых есть роли администратора безопасности или глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="211df-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="211df-135">**Включить живой ответ для серверов со страницы расширенных параметров** (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="211df-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="211df-136">Изменить эти параметры могут только пользователи, у которых есть роли администратора безопасности или глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="211df-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="211df-137">**Убедитесь, что на устройстве** назначен уровень восстановления автоматизации.</span><span class="sxs-lookup"><span data-stu-id="211df-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="211df-138">Необходимо включить, по крайней мере, минимальный уровень восстановления для данной группы устройств.</span><span class="sxs-lookup"><span data-stu-id="211df-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="211df-139">В противном случае вы не сможете установить сеанс Live Response для члена этой группы.</span><span class="sxs-lookup"><span data-stu-id="211df-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="211df-140">Вы получите следующую ошибку:</span><span class="sxs-lookup"><span data-stu-id="211df-140">You'll receive the following error:</span></span>

    ![Изображение сообщения об ошибке](images/live-response-error.png)

- <span data-ttu-id="211df-142">**Включить живое выполнение сценария** без подписи ответа (необязательный).</span><span class="sxs-lookup"><span data-stu-id="211df-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="211df-143">Разрешение использования неподписаных скриптов может повысить подверженность угрозам.</span><span class="sxs-lookup"><span data-stu-id="211df-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="211df-144">Не рекомендуется запускать неподписаные скрипты, так как это может повысить подверженность угрозам.</span><span class="sxs-lookup"><span data-stu-id="211df-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="211df-145">Однако если их необходимо использовать, необходимо включить параметр на странице [Расширенные параметры функций.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="211df-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="211df-146">**Убедитесь, что у вас есть соответствующие разрешения.**</span><span class="sxs-lookup"><span data-stu-id="211df-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="211df-147">Инициировать сеанс могут только пользователи, которые получили соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="211df-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="211df-148">Дополнительные сведения о назначениях ролей см. в дополнительных сведениях [о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="211df-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="211df-149">Возможность отправки файла в библиотеку доступна только тем, у кого есть соответствующие разрешения RBAC.</span><span class="sxs-lookup"><span data-stu-id="211df-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="211df-150">Кнопка серым цветом для пользователей с только делегированными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="211df-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="211df-151">В зависимости от роли, предоставленной вам, можно запускать базовые или расширенные команды живого ответа.</span><span class="sxs-lookup"><span data-stu-id="211df-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="211df-152">Разрешения пользователей контролируются настраиваемой ролью RBAC.</span><span class="sxs-lookup"><span data-stu-id="211df-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="211df-153">Обзор панели мониторинга ответов в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="211df-153">Live response dashboard overview</span></span>
<span data-ttu-id="211df-154">Когда вы инициируете сеанс живого ответа на устройстве, откроется панель мониторинга.</span><span class="sxs-lookup"><span data-stu-id="211df-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="211df-155">Панель мониторинга предоставляет сведения о сеансе, такие как следующие:</span><span class="sxs-lookup"><span data-stu-id="211df-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="211df-156">Кто создал сеанс</span><span class="sxs-lookup"><span data-stu-id="211df-156">Who created the session</span></span>
- <span data-ttu-id="211df-157">Когда сеанс начался</span><span class="sxs-lookup"><span data-stu-id="211df-157">When the session started</span></span>
- <span data-ttu-id="211df-158">Продолжительность сеанса</span><span class="sxs-lookup"><span data-stu-id="211df-158">The duration of the session</span></span>

<span data-ttu-id="211df-159">Панель мониторинга также предоставляет вам доступ к:</span><span class="sxs-lookup"><span data-stu-id="211df-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="211df-160">Завершить сеанс.</span><span class="sxs-lookup"><span data-stu-id="211df-160">Disconnect session</span></span>
- <span data-ttu-id="211df-161">Отправка файлов в библиотеку</span><span class="sxs-lookup"><span data-stu-id="211df-161">Upload files to the library</span></span> 
- <span data-ttu-id="211df-162">Консоль команд</span><span class="sxs-lookup"><span data-stu-id="211df-162">Command console</span></span>
- <span data-ttu-id="211df-163">Журнал команд</span><span class="sxs-lookup"><span data-stu-id="211df-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="211df-164">Инициировать сеанс живого ответа на устройстве</span><span class="sxs-lookup"><span data-stu-id="211df-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="211df-165">Во входе в Центр безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="211df-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="211df-166">Перейдите на страницу списка устройств и выберите устройство для исследования.</span><span class="sxs-lookup"><span data-stu-id="211df-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="211df-167">Откроется страница устройств.</span><span class="sxs-lookup"><span data-stu-id="211df-167">The devices page opens.</span></span>

3. <span data-ttu-id="211df-168">Запустите сеанс живого ответа, выбрав **сеанс инициировать сеанс живого ответа.**</span><span class="sxs-lookup"><span data-stu-id="211df-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="211df-169">Отображается командная консоль.</span><span class="sxs-lookup"><span data-stu-id="211df-169">A command console is displayed.</span></span> <span data-ttu-id="211df-170">Подождите, пока сеанс подключается к устройству.</span><span class="sxs-lookup"><span data-stu-id="211df-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="211df-171">Используйте встроенные команды для следственных действий.</span><span class="sxs-lookup"><span data-stu-id="211df-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="211df-172">Дополнительные сведения см. в [live response commands.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="211df-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="211df-173">После завершения расследования выберите сеанс **Отключение,** а затем выберите **Подтвердите.**</span><span class="sxs-lookup"><span data-stu-id="211df-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="211df-174">Команды ответа в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="211df-174">Live response commands</span></span>

<span data-ttu-id="211df-175">В зависимости от роли, предоставленной вам, можно запускать базовые или расширенные команды живого ответа.</span><span class="sxs-lookup"><span data-stu-id="211df-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="211df-176">Разрешения пользователей контролируются пользовательскими ролями RBAC.</span><span class="sxs-lookup"><span data-stu-id="211df-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="211df-177">Дополнительные сведения о назначениях ролей см. в дополнительных сведениях [о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="211df-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="211df-178">Live response — это облачная интерактивная оболочка, так как в зависимости от качества сети и системной нагрузки между конечным пользователем и целевым устройством время отклика может различаться.</span><span class="sxs-lookup"><span data-stu-id="211df-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="211df-179">Основные команды</span><span class="sxs-lookup"><span data-stu-id="211df-179">Basic commands</span></span>

<span data-ttu-id="211df-180">Следующие команды доступны для ролей пользователей, которые могут выполнять базовые команды **живого** ответа.</span><span class="sxs-lookup"><span data-stu-id="211df-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="211df-181">Дополнительные сведения о назначениях ролей см. в дополнительных сведениях [о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="211df-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="211df-182">Команда</span><span class="sxs-lookup"><span data-stu-id="211df-182">Command</span></span> | <span data-ttu-id="211df-183">Описание</span><span class="sxs-lookup"><span data-stu-id="211df-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="211df-184">Изменение текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="211df-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="211df-185">Очищает экран консоли.</span><span class="sxs-lookup"><span data-stu-id="211df-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="211df-186">Инициирует сеанс живого ответа на устройство.</span><span class="sxs-lookup"><span data-stu-id="211df-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="211df-187">Отображает все активные подключения.</span><span class="sxs-lookup"><span data-stu-id="211df-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="211df-188">Показывает список файлов и подтекстов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="211df-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`download <file_path> &` | <span data-ttu-id="211df-189">Скачивает файл в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="211df-189">Downloads a file in the background.</span></span> |
<span data-ttu-id="211df-190">драйверы</span><span class="sxs-lookup"><span data-stu-id="211df-190">drivers</span></span> |  <span data-ttu-id="211df-191">Отображает все драйверы, установленные на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-191">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="211df-192">Возвращает загрузку файла на первый план.</span><span class="sxs-lookup"><span data-stu-id="211df-192">Returns a file download to the foreground.</span></span> |
|`fileinfo` | <span data-ttu-id="211df-193">Получение сведений о файле.</span><span class="sxs-lookup"><span data-stu-id="211df-193">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="211df-194">Находит файлы с заданным именем на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-194">Locates files by a given name on the device.</span></span> |
|`help` | <span data-ttu-id="211df-195">Предоставляет сведения о справке для команд живого ответа.</span><span class="sxs-lookup"><span data-stu-id="211df-195">Provides help information for live response commands.</span></span> |
|`persistence` | <span data-ttu-id="211df-196">Показывает все известные методы сохранения на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-196">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="211df-197">Отображает все процессы, запущенные на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-197">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="211df-198">Отображает значения реестра.</span><span class="sxs-lookup"><span data-stu-id="211df-198">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="211df-199">Отображает все запланированные задачи на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-199">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="211df-200">Отображает все службы на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-200">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="211df-201">Задает режим ведения журнала терминала для отлаживания.</span><span class="sxs-lookup"><span data-stu-id="211df-201">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="211df-202">Расширенные команды</span><span class="sxs-lookup"><span data-stu-id="211df-202">Advanced commands</span></span>
<span data-ttu-id="211df-203">Для ролей пользователей, которые имеют возможность запускать расширенные команды живого ответа, доступны следующие команды. </span><span class="sxs-lookup"><span data-stu-id="211df-203">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="211df-204">Дополнительные сведения о назначениях ролей см. в дополнительных сведениях [о создании и управлении ролями.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="211df-204">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="211df-205">Команда</span><span class="sxs-lookup"><span data-stu-id="211df-205">Command</span></span> | <span data-ttu-id="211df-206">Описание</span><span class="sxs-lookup"><span data-stu-id="211df-206">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="211df-207">Анализирует объект с различными двигателями инкриминации для вынесения вердикта.</span><span class="sxs-lookup"><span data-stu-id="211df-207">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `getfile` | <span data-ttu-id="211df-208">Получает файл с устройства.</span><span class="sxs-lookup"><span data-stu-id="211df-208">Gets a file from the device.</span></span> <br> <span data-ttu-id="211df-209">ПРИМЕЧАНИЕ. Эта команда имеет предпосылок команду.</span><span class="sxs-lookup"><span data-stu-id="211df-209">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="211df-210">Вы можете использовать команду `-auto` совместно с `getfile` автоматическим запуском необходимой команды.</span><span class="sxs-lookup"><span data-stu-id="211df-210">You can use the `-auto` command in conjunction with `getfile` to automatically run the prerequisite command.</span></span> |
| `run` | <span data-ttu-id="211df-211">Запускает скрипт PowerShell из библиотеки на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-211">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="211df-212">Списки файлов, которые были загружены в библиотеку живого ответа.</span><span class="sxs-lookup"><span data-stu-id="211df-212">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="211df-213">Помещает файл из библиотеки на устройство.</span><span class="sxs-lookup"><span data-stu-id="211df-213">Puts a file from the library to the device.</span></span> <span data-ttu-id="211df-214">Файлы сохраняются в рабочей папке и удаляются при перезапуске устройства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="211df-214">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="211df-215">Исправление объекта на устройстве.</span><span class="sxs-lookup"><span data-stu-id="211df-215">Remediates an entity on the device.</span></span> <span data-ttu-id="211df-216">Действие по исправлению будет отличаться в зависимости от типа объекта:</span><span class="sxs-lookup"><span data-stu-id="211df-216">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="211df-217">- Файл: удаление</span><span class="sxs-lookup"><span data-stu-id="211df-217">- File: delete</span></span><br><span data-ttu-id="211df-218">- Процесс: остановка, удаление файла изображений</span><span class="sxs-lookup"><span data-stu-id="211df-218">- Process: stop, delete image file</span></span><br><span data-ttu-id="211df-219">- Служба: остановка, удаление файла изображений</span><span class="sxs-lookup"><span data-stu-id="211df-219">- Service: stop, delete image file</span></span><br><span data-ttu-id="211df-220">- Запись реестра: удаление</span><span class="sxs-lookup"><span data-stu-id="211df-220">- Registry entry: delete</span></span><br><span data-ttu-id="211df-221">- Запланированная задача: удаление</span><span class="sxs-lookup"><span data-stu-id="211df-221">- Scheduled task: remove</span></span><br><span data-ttu-id="211df-222">- Элемент папки запуска: удаление файла</span><span class="sxs-lookup"><span data-stu-id="211df-222">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="211df-223">ПРИМЕЧАНИЕ. Эта команда имеет предпосылок команду.</span><span class="sxs-lookup"><span data-stu-id="211df-223">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="211df-224">Вы можете использовать команду `-auto` совместно с `remediate` автоматическим запуском необходимой команды.</span><span class="sxs-lookup"><span data-stu-id="211df-224">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="211df-225">Восстанавливает объект, который был исправлен.</span><span class="sxs-lookup"><span data-stu-id="211df-225">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="211df-226">Использование команд живого ответа</span><span class="sxs-lookup"><span data-stu-id="211df-226">Use live response commands</span></span>

<span data-ttu-id="211df-227">Команды, которые можно использовать в консоли, следуют аналогичным принципам, как [и команды Windows.](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)</span><span class="sxs-lookup"><span data-stu-id="211df-227">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="211df-228">Расширенные команды предлагают более надежный набор действий, которые позволяют принимать более мощные действия, такие как скачивание и загрузка файла, запуск скриптов на устройстве и действия по исправлению на объекте.</span><span class="sxs-lookup"><span data-stu-id="211df-228">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="211df-229">Получить файл с устройства</span><span class="sxs-lookup"><span data-stu-id="211df-229">Get a file from the device</span></span>

<span data-ttu-id="211df-230">Для сценариев, когда вы хотите получить файл с исследуемой вами устройства, можно использовать `getfile` команду.</span><span class="sxs-lookup"><span data-stu-id="211df-230">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="211df-231">Это позволяет сохранить файл с устройства для дальнейшего исследования.</span><span class="sxs-lookup"><span data-stu-id="211df-231">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="211df-232">Применяются следующие ограничения размера файла:</span><span class="sxs-lookup"><span data-stu-id="211df-232">The following file size limits apply:</span></span>
>- <span data-ttu-id="211df-233">`getfile` ограничение: 3 ГБ</span><span class="sxs-lookup"><span data-stu-id="211df-233">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="211df-234">`fileinfo` ограничение: 10 ГБ</span><span class="sxs-lookup"><span data-stu-id="211df-234">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="211df-235">`library` ограничение: 250 МБ</span><span class="sxs-lookup"><span data-stu-id="211df-235">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="211df-236">Скачайте файл в фоновом режиме</span><span class="sxs-lookup"><span data-stu-id="211df-236">Download a file in the background</span></span>

<span data-ttu-id="211df-237">Чтобы группа операций безопасности продолжила изучение влияния устройства, файлы теперь можно скачивать в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="211df-237">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="211df-238">Чтобы скачать файл в фоновом режиме, в командной консоли живого ответа введите `download <file_path> &` .</span><span class="sxs-lookup"><span data-stu-id="211df-238">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="211df-239">Если вы ожидаете скачивания файла, его можно переместить в фоновом режиме с помощью Ctrl + Z.</span><span class="sxs-lookup"><span data-stu-id="211df-239">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="211df-240">Чтобы скачать файл на переднем плане, в командной консоли живого ответа введите `fg <command_id>` .</span><span class="sxs-lookup"><span data-stu-id="211df-240">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="211df-241">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="211df-241">Here are some examples:</span></span>


|<span data-ttu-id="211df-242">Команда</span><span class="sxs-lookup"><span data-stu-id="211df-242">Command</span></span>  |<span data-ttu-id="211df-243">Действие</span><span class="sxs-lookup"><span data-stu-id="211df-243">What it does</span></span>  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |<span data-ttu-id="211df-244">Начинается загрузка файла с *some_file.exe* в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="211df-244">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="211df-245">Возвращает загрузку с командным ИД *1234* на переднем плане.</span><span class="sxs-lookup"><span data-stu-id="211df-245">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="211df-246">Поместите файл в библиотеку</span><span class="sxs-lookup"><span data-stu-id="211df-246">Put a file in the library</span></span>

<span data-ttu-id="211df-247">В живом отклике есть библиотека, в которой можно вложить файлы.</span><span class="sxs-lookup"><span data-stu-id="211df-247">Live response has a library where you can put files into.</span></span> <span data-ttu-id="211df-248">В библиотеке хранится файлы (например, сценарии), которые можно запускать в сеансе живого ответа на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="211df-248">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="211df-249">Живой отклик позволяет запускать скрипты PowerShell, однако прежде чем запустить их, необходимо сначала поместить файлы в библиотеку.</span><span class="sxs-lookup"><span data-stu-id="211df-249">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="211df-250">Вы можете иметь коллекцию скриптов PowerShell, которые можно запускать на устройствах, с помощью которые вы инициируете сеансы живого ответа.</span><span class="sxs-lookup"><span data-stu-id="211df-250">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="211df-251">Отправка файла в библиотеку</span><span class="sxs-lookup"><span data-stu-id="211df-251">To upload a file in the library</span></span>

1. <span data-ttu-id="211df-252">Нажмите **кнопку Отправка файла в библиотеку**.</span><span class="sxs-lookup"><span data-stu-id="211df-252">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="211df-253">Щелкните **Обзор** и выберите файл.</span><span class="sxs-lookup"><span data-stu-id="211df-253">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="211df-254">Краткое описание.</span><span class="sxs-lookup"><span data-stu-id="211df-254">Provide a brief description.</span></span>

4. <span data-ttu-id="211df-255">Укажите, хотите ли вы переписать файл с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="211df-255">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="211df-256">Если вы хотите быть, узнайте, какие параметры необходимы для скрипта, выберите поле для проверки параметров скрипта.</span><span class="sxs-lookup"><span data-stu-id="211df-256">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="211df-257">В текстовом поле введите пример и описание.</span><span class="sxs-lookup"><span data-stu-id="211df-257">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="211df-258">Нажмите **кнопку Подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="211df-258">Click **Confirm**.</span></span> 

7. <span data-ttu-id="211df-259">(Необязательный) Чтобы убедиться, что файл был загружен в библиотеку, запустите `library` команду.</span><span class="sxs-lookup"><span data-stu-id="211df-259">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="211df-260">Отмена команды</span><span class="sxs-lookup"><span data-stu-id="211df-260">Cancel a command</span></span>
<span data-ttu-id="211df-261">В любое время во время сеанса можно отменить команду, нажав CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="211df-261">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="211df-262">Использование этого ярлыка не остановит команду в стороне агента.</span><span class="sxs-lookup"><span data-stu-id="211df-262">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="211df-263">Он отменит команду только на портале.</span><span class="sxs-lookup"><span data-stu-id="211df-263">It will only cancel the command in the portal.</span></span> <span data-ttu-id="211df-264">Таким образом, изменение операций, таких как "исправление", может продолжаться, в то время как команда отменяется.</span><span class="sxs-lookup"><span data-stu-id="211df-264">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

### <a name="automatically-run-prerequisite-commands"></a><span data-ttu-id="211df-265">Автоматически запускать команды обязательных условий</span><span class="sxs-lookup"><span data-stu-id="211df-265">Automatically run prerequisite commands</span></span>

<span data-ttu-id="211df-266">Некоторые команды имеют необходимые команды для запуска.</span><span class="sxs-lookup"><span data-stu-id="211df-266">Some commands have prerequisite commands to run.</span></span> <span data-ttu-id="211df-267">Если вы не запустите предпосылок, вы получите ошибку.</span><span class="sxs-lookup"><span data-stu-id="211df-267">If you don't run the prerequisite command, you'll get an error.</span></span> <span data-ttu-id="211df-268">Например, запуск команды `download` без `fileinfo` возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="211df-268">For example, running the `download` command without `fileinfo` will return an error.</span></span>

<span data-ttu-id="211df-269">Автоматический флаг можно использовать для автоматического запуска необходимых команд, например:</span><span class="sxs-lookup"><span data-stu-id="211df-269">You can use the auto flag to automatically run prerequisite commands, for example:</span></span>

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a><span data-ttu-id="211df-270">Запуск сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="211df-270">Run a PowerShell script</span></span> 

<span data-ttu-id="211df-271">Прежде чем запустить сценарий PowerShell, сначала необходимо отправить его в библиотеку.</span><span class="sxs-lookup"><span data-stu-id="211df-271">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="211df-272">После отправки сценария в библиотеку используйте команду `run` для запуска сценария.</span><span class="sxs-lookup"><span data-stu-id="211df-272">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="211df-273">Если вы планируете использовать неподписаный скрипт в сеансе, необходимо включить параметр на странице [Расширенные параметры функций.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="211df-273">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="211df-274">Разрешение использования неподписаных скриптов может повысить подверженность угрозам.</span><span class="sxs-lookup"><span data-stu-id="211df-274">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="211df-275">Применение параметров команды</span><span class="sxs-lookup"><span data-stu-id="211df-275">Apply command parameters</span></span>

- <span data-ttu-id="211df-276">Просмотр справки консоли, чтобы узнать о параметрах команды.</span><span class="sxs-lookup"><span data-stu-id="211df-276">View the console help to learn about command parameters.</span></span> <span data-ttu-id="211df-277">Чтобы узнать об отдельной команде, запустите:</span><span class="sxs-lookup"><span data-stu-id="211df-277">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="211df-278">При применении параметров к командам обратите внимание, что параметры обрабатываются на основе фиксированного порядка:</span><span class="sxs-lookup"><span data-stu-id="211df-278">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="211df-279">При указании параметров за пределами фиксированного порядка укажите имя параметра с дефисом перед предоставлением значения:</span><span class="sxs-lookup"><span data-stu-id="211df-279">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="211df-280">При использовании команд с необходимыми командами можно использовать флаги:</span><span class="sxs-lookup"><span data-stu-id="211df-280">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="211df-281">`<command name> -type file -id <file path> - auto` или `remediate file <file path> - auto`.</span><span class="sxs-lookup"><span data-stu-id="211df-281">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="211df-282">Поддерживаемые типы выходных данных</span><span class="sxs-lookup"><span data-stu-id="211df-282">Supported output types</span></span>

<span data-ttu-id="211df-283">Live response поддерживает типы вывода таблицы и формата JSON.</span><span class="sxs-lookup"><span data-stu-id="211df-283">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="211df-284">Для каждой команды по умолчанию существует выходное поведение.</span><span class="sxs-lookup"><span data-stu-id="211df-284">For each command, there's a default output behavior.</span></span> <span data-ttu-id="211df-285">Вы можете изменить выход в предпочтительном формате вывода с помощью следующих команд:</span><span class="sxs-lookup"><span data-stu-id="211df-285">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="211df-286">Меньше полей отображается в формате таблицы из-за ограниченного пространства.</span><span class="sxs-lookup"><span data-stu-id="211df-286">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="211df-287">Чтобы узнать больше о результатах, можно использовать команду вывода JSON, чтобы показать дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="211df-287">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="211df-288">Поддерживаемые выходные трубы</span><span class="sxs-lookup"><span data-stu-id="211df-288">Supported output pipes</span></span>

<span data-ttu-id="211df-289">Live response поддерживает выходные трубопроводы в CLI и файл.</span><span class="sxs-lookup"><span data-stu-id="211df-289">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="211df-290">CLI — это поведение вывода по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="211df-290">CLI is the default output behavior.</span></span> <span data-ttu-id="211df-291">Вывод можно с помощью следующей команды: [command] > [filename].txt.</span><span class="sxs-lookup"><span data-stu-id="211df-291">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="211df-292">Пример.</span><span class="sxs-lookup"><span data-stu-id="211df-292">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="211df-293">Просмотр журнала команд</span><span class="sxs-lookup"><span data-stu-id="211df-293">View the command log</span></span>

<span data-ttu-id="211df-294">Выберите **вкладку Журнал Команд,** чтобы увидеть команды, используемые на устройстве во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="211df-294">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="211df-295">Каждая команда отслеживается с полными сведениями, такими как:</span><span class="sxs-lookup"><span data-stu-id="211df-295">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="211df-296">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="211df-296">ID</span></span>
- <span data-ttu-id="211df-297">Командная строка</span><span class="sxs-lookup"><span data-stu-id="211df-297">Command line</span></span>
- <span data-ttu-id="211df-298">Duration</span><span class="sxs-lookup"><span data-stu-id="211df-298">Duration</span></span>
- <span data-ttu-id="211df-299">Боковая планка состояния и ввода или вывода</span><span class="sxs-lookup"><span data-stu-id="211df-299">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="211df-300">Ограничения</span><span class="sxs-lookup"><span data-stu-id="211df-300">Limitations</span></span>

- <span data-ttu-id="211df-301">Сеансы живого ответа ограничиваются 10 сеансами живого ответа одновременно.</span><span class="sxs-lookup"><span data-stu-id="211df-301">Live response sessions are limited to 10 live response sessions at a time.</span></span>
- <span data-ttu-id="211df-302">Масштабное выполнение команд не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="211df-302">Large-scale command execution is not supported.</span></span>
- <span data-ttu-id="211df-303">Неактивное время действия сеанса неактивного времени отклика — 5 минут.</span><span class="sxs-lookup"><span data-stu-id="211df-303">Live response session inactive timeout value is 5 minutes.</span></span> 
- <span data-ttu-id="211df-304">Пользователь может одновременно инициировать только один сеанс.</span><span class="sxs-lookup"><span data-stu-id="211df-304">A user can only initiate one session at a time.</span></span>
- <span data-ttu-id="211df-305">Устройство может быть только в одном сеансе одновременно.</span><span class="sxs-lookup"><span data-stu-id="211df-305">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="211df-306">Применяются следующие ограничения размера файла:</span><span class="sxs-lookup"><span data-stu-id="211df-306">The following file size limits apply:</span></span>
   - <span data-ttu-id="211df-307">`getfile` ограничение: 3 ГБ</span><span class="sxs-lookup"><span data-stu-id="211df-307">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="211df-308">`fileinfo` ограничение: 10 ГБ</span><span class="sxs-lookup"><span data-stu-id="211df-308">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="211df-309">`library` ограничение: 250 МБ</span><span class="sxs-lookup"><span data-stu-id="211df-309">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="211df-310">Связанная статья</span><span class="sxs-lookup"><span data-stu-id="211df-310">Related article</span></span>
- [<span data-ttu-id="211df-311">Примеры команд живых ответов</span><span class="sxs-lookup"><span data-stu-id="211df-311">Live response command examples</span></span>](live-response-command-examples.md)
