---
title: Управление microsoft Defender для конечной точки с помощью объектов групповой политики
description: Узнайте, как управлять Microsoft Defender для конечной точки с помощью объектов групповой политики
keywords: после миграции, управления, операций, обслуживания, использования, PowerShell, Microsoft Defender для endpoint, edr
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
ms.openlocfilehash: 15902e02156c59ec4edaed94f4ba321094bd42ac
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843026"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Управление защитником Майкрософт для конечной точки с помощью объектов групповой политики

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Рекомендуется использовать [Microsoft Endpoint Manager](/mem) для управления функциями защиты от угроз для устройств (также именуемой конечными точками). Endpoint Manager [включает](/mem/intune/fundamentals/what-is-intune) Microsoft Intune [и Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction). **[Дополнительные дополнительные Endpoint Manager](/mem/endpoint-manager-overview)**. 

Объекты групповой политики можно использовать в Azure Active Directory доменных службах для управления некоторыми настройками в Microsoft Defender для конечной точки.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Настройка Microsoft Defender для конечной точки с помощью объектов групповой политики

В следующей таблице перечислены различные задачи, которые можно выполнить для настройки Microsoft Defender для конечной точки с объектами групповой политики.

|Задача  |Дополнительные ресурсы  |
|---------|---------|
|**Управление настройками объектов пользователя и компьютера** <br/><br/>*Настройка встроенных объектов групповой политики или создание настраиваемых объектов групповой политики и организационных подразделений в соответствии с вашими организационными потребностями.*     |[Администрирование групповой политики в управляемом домене Azure Active Directory служб домена](/azure/active-directory-domain-services/manage-group-policy)   |
|**Настройка антивирусная программа в Microsoft Defender** <br/><br/>*Настройка функций антивирусного &, включая параметры политики, исключения, исправление и плановые проверки на устройствах организации (также именуемые конечными точками).*   |[Используйте параметры групповой политики для настройки и управления антивирусная программа в Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Использование групповой политики для обеспечения облачной защиты](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Управление правилами уменьшения поверхности атак в организации** <br/><br/>*Настройте правила уменьшения поверхности атаки, исключив & папки или добавив настраиваемый текст в уведомления, которые отображаются на устройствах пользователей.* |[Настройка правил уменьшения поверхности атаки с помощью объектов групповой политики](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Управление настройками защиты от эксплойтов**<br/><br/>*Вы можете настроить параметры защиты от эксплойтов, импортировать файл конфигурации и затем использовать групповую политику для развертывания этого файла конфигурации.*  |[Настройка параметров защиты от эксплойтов](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Импорт, экспорт и развертывание конфигураций защиты от эксплойтов](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Использование групповой политики для распространения конфигурации](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Включить защиту сети,** чтобы предотвратить использование сотрудниками приложений с вредоносным контентом в Интернете <br/><br/>*Сначала рекомендуется использовать [режим аудита](/microsoft-365/security/defender-endpoint/evaluate-network-protection) для защиты сети в тестовой среде, чтобы узнать, какие приложения будут заблокированы перед развертыванием.* |[Включаем защиту сети с помощью групповой политики](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей <br/><br/>*[Управляемый доступ к папкам](/microsoft-365/security/defender-endpoint/controlled-folders) также называется защитой от антивирусных программ.*  |[Включить управляемый доступ к папкам с помощью групповой политики](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Настройка фильтр SmartScreen в Microsoft Defender** защиты от вредоносных сайтов и файлов в Интернете.  |[Настройка параметров фильтр SmartScreen в Microsoft Defender групповой политики и управления мобильными устройствами (MDM) с помощью групповой политики](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Настройка шифрования и BitLocker** для защиты информации на устройствах организации, работающих Windows |[BitLocker Параметры групповой политики](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Настройка microsoft Defender Credential Guard для** защиты от атак кражи учетных данных |[Включить Credential Guard в Защитнике Windows с помощью групповой политики](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Настройка Центр безопасности в Microsoft Defender

Если вы еще этого не сделали, настройте Центр безопасности в Microsoft Defender **()** для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности [https://securitycenter.windows.com](https://securitycenter.windows.com) организации. 

Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть в Центр безопасности в Microsoft Defender.

- [Обзор Центр безопасности в Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Защита конечных точек: Центр безопасности в Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Дальнейшие действия

- [Получите обзор контроль угроз и уязвимостей](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Посетите панель мониторинга Центр безопасности в Microsoft Defender операций безопасности](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Управление microsoft Defender для конечной точки с помощью Intune](manage-atp-post-migration-intune.md)
