---
title: Включите облачную защиту в антивирусная программа в Microsoft Defender
description: Включите облачную защиту, чтобы воспользоваться преимуществами быстрых и продвинутых функций защиты.
keywords: антивирусная программа в Microsoft Defender, антивекав, безопасность, облако, блок с первого взгляда
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572061"
---
# <a name="turn-on-cloud-delivered-protection"></a>Включить облачную защиту

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Облачное антивирусная программа в Microsoft Defender является механизмом обеспечения обновленной защиты сети и конечных точек. Хотя это называется облачным сервисом, это не просто защита файлов, хранящихся в облаке; скорее, он использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, которая намного быстрее, чем традиционные обновления разведки безопасности.

антивирусная программа в Microsoft Defender использует многочисленные технологии обнаружения и профилактики для обеспечения точной, интеллектуальной защиты в режиме реального времени и интеллектуальной защиты. [Узнать о передовых технологиях, в основе microsoft Defender для защиты конечного точек следующего поколения.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

Вы можете включить антивирусная программа в Microsoft Defender защиту от облачных вычислений или выключить ее несколькими способами:

- Microsoft Intune
- Microsoft Endpoint Manager
- Групповая политика
- PowerShell cmdlets.

 Вы также можете включить или выключить его в отдельных клиентов с приложением Безопасность Windows приложение.

[См. Используйте облачную защиту Майкрософт](cloud-protection-microsoft-defender-antivirus.md) для обзора антивирусная программа в Microsoft Defender облачной защиты.

Для получения дополнительной информации о конкретных требованиях к сетевому подключению, чтобы обеспечить подключение конечных точек к облачной службе защиты, [см.](configure-network-connections-microsoft-defender-antivirus.md)

> [!NOTE]
> В Windows 10 нет никакой разницы между основными и расширенными **вариантами** **отчетности,** описанными в этой теме. Это устаревшее различие, и выбор любой из параметров приведет к одинаковому уровню облачной защиты. Нет никакой разницы в типе или объеме общей информации. Для получения дополнительной информации о том, что мы собираем, смотрите заявление [о конфиденциальности Майкрософт.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Используйте Intune для включить облачную защиту

1. Перейти к Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войти в систему.

2. На **панели Homee** выберите **конфигурацию устройства > профилей.**

3. Выберите **тип профиля ограничений** устройства, который вы хотите настроить. Если вам нужно создать новый **тип профиля ограничений** устройства, [см. Настройки параметров ограничения устройства в Microsoft Intune.](/intune/device-restrictions-configure)

4. Параметры **конфигурации**  >  **свойств: Редактировать**  >  **антивирусная программа в Microsoft Defender**.

5. В **коммутаторе защиты, поставляемом с** облачным доступом, **выберите Enable**.

6. В быстрых **пользователей перед примером представления** падения, выберите **Отправить все данные автоматически**.

Для получения дополнительной информации о профилях устройств Intune, включая способы создания и настройки их настроек, [см Microsoft Intune.](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Используйте Microsoft Endpoint Manager для включаемой облачной защиты

1. Перейти к Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войти в систему.

2. Выберите **Антивирус безопасности**  >  **Конечной точки**.

3. Выберите антивирусный профиль. (Если у вас его еще нет, или если вы хотите создать новый профиль, [см. Настройку настроек ограничения устройства в Microsoft Intune.](/intune/device-restrictions-configure)

4. Выберите **Свойства**. Затем, рядом с **настройками конфигурации,** **выберите Редактировать**.

5. Расширьте **защиту** облаков, а затем **в списке уровней защиты,** поставляемых в облако, выберите один из следующих:
   - **Высокий**: Применяется высокий уровень обнаружения.
   - **Высокий плюс**: Использует **высокий уровень** и применяет дополнительные меры защиты (может повлиять на производительность клиента).
   - **Нулевая толерантность**: Блокирует все неизвестные выполненные.

6. Выберите **Обзор и сохранить,** а затем выбрать **Сохранить**.

Для получения дополнительной информации о Microsoft Endpoint Configuration Manager, узнайте, [как создавать и развертывать антивирусные политики: Служба облачной защиты.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Использование групповой политики для включив облачную защиту

1. На устройстве управления групповой политикой откройте консоль [управления групповой политикой, нажмите](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))правой кнопкой мыши на объект групповой политики, который вы хотите настроить и выбрать **Edit.**

2. В редакторе **управления групповой политикой перейдите** на **компьютерную конфигурацию.**

3. Выберите **административные шаблоны.**

4. Расширьте дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > MAPS**

5. Дважды нажмите **Присоединяйтесь к Microsoft MAPS**. Убедитесь, что опция включена и установлена **на Basic MAPS** или Advanced **MAPS.** Нажмите **ОК**.

6. При необходимости **дополнительного анализа отправьте образцы файлов с двойным нажатием кнопки.** Убедитесь, что первый вариант установлен на **Enabled** и что другие параметры настроены либо:

    1. **Отправка безопасных образцов** (1)
    2. **Отправить все образцы** (3)

        >[!NOTE]
        > Опция **Send safe samples** (1) означает, что большинство образцов будут отправлены автоматически. Файлы, которые могут содержать личную информацию, по-прежнему будут оперативно и требуют дополнительного подтверждения.
        > Установка опции **Always Prompt** (0) снизит состояние защиты устройства. Установка его на **Never send** (2) означает, что функция Block at [First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) microsoft Defender for Endpoint не будет работать.

7. Нажмите **ОК**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Используйте смердлеты PowerShell для включив облачную защиту

Следующие cmdlets могут включить облачную защиту:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Для получения дополнительной информации о том, как использовать PowerShell с антивирусная программа в Microsoft Defender, [смесями Используйте PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для настройки и антивирусная программа в Microsoft Defender [и Defender cmdlets.](/powershell/module/defender/) [Политика CSP - Защитник](/windows/client-management/mdm/policy-csp-defender) также имеет более подробную информацию конкретно [о -SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> Вы также можете установить **-SubmitSamplesConsent** `SendSafeSamples` (параметр по умолчанию), `NeverSend` или `AlwaysPrompt` . Параметр `SendSafeSamples` означает, что большинство образцов будут отправлены автоматически. Файлы, которые могут содержать личную информацию, по-прежнему будут оперативно и требуют дополнительного подтверждения.

>[!WARNING]
> Настройка **-SubmitSamplesConsent** `NeverSend` или снизит `AlwaysPrompt` уровень защиты устройства. Кроме того, установка `NeverSend` означает, что функция Block at First [Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) Microsoft Defender for Endpoint не будет работать.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Используйте Windows управлению системой (WMI), чтобы включить облачную защиту

Используйте [ **метод** набора **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) класса для следующих свойств:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Более подробную информацию о разрешенных параметрах [можно получить Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Включите облачную защиту отдельных клиентов с помощью приложения Безопасность Windows

> [!NOTE]
> Если **настройка локальных параметров для представления отчетов по группе Майкрософт MAPS** установлена для **отключений,** то настройка защиты на основе облака в Windows Параметры году будет высеяна и недоступна.  Изменения, внесенные с помощью объекта групповой политики, необходимо сначала развернуть на отдельных конечных точках, прежде чем параметр будет обновлен в настройках Windows.

1. Откройте приложение Безопасность Windows, выбрав значок щита в баре задач или найме меню «Старт» для **Defender.**

2. Выберите **плитку & защиты** от угроз (или значок щита на левой планке меню), а **затем метку & virus для защиты** от угроз:

    ![Снимок экрана: метка параметров защиты от вирусов и угроз в приложении "Безопасность Windows"](images/defender/wdav-protection-settings-wdsc.png)

3. Подтвердите, **что облачная защита** и **автоматическое представление образцов** переключаются на **On**.

> [!NOTE]
> Если автоматическое представление образца было настроено с групповой политикой, то настройка будет серова и недоступна.

## <a name="related-articles"></a>Связанные статьи

- [Настройка времени ожидания блокировки облака](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Настройка блока с первого взгляда](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Использование командлетов PowerShell для управления антивирусной программой в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Помогите обезопасить Windows ПК с Endpoint Protection для Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Защитник cmdlets](/powershell/module/defender/)
- [Используйте облачную защиту Майкрософт в антивирусная программа в Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)
- [Как создавать и развертывать антивирусные политики: Служба облачной защиты](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
