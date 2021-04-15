---
title: Настройка уведомлений о антивирусных программах Microsoft Defender
description: Узнайте, как настроить и настроить стандартные и дополнительные антивирусные уведомления Microsoft Defender на конечных точках.
keywords: уведомления, защитник, антивирус, конечная точка, управление, администратор
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
ms.openlocfilehash: a91da48f27450d6f4a6fd2b9607aa979458ccf71
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765099"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Настройка уведомлений, которые отображаются в конечных точках

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

В Windows 10 уведомления приложений об обнаружении и исправлении вредоносных программ являются более надежными, последовательными и краткими.

Уведомления отображаются на конечных точках при завершении ручного и запланированного сканирования и обнаружении угроз. Эти уведомления также отображаются в **Центре** уведомлений, а сводка о проверках и обнаружениях угроз появляется через регулярные промежутки времени.

Можно также настроить, как стандартные уведомления отображаются на конечных точках, например уведомления о перезагрузке или при обнаружении и устранении угрозы.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Настройка дополнительных уведомлений, которые отображаются на конечных точках

Вы можете настроить отображение дополнительных уведомлений, например недавних сводок обнаружения угроз, в приложении [Windows Security](microsoft-defender-security-center-antivirus.md) и групповой политике.

> [!NOTE]
> В Windows 10, версии 1607  функция называлась Расширенные уведомления и может быть настроена в windows **Settings**  >  **Update &** безопасности  >  **Защитник Windows**. В параметрах групповой политики во всех версиях Windows 10 он называется **Расширенные уведомления.**

> [!IMPORTANT]
> Отключение дополнительных уведомлений не отключит важные уведомления, такие как обнаружение угрозы и оповещения о исправлении.

**Чтобы отключить дополнительные уведомления, используйте приложение Windows Security.**

1. Откройте приложение Безопасности Windows, щелкнув значок щита в панели задач или нажав меню пусков для **Defender.**

2. Щелкните **плитку** защиты & вирусов (или значок щита в левой панели меню), а затем **метку** параметров защиты & вирусов:

    ![Снимок экрана метки & защиты от угроз в приложении Windows Security](images/defender/wdav-protection-settings-wdsc.png)

3. Прокрутите в раздел **Уведомления** и нажмите **кнопку Изменить параметры уведомлений.**

4. Отключите **или**  включите дополнительные уведомления.

**Использование групповой политики для отключения дополнительных уведомлений:**

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **административные шаблоны**.

4. Расширь дерево до **компонентов Windows и > Microsoft Defender > Отчеты**.

5. Дважды **щелкните Кнопку Отключение расширенных уведомлений** и установите параметр **Включено**. Нажмите кнопку **ОК**. Это позволит избежать появления дополнительных уведомлений.

## <a name="configure-standard-notifications-on-endpoints"></a>Настройка стандартных уведомлений на конечных точках

Групповую политику можно использовать для:

- Отображение дополнительного настраиваемного текста в конечных точках, когда пользователю необходимо выполнить действие
- Скрыть все уведомления в конечных точках
- Скрыть уведомления о перезагрузке в конечных точках

Сокрытие уведомлений может быть полезно в ситуациях, когда нельзя скрыть весь антивирусный интерфейс Microsoft Defender. Дополнительные сведения см. в дополнительных сведениях о том, как запретить пользователям видеть и взаимодействовать с пользовательским интерфейсом [антивируса Microsoft Defender.](prevent-end-user-interaction-microsoft-defender-antivirus.md) 

> [!NOTE]
> Сокрытие уведомлений будет происходить только в конечных точках, в которые была развернута политика. Уведомления, связанные с действиями, которые необходимо принять (например, перезагрузка), по-прежнему будут отображаться на панели мониторинга мониторинга конечной точки и отчетах [Microsoft Endpoint Manager Endpoint Protection.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Инструкции по добавлению пользовательских контактных данных в уведомления, которые пользователи видят на компьютерах, см. в приложении [Customize the Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) для организации.

**Используйте групповую политику для сокрытия уведомлений:**

1. На компьютере управления групповой [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))политикой откройте консоль управления групповой политикой, щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.

3. Расширь дерево до **компонентов Windows и > антивируса Microsoft Defender > клиентского интерфейса.** 

4. Дважды нажмите **кнопку Подавления всех уведомлений** и установите параметр **Включено**. Нажмите кнопку **ОК**. Это позволит избежать появления дополнительных уведомлений.

**Используйте групповую политику для сокрытия уведомлений о перезагрузке:**

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **административные шаблоны**.

4. Расширь дерево до **компонентов Windows и > антивируса Microsoft Defender > клиентского интерфейса.**

5. Дважды нажмите **кнопку Подавляет уведомления о** перезагрузке и установите параметр **Включено**. Нажмите кнопку **ОК**. Это позволит избежать появления дополнительных уведомлений.

## <a name="related-topics"></a>Связанные статьи

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Настройка взаимодействия между конечными пользователями с антивирусом Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)