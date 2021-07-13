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
ms.date: 06/11/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 835195f0c35ada409ef632b2dbfa1b6de0291351
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409156"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Обнаружение конечных точек и ответ (EDR) в режиме блокировки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Что EDR в режиме блокировки?

[Обнаружение конечных точек](overview-endpoint-detection-response.md) и ответ (EDR) в режиме блокировки обеспечивают защиту от вредоносных артефактов, даже если антивирусная программа в Microsoft Defender работает в пассивном режиме. При включенном EDR режиме блоки блокируют вредоносные артефакты или поведение, обнаруженные на устройстве. EDR режиме блокировки работает за кулисами для устранения вредоносных артефактов, обнаруженных после нарушения. 

EDR в режиме блокировки также интегрирована с угрозами [& управление уязвимостями.](next-gen-threat-and-vuln-mgt.md) Команда безопасности организации получит рекомендации [](tvm-security-recommendation.md) по безопасности, чтобы включить EDR в режиме блокировки, если она еще не включена. 

:::image type="content" source="images/enable-edr-in-block-mode.png" alt-text="рекомендация включить EDR в режиме блокировки":::

> [!NOTE]
> Чтобы получить лучшую защиту, убедитесь в развертывании базовых показателей **[Microsoft Defender для конечных точек.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Что происходит при обнаружении чего-либо?

Когда EDR в режиме блокировки и обнаружен вредоносный артефакт, Microsoft Defender для конечных точек блокирует и устраняет этот артефакт. Ваша группа операций безопасности будет  видеть  состояние обнаружения заблокированным или предотвращенным в центре действий, [](respond-machine-alerts.md#check-activity-details-in-action-center)указанным в качестве завершенных действий.

На следующем изображении показан экземпляр нежелательного программного обеспечения, которое было обнаружено и заблокировано EDR режиме блокировки:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR в режиме блокировки обнаружил что-то":::


## <a name="enable-edr-in-block-mode"></a>Включить EDR в режиме блокировки

> [!IMPORTANT]
> Убедитесь, [что требования](#requirements-for-edr-in-block-mode) будут выполнены перед включением EDR в режиме блокировки.

1. Перейдите на [портал Microsoft 365 Defender и](microsoft-defender-security-center.md) войдите. 

2. Выберите **Параметры**  >  **расширенные функции**.

3. **Включаем EDR в режиме блокировки.**

   > [!NOTE]
   > EDR режиме блокировки можно включить только на Microsoft 365 Defender портале. Вы не можете использовать клавиши реестра, политики Intune или группы, чтобы включить или отключить EDR в режиме блокировки.

## <a name="requirements-for-edr-in-block-mode"></a>Требования к EDR в режиме блокировки

|Требования  |Сведения  |
|---------|---------|
|Разрешения |Роль глобального администратора или администратора безопасности, назначенная [в Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). См. [основные разрешения.](basic-permissions.md) |
|Операционная система     |Одна из следующих версий: <br/>- Windows 10 (все выпуски) <br/>- Windows Server, версия 1803 или более новая <br/>- Windows Server 2019 <br/>- Windows Server 2016 (только если антивирусная программа в Microsoft Defender находится в активном режиме)     |
|Windows Регистрация на E5     |Windows E5 входит в следующие подписки: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 вместе с Безопасность Microsoft 365 E5 надстройка <br/><br/>См. [Компоненты](/microsoft-365/enterprise/microsoft-365-overview#components) [и функции и возможности для каждого плана.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Антивирусная программа в Microsoft Defender  |антивирусная программа в Microsoft Defender должны быть установлены и запущены в активном или пассивном режиме. (Вы можете использовать антивирусная программа в Microsoft Defender наряду с антивирусным решением, не относя к Майкрософт.) [Подтвердим антивирусная программа в Microsoft Defender находится в активном или пассивном режиме.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Облачная защита |Убедитесь, антивирусная программа в Microsoft Defender настраивается таким образом, чтобы включена [облачная защита.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|антивирусная программа в Microsoft Defender клиента антивирусного программного обеспечения |Убедитесь, что клиент устарел. С помощью PowerShell запустите в качестве администратора группу [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus) В **строке AMProductVersion** необходимо увидеть **4.18.2001.10** или выше. |
|антивирусная программа в Microsoft Defender |Убедитесь, что ваш двигатель устарел. С помощью PowerShell запустите в качестве администратора группу [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus) В **строке AMEngineVersion** вы должны увидеть **1.1.16700.2** или выше. |

> [!IMPORTANT]
> Чтобы получить наилучшее значение защиты, убедитесь, что антивирусное решение настроено для получения регулярных обновлений и основных функций, а также настройки [исключений.](configure-exclusions-microsoft-defender-antivirus.md) EDR режиме блокировки касается исключений, определенных для антивирусная программа в Microsoft Defender.

## <a name="frequently-asked-questions"></a>Вопросы и ответы 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Нужно ли включить EDR в режиме блокировки, даже если антивирусная программа в Microsoft Defender работает на устройствах?

Рекомендуется сохранять EDR в режиме блокировки, независимо от того, антивирусная программа в Microsoft Defender работает в пассивном режиме или в активном режиме. EDR режиме блокировки обеспечивает еще один уровень защиты с Помощью Microsoft Defender для конечной точки. Это позволяет Defender для конечной точки принимать действия на основе обнаружения EDR нарушений. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Повлияет ли EDR в режиме блокировки на антивирусную защиту пользователя? 

EDR режиме блокировки не влияет на сторонную антивирусную защиту, запущенную на устройствах пользователей. EDR в режиме блокировки работает, если основное антивирусное решение что-то пропускает или если обнаружено сообщение о нарушении. EDR режиме блокировки работает так же, как антивирусная программа в Microsoft Defender в пассивном режиме, за исключением того, что он также блокирует и устраняет обнаруженные вредоносные артефакты или поведение.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Почему мне нужно поддерживать антивирусная программа в Microsoft Defender в курсе? 

Поскольку антивирусная программа в Microsoft Defender обнаруживает и устраняет вредоносные элементы, важно поддерживать его в курсе. Чтобы EDR режиме блокировки был эффективным, он использует новейшие модели обучения устройств, поведенческие обнаружения и heuristics. Пакет [возможностей Defender для конечной](microsoft-defender-endpoint.md) точки работает комплексно. Чтобы получить наилучшее значение защиты, антивирусная программа в Microsoft Defender быть в курсе. См. [антивирусная программа в Microsoft Defender управление обновлениями и применение базовых показателей.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-on"></a>Зачем нужна облачная защита? 

Чтобы включить функцию на устройстве, требуется облачная защита. Облачная защита позволяет [Defender for Endpoint](microsoft-defender-endpoint.md) предоставлять последнюю и наибольшую защиту с учетом широты и глубины сведений о безопасности, а также моделей обучения поведения и устройств.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Как настроить антивирусная программа в Microsoft Defender пассивный режим?

В зависимости от операционных систем, когда устройства, работающие с антивирусным и антивирусным решением, не от Microsoft, находятся на борту в Defender for Endpoint, антивирусная программа в Microsoft Defender автоматически переходить в пассивный режим. Дополнительные сведения см. в [антивирусная программа в Microsoft Defender функции Defender для конечных точек.](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Как подтвердить, что антивирусная программа в Microsoft Defender находится в активном или пассивном режиме?

Чтобы подтвердить, антивирусная программа в Microsoft Defender работает в активном или пассивном режиме, можно использовать командную подсказку или PowerShell на устройстве с Windows.


|Метод  |Procedure  |
|---------|---------|
| PowerShell     | 1. Выберите меню , начните вводить, а затем `PowerShell` откройте Windows PowerShell в результатах. <p>2. Введите `Get-MpComputerStatus` . <p>3. В списке результатов в строке **AMRunningMode** посмотрите одно из следующих значений: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Дополнительные данные см. в дополнительных данных [get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus)        |
|Командная строка     | 1. Выберите меню , начните вводить, а затем `Command Prompt` откройте Windows командную подсказку в результатах. <p>2. Введите `sc query windefend` . <p>3. В списке результатов в строке **STATE** подтвердим, что служба запущена.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Сколько времени необходимо для отключения EDR в режиме блокировки?

Если вы решили отключить EDR в режиме блокировки, для отключения этой возможности может занять до 30 минут.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Поддерживается EDR в режиме блокировки в Windows Server 2016?

Если антивирусная программа в Microsoft Defender работает в активном или пассивном режиме, EDR в режиме блокировки поддерживается следующие версии Windows:

- Windows 10 (все выпуски)
- Windows Сервер, версия 1803 или более новая 
- Windows Server 2019 

Если Windows Server 2016 работает антивирусная программа в Microsoft Defender активном режиме, а конечная точка находится на борту в Defender для конечной точки, EDR в режиме блокировки технически поддерживается. Однако EDR в режиме блокировки предназначен для дополнительной защиты, антивирусная программа в Microsoft Defender не является основным антивирусным решением на конечной точке. В этих случаях антивирусная программа в Microsoft Defender в пассивном режиме. В настоящее время антивирусная программа в Microsoft Defender в пассивном режиме не поддерживается Windows Server 2016. Дополнительные новости см. [в антивирусная программа в Microsoft Defender антивирусных](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)и антивирусных решениях, не в microsoft.

## <a name="see-also"></a>См. также

- [Блог Community технологий: введение EDR в режиме блокировки: остановка атак в их треках](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Блокировка с учетом поведения и автономность](behavioral-blocking-containment.md)

