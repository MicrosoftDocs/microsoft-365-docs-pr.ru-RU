---
title: Скрыть антивирусный интерфейс Microsoft Defender
description: В приложении Windows Security можно скрыть плитку защиты от вирусов и угроз.
keywords: Блокировка пользовательского интерфейса, режим без головы, скрыть приложение, скрыть параметры, скрыть интерфейс
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 93cd6331099c5c89aec2e0706f79ec7fb305b42a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765555"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Запретить пользователям видеть и взаимодействовать с пользовательским интерфейсом антивируса Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Можно использовать групповую политику, чтобы запретить пользователям конечных точек видеть антивирусный интерфейс Microsoft Defender. Вы также можете запретить им прио паузу в проверке.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Скрыть антивирусный интерфейс Microsoft Defender

В Windows 10 версии 1703 скрытие интерфейса скроет уведомления о антивирусе Microsoft Defender и предотвратит & защиты от угрозы в приложении Windows Security.

С набором параметров **включен:**

![Снимок экрана Windows Security без значка щита и раздела защиты от вирусов и угроз](images/defender/wdav-headless-mode-1703.png)

С набором параметра **Отключено или** не настроено:

![Снимок экрана Windows Security, показывающий значок щита и раздел защиты от вирусов и угроз](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
>Сокрытие интерфейса также предотвратит появления антивирусных уведомлений Microsoft Defender на конечной точке. Уведомления Microsoft Defender для конечной точки по-прежнему будут отображаться. Кроме того, можно настроить уведомления, которые отображаются [в конечных точках.](configure-notifications-microsoft-defender-antivirus.md)

В более ранних версиях Windows 10 параметр будет скрывать Защитник Windows клиентского интерфейса. Если пользователь по пытается открыть его, ему будет объявлено предупреждение: "Администратор системы имеет ограниченный доступ к этому приложению".

![Предупреждение при включенном безголовом режиме в Windows 10, версии более ранних версий 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Использование групповой политики для сокрытия интерфейса av-интерфейса Microsoft Defender от пользователей

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **административные шаблоны**.

4. Расширь дерево до **компонентов Windows и > антивируса Microsoft Defender > клиентского интерфейса.**

5. Дважды щелкните **параметр Включить безголевую настройку пользовательского интерфейса** и установите параметр **Включено.** Нажмите кнопку **ОК**. 

Подробнее [о том,](configure-local-policy-overrides-microsoft-defender-antivirus.md) как запретить пользователям изменять параметры политики на локальном уровне, см. в руб. Предотвращение изменения защиты пользователей на пк.

## <a name="prevent-users-from-pausing-a-scan"></a>Запретить пользователям прио паузу в проверке

Вы можете запретить пользователям прерывать проверки, которые могут быть полезны для обеспечения того, чтобы запланированные или по требованию проверки не прерывались пользователями.

> [!NOTE]
> Этот параметр не поддерживается в Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Использование групповой политики, чтобы запретить пользователям прио паузу в проверке

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **административные шаблоны**.

4. Расширь дерево до **компонентов**  >  **Антивирусной проверки Microsoft Defender**  >  **Microsoft** Defender.

5. Дважды щелкните **кнопку Разрешить пользователям приостанавлить** параметр сканирования и установить параметр **Отключен.** Нажмите кнопку **ОК**. 

## <a name="related-articles"></a>Статьи по теме

- [Настройка уведомлений, которые отображаются в конечных точках](configure-notifications-microsoft-defender-antivirus.md)

- [Настройка взаимодействия между конечными пользователями с антивирусом Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)