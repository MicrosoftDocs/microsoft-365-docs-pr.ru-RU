---
title: Включение присоединенный к домену устройств Windows 10 для управления Microsoft 365 для бизнеса
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Узнайте, как включить 365 Майкрософт для защиты локального AD в состав Windows 10 устройств.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870588"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="04ac1-103">Включение присоединенный к домену устройств Windows 10 для управления Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="04ac1-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="04ac1-p101">Если организация использует Windows Server Active Directory в локальной, Microsoft 365 Business можно настроить для защиты устройство Windows 10, при этом обеспечивают доступ к локальным ресурсам, которые требуют проверки подлинности на локальном. Это можно настроить путем синхронизации Active Directory с Azure Active Directory, следуют регистрации устройств Windows 10 Azure AD и подача заявок на их для управления мобильного устройства с Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="04ac1-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="04ac1-106">Настройка устройств, присоединенный к домену для управления Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="04ac1-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="04ac1-p102">Для настройки устройств присоединенный к домену организации, чтобы использовать возможности, предоставляемые Azure Active Directory в дополнение к локальной службы Active Directory, можно реализовать **гибридного Azure AD в состав устройств**. Это устройства, входящих в состав к Active Directory в локальной и Azure Active Directory. Гибридные Azure AD в состав устройств можно защищенного и управлять посредством 365 Microsoft Business...</span><span class="sxs-lookup"><span data-stu-id="04ac1-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="04ac1-110">Выполните следующие действия, чтобы сделать устройство Windows 10 гибридного Azure AD в состав и управлять посредством Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="04ac1-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="04ac1-111">Для синхронизации пользователей, групп и контактов из локального Active Directory в Azure Active Directory, запустите мастер синхронизации каталогов и Azure Active Directory подключение как описано в [Настройка синхронизации службы каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="04ac1-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="04ac1-112">Действия полностью совпадают для Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="04ac1-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="04ac1-113">Прежде чем завершить шаг 3, чтобы включить устройств Windows 10 для гибридных присоединился к Azure AD, необходимо убедитесь в том, что выполняются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="04ac1-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="04ac1-114">Последние версии Azure AD подключения.</span><span class="sxs-lookup"><span data-stu-id="04ac1-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="04ac1-p103">Подключение Azure AD синхронизировано все объекты-компьютеры устройств, которые необходимо объединить гибридного присоединился к Azure AD. Если объекты-компьютеры принадлежат определенного подразделения (OU), а затем убедитесь, что эти подразделения устанавливаются в Azure AD для синхронизации подключение также.</span><span class="sxs-lookup"><span data-stu-id="04ac1-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="04ac1-117">Регистрация существующего устройства присоединенный к домену Windows 10 гибридного Соединяемая Azure AD и назначить им для управления мобильного устройства с Intune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="04ac1-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="04ac1-p104">Следуйте инструкциям Пошаговое руководство по [настройке гибридного Azure Active Directory в состав устройств](https://go.microsoft.com/fwlink/p/?linkid=872870). Это позволит синхронизации Active Directory локальной в состав Windows 10 компьютеров и их в облаке Готово.</span><span class="sxs-lookup"><span data-stu-id="04ac1-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="04ac1-p105">Чтобы зарегистрировать устройства Windows 10 для управление мобильными устройствами, в разделе [Регистрация устройства Windows 10 Intune, с помощью групповой политики](https://go.microsoft.com/fwlink/p/?linkid=872871) для получения инструкций. Для настройки групповой политики на локальном компьютере уровня или для каждой массовой операции можно создать этот параметр групповой политики на сервере контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="04ac1-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

