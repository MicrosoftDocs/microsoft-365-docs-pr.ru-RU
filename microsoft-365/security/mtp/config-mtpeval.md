---
title: Настройка базовых принципов защиты от угроз Майкрософт для испытательной лабораторной среды
description: Настройка базовых принципов защиты от угроз Майкрософт, Office 365 ATP, Azure ATP, Microsoft Cloud App Security и пакета ATP для пробной лабораторной среды (Майкрософт)
keywords: Настройка пробной системы защиты от угроз Майкрософт, пробной конфигурации Майкрософт для защиты от угроз, Настройка базовых принципов защиты от угроз Майкрософт, основы защиты от угроз Майкрософт
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049513"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="51d47-104">Настройка принципов защиты от угроз Майкрософт для испытательной лабораторной среды</span><span class="sxs-lookup"><span data-stu-id="51d47-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="51d47-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="51d47-105">**Applies to:**</span></span>
- <span data-ttu-id="51d47-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="51d47-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="51d47-107">Создание пробной лабораторной среды Майкрософт для защиты от угроз и развертывание выполняется в три этапа:</span><span class="sxs-lookup"><span data-stu-id="51d47-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Подготовка пробной лабораторной среды Майкрософт по защите от угроз" />
      <br/><span data-ttu-id="51d47-109">Этап 1: подготовка</a></span><span class="sxs-lookup"><span data-stu-id="51d47-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Настройка пробной лабораторной среды Майкрософт для защиты от угроз" />
      <br/><span data-ttu-id="51d47-111">Этап 2: Настройка</a></span><span class="sxs-lookup"><span data-stu-id="51d47-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Настройка всех принципов защиты от угроз Майкрософт для испытательной лаборатории и встроенных конечных точек защиты от угроз Майкрософт" />
      <br/><span data-ttu-id="51d47-113">Этап 3: Настройка встроенного &</a></span><span class="sxs-lookup"><span data-stu-id="51d47-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="51d47-114">В настоящее время вы намерены на этапе настройки.</span><span class="sxs-lookup"><span data-stu-id="51d47-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="51d47-115">Подготовка — это ключ к любому успешному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="51d47-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="51d47-116">В этой статье вы узнаете о точках, которые необходимо учесть при подготовке к развертыванию пакета ATP для защитника Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51d47-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="51d47-117">Основы защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="51d47-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="51d47-118">Защита от угроз Майкрософт состоит из четырех базовых принципов.</span><span class="sxs-lookup"><span data-stu-id="51d47-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="51d47-119">Несмотря на то, что один из них уже может обеспечить безопасность вашей сетевой организации, при использовании четырех базовых принципов защиты от угроз Майкрософт вы узнаете, что ваша организация является наибольшим значением.</span><span class="sxs-lookup"><span data-stu-id="51d47-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![Of_page изображений](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="51d47-121">В этом разделе приведутся инструкции по настройке:</span><span class="sxs-lookup"><span data-stu-id="51d47-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="51d47-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51d47-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="51d47-123">Расширенная защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="51d47-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="51d47-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="51d47-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="51d47-125">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="51d47-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="51d47-126">Настройка Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="51d47-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="51d47-127">Пропустите этот шаг, если вы уже включили расширенную защиту от угроз для Office 365.</span><span class="sxs-lookup"><span data-stu-id="51d47-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="51d47-128">Существует модуль PowerShell, который называется *рекомендуемой конфигурацией Office 365 Advanced Threat protection Analyzer (Orca)* , который помогает определить некоторые из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="51d47-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="51d47-129">При запуске с правами администратора в клиенте командлет Get-Оркарепорт поможет создать оценку параметров защиты от нежелательной почты, защиты от фишинга и других сообщений санацией.</span><span class="sxs-lookup"><span data-stu-id="51d47-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="51d47-130">Вы можете скачать этот модуль из https://www.powershellgallery.com/packages/ORCA/.</span><span class="sxs-lookup"><span data-stu-id="51d47-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="51d47-131">Перейдите к разделу**Threat management** > **Policy** [Безопасность & безопасности центра](https://protection.office.com/homepage) > соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="51d47-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="51d47-132">![Of_page изображений](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="51d47-133">Выберите пункт **Защита от фишинга ATP**, выберите **создать** и введите имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="51d47-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="51d47-134">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51d47-134">Click **Next**.</span></span>
<span data-ttu-id="51d47-135">![Of_page изображений](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="51d47-136">Измените политику защиты от фишинга ATP.</span><span class="sxs-lookup"><span data-stu-id="51d47-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="51d47-137">Изменение **расширенного порога фишинга** на **2 агрессивно**.</span><span class="sxs-lookup"><span data-stu-id="51d47-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="51d47-138">Щелкните раскрывающееся меню **Добавить условие** и выберите домен (ы) в качестве домена получателя.</span><span class="sxs-lookup"><span data-stu-id="51d47-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="51d47-139">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51d47-139">Click **Next**.</span></span>
<span data-ttu-id="51d47-140">![Of_page изображений](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="51d47-141">Проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="51d47-141">Review your settings.</span></span> <span data-ttu-id="51d47-142">Щелкните **создать эту политику** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="51d47-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="51d47-143">![Of_page изображений](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="51d47-144">Выберите пункт **безопасные вложения ATP** и установите флажок **включить ATP для SharePoint, OneDrive и Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="51d47-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="51d47-145">![Of_page изображений](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="51d47-146">Нажмите значок +, чтобы создать новую политику безопасных вложений, примените ее к доменам получателя.</span><span class="sxs-lookup"><span data-stu-id="51d47-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="51d47-147">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="51d47-147">Click **Save**.</span></span>
<span data-ttu-id="51d47-148">![Of_page изображений](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="51d47-149">Затем выберите политику **безопасных ссылок ATP** , а затем щелкните значок карандаша, чтобы изменить политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51d47-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="51d47-150">Убедитесь, что флажок не **отслеживать, когда пользователи щелкать ссылку "безопасные ссылки** " не установлен, а остальные параметры выбраны.</span><span class="sxs-lookup"><span data-stu-id="51d47-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="51d47-151">Дополнительные сведения приведены в разделе [Параметры безопасных ссылок](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="51d47-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="51d47-152">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="51d47-152">Click **Save**.</span></span> 
<span data-ttu-id="51d47-153">![Of_page изображений](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="51d47-154">Затем выберите политику **защиты от вредоносных программ** , выберите значение по умолчанию и нажмите значок карандаша.</span><span class="sxs-lookup"><span data-stu-id="51d47-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="51d47-155">Нажмите кнопку **Параметры** и выберите Да, чтобы включить **ответ на обнаружение вредоносных программ**, **используя текст уведомления по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="51d47-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="51d47-156">Включите **Фильтр общих типов вложений** .</span><span class="sxs-lookup"><span data-stu-id="51d47-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="51d47-157">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="51d47-157">Click **Save**.</span></span>
<br><span data-ttu-id="51d47-158">![Of_page изображений](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="51d47-159">Перейдите к разделу >  [& безопасности Office 365](https://protection.office.com/homepage)**Поиск в журнале аудита** **поиска** > и включите аудит для.</span><span class="sxs-lookup"><span data-stu-id="51d47-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="51d47-160">![Of_page изображений](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="51d47-161">Интеграция Office 365 с пакетом ATP с помощью защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="51d47-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="51d47-162">Перейдите в раздел >  [& безопасности Office 365 Security](https://protection.office.com/homepage)**Management** > **Explorer** и выберите **Параметры вдатп** в правом верхнем углу экрана.</span><span class="sxs-lookup"><span data-stu-id="51d47-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="51d47-163">В диалоговом окне Подключение к Защитнику (Майкрософт) ATP включите параметр **подключиться к Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="51d47-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="51d47-164">![Of_page изображений](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="51d47-165">Настройка Advanced Threat Protection в Azure</span><span class="sxs-lookup"><span data-stu-id="51d47-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="51d47-166">Пропустите этот шаг, если вы уже включили службу Advanced Threat Protection в Azure</span><span class="sxs-lookup"><span data-stu-id="51d47-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="51d47-167">Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/info) > выберите **Дополнительные ресурсы** > **Azure Advanced Threat protection**.</span><span class="sxs-lookup"><span data-stu-id="51d47-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="51d47-168">![Of_page изображений](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="51d47-169">Нажмите кнопку **создать** , чтобы запустить мастер Advanced Threat protection.</span><span class="sxs-lookup"><span data-stu-id="51d47-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="51d47-170">![Of_page изображений](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="51d47-171">Выберите **указать имя пользователя и пароль для подключения к лесу Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="51d47-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="51d47-172">![Of_page изображений](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="51d47-173">Введите локальные учетные данные Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51d47-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="51d47-174">Это может быть любая учетная запись пользователя, имеющая доступ на чтение к Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51d47-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="51d47-175">![Of_page изображений](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="51d47-176">Затем выберите пункт **скачать файл установки и передачи датчиков** на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="51d47-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="51d47-177">![Of_page изображений](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="51d47-178">Выполните настройку датчика Azure ATP и начните выполнение мастера.</span><span class="sxs-lookup"><span data-stu-id="51d47-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="51d47-179">![Of_page изображений](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="51d47-180">Нажмите кнопку **Далее** в разделе Тип развертывания Sensor (датчик).</span><span class="sxs-lookup"><span data-stu-id="51d47-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="51d47-181">![Of_page изображений](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="51d47-182">Скопируйте ключ доступа, так как он понадобится для его последующего ввода в мастере.</span><span class="sxs-lookup"><span data-stu-id="51d47-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="51d47-183">![Of_page изображений](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="51d47-184">Скопируйте в мастер ключ доступа и нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="51d47-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="51d47-185">![Of_page изображений](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="51d47-186">Поздравляем, вы успешно настроили службу Advanced Threat Protection в Azure на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="51d47-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="51d47-187">![Of_page изображений](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="51d47-188">В разделе Параметры [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) выберите пункт **Защитник Windows ATP**, а затем включите переключатель.</span><span class="sxs-lookup"><span data-stu-id="51d47-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="51d47-189">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="51d47-189">Click **Save**.</span></span> 
<span data-ttu-id="51d47-190">![Of_page изображений](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="51d47-191">Пакет ATP для защитника Windows изменен в качестве пакета ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="51d47-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="51d47-192">Изменение фирменного стиля на всех наших порталах разбивается на согласованность.</span><span class="sxs-lookup"><span data-stu-id="51d47-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="51d47-193">Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="51d47-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="51d47-194">Пропустите этот шаг, если вы уже включили Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="51d47-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="51d47-195">Перейдите в раздел [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Security Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="51d47-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="51d47-196">![Of_page изображений](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="51d47-197">В информационном запросе для интеграции Azure ATP выберите **включить интеграцию данных Azure ATP**.</span><span class="sxs-lookup"><span data-stu-id="51d47-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="51d47-198">![Of_page изображений](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="51d47-199">Если вы не видите этот запрос, это может означать, что интеграция Azure ATP данных уже включена.</span><span class="sxs-lookup"><span data-stu-id="51d47-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="51d47-200">Тем не менее, если вы не уверены, обратитесь к ИТ ИТ администратора, чтобы подтвердить.</span><span class="sxs-lookup"><span data-stu-id="51d47-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="51d47-201">Перейдите к разделу **Параметры**, перейдите в раздел **Интеграция Azure ATP** вкл., а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="51d47-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="51d47-202">![Of_page изображений](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="51d47-203">Для новых экземпляров Azure ATP этот переключатель интеграции автоматически включается.</span><span class="sxs-lookup"><span data-stu-id="51d47-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="51d47-204">Прежде чем переходить к следующему шагу, убедитесь, что интеграция Azure ATP включена.</span><span class="sxs-lookup"><span data-stu-id="51d47-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="51d47-205">В разделе Параметры облачного обнаружения выберите **Интеграция с защитником Майкрософт**, а затем включите интеграцию.</span><span class="sxs-lookup"><span data-stu-id="51d47-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="51d47-206">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="51d47-206">Click **Save**.</span></span>
<span data-ttu-id="51d47-207">![Of_page изображений](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="51d47-208">В разделе Параметры облачного обнаружения выберите **обогащение пользователей**, а затем включите интеграцию с Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51d47-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="51d47-209">![Of_page изображений](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="51d47-210">Настройка Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="51d47-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="51d47-211">Пропустите этот шаг, если вы уже включили Advanced Threat Protection в защитнике Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51d47-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="51d47-212">Перейдите в раздел [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Center securitys Microsoft Защитник**.</span><span class="sxs-lookup"><span data-stu-id="51d47-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="51d47-213">Нажмите кнопку **Open** (Открыть).</span><span class="sxs-lookup"><span data-stu-id="51d47-213">Click **Open**.</span></span>
<br><span data-ttu-id="51d47-214">![Of_page изображений](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="51d47-215">Следуйте инструкциям мастера Advanced Threat Protection в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="51d47-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="51d47-216">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51d47-216">Click **Next**.</span></span> 
<br><span data-ttu-id="51d47-217">![Of_page изображений](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="51d47-218">Выберите в зависимости от предпочтительного расположения хранилища данных, политики хранения данных, размера организации и согласия пользователя по предварительным функциям.</span><span class="sxs-lookup"><span data-stu-id="51d47-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="51d47-219">![Of_page изображений](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="51d47-220">После этого невозможно изменить некоторые параметры, такие как расположение хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="51d47-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="51d47-221">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51d47-221">Click **Next**.</span></span> 

4. <span data-ttu-id="51d47-222">Нажмите **продолжить** , чтобы подготовиться к работе клиента, который является ПАКЕТом ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="51d47-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="51d47-223">![Of_page изображений](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="51d47-224">Применяйте конечные точки с помощью групповых политик, диспетчера конечных точек Майкрософт или запуска локального сценария для пакета ATP в защитнике Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="51d47-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="51d47-225">Для простоты в этом руководстве используется локальный скрипт.</span><span class="sxs-lookup"><span data-stu-id="51d47-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="51d47-226">Щелкните **скачать пакет** и скопируйте сценарий входящей миграции в конечные точки (s).</span><span class="sxs-lookup"><span data-stu-id="51d47-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="51d47-227">![Of_page изображений](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="51d47-228">В конечной точке запустите сценарий входящей миграции от имени администратора и нажмите Y.</span><span class="sxs-lookup"><span data-stu-id="51d47-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="51d47-229">![Of_page изображений](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="51d47-230">Поздравляем, вы выполнили переплату для первой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="51d47-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Of_page изображений](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="51d47-232">Скопируйте тест с определением в мастере Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="51d47-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="51d47-233">![Of_page изображений](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="51d47-234">Скопируйте скрипт PowerShell в командную строку с повышенными привилегиями и запустите его.</span><span class="sxs-lookup"><span data-stu-id="51d47-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="51d47-235">![Of_page изображений](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="51d47-236">В мастере нажмите кнопку **начать с помощью ATP "защитник Майкрософт"** .</span><span class="sxs-lookup"><span data-stu-id="51d47-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="51d47-237">![Of_page изображений](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="51d47-238">Посетите [Центр безопасности защитника Microsoft](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="51d47-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="51d47-239">Перейдите в раздел **Параметры** и выберите **Дополнительные функции**.</span><span class="sxs-lookup"><span data-stu-id="51d47-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="51d47-240">![Of_page изображений](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="51d47-241">Включите интеграцию с **Advanced Threat Protection в Azure**.</span><span class="sxs-lookup"><span data-stu-id="51d47-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="51d47-242">![Of_page изображений](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="51d47-243">Включите интеграцию с **Microsoft Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="51d47-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="51d47-244">![Of_page изображений](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="51d47-245">Включите интеграцию с **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="51d47-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="51d47-246">![Of_page изображений](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="51d47-247">Прокрутите список вниз и нажмите кнопку **сохранить настройки** , чтобы подтвердить новые интеграции.</span><span class="sxs-lookup"><span data-stu-id="51d47-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="51d47-248">![Of_page изображений](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="51d47-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="51d47-249">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="51d47-249">Next steps</span></span>
<span data-ttu-id="51d47-250">[Включите защиту от угроз Майкрософт](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) и [Создайте тестовое оповещение](generate-test-alert.md).</span><span class="sxs-lookup"><span data-stu-id="51d47-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
