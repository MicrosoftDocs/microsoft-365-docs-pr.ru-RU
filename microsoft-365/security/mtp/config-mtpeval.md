---
title: Настройка основ Защитника Microsoft 365 для пробной или пилотной среды
description: Настройте основы Защитника Microsoft 365, такие как Microsoft Defender для Office 365, Microsoft Defender для удостоверений, Microsoft Cloud App Security и Microsoft Defender для конечной точки, для пробной или пилотной среды.
keywords: настройка пробного комплекта Защиты от угроз (Майкрософт), конфигурация пробного комплекта Защиты от угроз (Майкрософт), настройка пилотного проекта Защиты от угроз (Майкрософт), настройка основ Защиты от угроз (Майкрософт), основы Защиты от угроз (Майкрософт)
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932242"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="8d2f1-104">Настройка основных элементов Microsoft 365 Defender для пробной лабораторной или пилотной среды</span><span class="sxs-lookup"><span data-stu-id="8d2f1-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8d2f1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-105">**Applies to:**</span></span>
- <span data-ttu-id="8d2f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d2f1-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="8d2f1-107">Создание пробной лабораторной или пилотной среды Microsoft 365 Defender и ее развертывание — это трех этапов:</span><span class="sxs-lookup"><span data-stu-id="8d2f1-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="8d2f1-108">[![Этап 1. Подготовка](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="8d2f1-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="8d2f1-109">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="8d2f1-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="8d2f1-110">[![Этап 2. Настройка](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="8d2f1-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="8d2f1-111">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="8d2f1-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Этап 3. Ветвь](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="8d2f1-113">Этап 3. Ветвь</span><span class="sxs-lookup"><span data-stu-id="8d2f1-113">Phase 3: Onboard</span></span> | <span data-ttu-id="8d2f1-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="8d2f1-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="8d2f1-115">Вернуться к пилотной книге</span><span class="sxs-lookup"><span data-stu-id="8d2f1-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="8d2f1-116">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="8d2f1-116">*You are here!*</span></span> | |

<span data-ttu-id="8d2f1-117">В настоящее время вы работаете на этапе настройки.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="8d2f1-118">Подготовка — это ключ к успешному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="8d2f1-119">В этой статье вы получите руководство по пунктам, которые необходимо учитывать при подготовке к развертыванию Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="8d2f1-120">Основы Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d2f1-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="8d2f1-121">Защитник Microsoft 365 состоит из четырех основных элементов.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="8d2f1-122">Хотя один из основных принципов уже может быть важным для безопасности вашей сетевой организации, включение четырех опор Защитника Microsoft 365 придаст вашей организации наибольшее значение.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="8d2f1-124">В этом разделе вы сможете настроить:</span><span class="sxs-lookup"><span data-stu-id="8d2f1-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="8d2f1-125">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="8d2f1-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="8d2f1-126">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="8d2f1-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="8d2f1-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8d2f1-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="8d2f1-128">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8d2f1-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="8d2f1-129">Настройка Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="8d2f1-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="8d2f1-130">Пропустите этот шаг, если вы уже включили Защитник для Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="8d2f1-131">Существует модуль PowerShell под названием *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* который помогает определить некоторые из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="8d2f1-132">При запуске в качестве администратора в клиенте get-ORCAReport поможет создать оценку параметров защиты от нежелательной почты, фишинга и других параметров санации сообщений.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="8d2f1-133">Вы можете скачать этот модуль из https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="8d2f1-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="8d2f1-134">Перейдите к политике управления угрозами в Центре & безопасности и соответствия требованиям [Office 365.](https://protection.office.com/homepage)  >    >  </span><span class="sxs-lookup"><span data-stu-id="8d2f1-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Изображение of_Office 365 security & Compliance Center Threat management page](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="8d2f1-136">Щелкните **"Антифишинг",** **выберите "Создать"** и в заполните имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="8d2f1-137">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-137">Click **Next**.</span></span>

   ![Изображение of_Office 365 security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="8d2f1-139">Изменение политики advanced anti-phishing в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8d2f1-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="8d2f1-141">Щелкните **меню "Добавить условия"** и выберите домены в качестве домена получателя.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="8d2f1-142">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-142">Click **Next**.</span></span>

   ![Изображение of_Office 365 security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="8d2f1-144">Просмотрите параметры.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-144">Review your settings.</span></span> <span data-ttu-id="8d2f1-145">Нажмите **кнопку "Создать эту политику"** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-145">Click **Create this policy** to confirm.</span></span> 

   ![Изображение of_Office 365 security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="8d2f1-147">Выберите **"Безопасные вложения"** и выберите параметр **"Включить ATP для SharePoint, OneDrive и Microsoft Teams".**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Изображение of_Office 365 & соответствия требованиям, на которой можно включить ATP для SharePoint, OneDrive и Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="8d2f1-149">Щелкните значок "+", чтобы создать новую политику безопасных вложений, примените ее в качестве домена получателя к доменам.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="8d2f1-150">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-150">Click **Save**.</span></span>

   ![Изображение of_Office 365 security & Compliance Center, где можно создать новую политику безопасных вложений](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="8d2f1-152">Затем выберите политику **безопасных ссылок,** а затем щелкните значок карандаша, чтобы изменить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="8d2f1-153">Убедитесь, **что** параметр "Не отслеживать" при выборе пользователями параметра "Безопасные ссылки" не выбран, а остальные параметры выбраны.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="8d2f1-154">Подробные [сведения см. в параметрах безопасных](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) ссылок.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="8d2f1-155">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-155">Click **Save**.</span></span> 

   ![Изображение of_Office 365 security & Compliance Center, на которой показано, что параметр "Не отслеживать" при нажатии кнопки "Безопасный" не выбран](../../media/mtp-eval-38.png)

9. <span data-ttu-id="8d2f1-157">Затем выберите политику **борьбы с вредоносными** программами, выберите значение по умолчанию и значок карандаша.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="8d2f1-158">Щелкните **"Параметры",** выберите **"Да" и используйте** текст уведомления по умолчанию, чтобы включить ответ **на обнаружение вредоносных программ.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="8d2f1-159">**Включите фильтр общих типов вложений.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="8d2f1-160">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-160">Click **Save**.</span></span>

    ![Изображение of_Office 365 security & Compliance Center, на которой показано, что ответ на обнаружение вредоносных программ включен с уведомлением по умолчанию и включен фильтр общих типов вложений](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="8d2f1-162">Перейдите к поиску в журнале аудита & центра безопасности и & Office [365](https://protection.office.com/homepage)  >    >   и включите аудит.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Изображение of_Office 365 security & Compliance Center, где можно включить поиск в журнале аудита](../../media/mtp-eval-40.png)

12. <span data-ttu-id="8d2f1-164">Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8d2f1-165">Перейдите в обозреватель управления угрозами Центра безопасности и соответствия & Office [365](https://protection.office.com/homepage)и выберите "Параметры конечной точки в Microsoft Defender для конечных точек" в правом верхнем  >    >   углу  экрана.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="8d2f1-166">В диалоговом окне "Защитник конечной точки" включите подключение к **Microsoft Defender для конечной точки.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Изображение of_Office 365 security & Compliance Center, где можно включить подключение к конечной точке в Microsoft Defender](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="8d2f1-168">Настройка Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="8d2f1-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="8d2f1-169">Пропустите этот шаг, если вы уже включили Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="8d2f1-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="8d2f1-170">Перейдите в [Центр безопасности Microsoft 365>](https://security.microsoft.com/info) выберите "Дополнительные **ресурсы** Microsoft Defender  >  **для удостоверений".**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Изображение of_Microsoft 365: страница "Центр безопасности 365", на которой можно открыть Microsoft Defender для удостоверений](../../media/mtp-eval-42.png)

2. <span data-ttu-id="8d2f1-172">Нажмите **кнопку** "Создать", чтобы запустить мастер Microsoft Defender для удостоверений.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Страница of_Microsoft защитника удостоверений, на которой нужно нажать кнопку "Создать"](../../media/mtp-eval-43.png)

3. <span data-ttu-id="8d2f1-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Страница of_Microsoft защитника удостоверений](../../media/mtp-eval-44.png)

4. <span data-ttu-id="8d2f1-176">Введите свои учетные данные Active Directory в локальной службе.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="8d2f1-177">Это может быть любая учетная запись пользователя с доступом на чтение в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Страница of_Microsoft Службы каталогов удостоверений в Защитнике удостоверений, на которой необходимо вложить учетные данные](../../media/mtp-eval-45.png)

5. <span data-ttu-id="8d2f1-179">Затем выберите **"Скачать установку датчика"** и передать файл на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Страница of_Microsoft защитника удостоверений, на которой можно выбрать "Загрузка программы установки датчика"](../../media/mtp-eval-46.png)

6. <span data-ttu-id="8d2f1-181">Выполните установку датчика удостоверений в Microsoft Defender и начните следовать за мастером.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Страница of_Microsoft защитника удостоверений, на которой нужно щелкнуть рядом, чтобы следовать за мастером датчика identity в Microsoft Defender для удостоверений](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="8d2f1-183">Нажмите **кнопку** "Далее" в типе развертывания датчика.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-183">Click **Next** at the sensor deployment type.</span></span>

   ![Страница of_Microsoft защитника изображений для удостоверений, на которой нужно щелкнуть рядом, чтобы перейти к следующей странице](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="8d2f1-185">Скопируйте ключ доступа, так как его необходимо ввести в мастере.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Страница of_the датчиков изображений, на которой необходимо скопировать ключ доступа, который необходимо ввести на следующей странице мастера настройки датчиков удостоверений в Microsoft Defender для удостоверений](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="8d2f1-187">Скопируйте ключ доступа в мастер и нажмите кнопку **"Установить".**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Страница of_Microsoft датчика удостоверений в Защитнике изображений, на которой необходимо предоставить клавишу доступа и нажать кнопку установки](../../media/mtp-eval-50.png)

10. <span data-ttu-id="8d2f1-189">Поздравляем, вы успешно настроили Microsoft Defender для удостоверений на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Завершение of_Microsoft защитника удостоверений для датчика удостоверений, где следует нажать кнопку "Готово"](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="8d2f1-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="8d2f1-192">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-192">Click **Save**.</span></span> 

    ![Изображение of_the параметров Microsoft Defender для удостоверений, на которой необходимо включить выключает Microsoft Defender для конечной точки](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="8d2f1-194">Защитник Windows ATP был повторно установлен в качестве Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8d2f1-195">Изменения, внесенные во все наши порталы, развявываются для согласованности.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="8d2f1-196">Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8d2f1-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="8d2f1-197">Пропустите этот шаг, если вы уже включили Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="8d2f1-198">Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/info)  >  **дополнительные ресурсы** Microsoft Cloud App  >  **Security.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Изображение of_Microsoft 365 Security Center, где вы можете увидеть карточку Microsoft Cloud App и нажать кнопку "Открыть"](../../media/mtp-eval-53.png)

2. <span data-ttu-id="8d2f1-200">В информационном запросе на интеграцию Microsoft Defender для удостоверений выберите **"Включить Microsoft Defender для интеграции данных удостоверений".**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Запрос of_the сведений об интеграции Microsoft Defender для удостоверений, где следует выбрать ссылку "Включить Microsoft Defender для интеграции данных удостоверений"](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="8d2f1-202">Если вы не видите этот запрос, это может означать, что интеграция данных в Microsoft Defender для удостоверений уже включена.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="8d2f1-203">Однако если вы не уверены, обратитесь к ИТ-администратору для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="8d2f1-204">Перейдите **в "Параметры",** включите выключаель интеграции с Microsoft Defender для **удостоверений** и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Страница of_the параметров изображения, на которой необходимо включить выключаель интеграции с Microsoft Defender для удостоверений и нажать кнопку "Сохранить"](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="8d2f1-206">Для новых экземпляров Microsoft Defender для удостоверений этот переключель интеграции автоматически включен.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="8d2f1-207">Перед тем как перейти к следующему шагу, подтвердите, что интеграция с Microsoft Defender для удостоверений включена.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="8d2f1-208">В параметрах облачного обнаружения выберите Microsoft Defender для интеграции **конечных** точек, а затем в включить интеграцию.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="8d2f1-209">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-209">Click **Save**.</span></span>

   ![Изображение of_the в Microsoft Defender для конечной точки, где в Microsoft Defender для интеграции конечных точек выбран блок несанкционированная проверка приложений.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="8d2f1-212">В параметрах облачного обнаружения выберите "Обогащение пользователей", а затем в рамках интеграции с Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Изображение раздела "Обогащение пользователей", в котором выбрано обогатить обнаруженные идентификаторы пользователей с помощью проверки имен пользователей Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="8d2f1-214">Настройка Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8d2f1-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="8d2f1-215">Пропустите этот шаг, если вы уже включили Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="8d2f1-216">Перейдите в [Центр безопасности Microsoft 365.](https://security.microsoft.com/info)  >  **Дополнительные ресурсы в** Центре безопасности Microsoft  >  **Defender.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="8d2f1-217">Нажмите кнопку **Open** (Открыть).</span><span class="sxs-lookup"><span data-stu-id="8d2f1-217">Click **Open**.</span></span>

   ![Изображение of_Microsoft Центр безопасности Защитника на странице Центра безопасности Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="8d2f1-219">Следуйте мастеру Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="8d2f1-220">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-220">Click **Next**.</span></span> 

   ![Изображение of_the мастера приветствия в Центре безопасности Microsoft Defender](../../media/mtp-eval-59.png)

3. <span data-ttu-id="8d2f1-222">Выберите в зависимости от предпочтительного расположения хранения данных, политики хранения данных, размера организации и отказа от предварительного просмотра функций.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Страница of_the для выбора страны хранения данных, политики хранения и размера организации.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="8d2f1-225">Впоследствии вы не сможете изменить некоторые параметры, например расположение хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="8d2f1-226">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-226">Click **Next**.</span></span> 

4. <span data-ttu-id="8d2f1-227">Нажмите **кнопку** "Продолжить", и она подавит Ваш Microsoft Defender для клиента endpoint.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Страница of_the с запросом нажать кнопку "Продолжить", чтобы создать облачный экземпляр](../../media/mtp-eval-61.png)

5. <span data-ttu-id="8d2f1-229">Подавите конечные точки с помощью групповых политик, Microsoft Endpoint Manager или с помощью локального сценария в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8d2f1-230">Для простоты в этом руководстве используется локальный сценарий.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="8d2f1-231">Щелкните **"Загрузить пакет"** и скопируйте сценарий в конечные точки.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Изображение of_page нажать кнопку "Загрузить пакет", чтобы скопировать сценарий в конечную точку или конечную точку](../../media/mtp-eval-62.png)

7. <span data-ttu-id="8d2f1-233">На конечной точке запустите сценарий под учетной записи администратора и выберите "Y".</span><span class="sxs-lookup"><span data-stu-id="8d2f1-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Изображение of_the командной линии, в которой вы запустите сценарий подбора и выберите Y, чтобы продолжить](../../media/mtp-eval-63.png)

8. <span data-ttu-id="8d2f1-235">Поздравляем, вы вошел в свою первую конечную точку.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Изображение of_the командной точки, где вы получаете подтверждение того, что вы вошел в первую конечную точку.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="8d2f1-238">Скопируйте тест обнаружения из мастера Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Изображение of_the выполнить тест обнаружения, где необходимо нажать кнопку "Копировать", чтобы скопировать тестовый сценарий обнаружения, который необходимо вжать в командную подсказку](../../media/mtp-eval-65.png)

10. <span data-ttu-id="8d2f1-240">Скопируйте сценарий PowerShell в командную команду с повышенными полномочиями и запустите его.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Изображение of_command, где следует скопировать сценарий PowerShell в командную командную команду с повышенными полномочиями и запустить его](../../media/mtp-eval-66.png)

11. <span data-ttu-id="8d2f1-242">Выберите **"Начать использовать Microsoft Defender для конечной точки"** в мастере.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Запрос of_the подтверждения изображения из мастера, в котором следует нажать кнопку "Начать использовать Microsoft Defender для конечной точки"](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="8d2f1-244">Посетите Центр [безопасности Microsoft Defender.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="8d2f1-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="8d2f1-245">Перейдите **в "Параметры"** и выберите **дополнительные функции.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Изображение of_Microsoft меню "Параметры центра безопасности Защитника", в котором следует выбрать дополнительные функции](../../media/mtp-eval-68.png)

13. <span data-ttu-id="8d2f1-247">Включив интеграцию с **Microsoft Defender для удостоверений.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Дополнительные of_Microsoft центра безопасности Защитника изображений, параметр "Защитник Майкрософт для удостоверений", который необходимо включить](../../media/mtp-eval-69.png)

14. <span data-ttu-id="8d2f1-249">Включив интеграцию с **Office 365 Threat Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Дополнительные of_Microsoft Центра безопасности Защитника изображений, параметр "Аналитика угроз Office 365", который необходимо включить](../../media/mtp-eval-70.png)

15. <span data-ttu-id="8d2f1-251">Включит **интеграцию с Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Дополнительные of_Microsoft Центра безопасности Защитника изображений, параметр Microsoft Cloud App Security, который необходимо включить](../../media/mtp-eval-71.png)

16. <span data-ttu-id="8d2f1-253">Прокрутите вниз и **нажмите кнопку "Сохранить** параметры", чтобы подтвердить новые интеграции.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Кнопка of_Save настройки изображения, которую необходимо нажать](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="8d2f1-255">Запуск службы Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d2f1-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="8d2f1-256">С 1 июня 2020 г. корпорация Майкрософт автоматически включает функции Защитника Microsoft 365 для всех соответствующих требованиям клиентов.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="8d2f1-257">Подробные сведения см. в этой статье Технического сообщества Майкрософт о [правах на лицензию.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)</span><span class="sxs-lookup"><span data-stu-id="8d2f1-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="8d2f1-258">Перейдите [в Центр безопасности Microsoft 365.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="8d2f1-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="8d2f1-259">Перейдите **в "Параметры"** и выберите **Microsoft 365 Defender.**</span><span class="sxs-lookup"><span data-stu-id="8d2f1-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="8d2f1-260">Снимок of_Microsoft 365 Defender со страницы параметров Центра безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d2f1-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="8d2f1-261">Более полное руководство см. в [подключе "Защитник Microsoft 365".](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="8d2f1-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="8d2f1-262">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="8d2f1-262">Congratulations!</span></span> <span data-ttu-id="8d2f1-263">Вы только что создали пробную или пилотную среду Microsoft 365 Defender!</span><span class="sxs-lookup"><span data-stu-id="8d2f1-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="8d2f1-264">Теперь вы можете ознакомиться с пользовательским интерфейсом Защитника Microsoft 365!</span><span class="sxs-lookup"><span data-stu-id="8d2f1-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="8d2f1-265">Узнайте, что вы можете узнать из следующего интерактивного руководства По Защитнику Microsoft 365 и узнать, как использовать каждую панель мониторинга для выполнения задач по ежедневной безопасности.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="8d2f1-266">Далее можно смоделировать атаку и увидеть, как возможности разных продуктов обнаруживают, создают оповещения и автоматически реагируют на атаки без файлов на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="8d2f1-267">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="8d2f1-267">Next step</span></span>
|[<span data-ttu-id="8d2f1-268">Этап моделирования атаки</span><span class="sxs-lookup"><span data-stu-id="8d2f1-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="8d2f1-269">Запустите имитацию атаки для пилотной среды Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8d2f1-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
