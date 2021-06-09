---
title: Использование Microsoft Teams собраний с Canvas
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
description: Интеграция Microsoft Teams собраний с Canvas
ms.openlocfilehash: 8ccf1c1d45d38fa4a92b556146744a2c17cd5105
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821923"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="a48ae-103">Использование Microsoft Teams собраний с Canvas</span><span class="sxs-lookup"><span data-stu-id="a48ae-103">Use Microsoft Teams meetings with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a48ae-104">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="a48ae-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a48ae-105">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="a48ae-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a48ae-106">Microsoft Teams собрания — это приложение для взаимодействия средств обучения (LTI), которое помогает преподавателям и учащимся легко перемещаться между их системой управления обучением (LMS) и Teams.</span><span class="sxs-lookup"><span data-stu-id="a48ae-106">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="a48ae-107">Пользователи могут получать доступ к группам классов, связанным с их курсом непосредственно из LMS.</span><span class="sxs-lookup"><span data-stu-id="a48ae-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="a48ae-108">Microsoft Office 365 Admin</span><span class="sxs-lookup"><span data-stu-id="a48ae-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="a48ae-109">Перед управлением интеграцией Microsoft Teams в Instructure Canvas важно, чтобы приложение **Microsoft-Teams-Sync-for-Canvas** Azure было одобрено администратором Microsoft Office 365 учреждения в клиенте Microsoft Azure, прежде чем завершить установку администрирования Canvas.</span><span class="sxs-lookup"><span data-stu-id="a48ae-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="a48ae-110">Во входе в Canvas.</span><span class="sxs-lookup"><span data-stu-id="a48ae-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="a48ae-111">Выберите **ссылку Администратор** в глобальной навигации, а затем выберите учетную запись.</span><span class="sxs-lookup"><span data-stu-id="a48ae-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="a48ae-112">В навигации администратора выберите **ссылку Параметры,** а затем вкладку **Интеграции.**</span><span class="sxs-lookup"><span data-stu-id="a48ae-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="a48ae-113">Введите имя клиента Майкрософт и атрибут входа.</span><span class="sxs-lookup"><span data-stu-id="a48ae-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="a48ae-114">Атрибут входа будет использоваться для связи пользователя Canvas с Azure Active Directory пользователем.</span><span class="sxs-lookup"><span data-stu-id="a48ae-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="a48ae-115">Выберите **обновление Параметры** один раз.</span><span class="sxs-lookup"><span data-stu-id="a48ae-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="a48ae-116">Чтобы утвердить доступ к приложению **Microsoft-Teams-Sync-for-Canvas** Azure, выберите ссылку на доступ к **клиенту Grant.**</span><span class="sxs-lookup"><span data-stu-id="a48ae-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="a48ae-117">Вы будете перенаправлены в конечную точку согласия администратора платформы администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a48ae-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissions](media/permissions.png)

7. <span data-ttu-id="a48ae-119">Выберите **Accept**.</span><span class="sxs-lookup"><span data-stu-id="a48ae-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="a48ae-120">Включи Microsoft Teams синхронизацию, включив очки.</span><span class="sxs-lookup"><span data-stu-id="a48ae-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="a48ae-122">Администрирование Canvas</span><span class="sxs-lookup"><span data-stu-id="a48ae-122">Canvas Admin</span></span>

<span data-ttu-id="a48ae-123">Настройка интеграции Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="a48ae-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="a48ae-124">В качестве администратора Canvas необходимо добавить приложение LTI Microsoft Teams собраний в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="a48ae-124">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="a48ae-125">Обратите внимание на ID клиента LTI для приложения.</span><span class="sxs-lookup"><span data-stu-id="a48ae-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="a48ae-126">Microsoft Teams - 170000000000703</span><span class="sxs-lookup"><span data-stu-id="a48ae-126">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="a48ae-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="a48ae-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="a48ae-128">Выберите **+ Приложение,** чтобы добавить Teams приложения LTI.</span><span class="sxs-lookup"><span data-stu-id="a48ae-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![внешние приложения](media/external-apps.png)

3. <span data-ttu-id="a48ae-130">Выберите **по client ID** для типа конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a48ae-130">Select **By Client ID** for configuration type.</span></span>

   ![добавление приложения](media/add-app.png)

4. <span data-ttu-id="a48ae-132">Введите предоставленный клиентский ID и выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="a48ae-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="a48ae-133">Вы заметите имя приложения Microsoft Teams собраний LTI для client ID для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="a48ae-133">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="a48ae-134">Нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="a48ae-134">Select **Install**.</span></span>

   <span data-ttu-id="a48ae-135">Приложение Microsoft Teams собраний LTI будет добавлено в список внешних приложений.</span><span class="sxs-lookup"><span data-stu-id="a48ae-135">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
