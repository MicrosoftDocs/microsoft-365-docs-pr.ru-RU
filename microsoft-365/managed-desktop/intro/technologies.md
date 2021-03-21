---
title: Технологии компьютеров, управляемых Майкрософт
description: В этой статье перечислены технологии и приложения, используемые в Microsoft Managed Desktop.
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22371d22562960efdc50235657a08e15dba893d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920580"
---
# <a name="microsoft-managed-desktop-technologies"></a>Технологии компьютеров, управляемых Майкрософт

В этой статье перечислены технологии и приложения, используемые в Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Лицензирование Microsoft 365 Enterprise требуется для всех пользователей microsoft Managed Desktop. Дополнительные сведения о требованиях к лицензированию для службы см. в дополнительных сведениях о требованиях к управляемому [рабочему столу Microsoft.](../get-ready/prerequisites.md)

В этой статье кратко излагаются компоненты, включенные в необходимые корпоративные лицензии, с описанием того, как служба использует каждый компонент с устройствами Microsoft Managed Desktop. Конкретные роли и обязанности для каждой области подробно описаны в документации Microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 или E5
 |
 --- | ---
Приложения Microsoft 365 для предприятия (64-битные) | Эти приложения Office будут поставляться с устройством: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype для бизнеса, OneNote.<br><br>64-битные полные версии Microsoft Project и Microsoft Visio не включены. Однако, поскольку установка этих приложений зависит от microsoft 365 Apps для корпоративной установки, Microsoft Managed Desktop создала по умолчанию развертывания Microsoft Intune и группы безопасности, которые можно использовать для развертывания этих приложений для лицензированных пользователей. Дополнительные сведения см. в [веб-сайте Install Microsoft Project или Microsoft Visio на управляемых настольных устройствах Microsoft.](../get-started/project-visio.md)
OneDrive |Единый знак Azure Active Directory включен для пользователей при первом входе в OneDrive.<br><br>Включено перенаправление известных папок для папок "Desktop", "Document" и "Pictures"; включен и настроен Microsoft Managed Desktop.
Store Apps |    Microsoft Sway и Power BI не поставляются с устройством. Эти приложения доступны для скачивания из Microsoft Store.
Приложения Win32 |    Команды не поставляются с устройством, а упакованы и предоставлены устройствами Microsoft для управляемых настольных компьютеров Майкрософт. Клиент Azure Information Protection не поставляется с устройством, но его можно упаковть для развертывания.
Веб-приложения |  Yammer, Office в браузере, Delve, Flow, StaffHub, PowerApps и Planner не отправляются с устройством. Пользователи могут получить доступ к веб-версии этих приложений с помощью браузера.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 или E3 с Microsoft Defender для конечной точки
Мы рекомендуем ИТ-администраторам настроить следующие параметры. Эти параметры не включены и не управляются в составе Microsoft Managed Desktop.

 |
 --- | ---
Windows Hello для бизнеса | Необходимо реализовать Windows Hello для бизнеса, чтобы заменить пароли на надежные двух факторов проверки подлинности для устройств Microsoft Managed Desktop. Дополнительные сведения см. в [windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Виртуализация приложений | Вы можете развернуть пакеты виртуализации приложений (App-V) с помощью клиента управления приложениями Intune Win32. Дополнительные сведения см. в [виртуализации приложений.](/windows/application-management/app-v/appv-technical-reference)
Предотвращение потери данных Microsoft 365 | Необходимо реализовать предотвращение потери данных Microsoft 365, чтобы отслеживать действия, которые принимаются в отношении элементов, которые вы определили конфиденциальными, и чтобы предотвратить непреднамеренное совместное использование этих элементов. Дополнительные сведения см. в [веб-сайте Microsoft 365 предотвращение потери данных.](../../compliance/endpoint-dlp-learn-about.md)


Функции, включенные и управляемые в рамках Microsoft Managed Desktop:

 |
 --- | ---
Шифрование диска BitLocker | Шифрование диска BitLocker используется для шифрования всех системных дисков. Дополнительные сведения см. в [сообщении BitLocker Drive Encryption.](/windows/security/information-protection/bitlocker/bitlocker-overview)
Защитник Windows System Guard | Защищает целостность системы при запуске и проверяет, что целостность системы действительно поддерживается. Дополнительные сведения см. [в Защитник Windows System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Credential Guard в Защитнике Windows | Защитник Windows credential Guard использует безопасность на основе виртуализации, чтобы изолировать секреты, чтобы получить к ним доступ только привилегированное системное программное обеспечение. Дополнительные сведения см. [в Защитник Windows System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender для конечной точки — обнаружение конечных точек и реагирование | Microsoft Managed Desktop Security Operations реагирует на оповещения и принимает меры для устранения угроз с помощью обнаружения и ответа конечных точек. Дополнительные сведения см. в [сайте Microsoft Defender for Endpoint - Endpoint Detection and Response](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response).
Microsoft Defender для конечной точки — эксперты по угрозам | Microsoft Managed Desktop интегрируется с сведениями и данными экспертов по угрозам с помощью целевых уведомлений об атаке. Перед тем, как включить эту службу, необходимо предоставить дополнительное согласие. Дополнительные сведения см. [в веб-сайте Microsoft Defender для конечной точки — эксперты по угрозам.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender для конечной точки — управление угрозами и уязвимостью | Необходимый для дальнейшего использования в плане службы microsoft Managed Desktop. Дополнительные сведения см. в [сайте Microsoft Defender for Endpoint - Threat and Vulnerability Management.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender для конечной точки — уменьшение поверхности атаки | Снижение поверхности атаки нацелено на рискованное поведение программного обеспечения, которое часто используется злоумышленниками. Дополнительные сведения см. в [веб-сайте Microsoft Defender для конечной точки — уменьшение поверхности атаки.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Защитник Microsoft для конечной точки — защита от эксплойтов | Защищает от вредоносных программ, использующих эксплойты для заражения устройств и распространяющихся путем автоматического применения методов смягчения последствий эксплойта как к операционным процессам, так и к приложениям. Дополнительные сведения см. в [сайте Microsoft Defender for Endpoint - Exploit Protection.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Защитник Microsoft для конечной точки — защита сети | Защита сети расширяет область smartScreen Защитника Майкрософт, чтобы заблокировать весь исходящие трафик HTTP и HTTPS, который пытается подключиться к источникам с низкой репутацией. Дополнительные сведения см. в [сайте Microsoft Defender for Endpoint - Network Protection.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Защита от взлома защитника Майкрософт | Защита от взлома Windows используется для предотвращения изменения параметров безопасности, таких как антивирусная защита. Дополнительные сведения см. в [веб-сайте Microsoft Defender Tamper Protection](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
Защита антивирусного поведения от Microsoft Defender, а также защита от вирусов в режиме реального времени | Всегда на сканирование для файлов и обработки угроз, которые не могут быть обнаружены в качестве вредоносных программ. Дополнительные сведения см. в [веб-сайте Microsoft Defender Antivirus Behaviour, heuristic и в]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)режиме реального времени.
Защита облачной защиты от антивируса Microsoft Defender | Обеспечивает динамическую почти мгновенную автоматизированную защиту от новых и возникающих угроз. Дополнительные сведения см. в [веб-сайте Microsoft Defender Antivirus Cloud-delivered Protection.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Block с первого взгляда" | Обеспечивает обнаружение и блокировку новых вредоносных программ, когда Windows обнаруживает подозрительный или неизвестный файл. Дополнительные сведения см. [в веб-сайте Microsoft Defender Block с первого взгляда.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender AV Потенциально нежелательные приложения | Потенциально нежелательные приложения используются для блокировки приложений, которые могут привести к медленному запуску компьютера, показу неожиданных объявлений или, в худшем случае, установке другого программного обеспечения, которое может быть неожиданным или нежелательным. Дополнительные сведения см. в [статью Microsoft Defender AV Potentially Unwanted Applications.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Защитник Windows брандмауэра с расширенным обеспечением безопасности | Фильтрация сетевого трафика на основе хозяйской сети для устройства, Защитник Windows брандмауэр блокирует несанкционированный сетевой трафик, который втекает в локальное устройство или выходит из него. Дополнительные сведения см. [в Защитник Windows брандмауэра с расширенным обеспечением безопасности.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Управление учетной записью пользователя | Управление учетной записью пользователя переключается на безопасный рабочий стол, если для задачи или действия требуется доступ к учетной записи администратора. Пользователям управляемых настольных компьютеров Майкрософт назначен стандартный доступ к пользователю при регистрации. Дополнительные сведения см. в [дополнительных сведениях в области управления учетной записью пользователя.](/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Корпоративная мобильность + безопасность E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Для управления устройствами MDM можно использовать все функции корпоративной мобильности и безопасности E3 и Azure Active Directory Premium P2.
Microsoft Cloud App Security |  Эту необязательный функцию можно использовать с помощью Microsoft Managed Desktop.
Azure Information Protection P2  | Эту необязательный функцию можно использовать с помощью Microsoft Managed Desktop.