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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: d8396c352e593f9922b11e23119f7d9718eaf752
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934229"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Управление microsoft Defender для конечной точки с помощью Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Мы рекомендуем использовать [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem)который включает Microsoft Intune (Intune) для управления функциями защиты от угроз для устройств (также именуемой конечными точками). [Дополнительные информацию о endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview).

В этой статье описывается, как найти параметры Microsoft Defender для конечных точек в Intune, а также перечислены различные задачи, которые можно выполнить.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Найдите параметры Microsoft Defender для конечных точек в Intune

> [!IMPORTANT]
> Чтобы настроить параметры, описанные в этой статье, необходимо быть глобальным администратором или администратором службы в Intune. Дополнительные новости см. **[в рубке Типы администраторов (Intune).](https://docs.microsoft.com/mem/intune/fundamentals/users-add#types-of-administrators)**

1. Перейдите на портал Azure [https://portal.azure.com](https://portal.azure.com) () и войдите.

2. В **azure Services** выберите **Intune**.

3. В области навигации слева выберите конфигурацию **устройства,** а затем в **статье Управление** выберите **Профили.**

4. Выберите существующий профиль или создайте новый.

> [!TIP]
> Нужна помощь? См. **[в этой ссылке Использование Microsoft Defender для конечной точки с помощью Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Настройка Microsoft Defender для конечной точки с помощью Intune

В следующей таблице перечислены различные задачи, которые можно выполнить для настройки Microsoft Defender для конечной точки с помощью Intune. Вам не нужно настраивать все сразу; выберите задачу, прочитайте соответствующие ресурсы и приступим.

|Task  |Дополнительные ресурсы  |
|---------|---------|
|**Управление устройствами организации с помощью Intune** для защиты этих устройств и данных, хранимых на них     |[Защита устройств с помощью Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/device-protect)         |
|**Интеграция Microsoft Defender для конечной точки с Intune** в качестве решения для защиты от мобильных угроз <br/>*(для устройств и устройств с Windows 10 или более поздней версии)*   |[Обеспечение соответствия требованиям для Microsoft Defender для конечной точки с условным доступом в Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)         |
|**Использование условного доступа для** управления устройствами и приложениями, которые могут подключаться к вашим ресурсам электронной почты и компании |[Настройка условного доступа в Microsoft Defender для конечной точки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Настройка параметров антивируса Microsoft Defender** с помощью поставщика служб конфигурации политики [(CSP политики)](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) |[Ограничения устройства: антивирус Microsoft Defender](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[CSP политики — Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)  | 
|**При необходимости укажите исключения для антивируса Microsoft Defender** <br/><br/>*Как правило, вам не нужно применять исключения. Антивирус Microsoft Defender включает ряд автоматических исключений, основанных на известных действиях операционной системы и типичных файлах управления, например используемых в корпоративном управлении, управлении базами данных и других корпоративных сценариях.* |[Рекомендации по проверке вирусов для корпоративных компьютеров, которые в настоящее время поддерживаются версиями Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Ограничения устройств: исключения антивирусов Microsoft Defender для устройств Windows 10](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Настройка исключений антивируса Microsoft Defender на Windows Server 2016 или 2019](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Настройте правила уменьшения поверхности атак,** чтобы настроить целевое поведение программного обеспечения, которое часто используется злоумышленниками.<br/><br/>*Сначала настройте правила уменьшения поверхности атаки в [режиме аудита](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender) (не менее одной недели и до двух месяцев). Вы можете отслеживать состояние с помощью Power BI [(получить наш](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)шаблон), а затем установить эти правила в активном режиме, когда вы будете готовы.* |[Режим аудита в Microsoft Defender для конечной точки ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Защита конечной точки: уменьшение поверхности атаки](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Узнайте больше о правилах уменьшения поверхности атаки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Блог сообщества tech: Demystifying правила уменьшения поверхности атаки - часть 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Настройка фильтрации сети для** блокировки исходящие подключения из любого приложения к IP-адресам или доменам с низкой репутацией  <br/><br/>*Фильтрация сети также называется [сетевой защитой.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/network-protection)*<br/><br/>*Убедитесь, что на устройствах Windows 10 установлены последние обновления платформы [антивирусных](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) программ.*|[Защита конечных точек: фильтрация сети](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Просмотр событий защиты сети в Windows Event Viewer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей <br/><br/>*[Управляемый доступ к папкам](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) также называется защитой от антивирусных программ.*  |[Защита конечной точки: доступ к управляемой папке](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Включить управляемый доступ к папкам в Intune](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Настройка защиты от эксплойтов** для защиты устройств организации от вредоносных программ, использующих эксплойты для распространения и заражения других устройств. <br/><br/> *[Защита от эксплойтов](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exploit-protection) также называется Exploit Guard.* |[Защита конечных точек: защита от использования защитника Майкрософт](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Включить защиту эксплойтов в Intune](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Настройте Microsoft Defender SmartScreen** для защиты от вредоносных сайтов и файлов в Интернете. <br/><br/> *Microsoft Edge должен быть установлен на устройствах организации. Для защиты в браузерах Google Chrome и FireFox настройте защиту от эксплойтов.*  |[SmartScreen защитника Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Ограничения устройства: SmartScreen защитника Майкрософт](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Параметры политики для управления SmartScreen в Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Настройка брандмауэра Microsoft Defender,** чтобы блокировать несанкционированный сетевой трафик, который втекает на устройства организации или выходит из нее.  |[Защита конечной точки: брандмауэр Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Брандмауэр Microsoft Defender с расширенным обеспечением безопасности](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Настройка шифрования и BitLocker для** защиты информации на устройствах организации под управлением Windows |[Защита конечной точки: шифрование Windows](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker для устройств Windows 10](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Настройка microsoft Defender Credential Guard для** защиты от атак кражи учетных данных |Для Windows 10, Windows Server 2016 и Windows Server 2019 см. в руб. Защита конечных точек: Защита учетных [данных защитника Майкрософт](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>В Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 и Windows Server 2012 R2 см. в статье Смягчение атак [pass-the-Hash (PtH)](https://www.microsoft.com/download/details.aspx?id=36036) и других краж учетных данных, версии 1 и 2  |
|**Настройте управление приложениями Microsoft Defender,** чтобы выбрать, следует ли проверять или доверять приложениям на устройствах организации <br/><br/>*Управление приложениями Microsoft Defender также называется [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview).*|[Развертывание политик управления приложениями Защитника Майкрософт с помощью Microsoft Intune](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Защита конечных точек: управление приложениями Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|
|**Настройка доступа к устройствам** и периферийным устройствам USB для предотвращения угроз в несанкционированных периферийных устройствах от компрометации устройств |[Управление USB-устройствами и другими съемными носители с помощью Microsoft Defender для конечной точки и Intune](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Настройка центра безопасности Microsoft Defender

Если вы еще этого не сделали, настройте центр безопасности **Microsoft Defender** Для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности [https://securitycenter.windows.com](https://securitycenter.windows.com) организации. 

Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть в Центре безопасности Microsoft Defender.

- [Обзор Центра безопасности Защитника Майкрософт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Защита конечной точки: Центр безопасности Защитника Майкрософт](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Дальнейшие действия

- [Обзор управления угрозами и уязвимостью](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Посетите панель мониторинга операций безопасности Центра безопасности Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)
