---
title: Развертывание приложений на устройствах
description: Сведения о добавлении и развертывании приложений на устройствах Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922030"
---
# <a name="deploy-apps-to-devices"></a>Развертывание приложений на устройствах
Часть включенной в Microsoft Managed Desktop включает добавление и развертывание приложений на устройствах пользователя. После использования портала Microsoft Managed Desktop можно добавить и развернуть приложения. 

Общий процесс выглядит так:
1. [Добавьте приложения](#1) на портал Microsoft Managed Desktop . Это могут быть существующие приложения для бизнеса или приложения из Microsoft Store для бизнеса, которые вы синхронизировали с Intune. 
2. [Создайте группы Azure Active Directory (AD)](#2) для назначения приложений . Вы будете использовать эти группы для управления назначением приложений.
3. [Назначение приложений пользователям](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Шаг 1. Добавление приложений на портал Microsoft Managed Desktop
Вы можете добавить приложения на основе [Win32 или Windows MSI](#lob-apps)или [приложения Microsoft Store для](#msfb-apps) бизнеса в Microsoft Managed Desktop, а затем развернуть их на устройствах Microsoft Managed Desktop.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 или приложения на основе Windows MSI в Microsoft Managed Desktop

Вы можете добавить приложения для бизнеса (LOB) на портал Microsoft Managed Desktop. Сведения о требованиях к приложениям, установленным на устройствах Microsoft Managed Desktop, см. в приложении [Microsoft Managed Desktop.](../service-description/mmd-app-requirements.md)

В этой процедуре необходимо выбрать, какое приложение нужно добавить, а затем настроить и загрузить источник приложения. 

**Добавление приложения LOB или приложения Windows на портал Microsoft Managed Desktop**

Вы можете войти на портал Microsoft Managed Desktop или войти в Intune, а затем найти microsoft Managed Desktop. Мы покажем вход на портал Microsoft Managed Desktop. 

1.    Во входе на [портал Администрирование управляемых настольных компьютеров](https://aka.ms/mmdportal)Майкрософт . 
2.    В **рамках инвентаризации** выберите **Приложения**.
3.    В рабочей нагрузке Приложения выберите **Добавить**.
4.    В **добавлении** приложения выберите **приложение Line-of-business или** Приложение Для Windows **(Win32).**
    - Если вы выбрали **приложение Line-of-business,** см. в этой строке Добавление [бизнес-приложения Windows в Microsoft Intune](/intune/lob-apps-windows) для инструкции по добавлению и настройке бизнес-приложений.
    - Если вы выбрали **приложение Windows (Win32),** см. в инструкции по добавлению и настройке приложений Windows руководство приложениями [Win32.](/intune/apps-win32-app-management)

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Приложения Microsoft Store для бизнеса
Если вы еще не зарегистрировались в Microsoft Store для бизнеса, вы можете зарегистрироваться при покупке приложений. После того как у вас есть приложения, вы можете синхронизировать их с Microsoft Managed Desktop. 

**Покупка приложений в Microsoft Store для бизнеса**

1. Во входе [в Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью Microsoft Store for Business Admin.
2. Выберите **Магазин для моей группы**.
3. Используйте поиск, чтобы найти нужное приложение и выбрать приложение.
4. Сведения о продукте выберите **Get the App**. Microsoft Store добавляет приложение в **ваши продукты** для организации.

**Принудительное синхронизация между Intune и Microsoft Store для бизнеса**
1. Во входе в [центр администрирования microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Выберите **соединители**  >  **администрирования клиента и**  >  **маркеры Microsoft Store для бизнеса.**
3. Выберите **синхронизацию,** чтобы получить приложения, приобретенные в Microsoft Store, в Intune.

**Чтобы убедиться, что синхронизация между Intune и Microsoft Store для бизнеса активна**
1. Во входе [в Microsoft Store для бизнеса](https://businessstore.microsoft.com) с учетной записью Microsoft Store for Business Admin.
2. Выберите **Управление**.
3. Выберите **Параметры,** а затем выберите **Распределить**.
4. В **средствах управления** убедитесь, что Intune указан в списке и состояние **Active**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Шаг 2. Создание групп Azure AD

Создайте три группы Azure AD для каждого приложения. В этой таблице описаны необходимые группы (доступные, необходимые и удалить). 

Тип назначения приложения |    Групповое использование    | Пример имени Azure AD
--- | --- | ---
Available |  Приложение будет доступно в приложении или веб-сайте портала компании. | MMD — *имя приложения* — доступно
Обязательный |  Приложение устанавливается на устройства в выбранных группах. | MMD — *имя приложения* — обязательное
Uninstall |  Приложение неустановлено с устройств в выбранных группах. | MMD — *имя приложения* — Uninstall

Добавьте пользователей в эти группы, чтобы сделать приложение доступным, установить приложение или удалить его с устройства Microsoft Managed Desktop. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Шаг 3. Назначение приложений пользователям

**Назначение приложения пользователям**

1. Во входе на [портал Администрирование управляемых настольных компьютеров](https://aka.ms/mmdportal)Майкрософт .
2. В области Управляемый рабочий стол выберите **Приложения.**
3. В рабочей нагрузке Приложения выберите приложение, которое необходимо назначить пользователям, и выберите **Группы Назначения пользователей.**
4. Для конкретного приложения выберите тип назначения (Доступные, необходимые, удалить) и назначить соответствующую группу.
5. В области Назначение приложений выберите **ОК.**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Действия по началу работы с управляемым рабочим столом Майкрософт

1. [Добавление и проверка контактов администратора на портале администрирования](add-admin-contacts.md)
2. [Настройка условного доступа](conditional-access.md)
3. [Назначение лицензий](assign-licenses.md)
4. [Развертывание корпоративного портала Intune](company-portal.md)
5. [Включение службы Enterprise State Roaming](enterprise-state-roaming.md)
6. [Настройка устройств](set-up-devices.md)
7. [Подготовка пользователей к работе с устройствами](get-started-devices.md)
8. Развертывание приложений (этот раздел)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->