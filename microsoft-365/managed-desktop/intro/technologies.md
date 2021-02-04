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
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094871"
---
# <a name="microsoft-managed-desktop-technologies"></a>Технологии компьютеров, управляемых Майкрософт

В этой статье перечислены технологии и приложения, используемые на компьютерах, управляемых Майкрософт.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Для всех пользователей компьютеров, управляемых Майкрософт, требуется лицензирование Microsoft 365 корпоративный. Дополнительные сведения о требованиях к лицензированию для службы см. в предварительных [требованиях для компьютеров,](../get-ready/prerequisites.md)управляемых Майкрософт.

В этой статье кратко описаны компоненты, включенные в необходимые корпоративные лицензии, а также описано, как служба использует каждый компонент с устройствами, управляемыми Майкрософт. Конкретные роли и обязанности для каждой области подробно описаны в документации microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 или E5
 |
 --- | ---
Приложения Microsoft 365 для предприятий (64-битная) | Эти приложения Office будут поставляться с устройством: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype для бизнеса, OneNote.<br><br>64-битные полные версии Microsoft Project и Microsoft Visio не включены. Однако поскольку установка этих приложений зависит от установки приложений Microsoft 365 для предприятий, на компьютере, управляемом Майкрософт, созданы развертывания Microsoft Intune и группы безопасности по умолчанию, которые затем можно использовать для развертывания этих приложений для лицензированных пользователей. Дополнительные сведения см. в сведениях об [установке Microsoft Project или Microsoft Visio на настольных](../get-started/project-visio.md)устройствах, управляемых Майкрософт.
OneDrive |Единый вход Azure Active Directory включен для пользователей при первом входе в OneDrive.<br><br>Включено перенаправление известных папок для папок "Рабочий стол", "Документ" и "Изображения"; включено и настроено на компьютерах, управляемых Майкрософт.
Приложения Магазина |    Microsoft Sway и Power BI не поставляются вместе с устройством. Эти приложения доступны для скачивания из Microsoft Store.
Приложения Win32 |    Teams не поставляется вместе с устройством, но упаковывается и предоставляется корпорацией Майкрософт для настольных устройств, управляемых Майкрософт. Клиент Azure Information Protection не поставляется вместе с устройством, но его можно упаковить для развертывания.
Веб-приложения |  Yammer, Office в браузере, Delve, Flow, StaffHub, PowerApps и Планировщике не поставляются вместе с устройством. Пользователи могут получить доступ к веб-версии этих приложений с помощью браузера.



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Корпоративная E5 или E3 с Microsoft Defender для конечной точки
Рекомендуемый
 |
 --- | ---
[Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | Клиентам рекомендуется реализовать Windows Hello для бизнеса, чтобы заменить пароли на надувную двух коэффициентную проверку подлинности, используемую на настольных устройствах, управляемых Майкрософт.
[Виртуализация приложений](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | Клиенты могут развертывать пакеты Application Virtualization (App-V) с помощью клиента управления приложениями Intune Win32.
[Предотвращение потери данных в Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | Клиентам рекомендуется реализовать службу защиты от потери данных Microsoft 365 для отслеживания действий, которые выполняются с элементами, которые вы определили как конфиденциальные, и для предотвращения непреднамеренного общего доступа к этим элементами.   

Включается в службу и управляется ей
 |
 --- | ---
[Шифрование диска BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | Шифрование диска BitLocker используется для шифрования всех системных дисков. 
[Защитник Windows System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | Защищает целостность системы при запуске и проверяет, действительно ли она поддерживается.
[Credential Guard в Защитнике Windows]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Защитник Windows Credential Guard использует безопасность на основе виртуализации для изоляции секретов, чтобы доступ к ним было только привилегированным системным программным обеспечением.
[Microsoft Defender для конечной точки | Обнаружение конечных точек и реагирование](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Microsoft Managed Desktop Security Operations реагирует на оповещения и принимает меры для устранения угроз с помощью обнаружения конечных точек и реагирования на них.
[Microsoft Defender для конечной точки | Эксперты по угрозам](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Компьютеры, управляемые Майкрософт, интегрируются с анализом и данными специалистов по угрозам с помощью целевых уведомлений о атаках. Клиенты должны предоставить дополнительное согласие, прежде чем эта служба будет включена.  
[Microsoft Defender для конечной точки | Управление угрозами и уязвимости](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | Требуется для дальнейшего использования в плане обслуживания компьютеров, управляемых Майкрософт.
[Microsoft Defender для конечной точки | Уменьшение числа поверхностей атаки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | Сокращение поверхности атаки нацелено на рискованные программные действия, которые злоумышленники часто используют.
[Microsoft Defender для конечной точки | Защита от эксплойтов](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | Защищает от вредоносных программ, которые используют эксплойты для заражения устройств и распространения путем автоматического применения методов защиты от эксплойтов к процессам операционной системы и приложениям.
[Microsoft Defender для конечной точки | Защита сети](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | Защита сети расширяет область smartScreen в Microsoft Defender, чтобы блокировать весь исходящие HTTP-трафик, который пытается подключиться к источникам с низкой репутацией.
[Защита от взлома в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Защита от взлома Windows используется для предотвращения изменения параметров безопасности, таких как защита от вирусов.
[Антивирусная защита от вирусов в Microsoft Defender, а также защита от вирусов в режиме реального времени]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | Всегда сканировать на обнаружение угроз файлов и процессов, которые могут не быть обнаружены как вредоносные программы.
[Облачная защита антивирусной программы "Microsoft Defender"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | Обеспечивает динамическую автоматическую защиту от новых и возникающих угроз практически мгновенно.
[Блокировка Microsoft Defender при первом виде](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | Обеспечивает обнаружение и блокировку новых вредоносных программ, когда Windows обнаруживает подозрительный или неизвестный файл.
[Потенциально нежелательные приложения в microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | Потенциально нежелательные приложения (PUA) используются для блокировки приложений, которые могут привести к медленному запуску компьютера, показу непредвиденных объявлений или установке другого программного обеспечения, которое может быть непредвиденным или нежелательным.
[Защитник Windows брандмауэра с расширенными мерами безопасности](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | Фильтрация сетевого трафика на основе хост-трафика для устройства, Защитник Windows брандмауэр блокирует несанкционированный сетевой трафик, который проходит в локальное устройство или из него.
[Контроль учетных записей пользователей](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | Контроль учетных записей пользователей переключается на безопасный рабочий стол, если для задачи или действия требуется доступ к учетной записи администратора. Пользователям компьютеров, управляемых Майкрософт, при регистрации будет назначен стандартный доступ пользователей. 


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Для управления устройствами MDM можно использовать все функции Enterprise Mobility + Security E3 и Azure Active Directory Premium P2.
Microsoft Cloud App Security |  Эту дополнительную функцию можно использовать с компьютером, управляемым Майкрософт.
Azure Information Protection P2  | Эту дополнительную функцию можно использовать с компьютером, управляемым Майкрософт.
