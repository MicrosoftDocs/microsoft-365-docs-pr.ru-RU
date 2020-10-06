---
title: Настройка принципов защиты от угроз Майкрософт для испытательной лаборатории или пилотной среды
description: Настройка базовых принципов защиты от угроз Майкрософт, таких как Office 365 ATP, Azure ATP, Microsoft Cloud App Security и Microsoft Defender ATP, для испытательной лаборатории или пилотной среды.
keywords: Настройка пробной системы защиты от угроз Майкрософт, пробной конфигурации Майкрософт для защиты от угроз, настройки пилотного проекта Майкрософт по защите от угроз, Настройка базовых принципов защиты от угроз Майкрософт, основы защиты от угроз Майкрософт
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
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 79e141ad85eecab827e0caa98fe022f88335c671
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368153"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="69ad1-104">Настройка принципов защиты от угроз Майкрософт для испытательной лаборатории или пилотной среды</span><span class="sxs-lookup"><span data-stu-id="69ad1-104">Configure Microsoft Threat Protection pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69ad1-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="69ad1-105">**Applies to:**</span></span>
- <span data-ttu-id="69ad1-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="69ad1-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="69ad1-107">Создание пробной лаборатории или испытательной среды Майкрософт для защиты от угроз и развертывание выполняется в три этапа:</span><span class="sxs-lookup"><span data-stu-id="69ad1-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Подготовка пробной лаборатории или пилотной среды Майкрософт для защиты от угроз" />
      <br/><span data-ttu-id="69ad1-109">Этап 1: подготовка </a></span><span class="sxs-lookup"><span data-stu-id="69ad1-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Настройка пробной лаборатории или пилотной среды Майкрософт для защиты от угроз" />
      <br/><span data-ttu-id="69ad1-111">Этап 2: Настройка </a></span><span class="sxs-lookup"><span data-stu-id="69ad1-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Настройте каждый из принципов защиты от угроз Майкрософт для пробной лаборатории или пилотной среды и встроенных конечных точек защиты от угроз Майкрософт." />
      <br/><span data-ttu-id="69ad1-113">Этап 3: Настройка встроенного & </a></span><span class="sxs-lookup"><span data-stu-id="69ad1-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="69ad1-114">В настоящее время вы находитесь на этапе настройки.</span><span class="sxs-lookup"><span data-stu-id="69ad1-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="69ad1-115">Подготовка — это ключ к любому успешному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="69ad1-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="69ad1-116">В этой статье вы узнаете о точках, которые необходимо учесть при подготовке к развертыванию пакета ATP для защитника Microsoft.</span><span class="sxs-lookup"><span data-stu-id="69ad1-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="69ad1-117">Основы защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69ad1-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="69ad1-118">Защита от угроз Майкрософт состоит из четырех базовых принципов.</span><span class="sxs-lookup"><span data-stu-id="69ad1-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="69ad1-119">Несмотря на то, что один из них уже может обеспечить безопасность вашей сетевой организации, при использовании четырех базовых принципов защиты от угроз Майкрософт вы узнаете, что ваша организация является наибольшим значением.</span><span class="sxs-lookup"><span data-stu-id="69ad1-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="69ad1-120">Image of_Microsoft защита от угроз для пользователей, Advanced Threat Protection в Azure, для конечных точек Microsoft Defender Advanced Threat Protection, для облачных приложений, Microsoft Cloud App Security и данных, Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="69ad1-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png)

<span data-ttu-id="69ad1-121">В этом разделе приведутся инструкции по настройке:</span><span class="sxs-lookup"><span data-stu-id="69ad1-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="69ad1-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="69ad1-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="69ad1-123">Расширенная защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="69ad1-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="69ad1-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="69ad1-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="69ad1-125">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="69ad1-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="69ad1-126">Настройка Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="69ad1-126">Configure Office 365 Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="69ad1-127">Пропустите этот шаг, если вы уже включили расширенную защиту от угроз для Office 365.</span><span class="sxs-lookup"><span data-stu-id="69ad1-127">Skip this step if you've already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="69ad1-128">Существует модуль PowerShell, который называется *рекомендуемой конфигурацией Office 365 Advanced Threat protection (Orca)* , который помогает определить некоторые из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="69ad1-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="69ad1-129">При запуске с правами администратора в клиенте командлет Get-Оркарепорт поможет создать оценку параметров защиты от нежелательной почты, защиты от фишинга и других сообщений санацией.</span><span class="sxs-lookup"><span data-stu-id="69ad1-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="69ad1-130">Вы можете скачать этот модуль из https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="69ad1-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="69ad1-131">Перейдите к разделу [Безопасность & безопасности центра соответствия требованиям Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Изображение 365 of_Office & безопасности центра соответствия требованиям "политика управления угрозами"](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="69ad1-133">Выберите пункт **Защита от фишинга ATP**, выберите **создать** и введите имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="69ad1-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="69ad1-134">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-134">Click **Next**.</span></span>

   ![Image 365 of_Office & Security — страница политики защиты от фишинга, где можно назвать политику](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="69ad1-136">Измените политику защиты от фишинга ATP.</span><span class="sxs-lookup"><span data-stu-id="69ad1-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="69ad1-137">Изменение **расширенного порога фишинга** на **2 агрессивно**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="69ad1-138">Щелкните раскрывающееся меню **Добавить условие** и выберите домен (ы) в качестве домена получателя.</span><span class="sxs-lookup"><span data-stu-id="69ad1-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="69ad1-139">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-139">Click **Next**.</span></span>

   ![Image 365 of_Office & безопасность: страница политики защиты от фишинга центра соответствия требованиям, где можно добавить условие для своего приложения](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="69ad1-141">Проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="69ad1-141">Review your settings.</span></span> <span data-ttu-id="69ad1-142">Щелкните **создать эту политику** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="69ad1-142">Click **Create this policy** to confirm.</span></span> 

   ![Image 365 of_Office & безопасность: страница политики защиты от фишинга центра соответствия требованиям, где можно просмотреть параметры и нажать кнопку Создать эту политику](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="69ad1-144">Выберите пункт **безопасные вложения ATP** и установите флажок **включить ATP для SharePoint, OneDrive и Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="69ad1-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image 365 of_Office & безопасности страница центра соответствия требованиям, где можно включить ATP для SharePoint, OneDrive и Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="69ad1-146">Нажмите значок +, чтобы создать новую политику безопасных вложений, примените ее к доменам получателя.</span><span class="sxs-lookup"><span data-stu-id="69ad1-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="69ad1-147">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-147">Click **Save**.</span></span>

   ![Image 365 of_Office & безопасность страница центра соответствия требованиям для создания новой политики безопасных вложений](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="69ad1-149">Затем выберите политику **безопасных ссылок ATP** , а затем щелкните значок карандаша, чтобы изменить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="69ad1-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="69ad1-150">Убедитесь, что флажок не **отслеживать, когда пользователи щелкать ссылку "безопасные ссылки** " не установлен, а остальные параметры выбраны.</span><span class="sxs-lookup"><span data-stu-id="69ad1-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="69ad1-151">Дополнительные сведения приведены в разделе [Параметры безопасных ссылок](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) .</span><span class="sxs-lookup"><span data-stu-id="69ad1-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="69ad1-152">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-152">Click **Save**.</span></span> 

   ![Image 365 of_Office & безопасность страница центра соответствия требованиям, в которой показано, что параметр не отслеживается, когда пользователь щелкать не выбрано](../../media/mtp-eval-38.png)

9. <span data-ttu-id="69ad1-154">Затем выберите политику **защиты от вредоносных программ** , выберите значение по умолчанию и нажмите значок карандаша.</span><span class="sxs-lookup"><span data-stu-id="69ad1-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="69ad1-155">Нажмите кнопку **Параметры** и выберите Да, чтобы включить **ответ на обнаружение вредоносных программ**, **используя текст уведомления по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="69ad1-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="69ad1-156">Включите **Фильтр общих типов вложений** .</span><span class="sxs-lookup"><span data-stu-id="69ad1-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="69ad1-157">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-157">Click **Save**.</span></span>

    ![Image 365 of_Office Security & странице центра соответствия требованиям, на которой показано, что ответ на обнаружение вредоносных программ включен с уведомлением по умолчанию, а также включен фильтр общих типов вложений](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="69ad1-159">Перейдите к разделу [& безопасности Office 365](https://protection.office.com/homepage)  >  **Search**  >  **Поиск в журнале аудита** поиска и включите аудит для.</span><span class="sxs-lookup"><span data-stu-id="69ad1-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image 365 of_Office & безопасности страница центра соответствия требованиям, где можно включить поиск по журналу аудита](../../media/mtp-eval-40.png)

12. <span data-ttu-id="69ad1-161">Интеграция Office 365 с пакетом ATP с помощью защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="69ad1-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="69ad1-162">Перейдите в раздел [& безопасности Office 365 Security](https://protection.office.com/homepage)  >  **Management**  >  **Explorer** и выберите **Параметры вдатп** в правом верхнем углу экрана.</span><span class="sxs-lookup"><span data-stu-id="69ad1-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="69ad1-163">В диалоговом окне Подключение к Защитнику (Майкрософт) ATP включите параметр **подключиться к Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>

    ![Image 365 of_Office & безопасности страница центра соответствия требованиям для защитника Windows](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="69ad1-165">Настройка Advanced Threat Protection в Azure</span><span class="sxs-lookup"><span data-stu-id="69ad1-165">Configure Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="69ad1-166">Пропустите этот шаг, если вы уже включили Advanced Threat Protection в Azure.</span><span class="sxs-lookup"><span data-stu-id="69ad1-166">Skip this step if you've already enabled Azure Advanced Threat Protection</span></span>

1. <span data-ttu-id="69ad1-167">Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/info) > выберите **Дополнительные ресурсы**  >  **Azure Advanced Threat protection**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>

   ![Image of_Microsoft 365 страница центра безопасности, на которой можно открыть службу Advanced Threat Protection в Azure](../../media/mtp-eval-42.png)

2. <span data-ttu-id="69ad1-169">Нажмите кнопку **создать** , чтобы запустить мастер Advanced Threat protection.</span><span class="sxs-lookup"><span data-stu-id="69ad1-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 

   ![Страница мастера создания образа of_Azure Advanced Threat Protection, на которой следует нажать кнопку Создать](../../media/mtp-eval-43.png)

3. <span data-ttu-id="69ad1-171">Выберите **указать имя пользователя и пароль для подключения к лесу Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Страница приветствия образа of_Azure Advanced Threat protection](../../media/mtp-eval-44.png)

4. <span data-ttu-id="69ad1-173">Введите локальные учетные данные Active Directory.</span><span class="sxs-lookup"><span data-stu-id="69ad1-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="69ad1-174">Это может быть любая учетная запись пользователя, имеющая доступ на чтение к Active Directory.</span><span class="sxs-lookup"><span data-stu-id="69ad1-174">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Azure Advanced Threat protection Services страница службы каталогов, где необходимо ввести учетные данные](../../media/mtp-eval-45.png)

5. <span data-ttu-id="69ad1-176">Затем выберите пункт **скачать файл установки и передачи датчиков** на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="69ad1-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Страница "изображение of_Azure Advanced Threat protection", на которой можно выбрать параметр скачать датчик](../../media/mtp-eval-46.png)

6. <span data-ttu-id="69ad1-178">Выполните настройку датчика Azure ATP и начните выполнение мастера.</span><span class="sxs-lookup"><span data-stu-id="69ad1-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>

   ![Изображение страница of_Azure Advanced Threat Protection, на которой следует нажать кнопку Далее, чтобы перейти к мастеру проверки датчиков Azure ATP](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="69ad1-180">Нажмите кнопку **Далее** в разделе Тип развертывания Sensor (датчик).</span><span class="sxs-lookup"><span data-stu-id="69ad1-180">Click **Next** at the sensor deployment type.</span></span>

   ![Изображение страница of_Azure Advanced Threat Protection, на которой следует нажать кнопку Далее, чтобы перейти к следующей странице](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="69ad1-182">Скопируйте ключ доступа, так как его необходимо ввести далее в мастере.</span><span class="sxs-lookup"><span data-stu-id="69ad1-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Страница датчиков of_the изображений, на которой нужно скопировать ключ доступа, который необходимо ввести на следующей странице мастера настройки датчика Azure ATP](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="69ad1-184">Скопируйте в мастер ключ доступа и нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Image of_Azure Advanced Threat Protection на странице мастера датчиков Azure ATP, где необходимо указать ключ доступа, а затем нажать кнопку "установить"](../../media/mtp-eval-50.png)

10. <span data-ttu-id="69ad1-186">Поздравляем, вы успешно настроили службу Advanced Threat Protection в Azure на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="69ad1-186">Congratulations, you've successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>

    ![Image of_Azure Advanced Threat protection мастер датчиков Azure ATP завершение установки, где следует нажать кнопку Готово](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="69ad1-188">В разделе Параметры [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) выберите пункт **Защитник Windows ATP**, а затем включите выключатель.</span><span class="sxs-lookup"><span data-stu-id="69ad1-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn on the toggle.</span></span> <span data-ttu-id="69ad1-189">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-189">Click **Save**.</span></span> 

    ![Image of_the страница параметров Azure Azure Azure, на которой следует включить переключатель защитника Windows ATP](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="69ad1-191">Пакет ATP для защитника Windows изменен в качестве пакета ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="69ad1-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="69ad1-192">Изменение фирменного стиля на всех наших порталах разбивается на согласованность.</span><span class="sxs-lookup"><span data-stu-id="69ad1-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="69ad1-193">Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="69ad1-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="69ad1-194">Пропустите этот шаг, если вы уже включили Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="69ad1-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="69ad1-195">Перейдите в раздел [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **More Resources**  >  **Security Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365 страница центра безопасности, на которой можно просмотреть карту Microsoft Cloud App Card и нажать кнопку Открыть](../../media/mtp-eval-53.png)

2. <span data-ttu-id="69ad1-197">В информационном запросе для интеграции Azure ATP выберите **включить интеграцию данных Azure ATP**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span>
  
   ![Image of_the сведения о запросе для интеграции Azure ATP, где следует выбрать ссылку "включить интеграцию данных Azure ATP".](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="69ad1-199">Если вы не видите этот запрос, это может означать, что интеграция Azure ATP данных уже включена.</span><span class="sxs-lookup"><span data-stu-id="69ad1-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="69ad1-200">Тем не менее, если вы не уверены, обратитесь к ИТ ИТ администратора, чтобы подтвердить.</span><span class="sxs-lookup"><span data-stu-id="69ad1-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="69ad1-201">Перейдите в раздел **Параметры**, включите переключатель **Интеграция Azure ATP** , а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-201">Go to **Settings**, turn on the **Azure ATP integration** toggle, then click **Save**.</span></span> 

   ![Страница "Параметры of_the изображений", на которой необходимо включить интеграцию Azure ATP, а затем нажмите кнопку Сохранить.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="69ad1-203">Для новых экземпляров Azure ATP этот переключатель интеграции автоматически включается.</span><span class="sxs-lookup"><span data-stu-id="69ad1-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="69ad1-204">Прежде чем переходить к следующему шагу, убедитесь, что интеграция Azure ATP включена.</span><span class="sxs-lookup"><span data-stu-id="69ad1-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="69ad1-205">В разделе Параметры облачного обнаружения выберите **Интеграция с защитником Майкрософт**, а затем включите интеграцию.</span><span class="sxs-lookup"><span data-stu-id="69ad1-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="69ad1-206">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-206">Click **Save**.</span></span>

   ![Image of_the страницу защитника Microsoft Defender, где установлен флажок Блокировать несанкционированные приложения под интеграцией Microsoft Defender ATP.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="69ad1-209">В разделе Параметры облачного обнаружения выберите **обогащение пользователей**, а затем включите интеграцию с Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="69ad1-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Изображение раздела "улучшение пользователей", в котором установлен флажок обогащенный идентификатор пользователя с идентификатором пользователя Azure Active Directory.](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="69ad1-211">Настройка Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="69ad1-211">Configure Microsoft Defender Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="69ad1-212">Пропустите этот шаг, если вы уже включили Advanced Threat Protection в защитнике Microsoft.</span><span class="sxs-lookup"><span data-stu-id="69ad1-212">Skip this step if you've already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="69ad1-213">Перейдите в раздел [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **More Resources**  >  **Center securitys Microsoft Защитник**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="69ad1-214">Нажмите кнопку **Open** (Открыть).</span><span class="sxs-lookup"><span data-stu-id="69ad1-214">Click **Open**.</span></span>

   ![Of_Microsoft "Центр безопасности защитника изображений" на странице центра обеспечения безопасности Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="69ad1-216">Следуйте инструкциям мастера Advanced Threat Protection в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="69ad1-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="69ad1-217">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-217">Click **Next**.</span></span> 

   ![Изображение of_the странице мастера приветствия центра безопасности защитника Майкрософт](../../media/mtp-eval-59.png)

3. <span data-ttu-id="69ad1-219">Выберите в зависимости от предпочтительного расположения хранилища данных, политики хранения данных, размера организации и согласия пользователя по предварительным функциям.</span><span class="sxs-lookup"><span data-stu-id="69ad1-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Изображение of_the страница для выбора страны хранения данных, политики хранения и размера организации.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="69ad1-222">После этого невозможно изменить некоторые параметры, такие как расположение хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="69ad1-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="69ad1-223">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-223">Click **Next**.</span></span> 

4. <span data-ttu-id="69ad1-224">Нажмите **продолжить** , чтобы подготовиться к работе клиента, который является ПАКЕТом ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="69ad1-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>

   ![Страница "of_the изображений" с запросом нажмите кнопку "продолжить", чтобы создать экземпляр облачной среды](../../media/mtp-eval-61.png)

5. <span data-ttu-id="69ad1-226">Применяйте конечные точки с помощью групповых политик, диспетчера конечных точек Майкрософт или запуска локального сценария для пакета ATP в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="69ad1-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="69ad1-227">Для простоты в этом руководстве используется локальный скрипт.</span><span class="sxs-lookup"><span data-stu-id="69ad1-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="69ad1-228">Щелкните **скачать пакет** и скопируйте сценарий входящей миграции в конечные точки (s).</span><span class="sxs-lookup"><span data-stu-id="69ad1-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Of_page изображений нажмите кнопку скачать пакет, чтобы скопировать сценарий входящей миграции в конечную точку или конечные точки.](../../media/mtp-eval-62.png)

7. <span data-ttu-id="69ad1-230">В конечной точке запустите сценарий входящей миграции от имени администратора и нажмите Y.</span><span class="sxs-lookup"><span data-stu-id="69ad1-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the Командная строка, в которой запускается сценарий входящей миграции, и нажмите Y, чтобы продолжить](../../media/mtp-eval-63.png)

8. <span data-ttu-id="69ad1-232">Поздравляем, вы выполнили отплату для первой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="69ad1-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the Командная строка, в которой вы получаете подтверждение, в котором вы настроили первую конечную точку.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="69ad1-235">Скопируйте тест с определением в мастере Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="69ad1-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>

   ![Image of_the выполните шаг проверки обнаружения, на котором необходимо нажать кнопку Копировать, чтобы скопировать тестовый сценарий обнаружения, который необходимо вставить в командную строку.](../../media/mtp-eval-65.png)

10. <span data-ttu-id="69ad1-237">Скопируйте скрипт PowerShell в командную строку с повышенными привилегиями и запустите его.</span><span class="sxs-lookup"><span data-stu-id="69ad1-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Image of_command запрос, в котором необходимо скопировать скрипт PowerShell в командную строку с повышенными привилегиями и запустить его](../../media/mtp-eval-66.png)

11. <span data-ttu-id="69ad1-239">В мастере нажмите кнопку **начать с помощью ATP "защитник Майкрософт"** .</span><span class="sxs-lookup"><span data-stu-id="69ad1-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>

    ![Of_the с запросом подтверждения в мастере, где следует нажать кнопку начать с помощью средства Microsoft Defender ATP.](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="69ad1-241">Посетите [Центр безопасности защитника Microsoft](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="69ad1-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="69ad1-242">Перейдите в раздел **Параметры** и выберите **Дополнительные функции**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Меню "Параметры центра безопасности защитника of_Microsoft защитника", в котором следует выбрать дополнительные функции](../../media/mtp-eval-68.png)

13. <span data-ttu-id="69ad1-244">Включите интеграцию с **Advanced Threat Protection в Azure**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  

    ![Image of_Microsoft Defender Security Center Advanced Features, параметр Advanced Threat Protection в Azure, который необходимо включить](../../media/mtp-eval-69.png)

14. <span data-ttu-id="69ad1-246">Включите интеграцию с **Microsoft Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced Features, Office 365 Threat Intelligence переключатель, который необходимо включить](../../media/mtp-eval-70.png)

15. <span data-ttu-id="69ad1-248">Включите интеграцию с **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced Features, Microsoft Cloud App Security — переключатель, который необходимо включить](../../media/mtp-eval-71.png)

16. <span data-ttu-id="69ad1-250">Прокрутите список вниз и нажмите кнопку **сохранить настройки** , чтобы подтвердить новые интеграции.</span><span class="sxs-lookup"><span data-stu-id="69ad1-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Изображение of_Save кнопка "Параметры", которую нужно щелкнуть](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="69ad1-252">Запуск службы защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="69ad1-252">Start the Microsoft Threat Protection service</span></span>

>[!NOTE]
><span data-ttu-id="69ad1-253">Начиная с 1 июня 2020 г. Корпорация Майкрософт автоматически включает функции защиты от угроз Майкрософт для всех соответствующих клиентов.</span><span class="sxs-lookup"><span data-stu-id="69ad1-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="69ad1-254">Подробные сведения можно узнать [в этой статье сообщества Майкрософт в конференции](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) .</span><span class="sxs-lookup"><span data-stu-id="69ad1-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="69ad1-255">Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="69ad1-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="69ad1-256">Перейдите в раздел **Параметры** и выберите **Защита от угроз Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="69ad1-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>

![<span data-ttu-id="69ad1-257">Снимок экрана с вариантом of_Microsoft защиты от угроз на странице параметров центра безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69ad1-257">Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="69ad1-258">Более подробная информация приведена в статье [Включение защиты от угроз Майкрософт](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="69ad1-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="69ad1-259">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="69ad1-259">Congratulations!</span></span> <span data-ttu-id="69ad1-260">Вы только что создали пробную лабораторию и пилотную среду Microsoft Threat protection!</span><span class="sxs-lookup"><span data-stu-id="69ad1-260">You've just created your Microsoft Threat Protection trial lab or pilot environment!</span></span> <span data-ttu-id="69ad1-261">Теперь вы можете ознакомиться с пользовательским интерфейсом защиты от угроз Майкрософт!</span><span class="sxs-lookup"><span data-stu-id="69ad1-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="69ad1-262">Ознакомьтесь со следующими сведениями в интерактивном руководстве по защите от угроз Майкрософт и Узнайте, как использовать каждую панель мониторинга для повседневных задач безопасности.</span><span class="sxs-lookup"><span data-stu-id="69ad1-262">See what you can learn from the following Microsoft Threat Protection interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="69ad1-263">Затем вы можете имитировать атаку и узнать, как обнаружение, создание оповещений и автоматический ответ на атаку, не имеющую файлов, на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="69ad1-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="69ad1-264">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="69ad1-264">Next step</span></span>
|<span data-ttu-id="69ad1-265">![Этап имитации атаки](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="69ad1-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="69ad1-266">Этап имитации атаки</span><span class="sxs-lookup"><span data-stu-id="69ad1-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="69ad1-267">Запустите моделирование атак для пилотной среды пилотной системы защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="69ad1-267">Run the attack simulation for your Microsoft Threat Protection pilot environment.</span></span>
|:-------|:-----|
