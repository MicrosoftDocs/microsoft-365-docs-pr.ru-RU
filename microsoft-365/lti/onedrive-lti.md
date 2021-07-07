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
ms.openlocfilehash: bcb374ed1666f23fa5f3d4692f43a4369670e891
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322225"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="274f9-103">Интеграция Microsoft OneDrive LTI с Canvas</span><span class="sxs-lookup"><span data-stu-id="274f9-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="274f9-104">Интеграция Microsoft OneDrive LTI с Canvas — это двухшаговая процедура.</span><span class="sxs-lookup"><span data-stu-id="274f9-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="274f9-105">Первый шаг включает Microsoft OneDrive Canvas, а второй шаг делает Microsoft OneDrive LTI доступным в курсах Canvas.</span><span class="sxs-lookup"><span data-stu-id="274f9-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="274f9-106">Рекомендуемые параметры браузера</span><span class="sxs-lookup"><span data-stu-id="274f9-106">Recommended browser settings</span></span>

- <span data-ttu-id="274f9-107">Файлы cookie должны быть включены для Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="274f9-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="274f9-108">Всплывающие окантовки не должны быть заблокированы для Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="274f9-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="274f9-109">Cookie-файлы не включены по умолчанию в режиме инкогнито браузера Chrome, и их необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="274f9-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="274f9-110">Microsoft OneDrive LTI работает в частном режиме в Microsoft Edge браузере.</span><span class="sxs-lookup"><span data-stu-id="274f9-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="274f9-111">Убедитесь, что вы не заблокировали файлы cookie (которые включены по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="274f9-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="274f9-112">Включить Microsoft OneDrive LTI в Canvas</span><span class="sxs-lookup"><span data-stu-id="274f9-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="274f9-113">Человек, который выполняет эту интеграцию, должен быть администратором Canvas и администратором Microsoft 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="274f9-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="274f9-114">Вход на <a href="https://onedrivelti.microsoft.com/admin" target="_blank">портал регистрации Microsoft OneDrive LTI</a></span><span class="sxs-lookup"><span data-stu-id="274f9-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="274f9-115">Выберите **кнопку Согласие администратора** и примите разрешения.</span><span class="sxs-lookup"><span data-stu-id="274f9-115">Select the **Admin Consent** button and accept the permissions.</span></span>

> [!CAUTION]
> <span data-ttu-id="274f9-116">Если этот шаг не выполнен, следующий шаг даст вам ошибку, и вы не сможете сделать этот шаг в течение часа после того, как вы получили ошибку.</span><span class="sxs-lookup"><span data-stu-id="274f9-116">If this step isn't performed, the following step will give you an error, and you won't be able to take this step for an hour once you've gotten the error.</span></span>

3. <span data-ttu-id="274f9-117">Выберите **кнопку Создание нового клиента LTI.**</span><span class="sxs-lookup"><span data-stu-id="274f9-117">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="274f9-118">На странице Регистрация LTI выберите **Canvas** в отсеве и введите базовый URL-адрес экземпляра Canvas.</span><span class="sxs-lookup"><span data-stu-id="274f9-118">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="274f9-119">Если экземпляр Canvas , https://contoso.test.instructure.com например, ]( (, то полный https://contoso.test.instructure.com) URL-адрес должен быть введен.</span><span class="sxs-lookup"><span data-stu-id="274f9-119">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Страница администрирования клиента LTI с полем для отсева для выбора потребительской платформы LTI и текстовым полем URL-адреса.":::

4. <span data-ttu-id="274f9-121">Скопируйте JSON, выбрав кнопку **Copy** (значок справа, который показывает две страницы поверх друг друга).</span><span class="sxs-lookup"><span data-stu-id="274f9-121">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="274f9-122">Это будет использоваться для создания ключа в Canvas.</span><span class="sxs-lookup"><span data-stu-id="274f9-122">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Изображение, на котором отображается кнопка копирования, которая скопирует отображаемого текста JSON и сделает его доступным для генерации ключей в Canvas.":::

5. <span data-ttu-id="274f9-124">Вопишите в экземпляр Canvas в качестве администратора и выберите **клавиши** разработчика из меню в левой части страницы.</span><span class="sxs-lookup"><span data-stu-id="274f9-124">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="274f9-125">В отсеве создайте ключ разработчика, выбрав **ключ LTI** из отсева справа верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="274f9-125">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Снимок экрана, на котором показана левая панели навигации с выбранными клавишами разработчика, и запись ключа LTI, выбранная из отсева справа от страницы.":::

6. <span data-ttu-id="274f9-127">На странице Настройка в отсеве **Метода** выберите в качестве метода вклейку JSON и вклеите текст **JSON,** скопированные в шаге 5 в текстовом поле, которое отображается.</span><span class="sxs-lookup"><span data-stu-id="274f9-127">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="274f9-128">Сохраните ключ, и он станет доступен в Canvas в **состоянии Off.**</span><span class="sxs-lookup"><span data-stu-id="274f9-128">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="274f9-129">Включи ключ **и** скопируйте ключ, заданный в столбце **Details,** который будет использоваться на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="274f9-129">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Страница Canvas с набором ключей в выключеном состоянии. Его необходимо будет включить, а ключ будет скопирован из столбца сведений на этой странице.":::

8. <span data-ttu-id="274f9-131">Вернись на Microsoft OneDrive портал регистрации LTI и вклей ключ в поле **Canvas Client ID.**</span><span class="sxs-lookup"><span data-stu-id="274f9-131">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="274f9-132">Выберите **Далее,** когда вы будете готовы.</span><span class="sxs-lookup"><span data-stu-id="274f9-132">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Страница регистрации клиента LTI, на которой показан текст JSON и текстовое поле, в которое должен быть скопирован ключ.":::

9. <span data-ttu-id="274f9-134">Просмотрите и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="274f9-134">Review and save your changes.</span></span> <span data-ttu-id="274f9-135">Сообщение будет отображаться при успешной регистрации.</span><span class="sxs-lookup"><span data-stu-id="274f9-135">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="274f9-136">Сведения о регистрации также можно просмотреть, выбрав кнопку **View LTI Tenants** на домашней странице.</span><span class="sxs-lookup"><span data-stu-id="274f9-136">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="274f9-137">Включить Microsoft OneDrive LTI в курсах Canvas</span><span class="sxs-lookup"><span data-stu-id="274f9-137">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="274f9-138">Администратор Canvas может включить Microsoft OneDrive LTI для всех курсов.</span><span class="sxs-lookup"><span data-stu-id="274f9-138">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="274f9-139">Если Microsoft OneDrive LTI необходим в определенном курсе (и не на всех курсах), преподавателю курса необходимо следовать тем же шагам в параметрах курса.</span><span class="sxs-lookup"><span data-stu-id="274f9-139">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="274f9-140">Войдите в качестве администратора и перейдите в **раздел Параметры.**</span><span class="sxs-lookup"><span data-stu-id="274f9-140">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="274f9-141">Перейдите в **раздел Приложения** и выберите кнопку **Настройка приложений** просмотра.</span><span class="sxs-lookup"><span data-stu-id="274f9-141">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="274f9-142">Выберите **кнопку Добавить приложение.**</span><span class="sxs-lookup"><span data-stu-id="274f9-142">Select the **Add App** button.</span></span>
4. <span data-ttu-id="274f9-143">В **отсеве типа** конфигурации выберите параметр **By Client ID.**</span><span class="sxs-lookup"><span data-stu-id="274f9-143">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="274f9-144">Вклеить значение ключа разработчика, сгенерированного ранее в поле **Client ID,** и выберите кнопку **Отправка.**</span><span class="sxs-lookup"><span data-stu-id="274f9-144">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Страница добавления приложения, показывающая параметр By client ID в меню выпадаемого типа конфигурации.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="274f9-146">Совместная Параметры для Microsoft OneDrive LTI в canvas Courses</span><span class="sxs-lookup"><span data-stu-id="274f9-146">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="274f9-147">Для совместной работы преподавателей и учащихся не следует включить параметр совместной работы.</span><span class="sxs-lookup"><span data-stu-id="274f9-147">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="274f9-148">Чтобы убедиться, что параметр не включен, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="274f9-148">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="274f9-149">Войдите в качестве администратора и перейдите в **раздел Параметры.**</span><span class="sxs-lookup"><span data-stu-id="274f9-149">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="274f9-150">Перейдите **в раздел Параметры** функций, а затем перейдите в раздел **Курс.**</span><span class="sxs-lookup"><span data-stu-id="274f9-150">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="274f9-151">Установите не **включенную функцию External Collaborations Tool.**</span><span class="sxs-lookup"><span data-stu-id="274f9-151">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="274f9-152">Совместная работа может быть назначена отдельным учащимся и группам учащихся.</span><span class="sxs-lookup"><span data-stu-id="274f9-152">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="274f9-153">Назначение отдельным учащимся работает по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="274f9-153">Assigning to individual students works by default.</span></span> <span data-ttu-id="274f9-154">Чтобы назначить совместную работу группе учащихся, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="274f9-154">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="274f9-155">Войдите в качестве администратора и перейдите в раздел **Ключи разработчика.**</span><span class="sxs-lookup"><span data-stu-id="274f9-155">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="274f9-156">Найдите ключ со значением 170000000000710 и установите его **на .**</span><span class="sxs-lookup"><span data-stu-id="274f9-156">Find the key with value 170000000000710 and set it to **On**.</span></span>
