---
title: Включение интеграции SIEM в Microsoft Defender для конечной точки
description: Включение интеграции SIEM для получения обнаружения в решении по безопасности и управлению событиями (SIEM).
keywords: включить соединителем siem, siem, соединителем, сведениями о безопасности и событиями
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
ms.openlocfilehash: 87078bb7bfc6b38788fea2a6a4c3c9108be1d5b4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842966"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ad17a-104">Включение интеграции SIEM в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ad17a-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ad17a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ad17a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ad17a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ad17a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="ad17a-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ad17a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad17a-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ad17a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="ad17a-109">Включение интеграции сведений о безопасности и управления событиями (SIEM), чтобы вы могли извлекть обнаружения из Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ad17a-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="ad17a-110">Вытяните обнаружения с помощью решения SIEM или непосредственно подключившись к API REST обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ad17a-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="ad17a-111">[Microsoft Defender for Endpoint Alert](alerts.md) состоит из одного или нескольких обнаружений.</span><span class="sxs-lookup"><span data-stu-id="ad17a-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="ad17a-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) состоит из подозрительного события, произошедшего на устройстве, и связанных с ним сведений оповещения.</span><span class="sxs-lookup"><span data-stu-id="ad17a-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="ad17a-113">API оповещений Microsoft Defender для конечных точек — это последний API для потребления оповещений и содержит подробный список связанных данных для каждого оповещения.</span><span class="sxs-lookup"><span data-stu-id="ad17a-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="ad17a-114">Дополнительные сведения см. в [дополнительных сведениях о](alerts.md) методах и свойствах alert и [list alerts.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="ad17a-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ad17a-115">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="ad17a-115">Prerequisites</span></span>

- <span data-ttu-id="ad17a-116">У пользователя, который активирует параметр, должны быть разрешения на создание приложения в Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="ad17a-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="ad17a-117">Это кто-то со следующими ролями:</span><span class="sxs-lookup"><span data-stu-id="ad17a-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="ad17a-118">Администратор безопасности и глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="ad17a-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="ad17a-119">Администратор облачного приложения</span><span class="sxs-lookup"><span data-stu-id="ad17a-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="ad17a-120">Администратор приложения</span><span class="sxs-lookup"><span data-stu-id="ad17a-120">Application Administrator</span></span>
  - <span data-ttu-id="ad17a-121">Владелец основного владельца службы</span><span class="sxs-lookup"><span data-stu-id="ad17a-121">Owner of the service principal</span></span>

- <span data-ttu-id="ad17a-122">Во время начальной активации отображается всплывающее экран для входа учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ad17a-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="ad17a-123">Убедитесь, что вы разрешаете всплывающие окантовки для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="ad17a-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="ad17a-124">Включение интеграции SIEM</span><span class="sxs-lookup"><span data-stu-id="ad17a-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="ad17a-125">В области навигации выберите **Параметры**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="ad17a-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![Изображение интеграции SIEM из Параметры menu1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="ad17a-127">Если вы столкнулись с ошибкой при попытке включить соединителем SIEM-приложение, проверьте параметры блокатора всплывающее окна в браузере.</span><span class="sxs-lookup"><span data-stu-id="ad17a-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="ad17a-128">Это может быть блокировка открываемого окна при вскрывии возможности.</span><span class="sxs-lookup"><span data-stu-id="ad17a-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="ad17a-129">Выберите **Включить интеграцию SIEM.**</span><span class="sxs-lookup"><span data-stu-id="ad17a-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="ad17a-130">Это активирует раздел сведений о доступе к соединителем **SIEM** с предварительно заселяемыми значениями, и приложение создается под вашим клиентом Azure Active Directory Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ad17a-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="ad17a-131">Секрет клиента отображается только один раз.</span><span class="sxs-lookup"><span data-stu-id="ad17a-131">The client secret is only displayed once.</span></span> <span data-ttu-id="ad17a-132">Убедитесь, что вы храните его копию в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="ad17a-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![Изображение интеграции SIEM из Параметры menu2](images/siem_details.png)

3. <span data-ttu-id="ad17a-134">Выберите тип SIEM, который используется в организации.</span><span class="sxs-lookup"><span data-stu-id="ad17a-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ad17a-135">Если вы выберете HP ArcSight, вам потребуется сохранить эти два файла конфигурации:</span><span class="sxs-lookup"><span data-stu-id="ad17a-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="ad17a-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="ad17a-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="ad17a-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="ad17a-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="ad17a-138">Если вы хотите напрямую подключиться к API REST обнаружения с помощью программного доступа, выберите **общий API.**</span><span class="sxs-lookup"><span data-stu-id="ad17a-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="ad17a-139">Скопируйте отдельные значения или выберите **сохранить сведения,** чтобы загрузить файл, содержащий все значения.</span><span class="sxs-lookup"><span data-stu-id="ad17a-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="ad17a-140">Выберите **маркеры Generate,** чтобы получить доступ и обновить маркер.</span><span class="sxs-lookup"><span data-stu-id="ad17a-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="ad17a-141">Необходимо создавать новый маркер обновления каждые 90 дней.</span><span class="sxs-lookup"><span data-stu-id="ad17a-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="ad17a-142">Следуйте инструкциям по созданию регистрации приложений Azure AD для [Microsoft Defender для конечной](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) точки и назначьте ему правильные разрешения на чтение оповещений.</span><span class="sxs-lookup"><span data-stu-id="ad17a-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="ad17a-143">Теперь можно приступить к настройке решения SIEM или подключению к API REST обнаружения с помощью программного доступа.</span><span class="sxs-lookup"><span data-stu-id="ad17a-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="ad17a-144">Вы должны использовать маркеры при настройке решения SIEM, чтобы разрешить ему получать обнаружения из Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="ad17a-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="ad17a-145">Интеграция Microsoft Defender для конечной точки с IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="ad17a-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="ad17a-146">Вы можете настроить IBM QRadar для сбора обнаружения в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ad17a-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ad17a-147">Дополнительные сведения см. в [центре знаний IBM.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="ad17a-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad17a-148">См. также</span><span class="sxs-lookup"><span data-stu-id="ad17a-148">See also</span></span>
- [<span data-ttu-id="ad17a-149">Настройте HP ArcSight, чтобы вытащить Microsoft Defender для обнаружения конечных точек</span><span class="sxs-lookup"><span data-stu-id="ad17a-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="ad17a-150">Microsoft Defender для полей обнаружения конечных точек</span><span class="sxs-lookup"><span data-stu-id="ad17a-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="ad17a-151">Pull Microsoft Defender для обнаружения конечных точек с помощью API REST</span><span class="sxs-lookup"><span data-stu-id="ad17a-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="ad17a-152">Устранение неполадок с интеграцией средства SIEM</span><span class="sxs-lookup"><span data-stu-id="ad17a-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
