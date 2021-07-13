---
title: Доступ к локальному ресурсу с устройства Azure AD в Microsoft 365 Бизнес
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Узнайте, как получить доступ к локальному ресурсу, например к линейке бизнес-приложений, файлам и принтерам с Azure Active Directory с Windows 10 устройства.
ms.openlocfilehash: 71d60e0187c917dffb7390afcedf22dc73f44008
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393466"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Доступ к локальному ресурсу с устройства Azure AD в Microsoft 365 бизнес премиум

Эта статья применима к Microsoft 365 бизнес премиум.

Любое Windows 10, которое Azure Active Directory, имеет доступ ко всем облачным ресурсам, например Microsoft 365 приложениям, и может быть защищено Microsoft 365 бизнес премиум. Вы также можете разрешить доступ к локальному ресурсу, например к приложениям бизнес-сети, файлам и принтерам. Чтобы разрешить доступ, используйте [azure AD Подключение](/azure/active-directory/connect/active-directory-aadconnect) для синхронизации локального Active Directory с Azure Active Directory.

Дополнительные дополнительные информации см. в обзоре Введение в [управление устройствами в Azure Active Directory.](/azure/active-directory/device-management-introduction)
Действия также суммируются в следующих разделах.

## <a name="run-azure-ad-connect"></a>Запуск Azure AD Подключение

Выполните следующие действия, чтобы включить присоединенные к вашей организации устройства Azure AD для доступа к локальному ресурсу.

1. Чтобы синхронизировать пользователей, групп и контактов из локального Active Directory в Azure Active Directory, запустите мастер синхронизации каталогов и Azure AD Подключение, как описано в настройках синхронизации каталогов для [Office 365](../enterprise/set-up-directory-synchronization.md).

2. После завершения синхронизации каталогов убедитесь, что Windows 10 устройств Azure AD. Этот шаг делается индивидуально на каждом Windows 10 устройстве. Сведения [см. в Windows устройств для Microsoft 365 бизнес премиум пользователей.](set-up-windows-devices.md)

3. После Windows 10 устройств Azure AD каждый пользователь должен перезагрудить свои устройства и войти с Microsoft 365 бизнес премиум учетными данными. Теперь все устройства также имеют доступ к локальному ресурсу.

Для получения доступа к локальному ресурсу для присоединенных устройств Azure AD не требуется дополнительных действий. Эта функциональность встроена в Windows 10.

Если у вас есть планы входа на устройство AADJ, кроме метода пароля, например PIN-код/bio-metric с помощью входа учетных данных WHFB, а затем доступ к локальному ресурсу (акции, принтеры и т.д.), следуйте этой статье [.](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)

Если организация не готова к развертыванию в описанной выше конфигурации устройств Azure AD, рассмотрите возможность настройки конфигурации устройств [Hybrid Azure AD Joined.](manage-windows-devices.md)

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Соображения при вступив Windows устройств в Azure AD

Если устройство Windows, к которое вы присоединились Azure-AD, ранее было соединено с доменом или в группе, рассмотрите следующие ограничения:

- Когда устройство Azure AD присоединяется, оно создает нового пользователя, не ссылаясь на существующий профиль. Профили необходимо перенести вручную. Профиль пользователя содержит сведения, такие как избранное, локальные файлы, параметры браузера и меню параметров. Оптимальный подход — найти сторонний инструмент для совмещая существующие файлы и параметры с новым профилем.

- Если устройство использует объекты групповой политики (GPO), некоторые [](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) GPOs могут не иметь сопоставимого поставщика служб конфигурации (CSP) в Intune. Запустите [средство MMAT,](https://www.microsoft.com/download/details.aspx?id=45520) чтобы найти сопоставимые CSP для существующих GPOs.

- Возможно, пользователи не смогут проверить подлинность приложений, которые зависят от проверки подлинности Active Directory. Оцените устаревшее приложение и по возможности обновим приложение, использующее современный auth.

- Обнаружение принтера Active Directory не будет работать. Вы можете предоставить прямой путь принтера для всех пользователей или использовать [универсальный шрифт](/universal-print/).

### <a name="related-articles"></a>Связанные статьи

[Необходимые условия для azure AD Подключение](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
