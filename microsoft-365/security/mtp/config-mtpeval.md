---
title: Настройка базовых принципов защитника Microsoft 365 для испытательной лаборатории или пилотной среды
description: Настройте для пробной лаборатории или пилотной среды защитник Microsoft 365, например защитник Майкрософт для Office 365, защитник Майкрософт для удостоверения, Microsoft Cloud App Security и защитник Майкрософт для конечной точки.
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
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 5259c7b74446ad273ff9b1ae0baccd339e34baa3
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984954"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="87bdd-104">Настройка базовых принципов защитника Microsoft 365 для испытательной лаборатории или пилотной среды</span><span class="sxs-lookup"><span data-stu-id="87bdd-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="87bdd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="87bdd-105">**Applies to:**</span></span>
- <span data-ttu-id="87bdd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87bdd-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="87bdd-107">Создание пробной лаборатории или пилотной среды защитника Microsoft 365 и развертывание этого процесса состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="87bdd-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Подготовка пробной лаборатории или пилотной среды защитника Microsoft 365" />
      <br/><span data-ttu-id="87bdd-109">Этап 1: подготовка </a></span><span class="sxs-lookup"><span data-stu-id="87bdd-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Настройка пробной лаборатории или пилотной среды защитника Microsoft 365" />
      <br/><span data-ttu-id="87bdd-111">Этап 2: Настройка </a></span><span class="sxs-lookup"><span data-stu-id="87bdd-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Настройте каждую из базовых принципов защитника Microsoft 365 для пробной лаборатории или пилотной среды защитника Microsoft 365, а также встроенных конечных точек." />
      <br/><span data-ttu-id="87bdd-113">Этап 3: Настройка встроенного & </a></span><span class="sxs-lookup"><span data-stu-id="87bdd-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="87bdd-114">В настоящее время вы находитесь на этапе настройки.</span><span class="sxs-lookup"><span data-stu-id="87bdd-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="87bdd-115">Подготовка — это ключ к любому успешному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="87bdd-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="87bdd-116">В этой статье вы узнаете о точках, которые необходимо учесть при подготовке развертывания защитника Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87bdd-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="87bdd-117">Основы защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87bdd-117">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="87bdd-118">Защитник Microsoft 365 состоит из четырех базовых принципов.</span><span class="sxs-lookup"><span data-stu-id="87bdd-118">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="87bdd-119">Несмотря на то, что один из них уже может обеспечить безопасность вашей организации, что позволит четыре основные основы защитника Microsoft 365 придать вашей организации наибольшее значение.</span><span class="sxs-lookup"><span data-stu-id="87bdd-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoftо решение для защитника 365 для пользователей, защитник Майкрософт для удостоверения, для конечных точек Microsoft Defender для конечной точки, для облачных приложений, Microsoft Cloud App Security и для данных, защитник Майкрософт для Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="87bdd-121">В этом разделе приведутся инструкции по настройке:</span><span class="sxs-lookup"><span data-stu-id="87bdd-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="87bdd-122">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="87bdd-122">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="87bdd-123">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="87bdd-123">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="87bdd-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="87bdd-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="87bdd-125">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="87bdd-125">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="87bdd-126">Настройка защитника Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="87bdd-126">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="87bdd-127">Пропустите этот шаг, если вы уже включили защитник для Office 365.</span><span class="sxs-lookup"><span data-stu-id="87bdd-127">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="87bdd-128">Существует модуль PowerShell, который называется *рекомендуемой конфигурацией Office 365 Advanced Threat protection (Orca)* , который помогает определить некоторые из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="87bdd-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="87bdd-129">При запуске с правами администратора в клиенте командлет Get-Оркарепорт поможет создать оценку параметров защиты от нежелательной почты, защиты от фишинга и других сообщений санацией.</span><span class="sxs-lookup"><span data-stu-id="87bdd-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="87bdd-130">Вы можете скачать этот модуль из https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="87bdd-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="87bdd-131">Перейдите к разделу [Безопасность & безопасности центра соответствия требованиям Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Изображение 365 of_Office & безопасности центра соответствия требованиям "политика управления угрозами"](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="87bdd-133">Нажмите кнопку **Защита от фишинга** , выберите **создать** и введите имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="87bdd-133">Click **Anti-phishing** , select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="87bdd-134">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-134">Click **Next**.</span></span>

   ![Image 365 of_Office & Security — страница политики защиты от фишинга, где можно назвать политику](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="87bdd-136">Изменение расширенной политики защиты от фишинга в защитнике Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="87bdd-136">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="87bdd-137">Изменение **расширенного порога фишинга** на **2 агрессивно**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="87bdd-138">Щелкните раскрывающееся меню **Добавить условие** и выберите домен (ы) в качестве домена получателя.</span><span class="sxs-lookup"><span data-stu-id="87bdd-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="87bdd-139">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-139">Click **Next**.</span></span>

   ![Image 365 of_Office & безопасность: страница политики защиты от фишинга центра соответствия требованиям, где можно добавить условие для своего приложения](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="87bdd-141">Проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="87bdd-141">Review your settings.</span></span> <span data-ttu-id="87bdd-142">Щелкните **создать эту политику** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="87bdd-142">Click **Create this policy** to confirm.</span></span> 

   ![Image 365 of_Office & безопасность: страница политики защиты от фишинга центра соответствия требованиям, где можно просмотреть параметры и нажать кнопку Создать эту политику](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="87bdd-144">Выберите пункт **безопасные вложения** и установите флажок **включить ATP для SharePoint, OneDrive и Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="87bdd-144">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image 365 of_Office & безопасности страница центра соответствия требованиям, где можно включить ATP для SharePoint, OneDrive и Microsoft Teams](../../media/mtp-eval-36.png)

6. <span data-ttu-id="87bdd-146">Нажмите значок +, чтобы создать новую политику безопасных вложений, примените ее к доменам получателя.</span><span class="sxs-lookup"><span data-stu-id="87bdd-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="87bdd-147">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-147">Click **Save**.</span></span>

   ![Image 365 of_Office & безопасность страница центра соответствия требованиям для создания новой политики безопасных вложений](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="87bdd-149">Затем выберите политику **безопасных ссылок** , а затем щелкните значок карандаш, чтобы изменить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="87bdd-149">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="87bdd-150">Убедитесь, что флажок не **отслеживать, когда пользователи щелкать ссылку "безопасные ссылки** " не установлен, а остальные параметры выбраны.</span><span class="sxs-lookup"><span data-stu-id="87bdd-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="87bdd-151">Дополнительные сведения приведены в разделе [Параметры безопасных ссылок](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) .</span><span class="sxs-lookup"><span data-stu-id="87bdd-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="87bdd-152">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-152">Click **Save**.</span></span> 

   ![Image 365 of_Office & безопасность страница центра соответствия требованиям, в которой показано, что параметр не отслеживается, когда пользователь щелкать не выбрано](../../media/mtp-eval-38.png)

9. <span data-ttu-id="87bdd-154">Затем выберите политику **защиты от вредоносных программ** , выберите значение по умолчанию и нажмите значок карандаша.</span><span class="sxs-lookup"><span data-stu-id="87bdd-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="87bdd-155">Нажмите кнопку **Параметры** и выберите Да, чтобы включить **ответ на обнаружение вредоносных программ** , **используя текст уведомления по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="87bdd-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="87bdd-156">Включите **Фильтр общих типов вложений** .</span><span class="sxs-lookup"><span data-stu-id="87bdd-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="87bdd-157">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-157">Click **Save**.</span></span>

    ![Image 365 of_Office Security & странице центра соответствия требованиям, на которой показано, что ответ на обнаружение вредоносных программ включен с уведомлением по умолчанию, а также включен фильтр общих типов вложений](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="87bdd-159">Перейдите к разделу [& безопасности Office 365](https://protection.office.com/homepage)  >  **Search**  >  **Поиск в журнале аудита** поиска и включите аудит для.</span><span class="sxs-lookup"><span data-stu-id="87bdd-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image 365 of_Office & безопасности страница центра соответствия требованиям, где можно включить поиск по журналу аудита](../../media/mtp-eval-40.png)

12. <span data-ttu-id="87bdd-161">Интегрируйте защитник Майкрософт для Office 365 с защитником Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87bdd-161">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="87bdd-162">Перейдите в раздел [& безопасности Office 365 Security](https://protection.office.com/homepage)  >  **Management**  >  **Explorer** и выберите **защитник Майкрософт для параметров конечной точки** в правом верхнем углу экрана.</span><span class="sxs-lookup"><span data-stu-id="87bdd-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="87bdd-163">В диалоговом окне защитник для конечной точки установите флажок **подключиться к защитнику Майкрософт для конечной точки**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-163">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Image 365 of_Office & безопасности страница центра соответствия требованиям к безопасности, на которой можно включить защитник Майкрософт для подключения к конечной точке](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="87bdd-165">Настройка защитника Майкрософт для удостоверения</span><span class="sxs-lookup"><span data-stu-id="87bdd-165">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="87bdd-166">Пропустите этот шаг, если вы уже включили защитник Майкрософт для удостоверения.</span><span class="sxs-lookup"><span data-stu-id="87bdd-166">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="87bdd-167">Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/info) , > выберите **Дополнительные ресурсы**  >  **защитник Майкрософт для удостоверения**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Image of_Microsoft-страница центра безопасности 365, на которой можно открыть защитник Майкрософт для удостоверения](../../media/mtp-eval-42.png)

2. <span data-ttu-id="87bdd-169">Нажмите кнопку **создать** , чтобы запустить мастер защитник Майкрософт для удостоверения.</span><span class="sxs-lookup"><span data-stu-id="87bdd-169">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Страница "защитник of_Microsoft образов для мастера удостоверений", на которой следует нажать кнопку "создать"](../../media/mtp-eval-43.png)

3. <span data-ttu-id="87bdd-171">Выберите **указать имя пользователя и пароль для подключения к лесу Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Защитник of_Microsoft образов для страницы приветствия удостоверений](../../media/mtp-eval-44.png)

4. <span data-ttu-id="87bdd-173">Введите локальные учетные данные Active Directory.</span><span class="sxs-lookup"><span data-stu-id="87bdd-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="87bdd-174">Это может быть любая учетная запись пользователя, имеющая доступ на чтение к Active Directory.</span><span class="sxs-lookup"><span data-stu-id="87bdd-174">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Microsoft Defender для страницы службы каталогов удостоверений, где необходимо ввести учетные данные](../../media/mtp-eval-45.png)

5. <span data-ttu-id="87bdd-176">Затем выберите пункт **скачать файл установки и передачи датчиков** на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="87bdd-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Защитник of_Microsoft образов для страницы идентификации, на которой можно выбрать параметр скачать датчик](../../media/mtp-eval-46.png)

6. <span data-ttu-id="87bdd-178">Выполните защитник Майкрософт для настройки датчика удостоверений и начните работу с мастером.</span><span class="sxs-lookup"><span data-stu-id="87bdd-178">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Image of_Microsoft защитник для страницы удостоверений, на котором следует нажать кнопку Далее, чтобы перейти к мастеру проверки подлинности Microsoft Defender](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="87bdd-180">Нажмите кнопку **Далее** в разделе Тип развертывания Sensor (датчик).</span><span class="sxs-lookup"><span data-stu-id="87bdd-180">Click **Next** at the sensor deployment type.</span></span>

   ![Of_Microsoft "защитник изображений" для удостоверения страницы, на которой необходимо нажать кнопку "Далее", чтобы перейти к следующей странице](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="87bdd-182">Скопируйте ключ доступа, так как его необходимо ввести далее в мастере.</span><span class="sxs-lookup"><span data-stu-id="87bdd-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Страница датчиков of_the изображений, на которой необходимо скопировать ключ доступа, который необходимо ввести в следующий защитник Майкрософт для страницы мастера настройки датчика удостоверений](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="87bdd-184">Скопируйте в мастер ключ доступа и нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Of_Microsoft защитника изображений на странице мастера датчиков удостоверений, где следует указать ключ доступа, а затем нажмите кнопку "установить".](../../media/mtp-eval-50.png)

10. <span data-ttu-id="87bdd-186">Поздравляем, вы успешно настроили защитник Майкрософт для удостоверения на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="87bdd-186">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft защитник для завершения установки мастера датчиков удостоверений, где следует нажать кнопку Готово](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="87bdd-188">В разделе [защитник Майкрософт для параметров удостоверения](https://go.microsoft.com/fwlink/?linkid=2040449) выберите \* \* защитник Майкрософт для конечной точки \* \*, а затем включите выключатель.</span><span class="sxs-lookup"><span data-stu-id="87bdd-188">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="87bdd-189">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-189">Click **Save**.</span></span> 

    ![Image of_the страницу "защитник Майкрософт для параметров удостоверений", на которой необходимо включить режим защитника Microsoft для конечных точек.](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="87bdd-191">Пакет ATP для защитника Windows изменен в качестве защитника Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87bdd-191">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="87bdd-192">Изменение фирменного стиля на всех наших порталах разбивается на согласованность.</span><span class="sxs-lookup"><span data-stu-id="87bdd-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="87bdd-193">Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="87bdd-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="87bdd-194">Пропустите этот шаг, если вы уже включили Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="87bdd-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="87bdd-195">Перейдите в раздел [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **More Resources**  >  **Security Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365 страница центра безопасности, на которой можно просмотреть карту Microsoft Cloud App Card и нажать кнопку Открыть](../../media/mtp-eval-53.png)

2. <span data-ttu-id="87bdd-197">В информационном запросе для интеграции защитника Майкрософт для удостоверения выберите **включить защитник Майкрософт для интеграции данных удостоверений**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-197">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Image of_the Information Prompt, чтобы интегрировать защитник Майкрософт для удостоверения, для которого необходимо выбрать ссылку включить защитник Майкрософт для идентификации данных удостоверений.](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="87bdd-199">Если вы не видите этот запрос, это может означать, что защитник Майкрософт для интеграции данных удостоверений уже включен.</span><span class="sxs-lookup"><span data-stu-id="87bdd-199">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="87bdd-200">Тем не менее, если вы не уверены, обратитесь к ИТ ИТ администратора, чтобы подтвердить.</span><span class="sxs-lookup"><span data-stu-id="87bdd-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="87bdd-201">Перейдите в раздел **Параметры** , включите **защитник Майкрософт для параметра интеграция удостоверений** , а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-201">Go to **Settings** , turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Страница "Параметры of_the изображений", на которой необходимо включить защитник Майкрософт для интеграции удостоверений, а затем нажмите кнопку Сохранить.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="87bdd-203">Этот переключатель интеграции автоматически включается для новых экземпляров защитника Майкрософт для экземпляров удостоверения.</span><span class="sxs-lookup"><span data-stu-id="87bdd-203">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="87bdd-204">Прежде чем переходить к следующему шагу, убедитесь, что защитник Майкрософт для интеграции удостоверений включен.</span><span class="sxs-lookup"><span data-stu-id="87bdd-204">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="87bdd-205">В разделе Параметры облачного обнаружения выберите **защитник Майкрософт для интеграции конечных точек** , а затем включите интеграцию.</span><span class="sxs-lookup"><span data-stu-id="87bdd-205">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration** , then enable the integration.</span></span> <span data-ttu-id="87bdd-206">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-206">Click **Save**.</span></span>

   ![Image of_the страницу защитника Майкрософт для конечной точки, где установлен флажок Блокировать несанкционированные приложения под защитником Майкрософт для интеграции конечных точек.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="87bdd-209">В разделе Параметры облачного обнаружения выберите **обогащение пользователей** , а затем включите интеграцию с Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="87bdd-209">Under Cloud discovery settings, select **User enrichment** , then enable the integration with Azure Active Directory.</span></span>

   ![Изображение раздела "улучшение пользователей", в котором установлен флажок обогащенный идентификатор пользователя с идентификатором пользователя Azure Active Directory.](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="87bdd-211">Настройка защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="87bdd-211">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="87bdd-212">Пропустите этот шаг, если вы уже включили защитник Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87bdd-212">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="87bdd-213">Перейдите в раздел [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **More Resources**  >  **Center securitys Microsoft Защитник**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="87bdd-214">Нажмите кнопку **Open** (Открыть).</span><span class="sxs-lookup"><span data-stu-id="87bdd-214">Click **Open**.</span></span>

   ![Of_Microsoft "Центр безопасности защитника изображений" на странице центра обеспечения безопасности Microsoft 365](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="87bdd-216">Следуйте указаниям мастера защитника Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87bdd-216">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="87bdd-217">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-217">Click **Next**.</span></span> 

   ![Изображение of_the странице мастера приветствия центра безопасности защитника Майкрософт](../../media/mtp-eval-59.png)

3. <span data-ttu-id="87bdd-219">Выберите в зависимости от предпочтительного расположения хранилища данных, политики хранения данных, размера организации и согласия пользователя по предварительным функциям.</span><span class="sxs-lookup"><span data-stu-id="87bdd-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Изображение of_the страница для выбора страны хранения данных, политики хранения и размера организации.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="87bdd-222">После этого невозможно изменить некоторые параметры, такие как расположение хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="87bdd-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="87bdd-223">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-223">Click **Next**.</span></span> 

4. <span data-ttu-id="87bdd-224">Нажмите **продолжить** , чтобы подготовиться к работе с защитником Майкрософт для клиента конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87bdd-224">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Страница "of_the изображений" с запросом нажмите кнопку "продолжить", чтобы создать экземпляр облачной среды](../../media/mtp-eval-61.png)

5. <span data-ttu-id="87bdd-226">Подключение конечных точек с помощью групповых политик, диспетчера конечных точек Майкрософт или Запуск локального сценария для конечной точки в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="87bdd-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="87bdd-227">Для простоты в этом руководстве используется локальный скрипт.</span><span class="sxs-lookup"><span data-stu-id="87bdd-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="87bdd-228">Щелкните **скачать пакет** и скопируйте сценарий входящей миграции в конечные точки (s).</span><span class="sxs-lookup"><span data-stu-id="87bdd-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Of_page изображений нажмите кнопку скачать пакет, чтобы скопировать сценарий входящей миграции в конечную точку или конечные точки.](../../media/mtp-eval-62.png)

7. <span data-ttu-id="87bdd-230">В конечной точке запустите сценарий входящей миграции от имени администратора и нажмите Y.</span><span class="sxs-lookup"><span data-stu-id="87bdd-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the Командная строка, в которой запускается сценарий входящей миграции, и нажмите Y, чтобы продолжить](../../media/mtp-eval-63.png)

8. <span data-ttu-id="87bdd-232">Поздравляем, вы выполнили отплату для первой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87bdd-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the Командная строка, в которой вы получаете подтверждение, в котором вы настроили первую конечную точку.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="87bdd-235">Скопируйте проверку обнаружения с помощью мастера защитника Microsoft для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="87bdd-235">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the выполните шаг проверки обнаружения, на котором необходимо нажать кнопку Копировать, чтобы скопировать тестовый сценарий обнаружения, который необходимо вставить в командную строку.](../../media/mtp-eval-65.png)

10. <span data-ttu-id="87bdd-237">Скопируйте скрипт PowerShell в командную строку с повышенными привилегиями и запустите его.</span><span class="sxs-lookup"><span data-stu-id="87bdd-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Image of_command запрос, в котором необходимо скопировать скрипт PowerShell в командную строку с повышенными привилегиями и запустить его](../../media/mtp-eval-66.png)

11. <span data-ttu-id="87bdd-239">В мастере нажмите кнопку **начать с помощью защитника Майкрософт для конечной точки** .</span><span class="sxs-lookup"><span data-stu-id="87bdd-239">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Of_the с запросом подтверждения в мастере, где следует нажать кнопку начать с помощью защитника Майкрософт для конечной точки.](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="87bdd-241">Посетите [Центр безопасности защитника Microsoft](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="87bdd-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="87bdd-242">Перейдите в раздел **Параметры** и выберите **Дополнительные функции**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Меню "Параметры центра безопасности защитника of_Microsoft защитника", в котором следует выбрать дополнительные функции](../../media/mtp-eval-68.png)

13. <span data-ttu-id="87bdd-244">Включите интеграцию с **защитником Майкрософт для удостоверения**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-244">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft Security Defender Center Advanced Features, защитник Майкрософт для параметра Identity — переключатель, который необходимо включить](../../media/mtp-eval-69.png)

14. <span data-ttu-id="87bdd-246">Включите интеграцию с **Microsoft Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced Features, Office 365 Threat Intelligence переключатель, который необходимо включить](../../media/mtp-eval-70.png)

15. <span data-ttu-id="87bdd-248">Включите интеграцию с **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced Features, Microsoft Cloud App Security — переключатель, который необходимо включить](../../media/mtp-eval-71.png)

16. <span data-ttu-id="87bdd-250">Прокрутите список вниз и нажмите кнопку **сохранить настройки** , чтобы подтвердить новые интеграции.</span><span class="sxs-lookup"><span data-stu-id="87bdd-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Изображение of_Save кнопка "Параметры", которую нужно щелкнуть](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="87bdd-252">Запуск службы Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87bdd-252">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="87bdd-253">Начиная с 1 июня 2020 г. Корпорация Майкрософт автоматически включает функции защитника Microsoft 365 для всех соответствующих клиентов.</span><span class="sxs-lookup"><span data-stu-id="87bdd-253">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="87bdd-254">Подробные сведения можно узнать [в этой статье сообщества Майкрософт в конференции](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) .</span><span class="sxs-lookup"><span data-stu-id="87bdd-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="87bdd-255">Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="87bdd-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="87bdd-256">Перейдите в раздел **Параметры** и выберите **защитник Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-256">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="87bdd-257">Снимок экрана с вариантом of_Microsoft защитника 365 на странице параметров центра безопасности Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="87bdd-257">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="87bdd-258">Более подробную информацию можно узнать [в статье Включение защитника Microsoft 365](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="87bdd-258">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="87bdd-259">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="87bdd-259">Congratulations!</span></span> <span data-ttu-id="87bdd-260">Вы только что создали пробную лабораторию или пилотную среду защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87bdd-260">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="87bdd-261">Теперь вы можете ознакомиться с пользовательским интерфейсом защитника Microsoft 365!</span><span class="sxs-lookup"><span data-stu-id="87bdd-261">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="87bdd-262">Узнайте, что можно изучить в следующем интерактивном руководстве по Защитнику Microsoft 365, и Узнайте, как использовать каждую панель мониторинга для повседневных задач безопасности.</span><span class="sxs-lookup"><span data-stu-id="87bdd-262">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="87bdd-263">Затем вы можете имитировать атаку и узнать, как обнаружение, создание оповещений и автоматический ответ на атаку, не имеющую файлов, на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="87bdd-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="87bdd-264">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="87bdd-264">Next step</span></span>
|<span data-ttu-id="87bdd-265">![Этап имитации атаки](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="87bdd-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="87bdd-266">Этап имитации атаки</span><span class="sxs-lookup"><span data-stu-id="87bdd-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="87bdd-267">Выполните имитацию атаки для вашей пилотной среды защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87bdd-267">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
