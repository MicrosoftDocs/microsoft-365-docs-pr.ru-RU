---
title: Скрыть интерфейс антивирусная программа в Microsoft Defender
description: Вы можете скрыть плитку защиты от вирусов и угроз в Безопасность Windows приложении.
keywords: Блокировка пользовательского интерфейса, режим без головы, скрыть приложение, скрыть параметры, скрыть интерфейс
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007677"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Запретить пользователям видеть или взаимодействовать с антивирусная программа в Microsoft Defender пользовательским интерфейсом

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Можно использовать групповую политику, чтобы запретить пользователям конечных точек видеть антивирусная программа в Microsoft Defender интерфейса. Вы также можете запретить им прио паузу в проверке.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Скрыть интерфейс антивирусная программа в Microsoft Defender

В Windows 10 версии 1703 скрытие интерфейса скроет антивирусная программа в Microsoft Defender уведомления и не позволит плитке защиты & вирусов появляться в приложении Безопасность Windows.

С набором параметров **включен:**

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Безопасность Windows без значка щита и раздела защиты от вирусов и угроз":::

С набором параметра **Отключено или** не настроено:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Снимок экрана Безопасность Windows с значком щита и разделами защиты от угроз":::

>[!NOTE]
>Сокрытие интерфейса также предотвратит антивирусная программа в Microsoft Defender уведомлений на конечной точке. Уведомления Microsoft Defender для конечной точки по-прежнему будут отображаться. Кроме того, можно настроить уведомления, которые отображаются [в конечных точках.](configure-notifications-microsoft-defender-antivirus.md)

В более ранних версиях Windows 10 параметр будет скрывать интерфейс Защитник Windows клиента. Если пользователь по пытается открыть его, ему будет объявлено предупреждение: "Администратор системы имеет ограниченный доступ к этому приложению".

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Предупреждение при включенном режиме без головы в Windows 10 версиях до 1703 г.":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Использование групповой политики для сокрытия интерфейса av-интерфейса Microsoft Defender от пользователей

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **административные шаблоны**.

4. Расширь **дерево, Windows компоненты > антивирусная программа в Microsoft Defender > клиентского интерфейса.**

5. Дважды щелкните **параметр Включить безголевую настройку пользовательского интерфейса** и установите параметр **Включено.** Нажмите кнопку **ОК**. 

Подробнее [о том,](configure-local-policy-overrides-microsoft-defender-antivirus.md) как запретить пользователям изменять параметры политики на локальном уровне, см. в руб. Предотвращение изменения защиты пользователей на пк.

## <a name="prevent-users-from-pausing-a-scan"></a>Запретить пользователям прио паузу в проверке

Вы можете запретить пользователям прерывать проверки, которые могут быть полезны для обеспечения того, чтобы запланированные или по требованию проверки не прерывались пользователями.

> [!NOTE]
> Этот параметр не поддерживается Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Использование групповой политики, чтобы запретить пользователям прио паузу в проверке

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **административные шаблоны**.

4. Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **сканирование.**

5. Дважды щелкните **кнопку Разрешить пользователям приостанавлить** параметр сканирования и установить параметр **Отключен.** Нажмите кнопку **ОК**. 

## <a name="related-articles"></a>Статьи по теме

- [Настройка уведомлений, отображающихся в конечных точках](configure-notifications-microsoft-defender-antivirus.md)

- [Настройка взаимодействия конечных пользователей с антивирусная программа в Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)