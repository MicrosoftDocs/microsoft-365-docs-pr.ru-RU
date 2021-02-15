---
title: Работа с консультационными службами Майкрософт
description: подготовка и действия для работы с MCS для упаковки приложений
keywords: Microsoft Managed Desktop, Microsoft 365, служба, документация, приложения, MCS, упаковка
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841427"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="1a17a-104">Работа с консультационными службами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1a17a-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="1a17a-105">Вы можете взаимодействовать со службами Microsoft Consulting Services (MCS) для упаковки приложений для использования с управляемыми Майкрософт настольными компьютерами.</span><span class="sxs-lookup"><span data-stu-id="1a17a-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="1a17a-106">Чтобы получить точные сведения, обратитесь к представителю вашей учетной записи, чтобы связаться с MCS и задайте область вашего проекта упаковки приложений.</span><span class="sxs-lookup"><span data-stu-id="1a17a-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="1a17a-107">Роли и обязанности.</span><span class="sxs-lookup"><span data-stu-id="1a17a-107">Roles and responsibilities</span></span>

<span data-ttu-id="1a17a-108">Для работы с упаковкой приложений MCS необходимо предоставить **указанные здесь элементы.**</span><span class="sxs-lookup"><span data-stu-id="1a17a-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="1a17a-109">Исходные файлы установщика (например, setup.exe или MSI).</span><span class="sxs-lookup"><span data-stu-id="1a17a-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="1a17a-110">Инструкции по установке с указанием сведений о том, как должна выглядеть окончательная установка.</span><span class="sxs-lookup"><span data-stu-id="1a17a-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="1a17a-111">Например, должен ли быть ярлык на рабочем столе для приложения?</span><span class="sxs-lookup"><span data-stu-id="1a17a-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="1a17a-112">Какова должна быть видимость приложения?</span><span class="sxs-lookup"><span data-stu-id="1a17a-112">What should the app's visibility be?</span></span> <span data-ttu-id="1a17a-113">Должно ли приложение подключаться к серверу и, если да, какое именно?</span><span class="sxs-lookup"><span data-stu-id="1a17a-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="1a17a-114">Подробные сведения [см. в шаблоне запроса на упаковку приложений.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)</span><span class="sxs-lookup"><span data-stu-id="1a17a-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="1a17a-115">Необходимо выполнить собственное приемочное тестирование, чтобы убедиться, что приложение работает так, как вам нужно в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="1a17a-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="1a17a-116">**MCS будет принимать на себя указанные действия.**</span><span class="sxs-lookup"><span data-stu-id="1a17a-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="1a17a-117">Проверка того, является ли приложение запрещенным или ограниченным в среде компьютеров, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1a17a-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="1a17a-118">Тестирование установки, запуска и установки приложения для обеспечения совместимости с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1a17a-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="1a17a-119">Если MCS обнаружит проблему совместимости, она передает приложение в программу [Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) для классических приложений для устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="1a17a-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="1a17a-120">Упаковка приложения в спецификацию и тестирование развертывания приложения с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="1a17a-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="1a17a-121">Расписание доставки приложения</span><span class="sxs-lookup"><span data-stu-id="1a17a-121">App delivery schedule</span></span>

<span data-ttu-id="1a17a-122">Начните процесс упаковки, загрузив сведения о приложении на портал управляемых Майкрософт компьютеров.</span><span class="sxs-lookup"><span data-stu-id="1a17a-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="1a17a-123">Группа упаковки проверяет новые отправки каждый четверг.</span><span class="sxs-lookup"><span data-stu-id="1a17a-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="1a17a-124">После проверки и упаковки упакованные приложения будут доставлены в следующую пятницу.</span><span class="sxs-lookup"><span data-stu-id="1a17a-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="1a17a-125">Можно запустить до пяти приложений в неделю, но служба может масштабироваться в ваших потребностях.</span><span class="sxs-lookup"><span data-stu-id="1a17a-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![календарь, показывающий процесс приложения в четверг (21-е в этом примере), проверку мультимедиа на следующий день, упаковку в следующий понедельник (25-е) и доставку приложения в следующую пятницу (29-е)](../../media/MCS-cal.png)

<span data-ttu-id="1a17a-127">После доставки приложения вы получите уведомление.</span><span class="sxs-lookup"><span data-stu-id="1a17a-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="1a17a-128">На этом этапе у вас есть 21 день, чтобы выполнить приемочное тестирование и утвердить работу на портале microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1a17a-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="1a17a-129">Если во время приемки тестирования обнаружена какая-либо проблема с приложением, отклонить приложение на портале Microsoft Managed Desktop, и вы будете подключены по электронной почте с пакетом MCS, чтобы понять и устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="1a17a-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="1a17a-130">Тестирование учетных записей и среды</span><span class="sxs-lookup"><span data-stu-id="1a17a-130">Testing accounts and environment</span></span>

<span data-ttu-id="1a17a-131">Чтобы группа упаковки завершила миграцию на Microsoft Intune, мы рекомендуем предоставить определенные разрешения:</span><span class="sxs-lookup"><span data-stu-id="1a17a-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="1a17a-132">Доступ к возможностям развертывания приложений Microsoft Intune для добавления и назначения приложения упаковода</span><span class="sxs-lookup"><span data-stu-id="1a17a-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="1a17a-133">Тестовые группы, учетные записи пользователей и лицензии для упаковщиков, которые могут тестировать приложения</span><span class="sxs-lookup"><span data-stu-id="1a17a-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="1a17a-134">McS будет использовать эти разрешения для выполнения следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1a17a-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="1a17a-135">Обеспечение работы приложения на виртуальной машине, настроенной для компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1a17a-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="1a17a-136">Отправка приложения в Microsoft Intune для развертывания пользователям</span><span class="sxs-lookup"><span data-stu-id="1a17a-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="1a17a-137">Без этих разрешений MCS может двигаться вперед, но они не смогут загружать приложения в среду.</span><span class="sxs-lookup"><span data-stu-id="1a17a-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


