---
title: Использование Microsoft OneDrive Обучение средства
ms.author: heidip
author: MicrosoftHeidi
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
description: Создание и оценка назначений, создание и куратор контента курсов и совместное взаимодействие с файлами в режиме реального времени с новым приложением Microsoft OneDrive Обучение средства взаимодействия.
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257072"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="d405c-103">Интеграция Microsoft OneDrive LTI с Canvas</span><span class="sxs-lookup"><span data-stu-id="d405c-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="d405c-104">Интеграция Microsoft OneDrive LTI с Canvas — это двухшаговая процедура.</span><span class="sxs-lookup"><span data-stu-id="d405c-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="d405c-105">Первый шаг включает Microsoft OneDrive Canvas, а второй шаг делает Microsoft OneDrive LTI доступным в курсах Canvas.</span><span class="sxs-lookup"><span data-stu-id="d405c-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="d405c-106">Рекомендуемые параметры браузера</span><span class="sxs-lookup"><span data-stu-id="d405c-106">Recommended browser settings</span></span>

- <span data-ttu-id="d405c-107">Файлы cookie должны быть включены для Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d405c-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="d405c-108">Всплывающие окантовки не должны быть заблокированы для Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d405c-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="d405c-109">Cookie-файлы не включены по умолчанию в режиме инкогнито браузера Chrome, и их необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="d405c-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="d405c-110">Microsoft OneDrive LTI работает в частном режиме в Microsoft Edge браузере.</span><span class="sxs-lookup"><span data-stu-id="d405c-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="d405c-111">Убедитесь, что вы не заблокировали файлы cookie (которые включены по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d405c-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="d405c-112">Включить Microsoft OneDrive LTI в Canvas</span><span class="sxs-lookup"><span data-stu-id="d405c-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d405c-113">Человек, который выполняет эту интеграцию, должен быть администратором Canvas и администратором Microsoft 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="d405c-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="d405c-114">Вход на <a href="https://onedrivelti.microsoft.com/admin" target="_blank">портал регистрации Microsoft OneDrive LTI</a></span><span class="sxs-lookup"><span data-stu-id="d405c-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="d405c-115">Выберите **кнопку Согласие администратора** и примите разрешения.</span><span class="sxs-lookup"><span data-stu-id="d405c-115">Select the **Admin Consent** button and accept the permissions.</span></span>
1. <span data-ttu-id="d405c-116">Выберите **кнопку Создание нового клиента LTI.**</span><span class="sxs-lookup"><span data-stu-id="d405c-116">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="d405c-117">На странице Регистрация LTI выберите **Canvas** в отсеве и введите базовый URL-адрес экземпляра Canvas.</span><span class="sxs-lookup"><span data-stu-id="d405c-117">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="d405c-118">Если экземпляр Canvas , https://contoso.test.instructure.com например, ]( (, то полный https://contoso.test.instructure.com) URL-адрес должен быть введен.</span><span class="sxs-lookup"><span data-stu-id="d405c-118">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Страница администрирования клиента LTI с полем для отсева для выбора потребительской платформы LTI и текстовым полем URL-адреса.":::

4. <span data-ttu-id="d405c-120">Скопируйте JSON, выбрав кнопку **Copy** (значок справа, который показывает две страницы поверх друг друга).</span><span class="sxs-lookup"><span data-stu-id="d405c-120">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="d405c-121">Это будет использоваться для создания ключа в Canvas.</span><span class="sxs-lookup"><span data-stu-id="d405c-121">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Изображение, на котором отображается кнопка копирования, которая скопирует отображаемого текста JSON и сделает его доступным для генерации ключей в Canvas.":::

5. <span data-ttu-id="d405c-123">Вопишите в экземпляр Canvas в качестве администратора и выберите **клавиши** разработчика из меню в левой части страницы.</span><span class="sxs-lookup"><span data-stu-id="d405c-123">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="d405c-124">В отсеве создайте ключ разработчика, выбрав **ключ LTI** из отсева справа верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d405c-124">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Снимок экрана, на котором показана левая панели навигации с выбранными клавишами разработчика, и запись ключа LTI, выбранная из отсева справа от страницы.":::

6. <span data-ttu-id="d405c-126">На странице Настройка в отсеве **Метода** выберите в качестве метода вклейку JSON и вклеите текст **JSON,** скопированные в шаге 5 в текстовом поле, которое отображается.</span><span class="sxs-lookup"><span data-stu-id="d405c-126">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="d405c-127">Сохраните ключ, и он станет доступен в Canvas в **состоянии Off.**</span><span class="sxs-lookup"><span data-stu-id="d405c-127">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="d405c-128">Включи ключ **и** скопируйте ключ, заданный в столбце **Details,** который будет использоваться на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="d405c-128">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Страница Canvas с набором ключей в выключеном состоянии. Его необходимо будет включить, а ключ будет скопирован из столбца сведений на этой странице.":::

8. <span data-ttu-id="d405c-130">Вернись на Microsoft OneDrive портал регистрации LTI и вклей ключ в поле **Canvas Client ID.**</span><span class="sxs-lookup"><span data-stu-id="d405c-130">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="d405c-131">Выберите **Далее,** когда вы будете готовы.</span><span class="sxs-lookup"><span data-stu-id="d405c-131">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Страница регистрации клиента LTI, на которой показан текст JSON и текстовое поле, в которое должен быть скопирован ключ.":::

9. <span data-ttu-id="d405c-133">Просмотрите и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="d405c-133">Review and save your changes.</span></span> <span data-ttu-id="d405c-134">Сообщение будет отображаться при успешной регистрации.</span><span class="sxs-lookup"><span data-stu-id="d405c-134">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="d405c-135">Сведения о регистрации также можно просмотреть, выбрав кнопку **View LTI Tenants** на домашней странице.</span><span class="sxs-lookup"><span data-stu-id="d405c-135">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="d405c-136">Включить Microsoft OneDrive LTI в курсах Canvas</span><span class="sxs-lookup"><span data-stu-id="d405c-136">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="d405c-137">Администратор Canvas может включить Microsoft OneDrive LTI для всех курсов.</span><span class="sxs-lookup"><span data-stu-id="d405c-137">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="d405c-138">Если Microsoft OneDrive LTI необходим в определенном курсе (и не на всех курсах), преподавателю курса необходимо следовать тем же шагам в параметрах курса.</span><span class="sxs-lookup"><span data-stu-id="d405c-138">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="d405c-139">Войдите в качестве администратора и перейдите в **раздел Параметры.**</span><span class="sxs-lookup"><span data-stu-id="d405c-139">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="d405c-140">Перейдите в **раздел Приложения** и выберите кнопку **Настройка приложений** просмотра.</span><span class="sxs-lookup"><span data-stu-id="d405c-140">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="d405c-141">Выберите **кнопку Добавить приложение.**</span><span class="sxs-lookup"><span data-stu-id="d405c-141">Select the **Add App** button.</span></span>
4. <span data-ttu-id="d405c-142">В **отсеве типа** конфигурации выберите параметр **By Client ID.**</span><span class="sxs-lookup"><span data-stu-id="d405c-142">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="d405c-143">Вклеить значение ключа разработчика, сгенерированного ранее в поле **Client ID,** и выберите кнопку **Отправка.**</span><span class="sxs-lookup"><span data-stu-id="d405c-143">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Страница добавления приложения, показывающая параметр By client ID в меню выпадаемого типа конфигурации.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="d405c-145">Совместная Параметры для Microsoft OneDrive LTI в canvas Courses</span><span class="sxs-lookup"><span data-stu-id="d405c-145">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="d405c-146">Для совместной работы преподавателей и учащихся не следует включить параметр совместной работы.</span><span class="sxs-lookup"><span data-stu-id="d405c-146">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="d405c-147">Чтобы убедиться, что параметр не включен, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d405c-147">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="d405c-148">Войдите в качестве администратора и перейдите в **раздел Параметры.**</span><span class="sxs-lookup"><span data-stu-id="d405c-148">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="d405c-149">Перейдите **в раздел Параметры** функций, а затем перейдите в раздел **Курс.**</span><span class="sxs-lookup"><span data-stu-id="d405c-149">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="d405c-150">Установите не **включенную функцию External Collaborations Tool.**</span><span class="sxs-lookup"><span data-stu-id="d405c-150">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="d405c-151">Совместная работа может быть назначена отдельным учащимся и группам учащихся.</span><span class="sxs-lookup"><span data-stu-id="d405c-151">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="d405c-152">Назначение отдельным учащимся работает по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d405c-152">Assigning to individual students works by default.</span></span> <span data-ttu-id="d405c-153">Чтобы назначить совместную работу группе учащихся, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d405c-153">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="d405c-154">Войдите в качестве администратора и перейдите в раздел **Ключи разработчика.**</span><span class="sxs-lookup"><span data-stu-id="d405c-154">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="d405c-155">Найдите ключ со значением 170000000000710 и установите его **на .**</span><span class="sxs-lookup"><span data-stu-id="d405c-155">Find the key with value 170000000000710 and set it to **On**.</span></span>
