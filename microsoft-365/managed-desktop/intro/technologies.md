---
title: Технологии компьютеров, управляемых Майкрософт
description: В этой статье перечислены технологии и приложения, используемые в компьютеры, управляемые Майкрософт.
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d70bb133904a7bcc9c30721d3f723b0fd8b88512
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287967"
---
# <a name="microsoft-managed-desktop-technologies"></a>Технологии компьютеров, управляемых Майкрософт

В этой статье перечислены технологии и приложения, используемые в компьютеры, управляемые Майкрософт.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 корпоративный требуется лицензирование для всех компьютеры, управляемые Майкрософт пользователей. Дополнительные сведения о требованиях к лицензированию для службы см. в [компьютеры, управляемые Майкрософт.](../get-ready/prerequisites.md)

В этой статье кратко описаны компоненты, включенные в необходимые лицензии Enterprise, с описанием того, как служба использует каждый компонент с компьютеры, управляемые Майкрософт устройствами. Конкретные роли и обязанности для каждой области подробно описаны в компьютеры, управляемые Майкрософт документации. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 или E5

| Продукт |Информация |
--- |--- 
Приложения Microsoft 365 для предприятий (64-битный) | Эти Office будут поставляться с устройством: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype для бизнеса, OneNote.<br><br>64-битные полные версии Microsoft Project Microsoft Visio не включены. Однако, поскольку установка этих приложений зависит от Приложения Microsoft 365 для предприятий установки, компьютеры, управляемые Майкрософт по умолчанию создали Microsoft Intune развертывания и группы безопасности, которые можно использовать для развертывания этих приложений для лицензированных пользователей. Дополнительные сведения см. в [Microsoft Project или Microsoft Visio на компьютеры, управляемые Майкрософт устройствах.](../get-started/project-visio.md)
OneDrive |Azure Active Directory Один вход включен для пользователей при первом входе в OneDrive.<br><br>Включено перенаправление известных папок для папок "Desktop", "Document" и "Pictures"; включена и настроена компьютеры, управляемые Майкрософт.
Store Apps | Microsoft Sway и Power BI не поставляются с устройством. Эти приложения доступны для скачивания из Microsoft Store.
Приложения Win32 | Teams не поставляется с устройством, но упаковывается и предоставляется Корпорацией Майкрософт для компьютеры, управляемые Майкрософт устройств. Клиент Azure Information Protection не поставляется с устройством, но его можно упаковть для развертывания.
Веб-приложения | Yammer, Office в браузере, Delve, Flow, StaffHub, PowerApps и Planner не отправляются с устройством. Пользователи могут получить доступ к веб-версии этих приложений с помощью браузера.

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Корпоративная E5 или E3 с Microsoft Defender для конечной точки

Мы рекомендуем ИТ-администраторам настроить следующие параметры. Эти параметры не включены и не управляются в компьютеры, управляемые Майкрософт.

Продукт  |Информация
--- | ---
Windows Hello для бизнеса | Необходимо реализовать Windows Hello для бизнеса, чтобы заменить пароли сильной двух-факторной проверкой подлинности для компьютеры, управляемые Майкрософт устройств. Дополнительные сведения см. [в Windows Hello для бизнеса.](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Виртуализация приложений | Вы можете развернуть пакеты виртуализации приложений (App-V) с помощью клиента управления приложениями Intune Win32. Дополнительные сведения см. в [виртуализации приложений.](/windows/application-management/app-v/appv-technical-reference)
Microsoft 365 защиты от потери данных | Необходимо реализовать Microsoft 365 защиты от потери данных, чтобы отслеживать действия, которые принимаются в отношении элементов, которые вы определили, что они являются конфиденциальными, и чтобы предотвратить непреднамеренное совместное использование этих элементов. Дополнительные сведения см. [в Microsoft 365 предотвращения потери данных.](../../compliance/endpoint-dlp-learn-about.md)

Функции, включенные и управляемые в компьютеры, управляемые Майкрософт:

Продукт |Информация
--- |---
Шифрование диска BitLocker | Шифрование диска BitLocker используется для шифрования всех системных дисков. Дополнительные сведения см. в [сообщении BitLocker Drive Encryption.](/windows/security/information-protection/bitlocker/bitlocker-overview)
Защитник Windows System Guard | Защищает целостность системы при запуске и проверяет, что целостность системы действительно поддерживается. Дополнительные сведения см. [в Защитник Windows System Guard.](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Credential Guard в Защитнике Windows | Защитник Windows Credential Guard использует безопасность на основе виртуализации, чтобы изолировать секреты, чтобы получить к ним доступ только привилегированное системное программное обеспечение. Дополнительные сведения см. [в Защитник Windows System Guard.](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender для конечной точки — обнаружение конечных точек и реагирование | компьютеры, управляемые Майкрософт Операции безопасности реагируют на оповещения и устраняют угрозы с помощью обнаружения и ответа конечных точек. Дополнительные сведения см. в [сайте Microsoft Defender for Endpoint - Endpoint Detection and Response](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response).
Microsoft Defender для конечной точки — эксперты по угрозам | компьютеры, управляемые Майкрософт интегрируется с сведениями и данными экспертов по угрозам с помощью целевых уведомлений об атаке. Перед тем, как включить эту службу, необходимо предоставить дополнительное согласие. Дополнительные сведения см. [в веб-сайте Microsoft Defender для конечной точки — эксперты по угрозам.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender для конечной точки — управление угрозами и уязвимостью | Необходимый для дальнейшего использования в компьютеры, управляемые Майкрософт службы. Дополнительные сведения см. в [сайте Microsoft Defender for Endpoint - Threat and Vulnerability Management.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender для конечной точки — уменьшение поверхности атаки | Снижение поверхности атаки нацелено на рискованное поведение программного обеспечения, которое часто используется злоумышленниками. Дополнительные сведения см. в [веб-сайте Microsoft Defender для конечной точки — уменьшение поверхности атаки.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Защитник Microsoft для конечной точки — защита от эксплойтов | Защищает от вредоносных программ, использующих эксплойты для заражения устройств и распространяющихся путем автоматического применения методов смягчения последствий эксплойта как к операционным процессам, так и к приложениям. Дополнительные сведения см. в [сайте Microsoft Defender for Endpoint - Exploit Protection.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Защитник Microsoft для конечной точки — защита сети | Защита сети расширяет область фильтр SmartScreen в Microsoft Defender, чтобы заблокировать весь исходящие http и HTTPS-трафик, который пытается подключиться к источникам с низкой репутацией. Дополнительные сведения см. в [сайте Microsoft Defender for Endpoint - Network Protection.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Защита от взлома защитника Майкрософт | Windows Защита от взлома используется для предотвращения изменения параметров безопасности, таких как антивирусная защита. Дополнительные сведения см. в [веб-сайте Microsoft Defender Tamper Protection](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
антивирусная программа в Microsoft Defender Антивирусная защита, основанная на поведении, а также в режиме реального времени | Всегда на сканирование для файлов и обработки угроз, которые не могут быть обнаружены в качестве вредоносных программ. Дополнительные сведения см. в антивирусная программа в Microsoft Defender на основе поведения, а также в области защиты от вирусов в режиме [реального времени.](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)
антивирусная программа в Microsoft Defender Защита с облачной доставкой | Обеспечивает динамическую почти мгновенную автоматизированную защиту от новых и возникающих угроз. Дополнительные сведения см. [в антивирусная программа в Microsoft Defender Cloud-delivered Protection.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Block с первого взгляда" | Обеспечивает обнаружение и блокировку новых вредоносных программ Windows обнаружения подозрительного или неизвестного файла. Дополнительные сведения см. [в веб-сайте Microsoft Defender Block с первого взгляда.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender AV Потенциально нежелательные приложения | Потенциально нежелательные приложения используются для блокировки приложений, которые могут привести к медленному запуску компьютера, показу неожиданных объявлений или, в худшем случае, установке другого программного обеспечения, которое может быть неожиданным или нежелательным. Дополнительные сведения см. в [статью Microsoft Defender AV Potentially Unwanted Applications.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Защитник Windows Брандмауэр с расширенным обеспечением безопасности | Фильтрация сетевого трафика на основе хозяйской сети для устройства, Защитник Windows брандмауэр блокирует несанкционированный сетевой трафик, который втекает в локальное устройство или выходит из него. Дополнительные сведения см. [в Защитник Windows брандмауэра с расширенным обеспечением безопасности.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Управление учетной записью пользователя | Управление учетной записью пользователя переключается на безопасный рабочий стол, если для задачи или действия требуется доступ к учетной записи администратора. компьютеры, управляемые Майкрософт пользователям назначен стандартный доступ к пользователю при регистрации. Дополнительные сведения см. в [дополнительных сведениях в области управления учетной записью пользователя.](/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

Продукт |Информация
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 | Вы можете использовать все функции Enterprise Mobility + Security E3 для управления устройствами MDM. Вы можете использовать Azure Active Directory Premium P2 как необязательный элемент с компьютеры, управляемые Майкрософт.
Microsoft Cloud App Security | Этот необязательный элемент можно использовать с помощью компьютеры, управляемые Майкрософт.
Azure Information Protection P2  | Этот необязательный элемент можно использовать с помощью компьютеры, управляемые Майкрософт.
