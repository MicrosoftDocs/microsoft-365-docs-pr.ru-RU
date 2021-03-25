---
title: Использование базовых разрешений для доступа к Центру безопасности Защитника Майкрософт
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
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163675"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Использование базовых разрешений для доступа к порталу

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

## <a name="assign-user-access-using-azure-powershell"></a>Назначение доступа пользователей с помощью Azure PowerShell
Вы можете назначить пользователям один из следующих уровней разрешений:
- Полный доступ (чтение и записи)
- Доступ только для чтения

### <a name="before-you-begin"></a>Перед началом работы

- Установка Azure PowerShell. Дополнительные сведения см. в [рублях "Установка и настройка Azure PowerShell".](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)<br>

    > [!NOTE]
    > Необходимо выполнить командлеты PowerShell в повышенной командной строке.

- Подключение к вашему Azure Active Directory. Дополнительные сведения см. в [дополнительных сведениях в connect-MsolService.](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)

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

Дополнительные сведения см. в [добавлении или удалите членов группы с помощью Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

## <a name="assign-user-access-using-the-azure-portal"></a>Назначение доступа пользователей с помощью портала Azure

Дополнительные сведения см. в ссылке Назначение ролей администратора и не администратора [пользователям с Помощью Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="related-topic"></a>Связанная тема

- [Управление доступом к порталу с помощью RBAC](rbac.md)
