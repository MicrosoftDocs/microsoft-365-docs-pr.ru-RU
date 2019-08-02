---
title: Развертывание приложений для настольных устройств, управляемых Майкрософт
description: Сведения для добавления и развертывания приложений на настольных устройствах, управляемых корпорацией Майкрософт.
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e842849afbedd506689caa9ffc0953a58e18fed
ms.sourcegitcommit: f5c9aff5700f7824bf71f4a7e8c7236f7d91043e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2019
ms.locfileid: "36059589"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Развертывание приложений на настольных устройствах, управляемых Майкрософт
Часть входящей миграции на Настольный компьютер Майкрософт с управляемым подключением включает добавление и развертывание приложений на устройствах пользователя. Когда вы используете портал для настольных компьютеров Майкрософт, вы можете добавлять и развертывать свои приложения. 

Общий процесс выглядит следующим образом:
1. [Добавление приложений на портал для настольных ПК, управляемых корпорацией Майкрософт](#1) . Это могут быть существующие бизнес-приложения (LOB) или приложения из Microsoft Store для бизнеса, которые вы синхронизированы с Intune. 
2. [Создайте группы Azure Active Directory (AD) для назначения приложения](#2) , вы будете использовать эти группы для управления назначением приложения.
3. [Назначение приложений пользователям](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Шаг 1: Добавление приложений на управляемый портал для настольных ПК Майкрософт
Вы можете добавить [приложения Win32 или Windows MSI](#lob-apps)или [Microsoft Store для бизнес-приложений](#msfb-apps) на компьютер с управляемым учетом Microsoft Store, а затем развернуть их на настольных устройствах, управляемых Майкрософт.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Приложения Win32 или Windows MSI для настольного компьютера, управляемого Майкрософт

Вы можете добавить бизнес-приложения (LOB) на портал для настольных компьютеров, управляемый Майкрософт. Для получения сведений о требованиях к приложениям, установленным на настольных компьютерах, управляемых Майкрософт, ознакомьтесь с [требованиями к](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)приложениям, управляемым Майкрософт.

В этой процедуре показано, как выбрать тип приложения, которое вы хотите добавить, а затем настроить и отправить источник приложения. 

**Добавление бизнес-приложения или приложения Windows в управляемый портал для настольных ПК Майкрософт**

Вы можете войти на портал для настольных компьютеров Майкрософт или войти в Intune, а затем найти компьютер, управляемый Майкрософт. Мы покажем вход на портал для настольных компьютеров, управляемый Майкрософт. 

1.  Войдите на [портал администрирования рабочих столов](http://aka.ms/mmdportal)с управляемыми правами Майкрософт. 
2.  В разделе **запасы**выберите **приложения**.
3.  В рабочей нагрузке приложений нажмите кнопку **Добавить**.
4.  В окне **Добавление приложения**выберите **бизнес-приложение** или **приложение Windows (Win32)**.
    - Если вы выбрали **бизнес-приложение**, ознакомьтесь со статьей [Добавление бизнес-приложения Windows в Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) для получения инструкций по добавлению и настройке бизнес-приложений.
    - Если вы выбрали **Windows App (Win32)**, ознакомьтесь с инструкциями по добавлению и настройке приложений Windows в разделе [Управление приложениями Win32](https://docs.microsoft.com/intune/apps-win32-app-management) .

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Приложения Microsoft Store для бизнеса
Если вы не зарегистрированы в Microsoft Store для бизнеса, вы можете зарегистрироваться при работе с приложениями. После создания приложений вы можете синхронизировать их с настольными компьютерами Майкрософт. 

**Приобретение приложений из Microsoft Store для бизнеса**

1. Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса.
2. Выберите **магазин для группы**.
3. Используйте поиск, чтобы найти нужное приложение, и выберите приложение.
4. В разделе сведения о продукте выберите пункт **Получение приложения**. Microsoft Store добавляет приложение в **продукты & услуг** для вашей организации.

**Принудительная синхронизация между Intune и Microsoft Store для бизнеса**
1. Войдите на [портал Azure](https://portal.azure.com/) как администратор Intune или глобальный администратор для вашего клиента
2. Выберите **все службы > Intune**. Intune находится в разделе Мониторинг и управление.
3. В области Intune выберите клиентские **приложения**, а затем выберите **Microsoft Store для бизнеса**.
4. Выберите **включить** , чтобы синхронизировать приложения Microsoft Store для бизнеса с Intune.
    - Если вы еще не сделали это, выполните вход и связывание учетной записи Microsoft Store для бизнеса с Intune
    - Выберите язык, на котором будут отображаться приложения из Microsoft Store для бизнеса в консоли Intune
    - Выберите **синхронизировать** для синхронизации приложений Microsoft Store для бизнеса с Intune.
    - Убедитесь, что синхронизация между Microsoft Store для бизнеса и Intune активна (следующий шаг). 

**Проверка активности синхронизации между Intune и Microsoft Store для бизнеса**
1. Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью администратора Microsoft Store для бизнеса.
2. Выберите **Управление**.
3. Выберите **Параметры** и нажмите кнопку **распределить**.
4. В разделе **средства управления**убедитесь, что в списке присутствует служба Intune и состояние **активна**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Шаг 2: создание групп Azure AD

Создайте три группы Azure AD для каждого приложения. В этой таблице перечислены необходимые группы (доступные, обязательные и удаляемые). 

Тип назначения приложения |   Использование группы   | Пример имени Azure AD
--- | --- | ---
Available |  Приложение будет доступно из приложения или веб-сайта корпоративного портала. | ММД — *имя приложения* — доступно
Обязательный |  Приложение устанавливается на устройствах в выбранных группах. | ММД — *имя приложения* — обязательный
Uninstall |  Приложение пароль удаляется с устройств в выбранных группах. | ММД — *имя приложения* — удаление

Добавьте пользователей в эти группы, чтобы сделать приложение доступ, установить приложение или удалить приложение с компьютера, управляемого Майкрософт. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Шаг 3: назначение приложений пользователям

**Назначение приложения пользователям**

1. Войдите на [портал администрирования рабочих столов](http://aka.ms/mmdportal)с управляемыми правами Майкрософт.
2. В области управляемый Рабочий стол выберите пункт **приложения**.
3. В рабочей нагрузке приложений выберите приложение, которому вы хотите назначить пользователей, и выберите **назначить группы пользователей**.
4. Для конкретного приложения выберите тип назначения (доступное, необходимое, удалите) и назначьте соответствующую группу.
5. В области назначить приложения нажмите кнопку **ОК**.

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->
