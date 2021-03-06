---
title: Создание и управление группами устройств в Microsoft Defender для конечной точки
description: Создайте группы устройств и установите на них уровни автоматического устранения, подтвердив правила, применимые к группе
keywords: группы устройств, группы, исправление, уровень, правила, группа aad, роль, назначение, ранж
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
ms.openlocfilehash: 49bd90d8a082f55622e54976cc8fc78229d8c646
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453541"
---
# <a name="create-and-manage-device-groups"></a>Создание групп устройств и управление ими

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- Azure Active Directory.
- Office 365:

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


В корпоративном сценарии группам операций безопасности обычно назначен набор устройств. Эти устройства сгруппируются на основе набора атрибутов, таких как домены, имена компьютеров или назначенные теги.

В Microsoft Defender для конечной точки можно создавать группы устройств и использовать их для:
- Ограничение доступа к связанным оповещениям и данным определенным группам пользователей Azure AD с [назначенными ролями RBAC](rbac.md) 
- Настройка различных параметров автоматической исправлений для различных наборов устройств
- Назначение определенных уровней исправлений для применения во время автоматизированных расследований
- В ходе исследования фильтруем список **Устройств для** определенных групп устройств с помощью **группового фильтра.**

Группы устройств можно создавать в контексте ролевого доступа (RBAC), чтобы контролировать, кто может принимать конкретные действия или видеть сведения, назначая группу устройств (ы) группе пользователей. Дополнительные сведения см. в [ссылке Управление доступом к порталу с помощью управления доступом на основе ролей.](rbac.md)

>[!TIP]
> Подробнее о приложении RBAC читайте в публикации "Ъ" "SoC работает с [RBAC".](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)

В процессе создания группы устройств вы будете:
- Установите уровень автоматического восстановления для этой группы. Дополнительные сведения об уровнях исправлений см. в этой ссылке Использование автоматического расследования для расследования и устранения [угроз.](automated-investigations.md)
- Укажите правило совпадения, определяющее, какая группа устройств относится к группе на основе имени устройства, домена, тегов и платформы ОС. Если устройство также совпадает с другими группами, оно добавляется только в группу устройств с наивысшим ранжом.
- Выберите группу пользователей Azure AD, которая должна иметь доступ к группе устройств.
- Ранжив группу устройств по сравнению с другими группами после ее создания.

>[!NOTE]
>Группа устройств доступна всем пользователям, если вы не назначите группе Azure AD.

## <a name="create-a-device-group"></a>Создание группы устройств

1. В области навигации выберите группы **Параметры**  >  конечных **точек.**  >    >  

2. Нажмите **кнопку Добавить группу устройств**.

3. Введите параметры имени группы и параметры автоматизации и укажите правило совпадения, определяющие, какие устройства относятся к группе. Узнайте, [как начинается автоматическое расследование.](automated-investigations.md#how-the-automated-investigation-starts)

    >[!TIP]
    >Если вы хотите группировать устройства по организационному подразделению, можно настроить ключ реестра для групповой принадлежности. Дополнительные сведения о тегах устройств см. в дополнительных сведениях [о создании и управлении тегами устройств.](machine-tags.md)

4. Просмотр нескольких устройств, которые будут соответствовать этому правилу. Если вы удовлетворены правилом, щелкните вкладку **Доступ пользователя.**

5. Назначьте группы пользователей, которые могут получить доступ к созданной группе устройств.

    >[!NOTE]
    >Вы можете предоставить доступ только к группам пользователей Azure AD, которые были назначены ролям RBAC.

6. Нажмите кнопку **Закрыть**. Применяются изменения конфигурации.

## <a name="manage-device-groups"></a>Управление группами устройств

Можно повысить или понизить ранг группы устройств, чтобы во время совпадения ему было отдано более высокое или более низкое значение. Если устройство совпадает с более чем одной группой, оно добавляется только в группу с самым высоким рейтингом. Кроме того, можно изменить и удалить группы.



>[!WARNING]
>Удаление группы устройств может повлиять на правила уведомления электронной почты. Если группа устройств настроена в соответствии с правилом уведомления по электронной почте, она будет удалена из этого правила. Если группа устройств является единственной группой, настроенной для уведомления электронной почты, это правило уведомления электронной почты будет удалено вместе с группой устройств.

По умолчанию группы устройств доступны всем пользователям с доступом на портал. Вы можете изменить поведение по умолчанию, назначив группы пользователей Azure AD группе устройств.

Устройства, не совпадают с группами, добавляются в группу Ungrouped devices (по умолчанию). Вы не можете изменить ранг этой группы или удалить ее. Однако можно изменить уровень исправлений этой группы и определить группы пользователей Azure AD, которые могут получить доступ к этой группе.

>[!NOTE]
> Применение изменений в конфигурации группы устройств может занять до нескольких минут.


### <a name="add-device-group-definitions"></a>Добавление определений группы устройств
Определения группы устройств также могут включать несколько значений для каждого условия. Можно установить несколько тегов, имен устройств и доменов для определения одной группы устройств.

1. Создайте новую группу устройств и выберите **вкладку Devices.**
2. Добавьте первое значение для одного из условий.
3. Выберите, `+` чтобы добавить больше строк того же типа свойства.

>[!TIP]
> Используйте оператор "OR" между строками одного типа условий, что позволяет использовать несколько значений для каждого свойства.
> Для каждого типа свойств можно добавить до 10 строк (значений) — тег, имя устройства, домен.

Дополнительные сведения о привязке к определениям групп устройств см. в группе [Device groups - Microsoft 365 безопасности.](https://sip.security.microsoft.com/homepage)

## <a name="related-topics"></a>Связанные статьи

- [Управление доступом к порталу с помощью управления доступом на основе ролей](rbac.md)
- [Создание тегов устройств и управление ими](machine-tags.md)
- [Получите список групп устройств клиента с Graph API](/graph/api/device-list-memberof)
