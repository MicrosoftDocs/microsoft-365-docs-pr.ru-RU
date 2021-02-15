---
title: Развертывание приложений на устройствах
description: Сведения о добавлении и развертывании приложений на настольных устройствах, управляемых Майкрософт.
keywords: Microsoft Managed Desktop, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769110"
---
# <a name="deploy-apps-to-devices"></a>Развертывание приложений на устройствах
Частью подключения к компьютеру, управляемому Майкрософт, является добавление и развертывание приложений на устройствах пользователей. После использования портала microsoft Managed Desktop можно добавлять и развертывать приложения. 

Общий процесс выглядит так:
1. [Добавьте приложения](#1) на портал управляемых Майкрософт компьютеров. Это могут быть бизнес-приложения или приложения из Microsoft Store для бизнеса, которые вы синхронизировали с Intune. 
2. [Создайте группы Azure Active Directory (AD)](#2) для назначения приложений. Вы будете использовать эти группы для управления назначением приложения.
3. [Назначение приложений пользователям](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Шаг 1. Добавление приложений на портал microsoft Managed Desktop
Вы можете добавить [win32,](#lob-apps)приложения на основе Windows MSI или приложения [Microsoft Store](#msfb-apps) для бизнеса на компьютеры, управляемые Майкрософт, а затем развернуть их на настольных устройствах, управляемых Майкрософт.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Приложения на основе Win32 или Windows MSI для компьютеров, управляемых Майкрософт

Вы можете добавить бизнес-приложения на портал microsoft Managed Desktop. Сведения о требованиях к приложениям, установленным на управляемых Майкрософт настольных устройствах, см. в сведениях о требованиях к приложениям для управляемых компьютеров [Майкрософт.](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)

В этой процедуре вы выберете, какое приложение вы хотите добавить, а затем настроите и загрузите источник приложения. 

**Добавление приложения для LOB или Windows на портал microsoft Managed Desktop**

Вы можете войти на портал microsoft Managed Desktop portal или войти в Intune, а затем найти компьютер, управляемый Майкрософт. Мы покажем вход на портал microsoft Managed Desktop. 

1.    Во sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal). 
2.    Under **Inventory**, select **Apps**.
3.    В рабочей нагрузке приложений выберите **"Добавить".**
4.    В **приложении "Добавить"** **выберите бизнес-приложение** или **приложение для Windows (Win32).**
    - Если вы выбрали **бизнес-приложение,** см. инструкции по добавлению и настройке бизнес-приложений в [Microsoft Intune.](https://docs.microsoft.com/intune/lob-apps-windows)
    - Если вы выбрали приложение **для Windows (Win32),** инструкции по добавлению и настройке приложений для Windows см. в руководстве по управлению приложениями [Win32.](https://docs.microsoft.com/intune/apps-win32-app-management)

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Приложения Microsoft Store для бизнеса
Если вы еще не зарегистрировались в Microsoft Store для бизнеса, вы можете зарегистрироваться при покупке приложений. После того как у вас есть приложения, вы можете синхронизировать их с компьютерами, управляемыми Майкрософт. 

**Покупка приложений из Microsoft Store для бизнеса**

1. Во sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.
2. Выберите **"Магазин" для моей группы.**
3. Используйте поиск, чтобы найти нужное приложение, и выберите его.
4. В сведениях о продукте выберите **"Получить приложение".** Microsoft Store добавляет приложение в **ваши продукты** для вашей организации.

**Принудительное синхронизация Между Intune и Microsoft Store для бизнеса**
1. Во входе в [Центр администрирования Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Выберите **соединители**  >  **администрирования клиентов и маркеры**  >  **Microsoft Store для бизнеса.**
3. Выберите **"Синхронизация",** чтобы получить приложения, приобретенные в Microsoft Store, в Intune.

**Проверка активности синхронизации Между Intune и Microsoft Store для бизнеса**
1. Во sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.
2. Выберите **"Управление".**
3. Выберите **"Параметры",** а затем выберите **"Распространить".**
4. В **средстве управления** убедитесь, что Intune указан в списке и находится в **активном состоянии.**  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Шаг 2. Создание групп Azure AD

Создайте три группы Azure AD для каждого приложения. В этой таблице описаны необходимые вам группы (доступные, необходимые и удалить). 

Тип назначения приложения |    Использование групп    | Пример имени Azure AD
--- | --- | ---
Available |  Приложение будет доступно из приложения или веб-сайта портала компании. | MMD — *имя приложения —* доступно
Обязательна |  Приложение устанавливается на устройства в выбранных группах. | MMD — *имя приложения* — обязательно
Uninstall |  Приложение будет выгрузлено с устройств в выбранных группах. | MMD *— имя приложения* — удалить

Добавьте пользователей в эти группы, чтобы сделать приложение доступным, установить приложение или удалить его с компьютера, управляемого Майкрософт. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Шаг 3. Назначение приложений пользователям

**Назначение приложения пользователям**

1. Во sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).
2. В области "Управляемый рабочий стол" выберите **"Приложения".**
3. В рабочей нагрузке "Приложения" выберите приложение, для которое нужно назначить пользователей, и выберите **"Назначить группы пользователей".**
4. Для конкретного приложения выберите тип назначения (доступен, требуется, удалить) и назначьте соответствующую группу.
5. В области "Назначить приложения" выберите **"ОК".**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Действия по началу работы с компьютером, управляемым Майкрософт

1. [Добавление и проверка контактов администратора на портале администрирования](add-admin-contacts.md)
2. [Настройка условного доступа](conditional-access.md)
3. [Назначение лицензий](assign-licenses.md)
4. [Развертывание корпоративного портала Intune](company-portal.md)
5. [Включение службы Enterprise State Roaming](enterprise-state-roaming.md)
6. [Настройка устройств](set-up-devices.md)
7. [Подготовка пользователей к работе с устройствами](get-started-devices.md)
8. Развертывание приложений (в этом разделе)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
