---
title: Обнаружение конечных точек и реагирование в режиме блокировки
description: Узнайте о обнаружение и нейтрализация атак на конечные точки в режиме блокировки
keywords: Microsoft Defender для конечной точки, mde, EDR в режиме блокирования, блокировка пассивного режима
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b0fe1da56c34cd0a79e1a41dba2fcb7a79c5a9f6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259577"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Обнаружение конечных точек и ответ (EDR) в режиме блокировки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Что EDR в режиме блокировки?

[Обнаружение конечных точек](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) и ответ (EDR) в режиме блокировки обеспечивают защиту от вредоносных артефактов, даже если антивирусная программа в Microsoft Defender работает в пассивном режиме. При включенном EDR режиме блоки блокируют вредоносные артефакты или поведение, обнаруженные на устройстве. EDR режиме блокировки работает за кулисами для устранения вредоносных артефактов, обнаруженных после нарушения. 

EDR в режиме блокировки также интегрирована с угрозами [& управление уязвимостями.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Команда безопасности организации получит рекомендации [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) по безопасности, чтобы включить EDR в режиме блокировки, если она еще не включена. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="рекомендация включить EDR в режиме блокировки":::

> [!NOTE]
> Чтобы получить лучшую защиту, убедитесь в развертывании базовых показателей **[Microsoft Defender для конечных точек.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>Что происходит при обнаружении чего-либо?

Когда EDR в режиме блокировки и обнаружен вредоносный артефакт, Microsoft Defender для конечных точек блокирует и устраняет этот артефакт. Состояние обнаружения будет заблокировано или **предотвращено** как завершенные действия в [центре действий.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center) 

На следующем изображении показан экземпляр нежелательного программного обеспечения, которое было обнаружено и заблокировано EDR режиме блокировки:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR в режиме блокировки обнаружил что-то":::


## <a name="enable-edr-in-block-mode"></a>Включить EDR в режиме блокировки

> [!IMPORTANT]
> Убедитесь, [что требования](#requirements-for-edr-in-block-mode) будут выполнены перед включением EDR в режиме блокировки.

1. Перейдите в Центр безопасности в Microsoft Defender [https://securitycenter.windows.com](https://securitycenter.windows.com) () и войдите. 

2. Выберите **Параметры**  >  **расширенные функции**.

3. **Включаем EDR в режиме блокировки.**

> [!NOTE]
> EDR режиме блокировки можно включить только в Центр безопасности в Microsoft Defender. Вы не можете использовать клавиши реестра, политики Intune или группы, чтобы включить или отключить EDR в режиме блокировки.

## <a name="requirements-for-edr-in-block-mode"></a>Требования к EDR в режиме блокировки

|Требования  |Сведения  |
|---------|---------|
|Разрешения |Роль глобального администратора или администратора безопасности, назначенная [в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). См. [основные разрешения.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions) |
|Операционная система     |Одна из следующих версий: <br/>- Windows 10 (все выпуски) <br/>- Windows Server, версия 1803 или более новая <br/>- Windows Server 2019  <p>**ПРИМЕЧАНИЕ:** EDR режиме блокировки не поддерживается на Windows Server 2016.       |
|Windows Регистрация на E5     |Windows E5 входит в следующие подписки: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 вместе с предложением & защиты от угроз <br/><br/>См. [Компоненты](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) [и функции и возможности для каждого плана.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Антивирусная программа в Microsoft Defender  |антивирусная программа в Microsoft Defender должны быть установлены и запущены в активном или пассивном режиме. (Вы можете использовать антивирусная программа в Microsoft Defender наряду с антивирусным решением, не относя к Майкрософт.) [Подтвердим антивирусная программа в Microsoft Defender находится в активном или пассивном режиме.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Облачная защита |Убедитесь, антивирусная программа в Microsoft Defender настраивается таким образом, чтобы включена [облачная защита.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) |
|антивирусная программа в Microsoft Defender клиента антивирусного программного обеспечения |Убедитесь, что клиент устарел. С помощью PowerShell запустите в качестве администратора группу [Get-MpComputerStatus.](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) В **строке AMProductVersion** необходимо увидеть **4.18.2001.10** или выше. |
|антивирусная программа в Microsoft Defender |Убедитесь, что ваш двигатель устарел. С помощью PowerShell запустите в качестве администратора группу [Get-MpComputerStatus.](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) В **строке AMEngineVersion** вы должны увидеть **1.1.16700.2** или выше. |

> [!IMPORTANT]
> Чтобы получить наилучшее значение защиты, убедитесь, что антивирусное решение настроено для получения регулярных обновлений и основных функций, а также настройки [исключений.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) EDR режиме блокировки касается исключений, определенных для антивирусная программа в Microsoft Defender.

## <a name="frequently-asked-questions"></a>Вопросы и ответы 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Нужно ли включить EDR в режиме блокировки, даже если антивирусная программа в Microsoft Defender работает на устройствах?

Рекомендуется сохранять EDR в режиме блокировки, независимо от того, антивирусная программа в Microsoft Defender работает в пассивном режиме или в активном режиме. EDR режиме блокировки обеспечивает еще один уровень защиты с Помощью Microsoft Defender для конечной точки. Это позволяет Defender для конечной точки принимать действия на основе обнаружения EDR нарушений. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Повлияет ли EDR в режиме блокировки на антивирусную защиту пользователя? 

EDR режиме блокировки не влияет на сторонную антивирусную защиту, запущенную на устройствах пользователей. EDR в режиме блокировки работает, если основное антивирусное решение что-то пропускает или если обнаружено сообщение о нарушении. EDR режиме блокировки работает так же, как [антивирусная программа в Microsoft Defender в](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)пассивном режиме, за исключением того, что он также блокирует и устраняет обнаруженные вредоносные артефакты или поведение. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Почему мне нужно поддерживать антивирусная программа в Microsoft Defender в курсе? 

Поскольку антивирусная программа в Microsoft Defender обнаруживает и устраняет вредоносные элементы, важно поддерживать его в курсе. Чтобы EDR режиме блокировки был эффективным, он использует новейшие модели обучения устройств, поведенческие обнаружения и heuristics. Пакет [возможностей Defender для конечной](https://docs.microsoft.com/windows/security/threat-protection) точки работает комплексно. Чтобы получить наилучшее значение защиты, антивирусная программа в Microsoft Defender быть в курсе.  

### <a name="why-do-we-need-cloud-protection-on"></a>Зачем нужна облачная защита? 

Чтобы включить функцию на устройстве, требуется облачная защита. Облачная защита позволяет [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) предоставлять последнюю и наибольшую защиту с учетом широты и глубины сведений о безопасности, а также моделей обучения поведения и устройств.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Как настроить антивирусная программа в Microsoft Defender пассивный режим?

См. [антивирусная программа в Microsoft Defender включить и подтвердить, что он в пассивном режиме.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Как подтвердить, что антивирусная программа в Microsoft Defender находится в активном или пассивном режиме?

Чтобы подтвердить, антивирусная программа в Microsoft Defender работает в активном или пассивном режиме, можно использовать командную подсказку или PowerShell на устройстве с Windows.

#### <a name="use-powershell"></a>Воспользуйтесь PowerShell

1. Выберите меню Пуск, начните вводить, а затем `PowerShell` откройте Windows PowerShell в результатах.

2. Тип `Get-MpComputerStatus`.

3. В списке результатов в строке **AMRunningMode** посмотрите одно из следующих значений:
   - `Normal` - Служба Defender работает нормально. Специальные режимы не включены.
   - `Passive Mode`- Если ваша организация использует Microsoft Defender для конечной точки вместе с решением, не использующим антивирусное или антивирусное программное обеспечение, антивирусная программа в Microsoft Defender автоматически переходит в пассивный режим. (Защита и угрозы в режиме реального времени не устраняются антивирусная программа в Microsoft Defender.)
   - `SxS Passive Mode`- Аналогично пассивному режиму, но с возможностью включить ограниченное периодическое сканирование.
   
Дополнительные данные см. в дополнительных данных [get-MpComputerStatus.](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)

#### <a name="use-command-prompt"></a>Использование командной подсказки

1. Выберите меню "Пуск", начните вводить, а `Command Prompt` затем откройте Windows командную подсказку в результатах.

2. Тип `sc query windefend`.

3. В списке результатов в строке **STATE** подтвердим, что служба запущена.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Сколько времени необходимо для отключения EDR в режиме блокировки?

Если вы решили отключить EDR в режиме блокировки, для отключения этой возможности может занять до 30 минут.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Поддерживается EDR в режиме блокировки в Windows Server 2016?

Нет. EDR в режиме блокировки поддерживается следующих версий Windows:

- Windows 10 (все выпуски)
- Windows Сервер, версия 1803 или более новая 
- Windows Server 2019 

## <a name="see-also"></a>См. также

- [Блог Community технологий: введение EDR в режиме блокировки: остановка атак в их треках](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Блокировка с учетом поведения и автономность](behavioral-blocking-containment.md)
- [Вместе лучше: антивирусная программа в Microsoft Defender и Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

