---
title: Настройка условного доступа
description: Как исключить некоторые учетные записи Майкрософт
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1b91186837ad558965d675f82d013a7081c7c7ec
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012501"
---
# <a name="adjust-conditional-access"></a>Настройка условного доступа

Если вы используете политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) в Организации, необходимо настроить их для исключения определенных учетных записей, чтобы обеспечить правильную работу управляемого рабочего стола Майкрософт.

Для этого выполните следующие действия:

1. Ознакомьтесь с разделом "откатить действия", [чтобы: планирование развертывания условного доступа в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).
2. Выполните действия, чтобы исключить группу *служебных учетных записей современного рабочего места* для всех политик.


Если у вас возникли сложности с использованием условного доступа, обратитесь в [службу поддержки](../working-with-managed-desktop/admin-support.md)администраторов.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Действия для начала работы с управляемым рабочим столом Майкрософт

1. [Добавление и проверка контактов администратора на портале администрирования](add-admin-contacts.md)
2. Настройка условного доступа (этот раздел)
3. [Назначение лицензий](assign-licenses.md)
4. [Развертывание корпоративного портала Intune](company-portal.md)
5. [Включение роуминга состояния предприятия](enterprise-state-roaming.md)
6. [Настройка устройств](set-up-devices.md)
7. [Подготовка пользователей к работе с устройствами](get-started-devices.md)
8. [Развертывание приложений](deploy-apps.md)