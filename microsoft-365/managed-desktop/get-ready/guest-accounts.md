---
title: Предварительные требования для гостевых учетных записей
description: Рекомендации по настройке учетных записей гостей и их корректировка
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694249"
---
# <a name="prerequisites-for-guest-accounts"></a>Предварительные требования для гостевых учетных записей

компьютеры, управляемые Майкрософт необходимы следующие параметры в организации Azure AD для доступа к учетной записи гостей. Эти параметры можно настроить на портале [Azure](https://portal.azure.com) в соответствии с настройками внешних удостоверений **и внешних параметров совместной работы:**

-   Для **приглашенных приглашений** ограничения, установленные для пользователей-членов и пользователей, назначенных на определенные роли администратора, могут приглашать гостевых пользователей, включая гостей **с разрешениями участников.**
-   Для **ограничений для совместной работы** выберите любой из этих параметров:
    -   Если вы **выбираете Разрешить приглашения, которые будут отправлены** в любой домен (наиболее включительный), никакой другой конфигурации не требуется.
    -   Если вы выберите **отказ в** приглашениях на указанные домены, убедитесь, что Microsoft.com не указаны в целевых доменах.
    -   Если вы выберите Разрешить приглашения только в указанные домены **(наиболее** ограничительные), убедитесь, что Microsoft.com указаны в целевых доменах. 

Если вы устанавливаете ограничения, взаимодействующие с этими настройками, не забудьте исключить Azure Active Directory учетные записи служб на **рабочем месте.** Например, если у вас есть политика условного доступа, которая не позволяет гостевых учетным записям получать доступ к порталу Intune, исключите группу **учетных** записей служб на современном рабочем месте из этой политики.

## <a name="steps-to-get-ready"></a>Действия, которые необходимо сделать, чтобы быть готовыми

1. См. [предварительные условия для компьютеров, управляемых Майкрософт](prerequisites.md).
2. Используйте [средства оценки готовности](readiness-assessment-tool.md).
3. [Необходимые условия для учетных записей гостей](guest-accounts.md) (Эта статья)
4. [Конфигурация сети для компьютеров, управляемых Майкрософт](network.md)
5. [Подготовка сертификатов и сетевых профилей для компьютеров, управляемых Майкрософт](certs-wifi-lan.md)
6. [Подготовка доступа к локальным ресурсам для компьютеров, управляемых Майкрософт](authentication.md)
7. [Приложения на компьютерах, управляемых Майкрософт](apps.md)
8. [Подготовка подключенных дисков для компьютеров, управляемых Майкрософт](mapped-drives.md)
9. [Подготовка ресурсов печати для компьютеров, управляемых Майкрософт](printing.md)
