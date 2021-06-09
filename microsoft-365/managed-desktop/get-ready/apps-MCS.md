---
title: Работа с консультационными службами Майкрософт
description: Подготовка и последующие действия для работы с MCS для упаковки приложений
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 7a967f5e4b2678b55ed87f2eaa68590703c55805
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840890"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="33dd2-104">Работа с консультационными службами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="33dd2-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="33dd2-105">Вы можете взаимодействовать с службами microsoft Consulting Services (MCS), чтобы получить пакет приложений для использования с компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33dd2-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="33dd2-106">Чтобы получить точные сведения, обратитесь к представителю учетной записи, чтобы связаться с MCS и расширить область вашего конкретного проекта упаковки приложений.</span><span class="sxs-lookup"><span data-stu-id="33dd2-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="33dd2-107">Роли и обязанности.</span><span class="sxs-lookup"><span data-stu-id="33dd2-107">Roles and responsibilities</span></span>

<span data-ttu-id="33dd2-108">Чтобы работать с упаковкой приложений MCS, **необходимо предоставить эти элементы:**</span><span class="sxs-lookup"><span data-stu-id="33dd2-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="33dd2-109">Исходные файлы установщика (например, setup.exe или .msi).</span><span class="sxs-lookup"><span data-stu-id="33dd2-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="33dd2-110">Инструкции по установке с указанием сведений о том, как должна выглядеть окончательная установка.</span><span class="sxs-lookup"><span data-stu-id="33dd2-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="33dd2-111">Например, должен ли быть ярлык рабочего стола в приложении?</span><span class="sxs-lookup"><span data-stu-id="33dd2-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="33dd2-112">Какова должна быть видимость приложения?</span><span class="sxs-lookup"><span data-stu-id="33dd2-112">What should the app's visibility be?</span></span> <span data-ttu-id="33dd2-113">Должно ли приложение подключаться к серверу и если да, то какое?</span><span class="sxs-lookup"><span data-stu-id="33dd2-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="33dd2-114">Подробные сведения см. в [шаблоне запроса на упаковку приложений.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)</span><span class="sxs-lookup"><span data-stu-id="33dd2-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="33dd2-115">Необходимо выполнить собственное тестирование приемки, чтобы убедиться, что приложение работает так, как нужно в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="33dd2-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="33dd2-116">**McS будет заботиться о таких действиях:**</span><span class="sxs-lookup"><span data-stu-id="33dd2-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="33dd2-117">Проверка запрета или ограничения приложения в компьютеры, управляемые Майкрософт среде.</span><span class="sxs-lookup"><span data-stu-id="33dd2-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="33dd2-118">Тестирование установки, запуска и деинсталлации приложения для обеспечения совместимости с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="33dd2-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="33dd2-119">Если mcS обнаружит проблему совместимости, приложение будет отдано в программу [App Assure](/fasttrack/products-and-capabilities#app-assure) для устранения.</span><span class="sxs-lookup"><span data-stu-id="33dd2-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="33dd2-120">Упаковка приложения в спецификацию, а затем тестирование развертывания приложения с помощью Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="33dd2-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="33dd2-121">Расписание доставки приложений</span><span class="sxs-lookup"><span data-stu-id="33dd2-121">App delivery schedule</span></span>

<span data-ttu-id="33dd2-122">Начните процесс упаковки, загрузив сведения о приложении на компьютеры, управляемые Майкрософт портал.</span><span class="sxs-lookup"><span data-stu-id="33dd2-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="33dd2-123">Группа по упаковке рассматривает новые материалы каждый четверг.</span><span class="sxs-lookup"><span data-stu-id="33dd2-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="33dd2-124">После проверки и упаковки упакованные приложения будут доставлены в следующую пятницу.</span><span class="sxs-lookup"><span data-stu-id="33dd2-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="33dd2-125">До пяти приложений в неделю могут быть упакованы для запуска, но служба может масштабироваться для удовлетворения ваших потребностей.</span><span class="sxs-lookup"><span data-stu-id="33dd2-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![календарь, показывающий приток приложений в четверг (21-е место в этом примере), проверку мультимедиа на следующий день, упаковку в следующий понедельник (25-е) и доставку приложений в следующую пятницу (29-е)](../../media/MCS-cal.png)

<span data-ttu-id="33dd2-127">Вы будете уведомлены после доставки приложения.</span><span class="sxs-lookup"><span data-stu-id="33dd2-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="33dd2-128">На данный момент у вас есть 21 день для выполнения тестирования приемки и утверждения работы на компьютеры, управляемые Майкрософт портале.</span><span class="sxs-lookup"><span data-stu-id="33dd2-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="33dd2-129">Если во время тестирования на приеме обнаруживается какая-то проблема с приложением, отклонить его на портале компьютеры, управляемые Майкрософт, и вы будете подключены по электронной почте с пакетом MCS, чтобы понять и устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="33dd2-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="33dd2-130">Тестирование учетных записей и среды</span><span class="sxs-lookup"><span data-stu-id="33dd2-130">Testing accounts and environment</span></span>

<span data-ttu-id="33dd2-131">Чтобы группа упаковки завершила перенос Microsoft Intune, рекомендуем предоставить определенные разрешения:</span><span class="sxs-lookup"><span data-stu-id="33dd2-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>

- <span data-ttu-id="33dd2-132">Доступ Microsoft Intune к возможностям развертывания приложений для пакета, чтобы добавить и назначить приложение</span><span class="sxs-lookup"><span data-stu-id="33dd2-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span>
- <span data-ttu-id="33dd2-133">Тестовые группы, учетные записи пользователей и лицензии для упаковщиков, чтобы они могли протестировать приложения</span><span class="sxs-lookup"><span data-stu-id="33dd2-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="33dd2-134">McS будет использовать эти разрешения для выполнения следующих действий:</span><span class="sxs-lookup"><span data-stu-id="33dd2-134">MCS will use those permissions to perform the following actions:</span></span>

- <span data-ttu-id="33dd2-135">Обеспечение работы приложения на виртуальной машине, настроенной для компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="33dd2-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
- <span data-ttu-id="33dd2-136">Отправка приложения в Microsoft Intune для развертывания для пользователей</span><span class="sxs-lookup"><span data-stu-id="33dd2-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="33dd2-137">Без этих разрешений mcS может двигаться вперед, но они не смогут загружать приложения в среду.</span><span class="sxs-lookup"><span data-stu-id="33dd2-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
