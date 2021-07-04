---
title: Используйте базовые разрешения для доступа к Центр безопасности в Microsoft Defender
description: Узнайте, как использовать основные разрешения для доступа к порталу Microsoft Defender для конечных точек.
keywords: назначение ролей пользователей, назначение доступа к чтением и записи, назначение доступа только для чтения, пользователя, ролей пользователей, ролей
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
ms.openlocfilehash: e7c208998e436245c53b90905858b7cf7ebe91d6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290199"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Использование основных разрешений для доступа к порталу

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- Azure Active Directory
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

Обратитесь к инструкциям ниже, чтобы использовать управление базовыми разрешениями.

Вы можете использовать любой из следующих решений:
- Azure PowerShell
- Портал Azure

Для детального контроля над разрешениями [переключение на](rbac.md)управление доступом на основе ролей.

## <a name="assign-user-access-using-azure-powershell"></a>Назначение доступа пользователя с помощью Azure PowerShell
Вы можете назначить пользователям один из следующих уровней разрешений:
- Полный доступ (чтение и записи)
- Доступ только для чтения

### <a name="before-you-begin"></a>Подготовка

- Установка Azure PowerShell. Дополнительные сведения см. в [том, как установить](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)и настроить Azure PowerShell.<br>

    > [!NOTE]
    > Необходимо выполнить командлеты PowerShell в повышенной командной строке.

- Подключение к Azure Active Directory. Дополнительные сведения см. [в Подключение-MsolService](/powershell/module/msonline/connect-msolservice).

**Полный доступ** <br>
Пользователи с полным доступом могут войти в систему, просмотреть всю системную информацию и разрешить оповещения, отправить файлы для глубокого анализа и скачать бортовой пакет.
Назначение прав на полный доступ требует добавления пользователей в встроенные роли AAD "Администратор безопасности" или "Глобальный администратор".

**Доступ только для чтения** <br>
Пользователи с доступом только для чтения могут войти в систему, просмотреть все оповещения и связанные сведения.
Они не смогут изменять состояния оповещений, отправлять файлы для глубокого анализа или выполнять операции по изменению состояния.
Назначение прав доступа только для чтения требует добавления пользователей в встроенную роль Azure AD azure.

Чтобы назначить роли безопасности, используйте следующие действия:

- Для **чтения и записи** назначьте пользователям роль администратора безопасности с помощью следующей команды:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- Для **доступа только для** чтения назначьте пользователям роль читателя безопасности с помощью следующей команды:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Дополнительные сведения см. в [добавлении или удалите](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)членов группы с помощью Azure Active Directory.

## <a name="assign-user-access-using-the-azure-portal"></a>Назначение доступа пользователей с помощью портала Azure

Дополнительные сведения см. в [ссылке Назначение ролей](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)администратора и не администратора пользователям с Azure Active Directory .

## <a name="related-topic"></a>Связанная тема

- [Управление доступом к порталу с помощью RBAC](rbac.md)
