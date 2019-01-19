---
title: Развертывание приложений для Microsoft Desktop управляемых устройств
description: Сведения по добавлению и развертывание приложений Microsoft Desktop управляемых устройств.
keywords: Microsoft Desktop управляемых, 365 Майкрософт, службы, документации, приложения, бизнес-приложений, бизнес-приложений
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341618"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Развертывание приложений для Microsoft Desktop управляемых устройств
Часть адаптация новых сотрудников к рабочему столу управляемых Microsoft включает добавление и развертывание приложений для устройства конечных пользователей. Если вы используете портал Microsoft Desktop управляемых, можно добавить и развертывание приложений. 

Весь процесс выглядит следующим образом:
1. [Установка приложений на портале Microsoft Desktop управляемых](#1) - это может существующих приложений бизнес (LOB) или приложений из хранилища Майкрософт для бизнеса, синхронизирован с Intune. 
2. [Создание Azure Active Directory (AD) группы для назначения приложения](#2) — эти группы будет использовать для управления назначения приложения.
3. [Назначение приложений для пользователей](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Шаг 1: Добавление приложений Microsoft Desktop управляемых портала
Добавление [Win32, приложений на основе Windows MSI](#lob-apps)или [Microsoft хранилища для бизнес-приложений](#msfb-apps) Microsoft Desktop управляемых и разверните их Microsoft Desktop управляемых устройств.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 или Windows приложений на основе MSI, в корпорацию Майкрософт управляемого рабочего стола

Портал Microsoft Desktop управляемых можно добавить ваших приложений бизнес (LOB). Сведения о требованиях для установки на устройствах Microsoft Desktop управляемых приложений в разделе [requirements приложения Microsoft Desktop управляемых](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

В этой процедуре будет предложено выбрать тип приложения, необходимо добавить и настройка и отправка исходного приложения. 

**Чтобы добавить БИЗНЕС-приложение или приложение Windows на портале Microsoft Desktop управляемых**

Можно вход на портал Microsoft Desktop управляемых или вход на портал Intune и затем найдите рабочий стол управляемых Microsoft. Вы увидите вход в портал Microsoft управляемых Desktop. 

1.  Войдите в [портал Microsoft управляемого рабочего стола администратора](http://aka.ms/mmdportal). 
2.  В разделе **запасов**выберите **приложения**.
3.  В рабочую нагрузку приложения затем выберите **Добавить**.
4.  В **приложении добавить**выберите **бизнес - приложение** или **приложение Windows (Win32) - предварительного просмотра**.
    - Если вы выбрали **бизнес - приложения**, в разделе [Add бизнес - приложения Windows Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) инструкции по добавлению и настройке бизнес-приложений.
    - Если выбран **Предварительный просмотр приложения Windows (Win32) -** видеть [управления приложениями Win32](https://docs.microsoft.com/intune/apps-win32-app-management) инструкции по добавлению и настройке приложения для Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Хранилище Microsoft для бизнес-приложений
Если вы еще не зарегистрированы хранилища Майкрософт для бизнеса, вы можете воспользоваться при покупке приложений. После того как ваших приложений можно синхронизировать их на рабочий стол управляемых Microsoft. 

**Покупки приложения из магазина корпорации Майкрософт для бизнеса**

1. Войдите в [Microsoft хранилища для бизнеса](https://businessstore.microsoft.com) с хранилищем Microsoft для учетной записи администратора предприятия.
2. Выберите **Поиск моей группы**.
3. Поиск, приложения, который будет и выберите приложение.
4. На сведения о продукте выберите **получить приложение**. Хранилище Microsoft добавляет приложение **службы & продуктов** для вашей организации.

**Для принудительной синхронизации между Intune и хранилища Майкрософт для бизнеса**
1. Войдите в [Портал Azure](https://portal.azure.com/) как глобальный администратор или администратор Intune для клиента
2. Выберите **все службы > Intune**. Intune возможности мониторинга + управления раздела.
3. В области Intune выберите **Клиентских приложений**и выберите **Microsoft хранилища для бизнеса**.
4. Установите флажок **Включить** синхронизацию хранилища Майкрософт для бизнес-приложений с помощью Intune.
    - Если это еще не сделано, sign up и свяжите Microsoft хранения для учетной записи бизнеса с Intune
    - Выберите язык отображения приложений в магазине Майкрософт для бизнеса в консоль Intune
    - Выберите **синхронизации** для синхронизации хранилища Майкрософт для бизнес-приложений с помощью Intune.
    - Убедитесь, что синхронизация между хранилища Майкрософт для бизнеса и Intune является активной (Далее). 

**Проверка синхронизации между Intune и хранилища Майкрософт для бизнеса**
1. Войдите в [Microsoft хранилища для бизнеса](https://businessstore.microsoft.com) с хранилищем Microsoft для учетной записи администратора предприятия.
2. Выберите **Управление**.
3. Выберите **Параметры** , а затем выберите **распределить**.
4. В разделе **средства управления**убедитесь, что указано Intune и что состояние является **активным**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Шаг 2: Создание группы Azure AD

Создайте три группы Azure AD для каждого приложения. В этой таблице перечислены группы, вам потребуются (доступен, необходимо и удалить). 

Тип назначения приложения |   Использование группы   | Имя примера Azure AD
--- | --- | ---
Доступно |  Приложение будет доступно из приложения портала компании или веб-сайта. | MMD — *имя приложения* — доступен
Обязательный |  Приложение устанавливается на устройствах в выбранных групп. | MMD — *имя приложения* — требуется
"Удалить", |  Установлено приложение удаляется из устройств в выбранных групп. | MMD — *имя приложения* — удаление

Добавьте пользователей в эти группы сделать доступных приложений, установка приложения или удалить приложения из свои устройства Microsoft управляемых Desktop. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Шаг 3: Назначение приложений для пользователей

**Чтобы назначить приложение для пользователей**

1. Войдите в [портал Microsoft управляемого рабочего стола администратора](http://aka.ms/mmdportal).
2. В области управляемого рабочего стола выберите **приложения**.
3. В рабочую нагрузку приложения выберите приложения, которые необходимо назначить пользователям и выберите пункт **назначить группы пользователей**.
4. Для конкретного приложения выберите тип назначения (доступен, необходимости удаления) и назначьте соответствующие группы.
5. В области Назначение приложения нажмите **кнопку OK**.

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