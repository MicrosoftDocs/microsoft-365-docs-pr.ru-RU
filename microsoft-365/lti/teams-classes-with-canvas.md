---
title: Использование Microsoft Teams классов с Canvas
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
description: Интеграция Microsoft Teams классов с Canvas
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454689"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="84737-103">Использование Microsoft Teams классов с Canvas</span><span class="sxs-lookup"><span data-stu-id="84737-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="84737-104">Microsoft Teams классов — это приложение Обучение Tools Interoperability (LTI), которое помогает преподавателям и учащимся легко перемещаться между Обучение системой управления (LMS) и Teams.</span><span class="sxs-lookup"><span data-stu-id="84737-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="84737-105">Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.</span><span class="sxs-lookup"><span data-stu-id="84737-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="84737-106">Необходимые условия перед развертыванием</span><span class="sxs-lookup"><span data-stu-id="84737-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="84737-107">Текущий класс Teams LTI поддерживает синхронизацию пользователей Canvas с Microsoft Azure Active Directory (AAD) в ограниченной области.</span><span class="sxs-lookup"><span data-stu-id="84737-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="84737-108">Клиент должен иметь точное соответствие между полем Canvas (email, user ID или SIS ID) и upN в Microsoft AAD.</span><span class="sxs-lookup"><span data-stu-id="84737-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="84737-109">Мы работаем над расширением гибкости функций синхронизации, но пока все пользователи Canvas, не совпадающие с upN в AAD, не будут добавлены в класс Teams, синхронизированный с Canvas.</span><span class="sxs-lookup"><span data-stu-id="84737-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="84737-110">Только один клиент Майкрософт может использоваться для сопоставления пользователей между Canvas и Microsoft.</span><span class="sxs-lookup"><span data-stu-id="84737-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="84737-111">Чтобы избежать дублирования групп, необходимо отключить SDS перед использованием Teams класса LTI.</span><span class="sxs-lookup"><span data-stu-id="84737-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="84737-112">Microsoft Office 365 Admin</span><span class="sxs-lookup"><span data-stu-id="84737-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="84737-113">Перед управлением интеграцией Microsoft Teams в Instructure Canvas важно, чтобы приложение **Microsoft-Teams-Sync-for-Canvas** Azure было одобрено администратором Microsoft Office 365 учреждения в клиенте Microsoft Azure, прежде чем завершить установку администрирования Canvas.</span><span class="sxs-lookup"><span data-stu-id="84737-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="84737-114">Во входе в Canvas.</span><span class="sxs-lookup"><span data-stu-id="84737-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="84737-115">Выберите **ссылку Администратор** в глобальной навигации, а затем выберите учетную запись.</span><span class="sxs-lookup"><span data-stu-id="84737-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="84737-116">В навигации администратора выберите **ссылку Параметры,** а затем вкладку **Интеграции.**</span><span class="sxs-lookup"><span data-stu-id="84737-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="84737-117">Включение Microsoft Teams синхронизации, включив очки.</span><span class="sxs-lookup"><span data-stu-id="84737-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="84737-119">Введите имя клиента Майкрософт и атрибут входа.</span><span class="sxs-lookup"><span data-stu-id="84737-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="84737-120">Атрибут входа будет использоваться для связи пользователя Canvas с Azure Active Directory пользователем.</span><span class="sxs-lookup"><span data-stu-id="84737-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="84737-121">Выберите **обновление Параметры** один раз.</span><span class="sxs-lookup"><span data-stu-id="84737-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="84737-122">Чтобы утвердить доступ к приложению **Microsoft-Teams-Sync-for-Canvas** Azure, выберите ссылку на доступ к **клиенту Grant.**</span><span class="sxs-lookup"><span data-stu-id="84737-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="84737-123">Вы будете перенаправлены в конечную точку согласия администратора платформы администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="84737-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissions](media/permissions.png)

8. <span data-ttu-id="84737-125">Выберите **Accept**.</span><span class="sxs-lookup"><span data-stu-id="84737-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="84737-126">Администрирование Canvas</span><span class="sxs-lookup"><span data-stu-id="84737-126">Canvas Admin</span></span>

<span data-ttu-id="84737-127">Настройка интеграции Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="84737-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="84737-128">В качестве администратора Canvas необходимо добавить приложение LTI Microsoft Teams классов в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="84737-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="84737-129">Обратите внимание на ID клиента LTI для приложения.</span><span class="sxs-lookup"><span data-stu-id="84737-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="84737-130">Microsoft Teams - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="84737-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="84737-131">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="84737-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="84737-132">Выберите **+ Приложение,** чтобы добавить Teams приложения LTI.</span><span class="sxs-lookup"><span data-stu-id="84737-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![внешние приложения](media/external-apps.png)

3. <span data-ttu-id="84737-134">Выберите **по client ID** для типа конфигурации.</span><span class="sxs-lookup"><span data-stu-id="84737-134">Select **By Client ID** for configuration type.</span></span>

   ![добавление приложения](media/add-app.png)

4. <span data-ttu-id="84737-136">Введите предоставленный клиентский ID и выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="84737-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="84737-137">Вы заметите имя приложения Microsoft Teams классов LTI для client ID для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="84737-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="84737-138">Нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="84737-138">Select **Install**.</span></span>

   <span data-ttu-id="84737-139">Приложение Microsoft Teams классов LTI будет добавлено в список внешних приложений.</span><span class="sxs-lookup"><span data-stu-id="84737-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="84737-140">Включение приложения LTI для курсов Canvas</span><span class="sxs-lookup"><span data-stu-id="84737-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="84737-141">Чтобы использовать приложение LTI в течение курса, инструктор курса Canvas должен включить синхронизацию интеграций. Каждый курс должен быть включен инструктором для создания соответствующей группы; глобального механизма создания групп нет.</span><span class="sxs-lookup"><span data-stu-id="84737-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="84737-142">Эта мера разработана в качестве меры предосторожности для предотвращения создания нежелательных групп.</span><span class="sxs-lookup"><span data-stu-id="84737-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="84737-143">Обратитесь к преподавателям в документацию [для](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) включения приложения LTI для каждого курса и завершения установки интеграции.</span><span class="sxs-lookup"><span data-stu-id="84737-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
