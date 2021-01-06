---
title: Настройка параметров после регистрации
description: Как исключить определенные учетные записи Майкрософт
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d7fe410f114d43d4f6c983aaf23d949298635318
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760107"
---
# <a name="adjust-settings-after-enrollment"></a>Настройка параметров после регистрации

После регистрации на компьютере, управляемом Майкрософт, необходимо настроить определенные параметры Microsoft Intune и Azure Active Directory (Azure AD), чтобы обеспечить управление и обеспечение безопасности. Установите следующие параметры, чтобы исключить группы Azure AD, содержащие настольные устройства и пользователей, управляемые Майкрософт. Действия по исключению групп см. в [подсети "Условный доступ: пользователи и группы".](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)

> [!NOTE]
> Если после регистрации в политиках в Microsoft Intune, Azure Active Directory или Microsoft 365 внести какие-либо изменения, возможно, что компьютеры, управляемые Майкрософт, перестанут работать надлежащим образом. Чтобы избежать проблем с операциями microsoft Managed Desktop, [](../get-ready/readiness-assessment-fix.md) проверьте параметры, описанные в описании исправления проблем, найденных средством оценки готовности, перед изменением политик.


## <a name="microsoft-intune-settings"></a>Параметры Microsoft Intune

- Профиль развертывания Autopilot: исключить группу **"Современные рабочие устройства — все**  устройства Azure AD". Действия см. в [подразделе "Регистрация устройств с Windows в Intune с помощью Windows Autopilot".](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- Политики условного доступа: исключить группу Azure AD **"Учетные** записи современных рабочих служб". По шагам см. [условный доступ: пользователи и группы.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)
- Многофакторная проверка подлинности: убедитесь, что все политики условного доступа, которые требуют многофакторной проверки подлинности, исключают группу **Azure** AD учетных записей современных рабочих служб. Дополнительные сведения [см.](../get-ready/readiness-assessment-fix.md#conditional-access-policies) в политиках условного доступа и [условном доступе: "Требовать многофайловую многофайловую аудию для всех пользователей".](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- Базовые параметры безопасности: исключить **группу "Современные рабочие устройства — все**  устройства Azure AD". По шагам [см. использование базовых параметров безопасности для настройки устройств с Windows 10 в Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines)
- Круг обновления Windows 10: исключите группу **"Современные рабочие устройства — все**  устройства Azure AD". По шагам [см. управление обновлениями программного обеспечения Windows 10 в Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)


## <a name="azure-active-directory-settings"></a>Параметры Azure Active Directory

Самостоятельный сброс пароля: выберите **выбранный** параметр, а затем выберите "Современные рабочие **устройства " — все группы** Azure AD". Дополнительные сведения см. в руководстве. В этом руководстве пользователи могут разблокировать свою учетную запись или сбросить пароли с помощью самостоятельного сброса [пароля Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Действия по началу работы с компьютером, управляемым Майкрософт

1. [Добавление и проверка контактов администратора на портале администрирования](add-admin-contacts.md)
2. Настройка параметров после регистрации (в этой статье)
3. [Назначение лицензий](assign-licenses.md)
4. [Развертывание корпоративного портала Intune](company-portal.md)
5. [Включение службы Enterprise State Roaming](enterprise-state-roaming.md)
6. [Настройка устройств](set-up-devices.md)
7. [Подготовка пользователей к работе с устройствами](get-started-devices.md)
8. [Развертывание приложений](deploy-apps.md)
