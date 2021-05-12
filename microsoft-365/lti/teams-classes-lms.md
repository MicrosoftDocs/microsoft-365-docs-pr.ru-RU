---
title: Использование Microsoft Teams классов в системе управления обучением
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Интеграция Microsoft Teams классов в систему управления обучением
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327823"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a><span data-ttu-id="8b96e-103">Использование Microsoft Teams классов в системе управления обучением</span><span class="sxs-lookup"><span data-stu-id="8b96e-103">Use Microsoft Teams classes in your Learning Management System</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b96e-104">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="8b96e-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8b96e-105">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="8b96e-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8b96e-106">Microsoft Teams классов — это приложение для взаимодействия средств обучения (LTI), которое помогает преподавателям и учащимся легко перемещаться между своей системой управления обучением (LMS) и Teams.</span><span class="sxs-lookup"><span data-stu-id="8b96e-106">Microsoft Teams class teams is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="8b96e-107">Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.</span><span class="sxs-lookup"><span data-stu-id="8b96e-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="8b96e-108">Утверждение приложения в клиенте Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="8b96e-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="8b96e-109">Следующие задачи завершались администратором Microsoft Office 365 и администратором Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="8b96e-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="8b96e-110">Перед управлением интеграцией в Blackboard Learn Ultra администратор Microsoft Office 365 должен утвердить приложение Blackboard **MSFT Teams** для приложения Learn Ultra Azure для клиента Microsoft Azure учреждения.</span><span class="sxs-lookup"><span data-stu-id="8b96e-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="8b96e-111">Найдите свой microsoft Tenant ID.</span><span class="sxs-lookup"><span data-stu-id="8b96e-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="8b96e-112">Узнайте, [как найти клиента.](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)</span><span class="sxs-lookup"><span data-stu-id="8b96e-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="8b96e-113">Перенаправляем конечную точку согласия администратора платформы администрирования Майкрософт в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8b96e-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="8b96e-114">Замените {tenant} на ID клиента Майкрософт вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8b96e-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="8b96e-115">Регистрация приложений интеграции</span><span class="sxs-lookup"><span data-stu-id="8b96e-115">Register the integration apps</span></span>

<span data-ttu-id="8b96e-116">В качестве администратора Blackboard Learn Ultra необходимо зарегистрировать 2 приложения интеграции LTI 1.3 в тестовой среде:</span><span class="sxs-lookup"><span data-stu-id="8b96e-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="8b96e-117">Интеграция класса learn Teams для поддержки синхронизации реестра</span><span class="sxs-lookup"><span data-stu-id="8b96e-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="8b96e-118">Приложение группы Microsoft Teams класса LTI</span><span class="sxs-lookup"><span data-stu-id="8b96e-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="8b96e-119">Обратите внимание на следующие ITI-ID клиента для обоих приложений:</span><span class="sxs-lookup"><span data-stu-id="8b96e-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="8b96e-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="8b96e-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="8b96e-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="8b96e-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="8b96e-122">Доступ к панели администрирования и в **рамках интеграции** найдите поставщики средств LTI.</span><span class="sxs-lookup"><span data-stu-id="8b96e-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![это диалоговое окно поставщика инструментов LTI, отображает список поставщиков](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="8b96e-124">Выберите **средство Регистрация LTI1.3/Advantage.**</span><span class="sxs-lookup"><span data-stu-id="8b96e-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="8b96e-125">Введите первый из предоставленных клиентских ИД (blackboard или Microsoft) и выберите **Отправка**.</span><span class="sxs-lookup"><span data-stu-id="8b96e-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![средство регистрации LTI с полем для ввода клиентского id](../media/lti-media/register-tool.png)

5. <span data-ttu-id="8b96e-127">Просмотрите предварительно заполненные параметры и убедитесь, что состояние средства помечено как утвержденное.</span><span class="sxs-lookup"><span data-stu-id="8b96e-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="8b96e-128">Прокрутите вниз, а затем выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="8b96e-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="8b96e-129">Повторите предыдущие действия, чтобы зарегистрировать вторую часть приложений LTI в среде.</span><span class="sxs-lookup"><span data-stu-id="8b96e-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="8b96e-130">Настройка приложения REST и совместного доступа к ресурсам cross origin</span><span class="sxs-lookup"><span data-stu-id="8b96e-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="8b96e-131">Администратору Blackboard Learn Ultra также потребуется настроить приложение REST и конфигурацию совместного использования ресурсов cross origin.</span><span class="sxs-lookup"><span data-stu-id="8b96e-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="8b96e-132">Выполните следующее, чтобы настроить приложение REST</span><span class="sxs-lookup"><span data-stu-id="8b96e-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="8b96e-133">Доступ к средствам администрирования Learn, а затем выберите **интеграции API REST** из раздела **Интеграции.**</span><span class="sxs-lookup"><span data-stu-id="8b96e-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="8b96e-134">Выберите **Создание интеграций** и введите тот же ID приложения и клиента, который вы ввели для средства Blackboard Learn Class Teams интеграции LTI.</span><span class="sxs-lookup"><span data-stu-id="8b96e-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="8b96e-135">Введите пользователь Learn (это может быть ваше собственное имя пользователя администрирования), или выберите **Просмотр,** чтобы найти.</span><span class="sxs-lookup"><span data-stu-id="8b96e-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="8b96e-136">Выберите **Да** для **доступа к конечным пользователям.**</span><span class="sxs-lookup"><span data-stu-id="8b96e-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="8b96e-137">Выберите **Да** для **авторизованной для действий в качестве пользователя**</span><span class="sxs-lookup"><span data-stu-id="8b96e-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="8b96e-138">Выберите **Отправка** после завершения.</span><span class="sxs-lookup"><span data-stu-id="8b96e-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="8b96e-139">Настройка совместного доступа к ресурсам попереме происхождения</span><span class="sxs-lookup"><span data-stu-id="8b96e-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="8b96e-140">Вы можете получить доступ к средствам администрирования Learn и выберите **раздел "Совместное** использование ресурсов по пересеченным ресурсам" из раздела **Интеграция.**</span><span class="sxs-lookup"><span data-stu-id="8b96e-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="8b96e-141">Выберите **создание конфигурации.**</span><span class="sxs-lookup"><span data-stu-id="8b96e-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="8b96e-142">Введите `https://bb-ms-teams-ultra-ext.api.blackboard.com` в начале.</span><span class="sxs-lookup"><span data-stu-id="8b96e-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="8b96e-143">Добавьте слово **Авторизация** в **разрешенных загонах**.</span><span class="sxs-lookup"><span data-stu-id="8b96e-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="8b96e-144">Set **Available** to **Yes**.</span><span class="sxs-lookup"><span data-stu-id="8b96e-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="8b96e-145">Выберите **Отправка** после завершения.</span><span class="sxs-lookup"><span data-stu-id="8b96e-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="8b96e-146">Включить класс Teams в blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="8b96e-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="8b96e-147">После включения средств LTI следующим шагом будет настройка интеграции microsoft Class Teams из Microsoft Office 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="8b96e-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="8b96e-148">Это можно сделать, следуя этим шагам в качестве администратора Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="8b96e-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="8b96e-149">В **learn Admin** Tools and  >  **Utilities** выберите Microsoft Teams **администрирования интеграции.**</span><span class="sxs-lookup"><span data-stu-id="8b96e-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![диалоговое окно инструментов и утилит со списком доступных инструментов](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="8b96e-151">Выберите почтовый ящик **для включить Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="8b96e-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="8b96e-152">Введите свой ID клиента в разделе Microsoft O365 Admin</span><span class="sxs-lookup"><span data-stu-id="8b96e-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="8b96e-153">Вы не сможете сохранить параметры до тех пор, пока приложение не будет утверждено администратором O365. См. [утверждение приложения в Microsoft Azure клиенте](#approve-the-app-in-the-microsoft-azure-tenant).</span><span class="sxs-lookup"><span data-stu-id="8b96e-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="8b96e-154">Когда глобальный администратор O365 утвердил приложение blackboard Teams в клиенте Microsoft, выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="8b96e-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
