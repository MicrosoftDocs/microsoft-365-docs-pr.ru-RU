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
ms.openlocfilehash: 760fcb94ec6d84a55fe4b8c3cb3540ae29994ae3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918446"
---
# <a name="adjust-settings-after-enrollment"></a>Настройка параметров после регистрации

После завершения регистрации в Microsoft Managed Desktop может потребоваться корректировка некоторых параметров управления. Чтобы проверить и настроить при необходимости, выполните следующие действия:

1. Просмотрите параметры Microsoft Intune и Azure Active Directory, описанные в следующем разделе.
2. Если какие-либо элементы применяются к среде, внесите описанные изменения.
3. Если необходимо дважды проверить правильность всех параметров, можно [](https://aka.ms/mmdart) повторно использовать средство оценки готовности, чтобы убедиться, что ничего не противоречит Microsoft Managed Desktop.

> [!NOTE]
> По мере продолжения операций в последующие месяцы при внесении изменений в политики Microsoft Intune, Azure Active Directory или Microsoft 365, влияющие на microsoft Managed Desktop, не исключено, что microsoft Managed Desktop может перестать работать должным образом. Чтобы избежать проблем со службой, ознакомьтесь [](../get-ready/readiness-assessment-fix.md) с определенными настройками, описанными в исправлении проблем, найденных средством оценки готовности, прежде чем менять перечисленные в ней политики. Вы также можете повторно использовать средство оценки готовности в любое время.


## <a name="microsoft-intune-settings"></a>Параметры Microsoft Intune

- Профиль развертывания автопилота: если вы используете политики автопилота, обнови каждую из них, чтобы исключить группу **Modern Workplace Devices -All** Azure AD. Чтобы обновить их,  в разделе Исключенные группы в разделе Назначения **выберите** группу Modern Workplace **Devices -All** Azure AD, созданную во время регистрации Microsoft Managed Desktop. Microsoft Managed Desktop также создадит профиль автопилота, который будет иметь имя "Современное рабочее место" (современный профиль **автопилота на рабочем месте).** При обновлении собственных профилей автопилота убедитесь, что вы не исключаете группу  Modern **Workplace Devices -All** Azure AD из профиля автопилота современного рабочего места, созданного Microsoft Managed Desktop. 

- Политики условного доступа. При создании новых политик условного доступа, связанных с Azure AD, Microsoft Intune или Microsoft Defender для конечной точки после регистрации microsoft Managed Desktop, исключите из них группу "Современные учетные записи службы рабочих мест **Azure** AD". Действия см. в [условном доступе: пользователи и группы.](/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop поддерживает отдельные политики условного доступа, чтобы ограничить доступ к этим учетным записям. Чтобы просмотреть политику условного доступа microsoft Managed Desktop **(Modern Workplace — Secure Workstation),** перейдите к Microsoft Endpoint Manager и перейдите к условному доступу в **endpoint Security.**  Не изменяйте политики условного доступа Azure AD, созданные Microsoft Managed Desktop с названием "Modern Workplace".

- Многофакторная проверка подлинности. При создании новых требований к многофакторной проверке подлинности в политиках условного доступа, связанных с Azure AD, Intune или Microsoft Defender для конечной точки после регистрации Microsoft Managed Desktop, исключите из них группу "Современные учетные записи службы рабочих мест **Azure** AD". Действия см. в [условном доступе: пользователи и группы.](/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop поддерживает отдельные политики условного доступа, чтобы ограничить доступ к членам этой группы. Чтобы просмотреть политику условного доступа microsoft Managed Desktop **(Modern Workplace - ),** перейдите к Microsoft Endpoint Manager и перейдите к условному доступу **в** **endpoint Security.** 

- Кольцо обновления Windows 10: для всех созданных политик кольцевых обновлений Windows 10 исключите из каждой политики группу Modern **Workplace Devices -All** Azure AD. Для действий см. в этой версии [Создать и назначить кольца обновления.](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft Managed Desktop также создал некоторые политики кольцевых обновлений, все из которых будут иметь имя "Modern Workplace" (например, современная политика обновления рабочих мест **[Broad],** современная политика обновления рабочих мест **[Fast],** современная политика обновления рабочих мест **[First]** и современная политика обновления рабочих мест **[Test]).** При обновлении собственных политик убедитесь,  что вы не исключаете группу Modern **Workplace Devices -All** Azure AD из созданных Microsoft Managed Desktop.


## <a name="azure-active-directory-settings"></a>Параметры Azure Active Directory

Сброс пароля самообслуживной службы. Если для всех пользователей используется сброс пароля самообслуживаемого, отрегулировать назначение, чтобы исключить учетные записи службы microsoft Managed Desktop. Чтобы изменить это назначение, создайте динамическую группу Azure AD для всех пользователей, кроме учетных записей *службы* Microsoft Managed Desktop, а затем используйте эту группу для назначения, а не "всех пользователей".

Чтобы помочь вам найти и исключить учетные записи службы, можно использовать пример динамического запроса:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

В этом запросе замените @TENANT доменным именем клиента.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Действия по началу работы с управляемым рабочим столом Майкрософт

1. [Добавление и проверка контактов администратора на портале администрирования](add-admin-contacts.md)
2. Настройка параметров после регистрации (в этой статье)
3. [Назначение лицензий](assign-licenses.md)
4. [Развертывание корпоративного портала Intune](company-portal.md)
5. [Включение службы Enterprise State Roaming](enterprise-state-roaming.md)
6. [Настройка устройств](set-up-devices.md)
7. [Подготовка пользователей к работе с устройствами](get-started-devices.md)
8. [Развертывание приложений](deploy-apps.md)