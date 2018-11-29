---
title: Автоматическая установка и удаление Office на устройствах с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Установка и удаление Office на устройствах Windows 10 из центра администрирования Microsoft 365 для бизнеса. '
ms.openlocfilehash: 997c001ed1520f1ac989255632d36f9b7bedd16c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870867"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="b0f63-103">Автоматическая установка и удаление Office на устройствах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="b0f63-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="b0f63-104">Из центра администрирования Office 365 бизнес вы можете легко и быстро установить Office на компьютерах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b0f63-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="b0f63-105">Прежде чем начать, прочитайте статью [Подготовка к установке Office для клиентов](prepare-for-office-client-deployment.md), чтобы понять, как это работает с ранее установленными приложениями Office.</span><span class="sxs-lookup"><span data-stu-id="b0f63-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="b0f63-106">Управление развертываниями Office</span><span class="sxs-lookup"><span data-stu-id="b0f63-106">Manage Office deployments</span></span>

1. <span data-ttu-id="b0f63-107">Войдите в [центр администрирования](https://aka.ms/bcsportal) с учетными данными глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="b0f63-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="b0f63-p101">В карточке **устройств** выберите команду **Управление развертывания Office**.    Если карточке **действия устройства** не отображаются на **домашней** странице центра администрирования нажмите кнопку **Add** (+) для добавления к домашней администрирования.</span><span class="sxs-lookup"><span data-stu-id="b0f63-p101">On the **Devices** card, choose **Manage Office Deployment**.    If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="b0f63-111">На панели **Управление развертыванием Office** нажмите кнопку **Добавить группу** и выберите группы, которые хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="b0f63-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="b0f63-112">Выбрав группу или группы, в раскрывающемся списке **Действие развертывания** выберите одно из действий: **Установить Office как можно быстрее** или **Удалить Office**.</span><span class="sxs-lookup"><span data-stu-id="b0f63-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="b0f63-114">Нажмите кнопку **Далее** \> просмотрите параметры и затем выберите **Подтверждение**.</span><span class="sxs-lookup"><span data-stu-id="b0f63-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="b0f63-115">32-разрядная версия Office будет автоматически установлена на устройствах пользователей, входящих в указанные вами группы, или удалена с них.</span><span class="sxs-lookup"><span data-stu-id="b0f63-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="b0f63-116">Для проверки откройте диспетчер задач на компьютере, выбранном для установки Office, и найдите процесс "Microsoft Office нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="b0f63-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


