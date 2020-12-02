---
title: Настройка параметров после регистрации
description: Как исключить некоторые учетные записи Майкрософт
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527701"
---
# <a name="adjust-settings-after-enrollment"></a>Настройка параметров после регистрации

После того как вы закончите регистрацию на рабочем столе Майкрософт, необходимо настроить некоторые параметры Microsoft Intune и Azure Active Directory (Azure AD), чтобы разрешить управление и обеспечить безопасность. Задайте следующие параметры, чтобы исключить группы Azure AD, которые содержат устройства и пользователей, управляемые корпорацией Майкрософт. Действия по исключению групп см в разделе [Условный доступ: пользователи и группы](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

## <a name="microsoft-intune-settings"></a>Параметры Microsoft Intune

- Профиль развертывания для автопилота: исключите **современные устройства "современные рабочие места" — все**  группы Azure AD. Для получения инструкций обратитесь к разделу [Регистрация устройств Windows в Intune с помощью Windows автопилота](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).
- Политики условного доступа: исключите группу Azure AD **служебных учетных записей современного рабочего места** . Для получения инструкций обратитесь [к разделу условный доступ: пользователи и группы](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).
- Многофакторная проверка подлинности: Убедитесь, что все политики условного доступа, требующие многофакторной проверки подлинности, исключают группу Azure AD **учетных записей служб современного рабочего** Дополнительные сведения см. в статье [политики условного доступа](../get-ready/readiness-assessment-fix.md#conditional-access-policies) и [Условный доступ: требовать MFA для всех пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Базовый план безопасности: исключите **устройства современного рабочего места — все**  группы Azure AD. В разделе [Использование базовых показателей безопасности для настройки устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).
- Windows 10 Update Ring: исключите **устройства современного рабочего места — все**  группы Azure AD. Дополнительные сведения: [Управление обновлениями программного обеспечения Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).


## <a name="azure-active-directory-settings"></a>Параметры Azure Active Directory

Самостоятельный сброс пароля: выберите параметр **выбрано** , а затем выберите " **современные устройства" — все** группы Azure AD. Дополнительные сведения см. [в разделе Tutorial: разрешить пользователям разблокировать свою учетную запись или сбросить пароли с помощью функции самообслуживания Azure Active Directory для самостоятельного сброса пароля](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Действия для начала работы с управляемым рабочим столом Майкрософт

1. [Добавление и проверка контактов администратора на портале администрирования](add-admin-contacts.md)
2. Настройка параметров после регистрации (Эта статья)
3. [Назначение лицензий](assign-licenses.md)
4. [Развертывание корпоративного портала Intune](company-portal.md)
5. [Включение службы Enterprise State Roaming](enterprise-state-roaming.md)
6. [Настройка устройств](set-up-devices.md)
7. [Подготовка пользователей к работе с устройствами](get-started-devices.md)
8. [Развертывание приложений](deploy-apps.md)
