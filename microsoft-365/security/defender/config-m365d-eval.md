---
title: Настройка столбов Microsoft 365 Defender для пробной лаборатории или пилотной среды
description: Настройте столбы Microsoft 365 Defender, такие как Microsoft Defender для Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security и Microsoft Defender для конечной точки, для пробной лаборатории или пилотной среды.
keywords: настройка пробной пробной системы Microsoft Threat Protection, конфигурация пробной конфигурации Microsoft Threat Protection, настройка пилотного проекта Microsoft Threat Protection, настройка столбов Microsoft Threat Protection, столбов Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5ab4019751a26507fcc80007d3262f20f861d25c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071486"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="75d57-104">Настройка столбов Microsoft 365 Defender для пробной лаборатории или пилотной среды</span><span class="sxs-lookup"><span data-stu-id="75d57-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75d57-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="75d57-105">**Applies to:**</span></span>
- <span data-ttu-id="75d57-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75d57-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="75d57-107">Создание пробной лаборатории или пилотной среды Microsoft 365 Defender и ее развертывание — это трех этапный процесс:</span><span class="sxs-lookup"><span data-stu-id="75d57-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="75d57-108">[![Этап 1. Подготовка](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="75d57-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="75d57-109">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="75d57-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="75d57-110">[![Этап 2. Настройка](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="75d57-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="75d57-111">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="75d57-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Этап 3. На борту](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="75d57-113">Этап 3. На борту</span><span class="sxs-lookup"><span data-stu-id="75d57-113">Phase 3: Onboard</span></span> | <span data-ttu-id="75d57-114">[![Назад к пилоту](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="75d57-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="75d57-115">Вернуться к экспериментальной книге воспроизведения</span><span class="sxs-lookup"><span data-stu-id="75d57-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="75d57-116">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="75d57-116">*You are here!*</span></span> | |

<span data-ttu-id="75d57-117">Вы в настоящее время на этапе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="75d57-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="75d57-118">Подготовка является ключом к успешному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="75d57-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="75d57-119">В этой статье вы будете ориентироваться на точки, которые необходимо учитывать при подготовке к развертыванию Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="75d57-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="75d57-120">Столбы Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75d57-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="75d57-121">Microsoft 365 Defender состоит из четырех столпов.</span><span class="sxs-lookup"><span data-stu-id="75d57-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="75d57-122">Хотя один из столбов уже может обеспечить безопасность вашей сетевой организации, включение четырех столбов Microsoft 365 Defender даст вашей организации наибольшее значение.</span><span class="sxs-lookup"><span data-stu-id="75d57-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Решение of_Microsoft 365 Defender для пользователей, Microsoft Defender for Identity, для конечных точек Microsoft Defender для конечной точки, для облачных приложений, microsoft Cloud App Security и для данных, Microsoft Defender для Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="75d57-124">В этом разделе вы сможете настроить:</span><span class="sxs-lookup"><span data-stu-id="75d57-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="75d57-125">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="75d57-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="75d57-126">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="75d57-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="75d57-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="75d57-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="75d57-128">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="75d57-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="75d57-129">Настройка Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="75d57-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="75d57-130">Пропустить этот шаг, если вы уже включили Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="75d57-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="75d57-131">Существует модуль PowerShell под названием *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* который помогает определить некоторые из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="75d57-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="75d57-132">При запуске в качестве администратора в клиенте get-ORCAReport поможет сгенерировать оценку параметров защиты от нежелательной почты, защиты от фишинга и других параметров гигиены сообщений.</span><span class="sxs-lookup"><span data-stu-id="75d57-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="75d57-133">Этот модуль можно скачать из https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="75d57-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="75d57-134">Перейдите к политике управления безопасностью Центра & Office [365.](https://protection.office.com/homepage)  >    >  </span><span class="sxs-lookup"><span data-stu-id="75d57-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Страница of_Office 365 & центра управления угрозами](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="75d57-136">Нажмите **кнопку "Анти-фишинг",** **выберите Создать** и заполнить имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="75d57-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="75d57-137">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="75d57-137">Click **Next**.</span></span>

   ![Страница of_Office 365 & центра по борьбе с фишингом, на которой можно назвать политику](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="75d57-139">Изменение политики расширенных антифишинга в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="75d57-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="75d57-140">Измените **расширенный порог фишинга** на **2 - Aggressive.**</span><span class="sxs-lookup"><span data-stu-id="75d57-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="75d57-141">Нажмите **кнопку Добавить** выпадаемое меню условия и выберите домен (s) в качестве домена получателя.</span><span class="sxs-lookup"><span data-stu-id="75d57-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="75d57-142">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="75d57-142">Click **Next**.</span></span>

   ![Страница of_Office 365 & центра защиты от фишинга, на которой можно добавить условие для его приложения](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="75d57-144">Просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="75d57-144">Review your settings.</span></span> <span data-ttu-id="75d57-145">Нажмите **кнопку Создать эту политику,** чтобы подтвердить.</span><span class="sxs-lookup"><span data-stu-id="75d57-145">Click **Create this policy** to confirm.</span></span> 

   ![Страница of_Office 365 & центра по борьбе с фишингом, на которой можно просмотреть параметры и нажать кнопку создать эту политику](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="75d57-147">Выберите **безопасные вложения** и выберите параметр Включить ATP для **SharePoint, OneDrive и Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="75d57-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Страница of_Office 365 & безопасности, на которой можно включить atP для SharePoint, OneDrive и Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="75d57-149">Щелкните значок +, чтобы создать новую политику безопасного вложения, применить ее в качестве домена получателя к доменам.</span><span class="sxs-lookup"><span data-stu-id="75d57-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="75d57-150">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75d57-150">Click **Save**.</span></span>

   ![Страница of_Office 365 & безопасности, на которой можно создать новую политику безопасного вложения](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="75d57-152">Далее выберите политику **безопасных ссылок,** а затем нажмите значок карандаша, чтобы изменить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75d57-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="75d57-153">Убедитесь, что не **отслеживайте,** когда пользователи щелкают параметр безопасных ссылок, а остальные параметры выбраны.</span><span class="sxs-lookup"><span data-stu-id="75d57-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="75d57-154">Подробные [сведения см. в параметрах](/microsoft-365/security/defender-365-security/recommended-settings-for-eop-and-office365) Безопасные ссылки.</span><span class="sxs-lookup"><span data-stu-id="75d57-154">See [Safe Links settings](/microsoft-365/security/defender-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="75d57-155">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75d57-155">Click **Save**.</span></span> 

   ![Страница of_Office 365 & центра соответствия требованиям, которая показывает, что параметр Не отслеживайте, когда пользователи щелкают безопасно, не выбран](../../media/mtp-eval-38.png)

9. <span data-ttu-id="75d57-157">Далее выберите **политику борьбы с вредоносными** программами, выберите значение по умолчанию и выберите значок карандаша.</span><span class="sxs-lookup"><span data-stu-id="75d57-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="75d57-158">Щелкните **Параметры** и выберите **Да и используйте текст** уведомления по умолчанию, чтобы включить ответ обнаружения **вредоносных программ.**</span><span class="sxs-lookup"><span data-stu-id="75d57-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="75d57-159">Включив фильтр **типов общих вложений.**</span><span class="sxs-lookup"><span data-stu-id="75d57-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="75d57-160">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75d57-160">Click **Save**.</span></span>

    ![Страница of_Office 365 & центра соответствия требованиям, которая показывает, что ответ на обнаружение вредоносных программ включен с помощью уведомления по умолчанию и включен фильтр типов вложений](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="75d57-162">Перейдите к журналу поиска журнала аудита безопасности Office [365 &](https://protection.office.com/homepage)Центра аудита соответствия требованиям и  >    >   включив аудит.</span><span class="sxs-lookup"><span data-stu-id="75d57-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Страница of_Office 365 & центра соответствия требованиям, на которой можно включить поиск журнала аудита](../../media/mtp-eval-40.png)

12. <span data-ttu-id="75d57-164">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="75d57-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75d57-165">Перейдите в центр управления & Office [365](https://protection.office.com/homepage)и выберите Microsoft Defender для параметров конечной точки в правом верхнем углу  >    >   экрана. </span><span class="sxs-lookup"><span data-stu-id="75d57-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="75d57-166">В диалоговом окне Защитник для конечной точки включите **подключение к Microsoft Defender для конечной точки.**</span><span class="sxs-lookup"><span data-stu-id="75d57-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Страница of_Office 365 & безопасности, на которой можно включить подключение Microsoft Defender для конечной точки](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="75d57-168">Настройка Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="75d57-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="75d57-169">Пропустить этот шаг, если вы уже включили Microsoft Defender для identity</span><span class="sxs-lookup"><span data-stu-id="75d57-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="75d57-170">Перейдите в Центр безопасности [Microsoft 365](https://security.microsoft.com/info) > **выберите** дополнительные ресурсы Microsoft Defender для  >  **удостоверения.**</span><span class="sxs-lookup"><span data-stu-id="75d57-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Страница of_Microsoft 365 Центр безопасности, на которой можно открыть Microsoft Defender для удостоверений](../../media/mtp-eval-42.png)

2. <span data-ttu-id="75d57-172">Нажмите **кнопку Создать,** чтобы запустить мастер Microsoft Defender для удостоверений.</span><span class="sxs-lookup"><span data-stu-id="75d57-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Страница мастера of_Microsoft Defender for Identity, на которой необходимо нажать кнопку Создать](../../media/mtp-eval-43.png)

3. <span data-ttu-id="75d57-174">Выберите Предоставление имени пользователя и пароля для подключения **к лесу Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="75d57-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Приветственный of_Microsoft Защитник удостоверений](../../media/mtp-eval-44.png)

4. <span data-ttu-id="75d57-176">Введите учетные данные Active Directory на месте.</span><span class="sxs-lookup"><span data-stu-id="75d57-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="75d57-177">Это может быть любая учетная запись пользователя, которая имеет доступ к active Directory.</span><span class="sxs-lookup"><span data-stu-id="75d57-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Страница of_Microsoft defender for Identity Directory, на которой необходимо поместить учетные данные](../../media/mtp-eval-45.png)

5. <span data-ttu-id="75d57-179">Далее выберите **настройка датчика загрузки** и передача файла на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="75d57-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Страница of_Microsoft Defender для удостоверений, на которой можно выбрать установку датчика загрузки](../../media/mtp-eval-46.png)

6. <span data-ttu-id="75d57-181">Выполните установку датчика идентификации Microsoft Defender для идентификации и начните следовать за мастером.</span><span class="sxs-lookup"><span data-stu-id="75d57-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Страница of_Microsoft Defender для удостоверения, на которой необходимо щелкнуть далее, чтобы следовать мастеру датчика идентификации Microsoft Defender для удостоверений](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="75d57-183">Нажмите **кнопку Далее** в типе развертывания датчика.</span><span class="sxs-lookup"><span data-stu-id="75d57-183">Click **Next** at the sensor deployment type.</span></span>

   ![Страница of_Microsoft Defender для удостоверения, на которой необходимо щелкнуть кнопку далее, чтобы перейти на следующую страницу](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="75d57-185">Скопируйте ключ доступа, так как необходимо ввести его далее в мастере.</span><span class="sxs-lookup"><span data-stu-id="75d57-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Страница of_the датчиков, на которой необходимо скопировать ключ доступа, который необходимо ввести на следующей странице мастера установки датчика настройки сенсора Microsoft Defender для удостоверений](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="75d57-187">Скопируйте ключ доступа в мастер и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="75d57-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Страница мастера of_Microsoft защитника для датчика удостоверений, на которой необходимо предоставить ключ доступа, а затем нажать кнопку установки](../../media/mtp-eval-50.png)

10. <span data-ttu-id="75d57-189">Поздравляем, вы успешно настроили Microsoft Defender для identity на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="75d57-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Завершение of_Microsoft защитника для мастера установки датчика удостоверений, на котором необходимо нажать кнопку готовой](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="75d57-191">В разделе [Защитник Майкрософт для](https://go.microsoft.com/fwlink/?linkid=2040449) параметров удостоверений выберите \*\*Microsoft Defender для конечной точки \*\*, а затем включив переключить.</span><span class="sxs-lookup"><span data-stu-id="75d57-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="75d57-192">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75d57-192">Click **Save**.</span></span> 

    ![Страница of_the защитника Майкрософт для параметров удостоверений, на которой необходимо включить переключить параметры Microsoft Defender для конечной точки](../../media/mtp-eval-52.png)

> [!NOTE]
> <span data-ttu-id="75d57-194">Защитник Windows atP был ребрендинг в качестве Защитника Microsoft для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="75d57-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75d57-195">Изменения в ребрендинге на всех наших порталах в настоящее время выкатываются для обеспечения согласованности.</span><span class="sxs-lookup"><span data-stu-id="75d57-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="75d57-196">Настройка безопасности облачных приложений Майкрософт</span><span class="sxs-lookup"><span data-stu-id="75d57-196">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="75d57-197">Пропустить этот шаг, если вы уже включили microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="75d57-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="75d57-198">Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/info)  >  **Дополнительные ресурсы** Microsoft Cloud App  >  **Security**.</span><span class="sxs-lookup"><span data-stu-id="75d57-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Страница of_Microsoft центра безопасности 365, на которой можно увидеть карту Microsoft Cloud App и нажать кнопку открыть](../../media/mtp-eval-53.png)

2. <span data-ttu-id="75d57-200">На информационном запросе для интеграции Microsoft Defender для удостоверений выберите **Включить Microsoft Defender для интеграции данных удостоверений.**</span><span class="sxs-lookup"><span data-stu-id="75d57-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Подсказка of_the для интеграции Microsoft Defender для удостоверений, где необходимо выбрать ссылку Включить microsoft Defender для интеграции данных удостоверений](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="75d57-202">Если вы не видите эту подсказку, это может означать, что интеграция данных Microsoft Defender для удостоверений уже включена.</span><span class="sxs-lookup"><span data-stu-id="75d57-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="75d57-203">Однако, если вы не уверены, обратитесь к ИТ-администратору, чтобы подтвердить это.</span><span class="sxs-lookup"><span data-stu-id="75d57-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="75d57-204">Перейдите **к параметрам,** включите переключить кнопку **Microsoft Defender для** интеграции удостоверений, а затем нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75d57-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Страница of_the, на которой необходимо включить переключению интеграции Microsoft Defender для удостоверений, а затем нажмите кнопку сохранить](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="75d57-206">Для новых экземпляров Microsoft Defender для удостоверений эта интеграция автоматически включена.</span><span class="sxs-lookup"><span data-stu-id="75d57-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="75d57-207">Подтвердите, что интеграция Microsoft Defender для удостоверений включена, прежде чем приступить к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="75d57-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="75d57-208">В настройках обнаружения облака выберите Microsoft Defender для интеграции **конечных** точек, а затем в этом параметре включить интеграцию.</span><span class="sxs-lookup"><span data-stu-id="75d57-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="75d57-209">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75d57-209">Click **Save**.</span></span>

   ![Изображение of_the для страницы Microsoft Defender для конечной точки, на которой выбирается блок несанкционированная проверка приложений в рамках интеграции Microsoft Defender для конечной точки.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="75d57-212">В параметрах обнаружения облака выберите обогащение **пользователей,** а затем включить интеграцию с Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75d57-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Изображение раздела Обогащение пользователей, в котором выбирается обогащение обнаруженных идентификаторов пользователей с помощью контрольного ящика имен пользователей Azure Active Directory.](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="75d57-214">Настройка Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="75d57-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="75d57-215">Пропустить этот шаг, если вы уже включили Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="75d57-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="75d57-216">Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/info)  >  **Дополнительные ресурсы** Microsoft Defender Security  >  **Center**.</span><span class="sxs-lookup"><span data-stu-id="75d57-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="75d57-217">Нажмите кнопку **Open** (Открыть).</span><span class="sxs-lookup"><span data-stu-id="75d57-217">Click **Open**.</span></span>

   ![Параметр of_Microsoft Центр безопасности Защитника на странице Microsoft 365 Центр безопасности](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="75d57-219">Следуйте мастеру Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="75d57-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="75d57-220">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="75d57-220">Click **Next**.</span></span> 

   ![Страница of_the Центра безопасности Защитника Майкрософт](../../media/mtp-eval-59.png)

3. <span data-ttu-id="75d57-222">Выбор зависит от предпочтительного расположения хранилища данных, политики хранения данных, размера организации и выбора функций предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="75d57-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Страница of_the для выбора страны хранения данных, политики хранения и размера организации.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="75d57-225">Вы не можете изменить некоторые параметры, например расположение хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="75d57-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="75d57-226">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="75d57-226">Click **Next**.</span></span> 

4. <span data-ttu-id="75d57-227">Нажмите **кнопку Продолжить,** и она будет поддерживать защитника Microsoft для клиента конечной точки.</span><span class="sxs-lookup"><span data-stu-id="75d57-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Запрос of_the страницы, нажав кнопку продолжить для создания облачного экземпляра](../../media/mtp-eval-61.png)

5. <span data-ttu-id="75d57-229">На борту конечных точек с помощью групповых политик, microsoft Endpoint Manager или запуска локального сценария в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="75d57-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75d57-230">Для простоты в этом руководстве используется локальный сценарий.</span><span class="sxs-lookup"><span data-stu-id="75d57-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="75d57-231">Нажмите **кнопку Скачать** пакет и скопируйте сценарий в конечной точке (ы).</span><span class="sxs-lookup"><span data-stu-id="75d57-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Изображение of_page нажать кнопку Пакет загрузки, чтобы скопировать сценарий включения в конечную точку или конечные точки](../../media/mtp-eval-62.png)

7. <span data-ttu-id="75d57-233">На конечной точке запустите сценарий в качестве администратора и выберите Y.</span><span class="sxs-lookup"><span data-stu-id="75d57-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Командная of_the, в которой вы запустите сценарий бортовой работы и выберите Y для работы](../../media/mtp-eval-63.png)

8. <span data-ttu-id="75d57-235">Поздравляем, вы вошел в первую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="75d57-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Изображение of_the, где вы получаете подтверждение того, что вы на борту вашей первой конечной точки.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="75d57-238">Скопируйте тест обнаружения в мастере Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="75d57-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the выполнить тестовый шаг обнаружения, на котором необходимо нажать копию, чтобы скопировать сценарий тестирования обнаружения, который необходимо вклеить в командную подсказку](../../media/mtp-eval-65.png)

10. <span data-ttu-id="75d57-240">Скопируйте скрипт PowerShell в командную команду и запустите его.</span><span class="sxs-lookup"><span data-stu-id="75d57-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Подсказка of_command, где следует скопировать сценарий PowerShell в командную команду и запустить его](../../media/mtp-eval-66.png)

11. <span data-ttu-id="75d57-242">Выберите **Начните использовать Microsoft Defender для конечной точки** из мастера.</span><span class="sxs-lookup"><span data-stu-id="75d57-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Запрос of_the подтверждения от мастера, где необходимо нажать кнопку Начните использовать Microsoft Defender для конечной точки](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="75d57-244">Посетите [Центр безопасности Защитника Майкрософт.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="75d57-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="75d57-245">Перейдите **в параметры** и выберите **расширенные функции.**</span><span class="sxs-lookup"><span data-stu-id="75d57-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Меню of_Microsoft Центра безопасности Защитника, в котором необходимо выбрать расширенные функции](../../media/mtp-eval-68.png)

13. <span data-ttu-id="75d57-247">Включи интеграцию с **Microsoft Defender для удостоверений.**</span><span class="sxs-lookup"><span data-stu-id="75d57-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Расширенные of_Microsoft Центра безопасности Защитника, параметр Microsoft Defender для удостоверений, чтобы включить](../../media/mtp-eval-69.png)

14. <span data-ttu-id="75d57-249">Включи интеграцию с **Office 365 Threat Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="75d57-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Расширенные of_Microsoft Центра безопасности Защитника, параметр Office 365 Threat Intelligence, который необходимо включить](../../media/mtp-eval-70.png)

15. <span data-ttu-id="75d57-251">Включение интеграции с **microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="75d57-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Расширенные of_Microsoft центр безопасности Defender, параметр Microsoft Cloud App Security, чтобы включить](../../media/mtp-eval-71.png)

16. <span data-ttu-id="75d57-253">Прокрутите вниз **и нажмите кнопку Сохранить параметры,** чтобы подтвердить новые интеграции.</span><span class="sxs-lookup"><span data-stu-id="75d57-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Кнопка of_Save, которую необходимо нажать](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="75d57-255">Запуск службы Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75d57-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="75d57-256">Начиная с 1 июня 2020 г. Корпорация Майкрософт автоматически включает функции Microsoft 365 Defender для всех подходящих клиентов.</span><span class="sxs-lookup"><span data-stu-id="75d57-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="75d57-257">Подробнее см. в статье [Microsoft Tech Community о праве на лицензию.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)</span><span class="sxs-lookup"><span data-stu-id="75d57-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="75d57-258">Перейдите в Центр безопасности [Microsoft 365](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="75d57-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="75d57-259">Перейдите **к параметрам** и выберите **Защитник Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="75d57-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="75d57-260">Снимок of_Microsoft 365 Defender со страницы Параметры Центра безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75d57-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="75d57-261">Дополнительные рекомендации см. в обзоре [Turn on Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="75d57-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span> 

<span data-ttu-id="75d57-262">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="75d57-262">Congratulations!</span></span> <span data-ttu-id="75d57-263">Вы только что создали пробную лабораторию Или пилотную среду Microsoft 365 Defender!</span><span class="sxs-lookup"><span data-stu-id="75d57-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="75d57-264">Теперь вы можете ознакомиться с пользовательским интерфейсом Microsoft 365 Defender!</span><span class="sxs-lookup"><span data-stu-id="75d57-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="75d57-265">Узнайте, что можно узнать из следующего интерактивного руководства Microsoft 365 Defender и узнайте, как использовать каждую панель мониторинга для выполнения задач ежедневной работы с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="75d57-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="75d57-266">Далее можно смоделировать атаку и увидеть, как возможности кросс-продукта обнаруживают, создают оповещения и автоматически реагируют на без файловую атаку на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="75d57-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="75d57-267">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="75d57-267">Next step</span></span>

- <span data-ttu-id="75d57-268">[Создание тестового оповещения](generate-test-alert.md) — запустите имитацию атаки в пробной лаборатории Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="75d57-268">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>