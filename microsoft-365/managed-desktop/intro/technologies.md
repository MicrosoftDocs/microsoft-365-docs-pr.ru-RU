---
title: Технологии компьютеров, управляемых Майкрософт
description: В этой статье перечислены технологии и приложения, используемые на компьютерах, управляемых Майкрософт.
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 70e4eb442f9c0e52dbf234280205dd908c135b8d
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233112"
---
# <a name="microsoft-managed-desktop-technologies"></a>Технологии компьютеров, управляемых Майкрософт

В этой статье перечислены технологии и приложения, используемые на компьютерах, управляемых Майкрософт.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Для всех пользователей компьютеров, управляемых Майкрософт, требуется лицензирование Microsoft 365 корпоративный. Дополнительные сведения о требованиях к лицензированию для службы см. в предварительных [требованиях для компьютеров,](../get-ready/prerequisites.md)управляемых Майкрософт.

В этой статье кратко описаны компоненты, включенные в необходимые корпоративные лицензии, а также описано, как служба использует каждый компонент на устройствах, управляемых Майкрософт. Конкретные роли и обязанности для каждой области подробно описаны в документации microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 или E5
 |
 --- | ---
Приложения Microsoft 365 для предприятий (64-битная) | Эти приложения Office будут поставляться с устройством: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype для бизнеса, OneNote.<br><br>64-битные полные версии Microsoft Project и Microsoft Visio не включены. Однако поскольку установка этих приложений зависит от установки приложений Microsoft 365 для предприятий, на компьютере, управляемом Майкрософт, созданы развертывания Microsoft Intune и группы безопасности по умолчанию, которые затем можно использовать для развертывания этих приложений для лицензированных пользователей. Дополнительные сведения см. в записи [установки Microsoft Project или Microsoft Visio на устройствах,](../get-started/project-visio.md)управляемых Майкрософт.
OneDrive |Единый вход Azure Active Directory включен для пользователей при первом входе в OneDrive.<br><br>Включено перенаправление известных папок для папок "Рабочий стол", "Документ" и "Изображения"; включено и настроено на компьютерах, управляемых Майкрософт.
Приложения Магазина |    Microsoft Sway и Power BI не поставляются вместе с устройством. Эти приложения доступны для скачивания из Microsoft Store.
Приложения Win32 |    Teams не поставляется вместе с устройством, но упаковывается и предоставляется корпорацией Майкрософт для настольных устройств, управляемых Майкрософт. Клиент Azure Information Protection не поставляется вместе с устройством, но его можно упаковить для развертывания.
Веб-приложения |  Yammer, Office в браузере, Delve, Flow, StaffHub, PowerApps и Планировщике не поставляются вместе с устройством. Пользователи могут получить доступ к веб-версии этих приложений с помощью браузера.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Корпоративная E5 или E3 с Microsoft Defender для конечной точки
ИТ-администраторам рекомендуется настроить следующие параметры. Эти параметры не включаются и не управляются в составе компьютеров, управляемых Майкрософт.

 |
 --- | ---
Windows Hello для бизнеса | Необходимо реализовать Windows Hello для бизнеса, чтобы заменить пароли на надежные двух коэффициенты проверки подлинности для настольных устройств, управляемых Майкрософт. Дополнительные сведения см. в [windows Hello для бизнеса.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Виртуализация приложений | Пакеты Application Virtualization (App-V) можно развернуть с помощью клиента управления приложениями Intune Win32. Дополнительные сведения [см. в виртуализации приложений.](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference)
Предотвращение потери данных в Microsoft 365 | Необходимо реализовать службу защиты от потери данных Microsoft 365, чтобы отслеживать действия, которые выполняются с элементами, которые вы определили как конфиденциальные, и предотвращать непреднамеренное совместное использование этих элементов. Дополнительные сведения см. в [microsoft 365 data loss prevention.](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)


Функции, включенные и управляемые в составе компьютеров, управляемых Майкрософт:

 |
 --- | ---
Шифрование диска BitLocker | Шифрование диска BitLocker используется для шифрования всех системных дисков. Дополнительные сведения см. в [подшифровке bitLocker Drive Encryption.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
Защитник Windows System Guard | Защищает целостность системы при запуске и проверяет, действительно ли она поддерживается. Дополнительные сведения [см. в Защитник Windows System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Credential Guard в Защитнике Windows | Защитник Windows Credential Guard использует безопасность на основе виртуализации для изоляции секретов, чтобы доступ к ним было только привилегированным системным программным обеспечением. Дополнительные сведения [см. в Защитник Windows System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender for Endpoint - Endpoint Detection and Response | Microsoft Managed Desktop Security Operations реагирует на оповещения и принимает меры для устранения угроз с помощью обнаружения конечных точек и реагирования на них. Дополнительные сведения см. в [microsoft Defender for Endpoint - Endpoint Detection and Response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response).
Microsoft Defender для конечной точки — эксперты по угрозам | Компьютеры, управляемые Майкрософт, интегрируются с анализом и данными специалистов по угрозам с помощью целевых уведомлений о атаках. Прежде чем эта служба будет включена, необходимо предоставить дополнительное согласие. Дополнительные сведения см. в [microsoft Defender for Endpoint — Threat Experts.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender for Endpoint - Threat and Vulnerability Management | Требуется для дальнейшего использования в плане обслуживания компьютеров, управляемых Майкрософт. Дополнительные сведения см. в [microsoft Defender for Endpoint - Threat and Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).
Microsoft Defender for Endpoint - Attack Surface Reduction | Сокращение поверхности атаки нацелено на рискованные программы, которые часто используются злоумышленниками. Дополнительные сведения см. в [microsoft Defender for Endpoint - Attack Surface Reduction](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).
Microsoft Defender для конечной точки — Защита от эксплойтов | Защищает от вредоносных программ, которые используют эксплойты для заражения устройств и распространения путем автоматического применения методов защиты от эксплойтов к процессам операционной системы и приложениям. Дополнительные сведения см. в [microsoft Defender for Endpoint — Защита от эксплойтов.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender for Endpoint - Network Protection | Защита сети расширяет область smartScreen в Microsoft Defender, чтобы блокировать весь исходящие трафик HTTP и HTTPS, которые пытаются подключиться к источникам с низкой репутацией. Дополнительные сведения см. в [microsoft Defender for Endpoint - Network Protection.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Защита от взлома в Microsoft Defender | Защита от взлома Windows используется для предотвращения изменения параметров безопасности, таких как защита от вирусов. Дополнительные сведения см. в под защитой от взлома [в Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Антивирусная защита от вирусов в Microsoft Defender, а также защита от вирусов в режиме реального времени | Всегда сканировать на угрозы файлов и процессов, которые не могут быть обнаружены как вредоносные программы. Дополнительные сведения см. в антивирусной защите на основе вирусов в Microsoft Defender, а также в антивирусной защите в режиме [реального времени.]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
Облачная защита антивирусной программы "Microsoft Defender" | Обеспечивает динамическую автоматическую защиту от новых и возникающих угроз практически мгновенно. Дополнительные сведения см. в антивирусной защите Microsoft [Defender Cloud-delivered Protection.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Блокировать при первом виде" | Обеспечивает обнаружение и блокировку новых вредоносных программ, когда Windows обнаруживает подозрительный или неизвестный файл. Дополнительные сведения см. в [блоке Microsoft Defender при первом виде.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Потенциально нежелательные приложения в microsoft Defender | Потенциально нежелательные приложения используются для блоки приложений, которые могут привести к медленному запуску компьютера, показу непредвиденных объявлений или установке другого программного обеспечения, которое может быть непредвиденным или нежелательным. Дополнительные сведения см. в записи av [в Microsoft Defender Potentially Unwanted Applications.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Защитник Windows брандмауэра с расширенными мерами безопасности | Двунаправная фильтрация сетевого трафика на основе хоста для устройства, Защитник Windows брандмауэр блокирует несанкционированный сетевой трафик, который проходит в локальное устройство или из него. Дополнительные сведения см. [в Защитник Windows брандмауэра с расширенными службами безопасности.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Контроль учетных записей пользователей | Контроль учетных записей пользователей переключается на безопасный рабочий стол, если для задачи или действия требуется доступ типа учетной записи администратора. Пользователям компьютеров, управляемых Майкрософт, при регистрации будет назначен стандартный доступ пользователей. Дополнительные сведения см. в [под управлением учетных записей пользователей.](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Для управления устройствами MDM можно использовать все функции Enterprise Mobility + Security E3 и Azure Active Directory Premium P2.
Microsoft Cloud App Security |  Эту дополнительную функцию можно использовать с компьютером, управляемым Майкрософт.
Azure Information Protection P2  | Эту дополнительную функцию можно использовать с компьютером, управляемым Майкрософт.
