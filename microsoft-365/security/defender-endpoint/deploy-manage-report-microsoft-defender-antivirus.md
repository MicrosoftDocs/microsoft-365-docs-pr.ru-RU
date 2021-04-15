---
title: Развертывание, управление и отчет об антивирусе Microsoft Defender
description: Антивирус Microsoft Defender можно развернуть и управлять ими с помощью Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell или WMI.
keywords: развертывание, управление, обновление, защита, антивирус Microsoft Defender
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
ms.openlocfilehash: b44bc529a14d12d2be49854c31a4ea11cdabc7d1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764847"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Развертывание, управление и отчет об антивирусе Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Можно развернуть, управлять антивирусом Microsoft Defender и сообщить о них по ряду способов.

Так как антивирусный клиент Microsoft Defender установлен в качестве основной части Windows 10, традиционное развертывание клиента в конечных точках не применяется.

Однако в большинстве случаев вам все равно потребуется включить службу защиты на конечных точках с помощью Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender или Объекты групповой политики, которые описаны в следующей таблице.

Вы также увидите дополнительные ссылки для:

- Управление антивирусной защитой Microsoft Defender, включая управление обновлениями продуктов и защиты
- Отчеты о защите антивируса Microsoft Defender

> [!IMPORTANT]
> В большинстве случаев Windows 10 отключает антивирус Microsoft Defender, если он находит другой антивирусный продукт, который запущен и устарел. Необходимо отключить или удалить сторонние антивирусные продукты до того, как будет функционировать антивирус Microsoft Defender. Если вы повторно включаете или устанавливаете сторонние антивирусные продукты, Windows 10 автоматически отключает антивирус Microsoft Defender.

Средство|Параметры развертывания<a href="#fn2" id="ref2">(2)</a>|Параметры управления (конфигурация по всей сети, политика или базовое развертывание)[(3)](#fn3)|Параметры отчетности  
---|---|---|---  
Microsoft Intune|[Добавление параметров защиты конечных точек в Intune](/intune/endpoint-protection-configure)|[Настройка параметров ограничения устройств в Intune](/intune/device-restrictions-configure)| [Использование консоли Intune для управления устройствами](/intune/device-management)  
Microsoft Endpoint Manager[(1)](#fn1)|Используйте роль [системной системы точки защиты][] конечных точек и [встань в endpoint Protection с настраиваемой клиентской настройкой][]|С [политиками по умолчанию и настраиваемыми политиками антивирусного обеспечения][] и [управлением клиентами][]|С помощью рабочего [пространства диспетчера конфигурации по умолчанию][] и оповещений [электронной почты][]  
Group Policy and Active Directory (domain-joined)|Используйте объект групповой политики для развертывания изменений конфигурации и обеспечения включения антивируса Microsoft Defender.|Используйте объекты групповой политики (GPOs) для настройки параметров обновления антивируса [Microsoft Defender][] и настройки [Защитник Windows функций][]|Отчеты конечной точки недоступны для групповой политики. Можно создать список [групповых политик,][] чтобы определить, не применяются ли какие-либо параметры или политики.
PowerShell|Развертывание с помощью групповой политики, Microsoft Endpoint Configuration Manager или вручную на отдельных конечных точках.|Используйте [командлеты Set-MpPreference] и [Update-MpSignature,] доступные в модуле Defender.|Используйте соответствующие [командлеты Get-cmdlets, доступные в модуле Defender][]
Инструментарий управления Windows (WMI)|Развертывание с помощью групповой политики, Microsoft Endpoint Configuration Manager или вручную на отдельных конечных точках.|Используйте [метод Set класса MSFT_MpPreference и][] метод Update класса [MSFT_MpSignature][]|Используйте [класс MSFT_MpComputerStatus][] и метод получения связанных классов [в поставщике WMIv2 Защитник Windows WMIv2][]
Microsoft Azure|Развертывание microsoft Antimalware для Azure на портале Azure с помощью Visual Studio конфигурации виртуальных машин или с помощью скоммлетов [Azure PowerShell.](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) Вы также можете [установить защиту конечных точек в Azure Defender*](/azure/security-center/security-center-install-endpoint-protection)|Настройка microsoft Antimalware для виртуальных машин и облачных служб с помощью [cmdlets Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) или [использование примеров кода](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Чтобы включить мониторинг, используйте microsoft Antimalware для виртуальных машин и облачных служб с помощью [cmdlets Azure PowerShell.](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) Вы также можете просмотреть отчеты об использовании в Azure Active [][] Directory для определения подозрительной активности, включая отчет о возможно зараженных устройствах, а также настроить средство SIEM для отчета о событиях антивируса [Microsoft Defender][] и добавления этого средства в качестве приложения в AAD.

1. <span id="fn1" />Доступность некоторых функций и функций, особенно связанных с облачной защитой, отличается от Microsoft Endpoint Manager (Current Branch) и System Center 2012 Configuration Manager. В этой библиотеке мы сосредоточились на Windows 10, Windows Server 2016 и Microsoft Endpoint Manager (Current Branch). См. в статье Использование облачной защиты Microsoft в [антивирусе Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) для таблицы, описываемой основными различиями. [(Возвращение в таблицу)](#ref2)
  
2.  <span id="fn2" />В Windows 10 антивирус Microsoft Defender — это компонент, доступный без установки или развертывания дополнительного клиента или службы. Он автоматически будет включен, если сторонние антивирусные продукты будут либо неустановлены, либо устарели (за исключением[Windows Server 2016).](microsoft-defender-antivirus-on-windows-server.md) Поэтому традиционное развертывание не требуется. Развертывание здесь относится к обеспечению того, чтобы антивирусный компонент Microsoft Defender был доступен и включен на конечных точках или серверах. [(Возвращение в таблицу)](#ref2)

3. <span id="fn3" />Конфигурация функций и защиты, включая настройку обновлений продукта и защиты, далее описана в разделе Настройка антивирусных функций [Microsoft Defender](configure-notifications-microsoft-defender-antivirus.md) в этой библиотеке. [(Возвращение в таблицу)](#ref2)

[Роль системы сайта точки защиты конечной точки]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[по умолчанию и настроенные политики противомалярийных программ]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[управление клиентом]:  /configmgr/core/clients/manage/manage-clients
[включить защиту конечных точек с настраиваемой настройкой клиента]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Рабочее пространство диспетчера конфигурации]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[оповещений электронной почты]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[Set method of the MSFT_MpPreference class]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[Метод обновления класса MSFT_MpSignature]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Защитник Windows поставщик WMIv2]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Командлеты get-cmdlets доступны в модуле Defender]: /powershell/module/defender/
[Настройка параметров обновления антивируса Microsoft Defender]: manage-updates-baselines-microsoft-defender-antivirus.md
[Настройка Защитник Windows]: configure-microsoft-defender-antivirus-features.md
[Групповые политики, чтобы определить, не применяются ли какие-либо параметры или политики]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Возможно зараженные устройства]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[События антивируса Microsoft Defender]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>В этом разделе

Статья | Описание
---|---
[Развертывание и развертывание антивирусной защиты Microsoft Defender](deploy-microsoft-defender-antivirus.md) | Хотя клиент установлен в качестве основной части Windows 10 и традиционное развертывание не применяется, вам все равно потребуется включить клиента на конечных точках с помощью Microsoft Endpoint Configuration Manager, Microsoft Intune или Объекты групповой политики. 
[Управление обновлениями антивируса Microsoft Defender и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md) | Обновление антивируса Microsoft Defender можно обновить двумя частями: обновление клиента на конечных точках (обновления продуктов) и обновление сведений о безопасности (обновления защиты). Сведения о безопасности можно обновить с помощью Microsoft Endpoint Configuration Manager, Group Policy, PowerShell и WMI.
[Мониторинг и отчет об антивирусной защите Защитника Майкрософт](report-monitor-microsoft-defender-antivirus.md) | Для мониторинга состояния защиты и создания отчетов о защите конечных точек можно использовать Microsoft Intune, Microsoft Endpoint Configuration Manager, надстройку update Compliance для Пакета управления операциями Майкрософт или сторонний продукт SIEM (с помощью журналов событий Windows).