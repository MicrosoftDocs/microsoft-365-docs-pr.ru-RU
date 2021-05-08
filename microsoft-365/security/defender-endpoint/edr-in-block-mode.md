---
title: Обнаружение конечных точек и реагирование в режиме блокировки
description: Узнайте об обнаружении конечных точек и ответе в режиме блокировки
keywords: Microsoft Defender для конечной точки, mde, EDR в режиме блока, блокировка пассивного режима
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
ms.date: 05/06/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 78201fd20d689a6774eb5395aa787a2b15147972
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274488"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Обнаружение конечных точек и ответ (EDR) в режиме блокировки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Что такое EDR в режиме блокировки?

[Обнаружение и ответ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) конечной точки (EDR) в режиме блокировки обеспечивают защиту от вредоносных артефактов, даже если антивирус Microsoft Defender работает в пассивном режиме. При включении EDR в режиме блокировки блокирует вредоносные артефакты или поведение, обнаруженные на устройстве. EDR в режиме блокировки работает за кулисами для устранения вредоносных артефактов, которые обнаруживаются после нарушения. 

EDR в режиме блокировки также интегрирован с управлением [& уязвимостей.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Команда безопасности организации получит рекомендации [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) по безопасности, чтобы включить EDR в режиме блокировки, если она еще не включена. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="рекомендация включить EDR в режиме блокировки":::

> [!NOTE]
> Чтобы получить лучшую защиту, убедитесь в развертывании базовых показателей **[Microsoft Defender для конечных точек.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>Что происходит при обнаружении чего-либо?

Когда EDR в режиме блокировки включен и обнаружен вредоносный артефакт, Microsoft Defender для конечных точек блокирует и устраняет этот артефакт. Ваша группа операций безопасности будет  видеть  состояние обнаружения заблокированным или предотвращенным в центре действий, [](respond-machine-alerts.md#check-activity-details-in-action-center)указанным в качестве завершенных действий.

На следующем изображении показан экземпляр нежелательного программного обеспечения, которое было обнаружено и заблокировано через EDR в режиме блокировки:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR в режиме блокировки обнаружил что-то":::


## <a name="enable-edr-in-block-mode"></a>Включить EDR в режиме блокировки

> [!IMPORTANT]
> Убедитесь, [что требования](#requirements-for-edr-in-block-mode) будут выполнены перед включением EDR в режиме блокировки.

1. Перейдите в Центр безопасности защитника Майкрософт [https://securitycenter.windows.com](https://securitycenter.windows.com) () и войдите. 

2. Выбор   >  **расширенных функций Параметры**.

3. Включив **EDR в режиме блокировки.**

> [!NOTE]
> EDR в режиме блокировки можно включить только в Центре безопасности Защитника Майкрософт. Чтобы включить или отключить EDR в режиме блокировки, нельзя использовать клавиши реестра, intune или групповые политики.

## <a name="requirements-for-edr-in-block-mode"></a>Требования к EDR в режиме блокировки

|Требования  |Сведения  |
|---------|---------|
|Разрешения |Роль глобального администратора или администратора безопасности, назначенная в [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) См. [основные разрешения.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions) |
|Операционная система     |Одна из следующих версий: <br/>- Windows 10 (все выпуски) <br/>- Windows Server, версия 1803 или более новая <br/>- Windows Server 2019 <br/>- Windows Server 2016 (только если антивирус Microsoft Defender находится в активном режиме)     |
|Регистрация Windows E5     |Windows E5 включена в следующие подписки: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 вместе с предложением & защиты от угроз <br/><br/>См. [Компоненты](/microsoft-365/enterprise/microsoft-365-overview#components) [и функции и возможности для каждого плана.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Антивирусная программа в Microsoft Defender  |Антивирус Microsoft Defender должен быть установлен и запущен в активном или пассивном режиме. (Антивирус Microsoft Defender можно использовать вместе с антивирусным решением, не относя к Майкрософт.) [Подтвердим, что антивирус Microsoft Defender находится в активном или пассивном режиме.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Облачная защита |Убедитесь, что антивирус Microsoft Defender настроен таким образом, чтобы включена [облачная защита.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Клиент антивирусных программ Microsoft Defender |Убедитесь, что клиент устарел. С помощью PowerShell запустите в качестве администратора группу [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus) В **строке AMProductVersion** необходимо увидеть **4.18.2001.10** или выше. |
|Антивирусный движок Microsoft Defender |Убедитесь, что ваш двигатель устарел. С помощью PowerShell запустите в качестве администратора группу [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus) В **строке AMEngineVersion** вы должны увидеть **1.1.16700.2** или выше. |

> [!IMPORTANT]
> Чтобы получить наилучшее значение защиты, убедитесь, что антивирусное решение настроено для получения регулярных обновлений и основных функций, а также настройки [исключений.](configure-exclusions-microsoft-defender-antivirus.md) EDR в режиме блокировки касается исключений, определенных для антивируса Microsoft Defender.

## <a name="frequently-asked-questions"></a>Вопросы и ответы 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Нужно ли включить EDR в режиме блокировки даже при запуске антивируса Microsoft Defender на устройствах?

Рекомендуется поддерживать EDR в режиме блокировки, независимо от того, работает ли антивирус Microsoft Defender в пассивном или активном режиме. EDR в режиме блокировки обеспечивает еще один уровень защиты с Помощью Microsoft Defender для конечной точки. Это позволяет Защитнику для конечной точки принимать действия на основе обнаружения EDR после нарушения поведения. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Повлияет ли EDR в режиме блокировки на антивирусную защиту пользователя? 

EDR в режиме блокировки не влияет на сторонную антивирусную защиту, запущенную на устройствах пользователей. EDR в режиме блокировки работает, если основное антивирусное решение пропускает что-то или если обнаружено сообщение о нарушении. EDR в режиме блокировки работает так же, как [антивирус Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)в пассивном режиме, за исключением того, что блокирует и устраняет обнаруженные вредоносные артефакты или поведение. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Зачем нужно поддерживать антивирус Microsoft Defender в курсе? 

Так как антивирус Microsoft Defender обнаруживает и устраняет вредоносные элементы, важно поддерживать его в курсе. Чтобы EDR в режиме блокировки был эффективным, он использует новейшие модели обучения устройств, поведенческие обнаружения и heuristics. Пакет [возможностей Defender для конечной](microsoft-defender-endpoint.md) точки работает комплексно. Чтобы получить наилучшее значение защиты, необходимо сохранить антивирус Microsoft Defender в курсе. См. в руб. Управление обновлениями [антивируса Microsoft Defender и применение базовых показателей.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-on"></a>Зачем нужна облачная защита? 

Чтобы включить функцию на устройстве, требуется облачная защита. Облачная защита позволяет [Defender for Endpoint](microsoft-defender-endpoint.md) предоставлять последнюю и наибольшую защиту с учетом широты и глубины сведений о безопасности, а также моделей обучения поведения и устройств.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Как настроить антивирус Microsoft Defender на пассивный режим?

В зависимости от операционных систем, когда устройства, работающие с антивирусным и антивирусным решением, не от Microsoft, находятся на борту в Defender for Endpoint, антивирус Microsoft Defender может автоматически перейти в пассивный режим. Дополнительные сведения см. в [программах Antivirus и Microsoft Defender for Endpoint.](microsoft-defender-antivirus-compatibility.md#antivirus-and-microsoft-defender-for-endpoint) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Как подтвердить, что антивирус Microsoft Defender находится в активном или пассивном режиме?

Чтобы подтвердить, работает ли антивирус Microsoft Defender в активном или пассивном режиме, можно использовать командную подсказку или PowerShell на устройстве под управлением Windows.


|Метод  |Procedure  |
|---------|---------|
| PowerShell     | 1. Выберите меню Пуск, начните печатать и Windows PowerShell `PowerShell` в результатах. <p>2. Введите `Get-MpComputerStatus` . <p>3. В списке результатов в строке **AMRunningMode** посмотрите одно из следующих значений: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Дополнительные данные см. в дополнительных данных [get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus)        |
|Командная строка     | 1. Выберите меню "Пуск", начните печатать, а затем откройте командную подсказку `Command Prompt` Windows в результатах. <p>2. Введите `sc query windefend` . <p>3. В списке результатов в строке **STATE** подтвердим, что служба запущена.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Сколько времени необходимо для отключения EDR в режиме блокировки?

Если вы решили отключить EDR в режиме блокировки, для отключения этой возможности может занять до 30 минут.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Поддерживается ли EDR в режиме блокировки на Windows Server 2016?

Если антивирус Microsoft Defender работает в активном или пассивном режиме, EDR в режиме блокировки поддерживается следующими версиями Windows:

- Windows 10 (все выпуски)
- Windows Server, версия 1803 или более новая 
- Windows Server 2019 

Если в Windows Server 2016 антивирус Microsoft Defender работает в активном режиме, а конечная точка находится на борту в Defender для конечной точки, то EDR в режиме блокировки поддерживается. Тем не менее, EDR в режиме блокировки предназначен для дополнительной защиты, когда антивирус Microsoft Defender не является основным антивирусным решением на конечной точке. 

## <a name="see-also"></a>См. также

- [Блог сообщества tech: Введение EDR в режиме блокировки: остановка атак в их треках](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Блокировка с учетом поведения и автономность](behavioral-blocking-containment.md)
- [Вместе лучше: антивирусная программа в Microsoft Defender и Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

