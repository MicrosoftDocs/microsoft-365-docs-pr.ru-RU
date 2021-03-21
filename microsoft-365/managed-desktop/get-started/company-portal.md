---
title: Установка портала компании Intune на устройствах
description: Сведения об установке приложения портала компании на устройствах Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Портал компании
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925778"
---
# <a name="install-intune-company-portal-on-devices"></a>Установка портала компании Intune на устройствах

Microsoft Managed Desktop требует, чтобы ИТ-администраторы устанавливали портал компании Intune для своих пользователей на устройствах Microsoft Managed Desktop. Вот некоторые преимущества для организации:
- У пользователей есть одно место для просмотра и установки доступных приложений. 
- ИТ-администраторы могут организовывать приложения по категориям для своих пользователей.  
- Некоторые приложения (например, Microsoft Project и Microsoft Visio) требуют развертывания портала компании с помощью Microsoft Managed Desktop.
- ИТ-администраторы могут настраивать портал компании для своей организации. Это включает визуализацию бренда, добавление локальных контактов поддержки и другие. Дополнительные сведения см. [в сайте How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).   

В этом разделе документироваться процесс развертывания портала компании Intune для пользователей управляемых настольных компьютеров Майкрософт. Общий процесс выглядит так:
1. Покупка портала компании в Microsoft Store для бизнеса и синхронизация с Intune
2. Назначение портала компании пользователям
3. Сообщить пользователям об изменении

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Шаг 1 — Покупка портала компании в Microsoft Store для бизнеса и синхронизация с Intune
Сведения о том, как приобрести приложения и синхронизироваться с Intune, см. в [веб-сайте Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in Deploy apps to Microsoft Managed Desktop *devices.*

В этом разделе приводится информация о том, как: 
- Покупка портала компании в Microsoft Store для бизнеса 
- Синхронизация усилий между Intune и Microsoft Store для бизнеса
- Проверка активной синхронизации между Intune и Microsoft Store для бизнеса 

## <a name="step-2---assign-company-portal-to-your-users"></a>Шаг 2 . Назначение портала компании пользователям
После регистрации в Microsoft Managed Desktop Microsoft Managed Desktop Operations автоматически развертывает портал компании для клиента и установит приложение на устройствах Microsoft Managed Desktop в организации.

## <a name="step-3---communicate-change-to-your-users"></a>Шаг 3 . Изменение связи с пользователями
В качестве ИТ-администратора организации важно, чтобы пользователи знали, как использовать портал компании в организации. Microsoft Managed Desktop рекомендует:
- Действия по установке приложений с портала компании. Дополнительные сведения см. в [раздел Установка и совместное приложение на устройстве.](/intune-user-help/install-apps-cpapp-windows)
- Отправка запросов ИТ-администраторам для приложений, недоступных в настоящее время. Дополнительные сведения см. в [примере Request an app for work or school.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Действия по началу работы с управляемым рабочим столом Майкрософт

1. [Добавление и проверка контактов администратора на портале администрирования](add-admin-contacts.md)
2. [Настройка условного доступа](conditional-access.md)
3. [Назначение лицензий](assign-licenses.md)
4. Развертывание портала компании Intune (этот раздел)
5. [Включение службы Enterprise State Roaming](enterprise-state-roaming.md)
6. [Настройка устройств](set-up-devices.md)
7. [Подготовка пользователей к работе с устройствами](get-started-devices.md)
8. [Развертывание приложений](deploy-apps.md)