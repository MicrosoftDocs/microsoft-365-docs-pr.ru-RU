---
title: Изменение или Настройка параметров защиты приложений для устройств с Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Узнайте, как создавать и редактировать политики управления приложениями и защищать рабочие файлы на устройствах с Windows 10 для пользователей.
ms.openlocfilehash: f85a59649e43c141b62091337b842a490d411833
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289206"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="b01df-103">Установка и редактирование параметров защиты приложений для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="b01df-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="b01df-104">Эта статья относится к Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b01df-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="b01df-105">Изменение политики управления приложениями для Windows 10</span><span class="sxs-lookup"><span data-stu-id="b01df-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="b01df-106">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b01df-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="b01df-107">В левой панели навигации выберите пункт **Devices** \> **политики** устройств.</span><span class="sxs-lookup"><span data-stu-id="b01df-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="b01df-108">Выберите существующую политику приложений Windows и нажмите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="b01df-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="b01df-109">Нажмите кнопку **изменить** рядом с параметром, который нужно изменить, а затем **Сохраните**.</span><span class="sxs-lookup"><span data-stu-id="b01df-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="b01df-110">Создание политики управления приложениями для Windows 10</span><span class="sxs-lookup"><span data-stu-id="b01df-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="b01df-111">Если у ваших пользователей есть личные устройства с Windows 10, используемые для выполнения рабочих задач, на этих устройствах также можно настроить защиту данных компании.</span><span class="sxs-lookup"><span data-stu-id="b01df-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="b01df-112">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b01df-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="b01df-113">В левой панели навигации выберите пункт **Devices** \> **политики** устройств \> **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b01df-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="b01df-114">На панели **Добавить политику** введите уникальное имя политики.</span><span class="sxs-lookup"><span data-stu-id="b01df-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="b01df-115">В поле **Тип политики** выберите **Управление приложениями для Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="b01df-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="b01df-116">В разделе **тип устройства**выберите **персональный** или **принадлежащий компании**.</span><span class="sxs-lookup"><span data-stu-id="b01df-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="b01df-117">Параметр **Шифровать рабочие файлы** включается автоматически.</span><span class="sxs-lookup"><span data-stu-id="b01df-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="b01df-118">Если вы не хотите, чтобы пользователи сохраняли рабочие файлы на компьютере, **включите** параметр **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b01df-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="b01df-119">Разверните узел **Восстановление данных на устройствах с Windows**.</span><span class="sxs-lookup"><span data-stu-id="b01df-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="b01df-120">Рекомендуем **включить его.**</span><span class="sxs-lookup"><span data-stu-id="b01df-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="b01df-121">Прежде чем переходить к расположению сертификата агента восстановления данных, необходимо сначала создать его.</span><span class="sxs-lookup"><span data-stu-id="b01df-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="b01df-122">Инструкции приведены в разделе [Создание и проверка сертификата агента восстановления шифрованной файловой системы (DRA](https://go.microsoft.com/fwlink/p/?linkid=853700)).</span><span class="sxs-lookup"><span data-stu-id="b01df-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="b01df-123">По умолчанию рабочие файлы шифруются с помощью секретного ключа, хранящегося на устройстве и связанного с профилем пользователя.</span><span class="sxs-lookup"><span data-stu-id="b01df-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="b01df-124">Открыть и расшифровать файл может только пользователь.</span><span class="sxs-lookup"><span data-stu-id="b01df-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="b01df-125">Однако в случае потери устройства или удаления пользователя файл может остаться в зашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="b01df-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="b01df-126">Администратор может использовать сертификат агента восстановления данных (DRA) для расшифровки файла.</span><span class="sxs-lookup"><span data-stu-id="b01df-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="b01df-128">Разверните раздел **Защита дополнительных сетевых и облачных расположений** , если вы хотите добавить дополнительные домены или расположения SharePoint Online, чтобы обеспечить защиту файлов во всех перечисленных приложениях.</span><span class="sxs-lookup"><span data-stu-id="b01df-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="b01df-129">Если в каком-либо поле вам нужно ввести несколько элементов, разделяйте их точкой с запятой (;).</span><span class="sxs-lookup"><span data-stu-id="b01df-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="b01df-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="b01df-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="b01df-133">Нажмите кнопку **Добавить**, чтобы сохранить политику и назначить ее устройствам.</span><span class="sxs-lookup"><span data-stu-id="b01df-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
