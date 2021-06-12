---
title: Управление Microsoft Defender для конечной точки с помощью Intune
description: Узнайте, как управлять Microsoft Defender для конечной точки с помощью Intune
keywords: после переноса, управления, операций, обслуживания, использования, intune, Microsoft Defender для конечной точки, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: ccbcbcb71d60dadf24b6f94bab126a1f1ca1c322
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908285"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Управление microsoft Defender для конечной точки с помощью Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Мы рекомендуем [использовать Microsoft Endpoint Manager,](/mem)который включает Microsoft Intune (Intune) для управления функциями защиты от угроз для устройств (также именуемой конечными точками). [Дополнительные дополнительные Endpoint Manager](/mem/endpoint-manager-overview).

В этой статье описывается, как найти параметры Microsoft Defender для конечных точек в Intune, а также перечислены различные задачи, которые можно выполнить.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Найдите параметры Microsoft Defender для конечных точек в Intune

> [!IMPORTANT]
> Чтобы настроить параметры, описанные в этой статье, необходимо быть глобальным администратором или администратором службы в Intune. Дополнительные новости см. **[в рубке Типы администраторов (Intune).](/mem/intune/fundamentals/users-add#types-of-administrators)**

1. Перейдите на портал Azure [https://portal.azure.com](https://portal.azure.com) () и войдите.

2. В **azure Services** выберите **Intune**.

3. В области навигации слева выберите конфигурацию **устройства,** а затем в **статье Управление** выберите **Профили.**

4. Выберите существующий профиль или создайте новый.

> [!TIP]
> Нужна помощь? См. **[в этой ссылке Использование Microsoft Defender для конечной точки с помощью Intune.](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Настройка Microsoft Defender для конечной точки с помощью Intune

В следующей таблице перечислены различные задачи, которые можно выполнить для настройки Microsoft Defender для конечной точки с помощью Intune. Вам не нужно настраивать все сразу; выберите задачу, прочитайте соответствующие ресурсы и приступим.

|Задача  |Дополнительные ресурсы  |
|---------|---------|
|**Управление устройствами организации с помощью Intune** для защиты этих устройств и данных, хранимых на них     |[Защита устройств с помощью Microsoft Intune](/mem/intune/protect/device-protect)         |
|**Интеграция Microsoft Defender для конечной точки с Intune** в качестве решения для защиты от мобильных угроз <br/>*(для android-устройств и устройств, работающих Windows 10 или более поздней версии)*   |[Обеспечение соответствия требованиям для Microsoft Defender для конечной точки с условным доступом в Intune](/mem/intune/protect/advanced-threat-protection)         |
|**Использование условного доступа для** управления устройствами и приложениями, которые могут подключаться к вашим ресурсам электронной почты и компании |[Настройка условного доступа в Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Настройка параметров антивирусная программа в Microsoft Defender с** помощью поставщика служб конфигурации политики [(CSP политики)](/windows/client-management/mdm/policy-configuration-service-provider) |[Ограничения устройства: антивирусная программа в Microsoft Defender](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[CSP политики — Microsoft Defender для конечной точки](/windows/client-management/mdm/policy-csp-defender)  | 
|**При необходимости укажите исключения для антивирусная программа в Microsoft Defender** <br/><br/>*Как правило, вам не нужно применять исключения. антивирусная программа в Microsoft Defender включает ряд автоматических исключений, основанных на известных действиях операционной системы и типичных файлах управления, например используемых в корпоративном управлении, управлении базами данных и других корпоративных сценариях.* |[Рекомендации по проверке вирусов для Enterprise компьютеров, на которые в настоящее время запущены поддерживаемые версии Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Ограничения устройств: антивирусная программа в Microsoft Defender исключений для Windows 10 устройств](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Настройка антивирусная программа в Microsoft Defender исключений на Windows Server 2016 или 2019 г.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Настройте правила уменьшения поверхности атак,** чтобы настроить целевое поведение программного обеспечения, которое часто используется злоумышленниками.<br/><br/>*Сначала настройте правила уменьшения поверхности атаки в [режиме аудита](/microsoft-365/security/defender-endpoint/audit-windows-defender) (не менее одной недели и до двух месяцев). Вы можете отслеживать состояние с Power BI (получить [наш](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)шаблон), а затем установить эти правила в активном режиме, когда вы будете готовы.* |[Режим аудита в Microsoft Defender для конечной точки ](/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Защита конечной точки: уменьшение поверхности атаки](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Узнайте больше о правилах уменьшения поверхности атаки](/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Tech Community блоге: Demystifying attack surface reduction rules - Part 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Настройка фильтрации сети для** блокировки исходящие подключения из любого приложения к IP-адресам или доменам с низкой репутацией  <br/><br/>*Фильтрация сети также называется [сетевой защитой.](/microsoft-365/security/defender-endpoint/network-protection)*<br/><br/>*Убедитесь, Windows 10 устройствам установлены [последние](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) обновления платформы антивирусных программ.*|[Защита конечных точек: фильтрация сети](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Просмотр событий защиты сети в Windows просмотра событий](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей <br/><br/>*[Управляемый доступ к папкам](/microsoft-365/security/defender-endpoint/controlled-folders) также называется защитой от антивирусных программ.*  |[Защита конечной точки: доступ к управляемой папке](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Включить управляемый доступ к папкам в Intune](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Настройка защиты от эксплойтов** для защиты устройств организации от вредоносных программ, использующих эксплойты для распространения и заражения других устройств. <br/><br/> *[Защита от эксплойтов](/microsoft-365/security/defender-endpoint/exploit-protection) также называется Exploit Guard.* |[Защита конечной точки: Exploit Guard в Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Включить защиту эксплойтов в Intune](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Настройка фильтр SmartScreen в Microsoft Defender** защиты от вредоносных сайтов и файлов в Интернете. <br/><br/> *Microsoft Edge должны быть установлены на устройствах организации. Для защиты в браузерах Google Chrome и FireFox настройте защиту от эксплойтов.*  |[фильтр SmartScreen в Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Ограничения устройства: фильтр SmartScreen в Microsoft Defender](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Параметры политики для управления SmartScreen в Intune](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Настройка брандмауэр в Microsoft Defender,** чтобы блокировать несанкционированный сетевой трафик, который пропускается на устройства организации или выходит из нее.  |[Защита конечных точек: брандмауэр в Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [брандмауэр в Microsoft Defender с расширенным обеспечением безопасности](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Настройка шифрования и BitLocker** для защиты информации на устройствах организации, работающих Windows |[Защита конечной точки: Windows шифрование](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker для Windows 10 устройств](/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Настройка microsoft Defender Credential Guard для** защиты от атак кражи учетных данных |В Windows 10, Windows Server 2016 и Windows Server 2019 см. в руб. Защита конечных точек: защита учетных данных [защитника Майкрософт](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>В Windows 7 SP1 Windows Сервер 2008 R2 SP1, Windows 8.1 и Windows Server 2012 R2 см. в статье Смягчение атак [pass-the-Hash (PtH)](https://www.microsoft.com/download/details.aspx?id=36036) и других краж учетных данных версии 1 и 2  |
|**Настройте управление приложениями Microsoft Defender,** чтобы выбрать, следует ли проверять или доверять приложениям на устройствах организации <br/><br/>*Управление приложениями Microsoft Defender также называется [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview).*|[Развертывание политик управления приложениями Microsoft Defender с помощью Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Защита конечных точек: управление приложениями Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|**Настройка доступа к устройствам** и периферийным устройствам USB для предотвращения угроз в несанкционированных периферийных устройствах от компрометации устройств |[Управление USB-устройствами и другими съемными носители с помощью Microsoft Defender для конечной точки и Intune](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Настройка Центр безопасности в Microsoft Defender

Если этого еще не сделано, настройте портал Microsoft 365 Defender для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности организации. См. [Центр безопасности в Microsoft Defender](microsoft-defender-security-center.md). Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть на портале Microsoft 365 Defender.

- [Обзор Центр безопасности в Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Защита конечных точек: Центр безопасности в Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Дальнейшие действия

- [Получите обзор контроль угроз и уязвимостей](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Посетите панель мониторинга Центр безопасности в Microsoft Defender операций безопасности](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
