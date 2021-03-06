---
title: Используйте управление доступом на основе ролей для предоставления мелкозернистого доступа к Центр безопасности в Microsoft Defender
description: Создайте роли и группы в операциях безопасности, чтобы предоставить доступ к порталу.
keywords: rbac, role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071878"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Управление доступом к порталу с помощью управления доступом на основе ролей

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- Azure Active Directory.
- Office 365:

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

С помощью управления доступом на основе ролей (RBAC) можно создавать роли и группы в группе операций безопасности, чтобы предоставить соответствующий доступ к порталу. На основе ролей и групп, которые вы создаете, у вас есть тонкий контроль над тем, что пользователи с доступом к порталу могут видеть и делать. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

Как правило, крупные группы операций безопасности с распределенной геомагности принимают модель, основанную на уровнях, для назначения и авторизации доступа к порталам безопасности. Типичные уровни включают следующие три уровня:

Уровень | Описание
:---|:---
Уровень 1 | **Локализованная группа операций безопасности / ИТ-группа** <br> Обычно эта группа проводит проверку и изучает оповещения, содержащиеся в их геолокации, и в случаях, когда требуется активное исправление, передается на уровень 2.
Уровень 2 | **Группа региональных операций по безопасности** <br> Эта группа может видеть все устройства для своего региона и выполнять действия по исправлению.
Уровень 3 | **Группа глобальных операций по безопасности** <br> Эта группа состоит из экспертов по безопасности и уполномочена видеть и выполнять все действия с портала.

Defender for Endpoint RBAC предназначен для поддержки модели выбора на уровне или на основе ролей, а также позволяет детально контролировать, какие роли можно видеть, к каким устройствам можно получить доступ и какие действия они могут принимать. Рамки RBAC в центре вокруг следующих элементов управления:

- **Управление, которые могут принимать конкретные действия**
  - Создание настраиваемой роли и управление возможностями Defender для конечных точек, к которые они могут получить доступ с детализацией.
 
- **Управление, которое может видеть сведения о определенных группах устройств или группах**
  - [Создайте](machine-groups.md) группы устройств по определенным критериям, таким как имена, теги, домены и другие, а затем предоставить им доступ к роли с помощью определенной группы пользователей Azure Active Directory Azure AD.

Чтобы реализовать доступ на основе ролей, необходимо определить роли администратора, назначить соответствующие разрешения и назначить группы пользователей Azure AD, назначенные этим ролям.


### <a name="before-you-begin"></a>Прежде чем начать
Перед использованием RBAC важно понимать роли, которые могут предоставлять разрешения, и последствия включаемого RBAC.


> [!WARNING]
> Прежде чем включить эту функцию, важно иметь роль глобального администратора или администратора безопасности в Azure AD и чтобы группы Azure AD были готовы к снижению риска блокировки портала. 

При первом входе в Центр безопасности в Microsoft Defender доступ предоставляется либо полный доступ, либо только для чтения. Полный доступ предоставляется пользователям с ролями администратора безопасности или глобального администратора в Azure AD. Доступ только к чтению предоставляется пользователям с ролью читателя безопасности в Azure AD. 

Кто-то с ролью администратора Defender for Endpoint Global имеет неограниченный доступ ко всем устройствам, независимо от их объединения групп устройств и назначений групп пользователей Azure AD.

> [!WARNING]
> Изначально создавать и назначать роли в Центр безопасности в Microsoft Defender смогут только те, у кого есть права глобального администратора Azure AD или администратора безопасности, поэтому важно, чтобы в Azure AD были готовы правильные группы.
>
> **Включение управления доступом на основе ролей приведет к тому, что пользователи с разрешениями только для чтения (например, пользователи, на которые назначена роль читателя службы безопасности Azure AD) будут терять доступ до тех пор, пока они не будут назначены роли.** 
>
>Пользователям с разрешениями администратора автоматически назначена встроенная роль глобального администратора Defender for Endpoint с полными разрешениями. После выбора использования RBAC можно назначить дополнительных пользователей, которые не являются глобальными администраторами Azure AD или администраторами безопасности, в роль глобального администратора Defender for Endpoint. 
>
> После выбора использования RBAC нельзя вернуться к начальным ролям, как при первом входе на портал. 



## <a name="related-topic"></a>Связанная тема
- [Создание и управление группами устройств в Microsoft Defender для конечной точки](machine-groups.md)
