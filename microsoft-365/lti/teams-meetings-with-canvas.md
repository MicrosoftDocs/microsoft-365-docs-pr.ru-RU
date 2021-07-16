---
title: Использование Microsoft Teams собраний с Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Интеграция Microsoft Teams собраний с Canvas
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454677"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="44974-103">Использование Microsoft Teams собраний с Canvas</span><span class="sxs-lookup"><span data-stu-id="44974-103">Use Microsoft Teams meetings with Canvas</span></span>

<span data-ttu-id="44974-104">Microsoft Teams собрания — это приложение Обучение средства взаимодействия (LTI), которое помогает преподавателям и учащимся легко перемещаться между Обучение системой управления (LMS) и Teams.</span><span class="sxs-lookup"><span data-stu-id="44974-104">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="44974-105">Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.</span><span class="sxs-lookup"><span data-stu-id="44974-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="44974-106">Microsoft Office 365 Admin</span><span class="sxs-lookup"><span data-stu-id="44974-106">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="44974-107">Перед управлением интеграцией Microsoft Teams в Instructure Canvas важно, чтобы приложение **Microsoft-Teams-Sync-for-Canvas** Azure было одобрено администратором Microsoft Office 365 учреждения в клиенте Microsoft Azure, прежде чем завершить установку администрирования Canvas.</span><span class="sxs-lookup"><span data-stu-id="44974-107">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="44974-108">Во входе в Canvas.</span><span class="sxs-lookup"><span data-stu-id="44974-108">Sign in to Canvas.</span></span>

2. <span data-ttu-id="44974-109">Выберите **ссылку Администратор** в глобальной навигации, а затем выберите учетную запись.</span><span class="sxs-lookup"><span data-stu-id="44974-109">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="44974-110">В навигации администратора выберите **ссылку Параметры,** а затем вкладку **Интеграции.**</span><span class="sxs-lookup"><span data-stu-id="44974-110">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="44974-111">Введите имя клиента Майкрософт и атрибут входа.</span><span class="sxs-lookup"><span data-stu-id="44974-111">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="44974-112">Атрибут входа будет использоваться для связи пользователя Canvas с Azure Active Directory пользователем.</span><span class="sxs-lookup"><span data-stu-id="44974-112">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="44974-113">Выберите **обновление Параметры** один раз.</span><span class="sxs-lookup"><span data-stu-id="44974-113">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="44974-114">Чтобы утвердить доступ к приложению **Microsoft-Teams-Sync-for-Canvas** Azure, выберите ссылку на доступ к **клиенту Grant.**</span><span class="sxs-lookup"><span data-stu-id="44974-114">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="44974-115">Вы будете перенаправлены в конечную точку согласия администратора платформы администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="44974-115">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissions](media/permissions.png)

7. <span data-ttu-id="44974-117">Выберите **Accept**.</span><span class="sxs-lookup"><span data-stu-id="44974-117">Select **Accept**.</span></span>

8. <span data-ttu-id="44974-118">Включи Microsoft Teams синхронизацию, включив очки.</span><span class="sxs-lookup"><span data-stu-id="44974-118">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="44974-120">Администрирование Canvas</span><span class="sxs-lookup"><span data-stu-id="44974-120">Canvas Admin</span></span>

<span data-ttu-id="44974-121">Настройка интеграции Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="44974-121">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="44974-122">В качестве администратора Canvas необходимо добавить приложение LTI Microsoft Teams собраний в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="44974-122">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="44974-123">Обратите внимание на ID клиента LTI для приложения.</span><span class="sxs-lookup"><span data-stu-id="44974-123">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="44974-124">Microsoft Teams - 170000000000703</span><span class="sxs-lookup"><span data-stu-id="44974-124">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="44974-125">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="44974-125">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="44974-126">Выберите **+ Приложение,** чтобы добавить Teams приложения LTI.</span><span class="sxs-lookup"><span data-stu-id="44974-126">Select **+ App** to add the Teams LTI apps.</span></span>

   ![внешние приложения](media/external-apps.png)

3. <span data-ttu-id="44974-128">Выберите **по client ID** для типа конфигурации.</span><span class="sxs-lookup"><span data-stu-id="44974-128">Select **By Client ID** for configuration type.</span></span>

   ![добавление приложения](media/add-app.png)

4. <span data-ttu-id="44974-130">Введите предоставленный клиентский ID и выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="44974-130">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="44974-131">Вы заметите имя приложения Microsoft Teams собраний LTI для client ID для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="44974-131">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="44974-132">Нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="44974-132">Select **Install**.</span></span>

   <span data-ttu-id="44974-133">Приложение Microsoft Teams собраний LTI будет добавлено в список внешних приложений.</span><span class="sxs-lookup"><span data-stu-id="44974-133">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="44974-134">Включить курсы canvas</span><span class="sxs-lookup"><span data-stu-id="44974-134">Enable for Canvas Courses</span></span>

<span data-ttu-id="44974-135">Чтобы использовать LTI в течение курса, инструктор курса Canvas должен включить синхронизацию интеграций. Каждый курс должен быть включен инструктором для создания соответствующего Teams; глобального механизма создания Teams нет.</span><span class="sxs-lookup"><span data-stu-id="44974-135">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="44974-136">Это разработано с осторожностью, чтобы предотвратить нежелательные Teams создания.</span><span class="sxs-lookup"><span data-stu-id="44974-136">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="44974-137">Обратитесь к преподавателям в [документацию для](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) включения LTI для каждого курса и завершения установки интеграции.</span><span class="sxs-lookup"><span data-stu-id="44974-137">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
