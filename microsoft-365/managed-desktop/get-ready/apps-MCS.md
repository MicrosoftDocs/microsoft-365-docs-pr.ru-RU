---
title: Работа с консультационными службами Майкрософт
description: подготовка и дальнейшие действия по работе с MCS для упаковки приложений
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, приложения, MCS, упаковка
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4491504616eb4bb447f12d08dddb12c73c2a88ac
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962626"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="9a3d1-104">Работа с консультационными службами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9a3d1-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="9a3d1-105">Вы можете приступить к работе со службами Microsoft консультационной службы (MCS), чтобы ваши приложения были упакованы для использования на настольном компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="9a3d1-106">Для получения подробных сведений свяжитесь с представителем по учетной записи, чтобы связаться с MCS и областью действия конкретного проекта упаковки приложений.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="9a3d1-107">Роли и обязанности</span><span class="sxs-lookup"><span data-stu-id="9a3d1-107">Roles and responsibilities</span></span>

<span data-ttu-id="9a3d1-108">Для работы с упаковкой приложений MCS **необходимо предоставить следующие элементы**:</span><span class="sxs-lookup"><span data-stu-id="9a3d1-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="9a3d1-109">Исходные файлы установщика (например, Setup. exe или. msi).</span><span class="sxs-lookup"><span data-stu-id="9a3d1-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="9a3d1-110">Инструкции по установке, указывающие сведения о том, как должна выглядеть Последняя установка.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="9a3d1-111">Например, должно ли приложение иметь ярлык на рабочем столе?</span><span class="sxs-lookup"><span data-stu-id="9a3d1-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="9a3d1-112">Какова видимость приложения?</span><span class="sxs-lookup"><span data-stu-id="9a3d1-112">What should the app's visibility be?</span></span> <span data-ttu-id="9a3d1-113">Должно ли приложение подключиться к серверу, и если да, то какое из них?</span><span class="sxs-lookup"><span data-stu-id="9a3d1-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="9a3d1-114">Дополнительные сведения см. в статье [шаблон запроса упаковки приложений](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="9a3d1-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="9a3d1-115">Чтобы убедиться, что приложение работает так же, как в вашей среде, необходимо выполнить собственный приемочный тест.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="9a3d1-116">**MCS будет выполнять следующие действия:**</span><span class="sxs-lookup"><span data-stu-id="9a3d1-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="9a3d1-117">Проверка того, что приложение запрещено или ограничено в среде настольных компьютеров, управляемой Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="9a3d1-118">Тестирование установки, запуска и удаления приложения, чтобы обеспечить совместимость с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="9a3d1-119">Если сервер MCS обнаруживает проблему совместимости, он переводит приложение на [классическое приложение](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) , которое гарантирует исправление.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="9a3d1-120">Упаковка приложения в спецификацию и тестирование развертывания приложения с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="9a3d1-121">Расписание доставки приложений</span><span class="sxs-lookup"><span data-stu-id="9a3d1-121">App delivery schedule</span></span>

<span data-ttu-id="9a3d1-122">Начните процесс упаковки, отправив сведения о приложении на портал для настольных компьютеров, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="9a3d1-123">Группа упаковки рассматривает новые отправки каждый четверг.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="9a3d1-124">После просмотра и упаковки Упакованные приложения доставляются в пятницу ниже.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="9a3d1-125">До пяти приложений в неделю можно упаковывать для запуска, но служба может масштабироваться в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![Календарь, покажет приложение в четверг (21 в данном примере), проверка мультимедиа на следующий день, Упаковка на следующий понедельник (25-й) и доставка приложений на последующую пятницу (29-й)](images/MCS-cal.png)

<span data-ttu-id="9a3d1-127">Вы получите уведомление после доставки приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="9a3d1-128">В этот момент у вас есть 21 дня для проведения приемочного тестирования и выхода из работы на портале управляемых компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="9a3d1-129">Если во время приемочного тестирования возникла проблема с приложением, отклоните приложение на портале, управляемом Майкрософт, и вы будете подключены через электронную почту с помощью диспетчера MCS, чтобы понять и устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="9a3d1-130">Тестирование учетных записей и среды</span><span class="sxs-lookup"><span data-stu-id="9a3d1-130">Testing accounts and environment</span></span>

<span data-ttu-id="9a3d1-131">Чтобы группа упаковки выполнила миграцию в Microsoft Intune, мы рекомендуем предоставить определенные разрешения:</span><span class="sxs-lookup"><span data-stu-id="9a3d1-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="9a3d1-132">Доступ к возможностям развертывания приложений Microsoft Intune для добавления и назначения приложения с помощью упаковщика</span><span class="sxs-lookup"><span data-stu-id="9a3d1-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="9a3d1-133">Тестовые группы, учетные записи пользователей и лицензии для упаковщиков, которые смогут тестировать приложения</span><span class="sxs-lookup"><span data-stu-id="9a3d1-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="9a3d1-134">MCS будет использовать эти разрешения для выполнения следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9a3d1-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="9a3d1-135">Проверка работы приложения на виртуальной машине, настроенной на компьютере, управляемом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9a3d1-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="9a3d1-136">Отправка приложения в Microsoft Intune для развертывания пользователям</span><span class="sxs-lookup"><span data-stu-id="9a3d1-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="9a3d1-137">Без этих разрешений для MCS можно перемещаться вперед, но они не смогут загружать приложения в среду.</span><span class="sxs-lookup"><span data-stu-id="9a3d1-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


