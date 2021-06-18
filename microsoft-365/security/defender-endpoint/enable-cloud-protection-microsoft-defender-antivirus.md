---
title: Включаем облачную защиту в антивирусная программа в Microsoft Defender
description: Включаем облачную защиту, чтобы воспользоваться возможностями быстрой и продвинутой защиты.
keywords: антивирусная программа в Microsoft Defender, антивирус, безопасность, облако, блок с первого взгляда
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 694c09c5136f874550fa4a47586f3268ee2d0833
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007189"
---
# <a name="turn-on-cloud-delivered-protection"></a>Включить облачную защиту

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Облачная антивирусная программа в Microsoft Defender — это механизм доставки обновленной защиты в сеть и конечные точки. Хотя это называется облачной службой, это не просто защита файлов, хранимых в облаке; вместо этого он использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, значительно более быстрой, чем традиционные обновления службы безопасности.

антивирусная программа в Microsoft Defender использует несколько технологий обнаружения и предотвращения для обеспечения точной и интеллектуальной защиты в режиме реального времени. [Узнать о передовых технологиях в центре защиты Microsoft Defender для endpoint следующего поколения.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

Вы можете включить антивирусная программа в Microsoft Defender-доставленную защиту несколькими способами:

- Microsoft Intune
- Microsoft Endpoint Manager
- Групповая политика
- Cmdlets PowerShell.

 Вы также можете включить его или отключить в отдельных клиентах с помощью Безопасность Windows приложения.

См. [статью Использование облачной защиты](cloud-protection-microsoft-defender-antivirus.md) Майкрософт для обзора антивирусная программа в Microsoft Defender облачной защиты.

Дополнительные сведения о конкретных требованиях к сетевому подключению, чтобы конечные точки могли подключаться к службе защиты с облачной доставкой, см. в статью Настройка и проверка [сетевых подключений.](configure-network-connections-microsoft-defender-antivirus.md)

> [!NOTE]
> В Windows 10 нет разницы между основными  и расширенными вариантами отчетности, описанными в этой теме.  Это устаревшее различие, и выбор любого параметра приведет к такому же уровню облачной защиты. Нет разницы в типе или количестве общих сведений. Дополнительные сведения о том, что мы собираем, см. в [заявлении о конфиденциальности Майкрософт.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Использование Intune для включаемой облачной защиты

1. Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.

2. На **домашней области** выберите **конфигурацию устройства > профилей.**

3. Выберите тип **профиля ограничений** устройства, который необходимо настроить. Если необходимо создать новый  тип профиля ограничений устройства, см. в странице Настройка параметров ограничения [устройств в Microsoft Intune.](/intune/device-restrictions-configure)

4. Выберите **параметры**  >  **конфигурации свойств: изменить**  >  **антивирусная программа в Microsoft Defender.**

5. В **облачном коммутаторе защиты** выберите **Включить**.

6. В **запросе пользователей перед отсевом** образца отправки выберите **отправить все данные автоматически.**

Дополнительные сведения о профилях устройств Intune, в том числе о создании и настройке параметров, см. в Microsoft Intune [профилей устройств?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Используйте Microsoft Endpoint Manager, чтобы включить облачную защиту

1. Перейдите в центр администрирования Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите в систему.

2. Выберите **антивирус безопасности**  >  **конечных точек**.

3. Выберите антивирусный профиль. (Если у вас еще нет его или вы хотите создать новый [профиль,](/intune/device-restrictions-configure)см. параметры ограничения устройств в Microsoft Intune .

4. Выбор **свойств**. Затем, рядом с **настройками конфигурации,** выберите **Изменить**.

5. **Расширив** защиту облака, а затем в **списке** уровней защиты с доставкой в облаке выберите один из следующих:
   - **High**: применяет высокий уровень обнаружения.
   - **Высокий плюс:** использует **высокий** уровень и применяет дополнительные меры защиты (может повлиять на производительность клиента).
   - **Нулевая толерантность.** Блокирует все неизвестные исполняемые.

6. Выберите **Обзор + сохранить,** а **затем** сохранить .

Дополнительные сведения о настройке Microsoft Endpoint Configuration Manager см. в дополнительных сведениях о создании и развертывании политик антивирусного [обеспечения: служба облачной защиты.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Использование групповой политики для включаемой облачной защиты

1. На устройстве управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.

2. В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Выберите **административные шаблоны.**

4. Расширение дерева до **Windows компонентов > антивирусная программа в Microsoft Defender > MAPS**

5. Дважды щелкните **Присоединиться к Microsoft MAPS**. Убедитесь, что параметр включен и задарен **базовым картам или** **расширенным КАРТАм.** Нажмите **ОК**.

6. Дважды **щелкните Отправить образцы файлов при необходимости дополнительного анализа.** Убедитесь, что для первого параметра установлен параметр **Включен,** а остальные параметры заме-

    1. **Отправка безопасных образцов** (1)
    2. **Отправка всех образцов** (3)

        >[!NOTE]
        > Параметр **Отправка безопасных образцов** (1) означает, что большинство образцов будут отправлены автоматически. Файлы, в которых могут содержаться персональные данные, будут по-прежнему подсказок и требуют дополнительного подтверждения.
        > Настройка параметра **Always Prompt** (0) снижает состояние защиты устройства. Настройка функции **Никогда** не отправлять (2) означает, что функция [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) Microsoft Defender для конечной точки не будет работать.

7. Нажмите **ОК**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Чтобы включить облачную защиту, используйте cmdlets PowerShell

Следующие cmdlets могут включить облачную защиту:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Дополнительные сведения о том, как использовать PowerShell с антивирусная программа в Microsoft Defender, см. в см. в рублях Use [PowerShell cmdlets to configure and run антивирусная программа в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Defender.](/powershell/module/defender/) [Политика CSP - Defender](/windows/client-management/mdm/policy-csp-defender) также имеет больше сведений конкретно о [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> Вы также можете **установить -SubmitSamplesConsent** `SendSafeSamples` (параметр по умолчанию), `NeverSend` или `AlwaysPrompt` . Параметр `SendSafeSamples` означает, что большинство образцов будут отправлены автоматически. Файлы, в которых могут содержаться персональные данные, будут по-прежнему подсказок и требуют дополнительного подтверждения.

>[!WARNING]
> Параметр **-SubmitSamplesConsent** или понизит уровень `NeverSend` защиты `AlwaysPrompt` устройства. Кроме того, настройка этого параметра означает, что функция Block at First Sight Microsoft Defender для конечной точки не `NeverSend` будет работать. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Используйте Windows управления (WMI), чтобы включить облачную защиту

Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) для следующих свойств:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Дополнительные сведения о разрешенных параметрах см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Включив облачную защиту для отдельных клиентов с помощью Безопасность Windows приложения

> [!NOTE]
> Если для настройки локального параметра переопределения для отчетов о  параметре групповой политики **Microsoft MAPS** задан параметр **Отключен,** то параметр облачной защиты в Windows Параметры будет серым и недоступным. Изменения, внесенные с помощью объекта групповой политики, необходимо сначала развернуть на отдельных конечных точках, прежде чем параметр будет обновлен в настройках Windows.

1. Откройте приложение Безопасность Windows, выбрав значок щита в панели задач или нажав меню пусков для **Defender.**

2. Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем **метку** параметров защиты & вирусов:

    :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Снимок экрана параметров защиты & вирусов":::

3. **Подтвердим, что** облачные средства защиты **и** автоматическая отправка образцов переключаются на **On**.

> [!NOTE]
> Если автоматическая отправка образца настроена с помощью групповой политики, параметр будет серым и недоступным.

## <a name="related-articles"></a>Статьи по теме

- [Настройка времени ожидания блокировки облака](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Настройка блока с первого взгляда](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Использование командлетов PowerShell для управления антивирусной программой в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Справка по Windows компьютеров с Endpoint Protection для Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Cmdlets Defender](/powershell/module/defender/)
- [Используйте облачную защиту Microsoft в антивирусная программа в Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)
- [Создание и развертывание политик противомалярийных программ: служба облачной защиты](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
