---
title: Управление мобильными устройствами для Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Поймите, как Contoso использует Microsoft Intune в Microsoft 365 для предприятия для управления своими устройствами и приложениями, которые работают на них.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754001"
---
# <a name="mobile-device-management-for-contoso"></a>Управление мобильными устройствами для Contoso

Microsoft 365 для предприятия включает Intune и набор служб Azure, которые поддерживают управление мобильными устройствами, управление приложениями и безопасность.

У Contoso много сотрудников с поддержкой мобильных устройств. Некоторые из них имеют офисы в расположениях Contoso, а некоторые не имеют офисов. Contoso требовался способ обеспечить производительность сотрудников, но обеспечить безопасность устройств, данных Contoso, хранимых на этих устройствах, и поведения приложений.

## <a name="plan"></a>Планирование

Contoso определила следующие случаи использования Intune для управления мобильными устройствами для Microsoft 365 для предприятия:

- Защита Exchange Online электронной почты и данных для безопасного доступа с мобильных устройств.
- Реализация программы bring-your-own-device (BYOD) для сотрудников Contoso.
- Выпуск телефонов, которые принадлежат организации, и планшеты с ограниченным использованием для сотрудников Contoso.

Contoso не использует Intune для:

- Разрешить сотрудникам безопасный доступ к Microsoft 365 из неугодного публичного киоска.
- Защита локальной электронной почты и данных, чтобы к ней можно было безопасно получить доступ с мобильных устройств, так как на локальном сервере Microsoft Exchange нет.

## <a name="deploy"></a>Развертывание

Процедура настройки инфраструктуры управления мобильными устройствами в Contoso:

- Установите Intune в качестве органа управления мобильными устройствами (MDM) и используйте Intune в Azure для администрирования контента и управления устройствами
- Созданные Azure Active Directory (Azure AD) группы для устройств для регистрации и параметров Intune и политики условного доступа на основе устройств

  Дополнительные сведения см. в дополнительных сведениях о политиках условного доступа [Contoso.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)

- Включена платформа устройств Apple для поддержки сотрудников с iPads, iMacs и iPhones, а также корпоративных iPhones.
- Создание политик использования применительно к Contoso, которые отображаются во время установки корпоративного портала для Contoso на мобильных устройствах
- Для устройств, которые не зарегистрированы, реализован набор политик управления мобильными приложениями (MAM), которые требуют проверки подлинности для доступа к Microsoft 365 службам
- Создание политик Intune, обеспечивающих следующее:
  - Разрешенные приложения.
  - Шифрование устройств, чтобы предотвратить несанкционированный доступ.
  - Шестизначный ПИН-код или пароль.
  - Период неактивности и времени ожидания.
  - Антивирусная и вредоносная защита, а также обновления подписей с Защитник Windows на Windows 10 устройствах.
  - Автоматические обновления на Windows 10 устройствах с последними обновлениями безопасности.
  - Нажатие сертификатов на управляемые устройства.
  - Четкое разделение корпоративных и личных данных. Пользователи или администраторы могут выборочно стирать корпоративные данные с устройства, не трогая личные данные, такие как рисунки, личные учетные записи электронной почты и личные файлы.

Contoso зарегистрировала развернутые компьютеры и смартфоны и планшеты, добавив их в соответствующие группы устройств Intune. Они также создали программу BYOD для сотрудников для регистрации своих личных устройств. Зарегистрированные устройства получают политики Intune, что приводит к управляемым и защищенным устройствам и их приложениям. Устройства, которые не зарегистрированы, имеют политики управления мобильными приложениями (MAM), которые указывают разрешенные приложения.

Вот архитектура развертывания мобильных устройств Contoso.

![Инфраструктура развертывания для управления мобильными устройствами Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Следующий этап

Узнайте, как Contoso использует возможности защиты информации Microsoft 365 предприятия для классификации, идентификации и защиты важных цифровых активов в организации. [](contoso-info-protect.md)

## <a name="see-also"></a>См. также

[Управление устройствами для Microsoft 365](device-management-roadmap-microsoft-365.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Руководства по лаборатории тестирования](m365-enterprise-test-lab-guides.md)

