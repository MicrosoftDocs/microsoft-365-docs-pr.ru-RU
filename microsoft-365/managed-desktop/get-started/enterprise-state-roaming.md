---
title: Включение службы Enterprise State Roaming
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409120"
---
# <a name="enable-enterprise-state-roaming"></a>Включение службы Enterprise State Roaming

[Enterprise государственного роуминга](/azure/active-directory/devices/enterprise-state-roaming-overview) позволяет пользователям безопасно синхронизировать данные параметров пользователей и приложений в облаке. Это означает, что они будут иметь одинаковый опыт независимо от того, Windows устройство они впишут. Например, если заменить одно из компьютеры, управляемые Майкрософт на новое, оно будет выглядеть и вести себя точно так же, как и последнее. Enterprise Государственный роуминг является необязательным элементом для службы компьютеры, управляемые Майкрософт, которую можно настроить для пользователей и которая не включена или не управляется в компьютеры, управляемые Майкрософт.

Чтобы включить Enterprise государственного роуминга, выполните действия в [Enterprise государственного роуминга в Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

>[!NOTE]
>Если включить Enterprise государственного роуминга, в списке предпочтительных языков будет перезаписывать язык, выбранный во время установки устройства. Несмотря на то, что пользователи могут легко это исправить, изначально это может привести к непоследовательной локализации. Определите, Enterprise ли государственный роуминг является правильным для пользователей перед настройкой устройств.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Шаги для начала работы с компьютеры, управляемые Майкрософт

1. [Добавление и проверка контактов администратора на портале администрирования](add-admin-contacts.md)
2. [Настройка условного доступа](conditional-access.md)
3. [Назначение лицензий](assign-licenses.md)
4. [Развертывание корпоративного портала Intune](company-portal.md)
5. Включить Enterprise государственного роуминга (этот раздел)
6. [Настройка устройств](set-up-devices.md)
7. [Подготовка пользователей к работе с устройствами](get-started-devices.md)
8. [Развертывание приложений](deploy-apps.md)
