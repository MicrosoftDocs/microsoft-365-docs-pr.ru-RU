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
ms.openlocfilehash: 1b8f2e7c7435f2161f7261722795b35ca848ec2f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934241"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Управление защитником Майкрософт для конечной точки с помощью объектов групповой политики

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Мы рекомендуем использовать [Microsoft Endpoint Manager](https://docs.microsoft.com/mem) для управления функциями защиты от угроз для устройств (также именуемой конечными точками). Endpoint Manager включает [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) и [Microsoft Endpoint Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) **[Дополнительные информацию о endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)**. 

Объекты групповой политики можно использовать в службах домена Azure Active Directory для управления некоторыми настройками в Microsoft Defender для конечной точки.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Настройка Microsoft Defender для конечной точки с помощью объектов групповой политики

В следующей таблице перечислены различные задачи, которые можно выполнить для настройки Microsoft Defender для конечной точки с объектами групповой политики.

|Task  |Дополнительные ресурсы  |
|---------|---------|
|**Управление настройками объектов пользователя и компьютера** <br/><br/>*Настройка встроенных объектов групповой политики или создание настраиваемых объектов групповой политики и организационных подразделений в соответствии с вашими организационными потребностями.*     |[Администрирование групповой политики в управляемом домене Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|**Настройка антивируса Microsoft Defender** <br/><br/>*Настройка функций антивирусного &, включая параметры политики, исключения, исправление и плановые проверки на устройствах организации (также именуемые конечными точками).*   |[Настройка и управление антивирусной программой Microsoft Defender с помощью параметров групповой политики](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Использование групповой политики для обеспечения облачной защиты](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Управление правилами уменьшения поверхности атак в организации** <br/><br/>*Настройте правила уменьшения поверхности атаки, исключив & папки или добавив настраиваемый текст в уведомления, которые отображаются на устройствах пользователей.* |[Настройка правил уменьшения поверхности атаки с помощью объектов групповой политики](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Управление настройками защиты от эксплойтов**<br/><br/>*Вы можете настроить параметры защиты от эксплойтов, импортировать файл конфигурации и затем использовать групповую политику для развертывания этого файла конфигурации.*  |[Настройка параметров защиты от эксплойтов](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Импорт, экспорт и развертывание конфигураций защиты от эксплойтов](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Использование групповой политики для распространения конфигурации](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Включить защиту сети,** чтобы предотвратить использование сотрудниками приложений с вредоносным контентом в Интернете <br/><br/>*Сначала рекомендуется использовать [режим аудита](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) для защиты сети в тестовой среде, чтобы узнать, какие приложения будут заблокированы перед развертыванием.* |[Включаем защиту сети с помощью групповой политики](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей <br/><br/>*[Управляемый доступ к папкам](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) также называется защитой от антивирусных программ.*  |[Включить управляемый доступ к папкам с помощью групповой политики](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Настройте Microsoft Defender SmartScreen** для защиты от вредоносных сайтов и файлов в Интернете.  |[Настройка параметров групповой политики Microsoft Defender SmartScreen и управления мобильными устройствами (MDM) с помощью групповой политики](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Настройка шифрования и BitLocker для** защиты информации на устройствах организации под управлением Windows |[Параметры групповой политики BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Настройка microsoft Defender Credential Guard для** защиты от атак кражи учетных данных |[Включить Защитник Windows учетных данных с помощью групповой политики](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Настройка центра безопасности Microsoft Defender

Если вы еще этого не сделали, настройте центр безопасности **Microsoft Defender** Для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности [https://securitycenter.windows.com](https://securitycenter.windows.com) организации. 

Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть в Центре безопасности Microsoft Defender.

- [Обзор Центра безопасности Защитника Майкрософт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Защита конечной точки: Центр безопасности Защитника Майкрософт](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Дальнейшие действия

- [Обзор управления угрозами и уязвимостью](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Посетите панель мониторинга операций безопасности Центра безопасности Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Управление microsoft Defender для конечной точки с помощью Intune](manage-atp-post-migration-intune.md)
