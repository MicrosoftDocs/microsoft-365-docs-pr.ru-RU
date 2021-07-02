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
ms.openlocfilehash: 50e4e8ef912a8f19f379bba29b328a5a27358b5c
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256907"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="cb1a5-103">Использование Microsoft Teams классов с Canvas</span><span class="sxs-lookup"><span data-stu-id="cb1a5-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb1a5-104">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cb1a5-105">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cb1a5-106">Microsoft Teams классов — это приложение Обучение Tools Interoperability (LTI), которое помогает преподавателям и учащимся легко перемещаться между Обучение системой управления (LMS) и Teams.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="cb1a5-107">Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="cb1a5-108">Microsoft Office 365 Admin</span><span class="sxs-lookup"><span data-stu-id="cb1a5-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="cb1a5-109">Перед управлением интеграцией Microsoft Teams в Instructure Canvas важно, чтобы приложение **Microsoft-Teams-Sync-for-Canvas** Azure было одобрено администратором Microsoft Office 365 учреждения в клиенте Microsoft Azure, прежде чем завершить установку администрирования Canvas.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="cb1a5-110">Во входе в Canvas.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-110">Sign in to Canvas.</span></span>

2. <span data-ttu-id="cb1a5-111">Выберите **ссылку Администратор** в глобальной навигации, а затем выберите учетную запись.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="cb1a5-112">В навигации администратора выберите **ссылку Параметры,** а затем вкладку **Интеграции.**</span><span class="sxs-lookup"><span data-stu-id="cb1a5-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="cb1a5-113">Включение Microsoft Teams синхронизации, включив очки.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-113">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="cb1a5-115">Введите имя клиента Майкрософт и атрибут входа.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-115">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="cb1a5-116">Атрибут входа будет использоваться для связи пользователя Canvas с Azure Active Directory пользователем.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-116">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="cb1a5-117">Выберите **обновление Параметры** один раз.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-117">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="cb1a5-118">Чтобы утвердить доступ к приложению **Microsoft-Teams-Sync-for-Canvas** Azure, выберите ссылку на доступ к **клиенту Grant.**</span><span class="sxs-lookup"><span data-stu-id="cb1a5-118">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="cb1a5-119">Вы будете перенаправлены в конечную точку согласия администратора платформы администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-119">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissions](media/permissions.png)

8. <span data-ttu-id="cb1a5-121">Выберите **Accept**.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-121">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="cb1a5-122">Администрирование Canvas</span><span class="sxs-lookup"><span data-stu-id="cb1a5-122">Canvas Admin</span></span>

<span data-ttu-id="cb1a5-123">Настройка интеграции Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="cb1a5-124">В качестве администратора Canvas необходимо добавить приложение LTI Microsoft Teams классов в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="cb1a5-125">Обратите внимание на ID клиента LTI для приложения.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="cb1a5-126">Microsoft Teams - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="cb1a5-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="cb1a5-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="cb1a5-128">Выберите **+ Приложение,** чтобы добавить Teams приложения LTI.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-128">Select **+ App** to add the Teams LTI apps.</span></span>

   ![внешние приложения](media/external-apps.png)

3. <span data-ttu-id="cb1a5-130">Выберите **по client ID** для типа конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-130">Select **By Client ID** for configuration type.</span></span>

   ![добавление приложения](media/add-app.png)

4. <span data-ttu-id="cb1a5-132">Введите предоставленный клиентский ID и выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-132">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="cb1a5-133">Вы заметите имя приложения Microsoft Teams классов LTI для client ID для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="cb1a5-134">Нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-134">Select **Install**.</span></span>

   <span data-ttu-id="cb1a5-135">Приложение Microsoft Teams классов LTI будет добавлено в список внешних приложений.</span><span class="sxs-lookup"><span data-stu-id="cb1a5-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
