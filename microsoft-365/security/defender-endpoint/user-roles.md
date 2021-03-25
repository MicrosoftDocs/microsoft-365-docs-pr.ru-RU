---
title: Создание ролей и управление ими для управления доступом на основе ролей
description: Создание ролей и определение разрешений, присвоенных роли в рамках реализации управления доступом на основе ролей в Центре безопасности Защитника Майкрософт
keywords: роли пользователей, роли, доступ к rbac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073989"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="968b7-104">Создание ролей и управление ими для управления доступом на основе ролей</span><span class="sxs-lookup"><span data-stu-id="968b7-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="968b7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="968b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="968b7-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="968b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="968b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="968b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="968b7-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="968b7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="968b7-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="968b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="968b7-110">Создание ролей и назначение роли группе Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="968b7-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="968b7-111">В следующих действиях вы можете узнать, как создавать роли в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="968b7-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="968b7-112">Предполагается, что вы уже создали группы пользователей Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="968b7-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="968b7-113">Войдите в [Центр безопасности Microsoft Defender с](https://securitycenter.windows.com/) помощью учетной записи с администратором безопасности или ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="968b7-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="968b7-114">В области навигации выберите **Параметры > ролей**.</span><span class="sxs-lookup"><span data-stu-id="968b7-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="968b7-115">Выберите **элемент Добавить**.</span><span class="sxs-lookup"><span data-stu-id="968b7-115">Select **Add item**.</span></span>

4. <span data-ttu-id="968b7-116">Введите имя роли, описание и разрешения, которые необходимо назначить роли.</span><span class="sxs-lookup"><span data-stu-id="968b7-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="968b7-117">Выберите **Далее,** чтобы назначить роль группе безопасности Azure AD.</span><span class="sxs-lookup"><span data-stu-id="968b7-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="968b7-118">Используйте фильтр, чтобы выбрать группу Azure AD, к которую необходимо добавить эту роль.</span><span class="sxs-lookup"><span data-stu-id="968b7-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="968b7-119">**Сохранить и закрыть**.</span><span class="sxs-lookup"><span data-stu-id="968b7-119">**Save and close**.</span></span>

8. <span data-ttu-id="968b7-120">Применить параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="968b7-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="968b7-121">После создания ролей необходимо создать группу устройств и предоставить доступ к группе устройств, назначив ее только что созданной роли.</span><span class="sxs-lookup"><span data-stu-id="968b7-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="968b7-122">Параметры разрешений</span><span class="sxs-lookup"><span data-stu-id="968b7-122">Permission options</span></span>

- <span data-ttu-id="968b7-123">**Просмотр данных**</span><span class="sxs-lookup"><span data-stu-id="968b7-123">**View data**</span></span>
    - <span data-ttu-id="968b7-124">**Операции безопасности** — просмотр всех данных операций безопасности на портале</span><span class="sxs-lookup"><span data-stu-id="968b7-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="968b7-125">**Управление угрозами и уязвимостью** — просмотр данных управления угрозами и уязвимостей на портале</span><span class="sxs-lookup"><span data-stu-id="968b7-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="968b7-126">**Активные действия по исправлению**</span><span class="sxs-lookup"><span data-stu-id="968b7-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="968b7-127">**Операции безопасности** . Принятие ответных действий, утверждение или отклонение в ожидании действий по исправлению, управление разрешенными и заблокированными списками для автоматизации и индикаторов</span><span class="sxs-lookup"><span data-stu-id="968b7-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="968b7-128">**Управление угрозами и уязвимостями — обработка исключений** — создание новых исключений и управление активными исключениями</span><span class="sxs-lookup"><span data-stu-id="968b7-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="968b7-129">**Управление угрозами** и уязвимостью — обработка исправлений — отправка новых запросов на исправление, создание билетов и управление существующими действиями по исправлению.</span><span class="sxs-lookup"><span data-stu-id="968b7-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="968b7-130">**Проверка** оповещений . Управление оповещениями, инициирование автоматических расследований, выполнение сканов, сбор пакетов расследований, управление тегами устройств и скачивание только переносных исполняемых (PE) файлов</span><span class="sxs-lookup"><span data-stu-id="968b7-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="968b7-131">**Управление настройками** системы портала — Настройка параметров хранения, параметров API siem и угроз intel (применяется глобально), расширенных параметров, автоматических загрузок файлов, ролей и групп устройств</span><span class="sxs-lookup"><span data-stu-id="968b7-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="968b7-132">Этот параметр доступен только в роли администратора конечной точки Microsoft Defender для конечной точки (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="968b7-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="968b7-133">**Управление настройками** безопасности в Центре безопасности — настройка параметров подавления оповещений, управление исключениями папок для автоматизации, устройств на борту и на борту, а также управление уведомлениями электронной почты, управление лабораторией оценки</span><span class="sxs-lookup"><span data-stu-id="968b7-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="968b7-134">**Возможности живого ответа**</span><span class="sxs-lookup"><span data-stu-id="968b7-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="968b7-135">**Основные** команды:</span><span class="sxs-lookup"><span data-stu-id="968b7-135">**Basic** commands:</span></span>
        - <span data-ttu-id="968b7-136">Запуск сеанса живого ответа</span><span class="sxs-lookup"><span data-stu-id="968b7-136">Start a live response session</span></span>
        - <span data-ttu-id="968b7-137">Выполните чтение только команд живого ответа на удаленном устройстве (за исключением копирования и выполнения файлов</span><span class="sxs-lookup"><span data-stu-id="968b7-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="968b7-138">**Расширенные** команды:</span><span class="sxs-lookup"><span data-stu-id="968b7-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="968b7-139">Скачивание файла с удаленного устройства с помощью живого ответа</span><span class="sxs-lookup"><span data-stu-id="968b7-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="968b7-140">Скачивание файлов PE и non-PE со страницы файла</span><span class="sxs-lookup"><span data-stu-id="968b7-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="968b7-141">Отправка файла на удаленное устройство</span><span class="sxs-lookup"><span data-stu-id="968b7-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="968b7-142">Просмотр сценария из библиотеки файлов</span><span class="sxs-lookup"><span data-stu-id="968b7-142">View a script from the files library</span></span>
        - <span data-ttu-id="968b7-143">Выполнение скрипта на удаленном устройстве из библиотеки файлов</span><span class="sxs-lookup"><span data-stu-id="968b7-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="968b7-144">Дополнительные сведения о доступных командах см. в сайте [Investigate devices using Live response.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="968b7-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="968b7-145">Изменение ролей</span><span class="sxs-lookup"><span data-stu-id="968b7-145">Edit roles</span></span>

1. <span data-ttu-id="968b7-146">Войдите в [Центр безопасности Microsoft Defender с](https://securitycenter.windows.com/) помощью учетной записи с администратором безопасности или ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="968b7-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="968b7-147">В области навигации выберите **Параметры > ролей**.</span><span class="sxs-lookup"><span data-stu-id="968b7-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="968b7-148">Выберите роль, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="968b7-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="968b7-149">Щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="968b7-149">Click **Edit**.</span></span>

5. <span data-ttu-id="968b7-150">Измените сведения или группы, которые назначены роли.</span><span class="sxs-lookup"><span data-stu-id="968b7-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="968b7-151">Нажмите **кнопку Сохранить и закрыть**.</span><span class="sxs-lookup"><span data-stu-id="968b7-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="968b7-152">Удаление ролей</span><span class="sxs-lookup"><span data-stu-id="968b7-152">Delete roles</span></span>

1. <span data-ttu-id="968b7-153">Войдите в [Центр безопасности Microsoft Defender с](https://securitycenter.windows.com/) помощью учетной записи с администратором безопасности или ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="968b7-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="968b7-154">В области навигации выберите **Параметры > ролей**.</span><span class="sxs-lookup"><span data-stu-id="968b7-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="968b7-155">Выберите роль, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="968b7-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="968b7-156">Нажмите кнопку drop-down и выберите **роль Удалить**.</span><span class="sxs-lookup"><span data-stu-id="968b7-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="968b7-157">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="968b7-157">Related topic</span></span>

- [<span data-ttu-id="968b7-158">Основные разрешения пользователей на доступ к порталу</span><span class="sxs-lookup"><span data-stu-id="968b7-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="968b7-159">Создание и управление группами устройств</span><span class="sxs-lookup"><span data-stu-id="968b7-159">Create and manage device groups</span></span>](machine-groups.md)
