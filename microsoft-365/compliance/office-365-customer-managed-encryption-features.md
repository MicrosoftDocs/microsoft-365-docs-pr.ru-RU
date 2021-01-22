---
title: Возможности шифрования под управлением клиента
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: В этой статье вы узнаете о технологиях шифрования, которые можно настраивать и управлять в Microsoft 365.
ms.openlocfilehash: bb6f9fedf915fd261266a9ed5d0c561d1352ea09
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921559"
---
# <a name="customer-managed-encryption-features"></a>Возможности шифрования под управлением клиента

Наряду с технологиями шифрования в Microsoft 365, управляемыми корпорацией Майкрософт, Microsoft 365 также работает с дополнительными технологиями шифрования, которые можно настроить и управлять, например:

- [Управление правами Azure](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Шифрование сообщений Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Защита потока почты с партнерской организацией](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Дополнительные сведения об этих технологиях см. в описаниях служб [Microsoft 365.](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)

## <a name="azure-rights-management"></a>Управление правами Azure

[Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) — это технология защиты, используемая [Azure Information Protection.](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) В нем используются политики шифрования, удостоверений и авторизации для защиты файлов и электронной почты на различных платформах и устройствах — телефонах, планшетах и ПК. Сведения могут быть защищены как в организации, так и за ее пределами, так как защита остается за данными. Azure RMS обеспечивает постоянную защиту всех типов файлов, защищает файлы в любом месте, поддерживает совместную работу между компанией и широкий спектр устройств с Windows и других устройств. Защита Azure RMS также может дополнить политики защиты от потери [данных (DLP).](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Дополнительные сведения о том, какие приложения и службы могут использовать службу управления правами Azure из Azure Information Protection, см. в сведениях о том, как приложения поддерживают [службу управления правами Azure.](https://docs.microsoft.com/information-protection/understand-explore/applications-support)

Служба Azure RMS интегрирована с Microsoft 365 и доступна всем клиентам. Сведения о настройке Microsoft 365 для использования Azure RMS см. в подстройке "Настройка IRM для использования службы управления правами Azure" и "Настройка управления правами на данные" в Центре администрирования [SharePoint.](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx) При использовании локального сервера RMS Active Directory (AD) можно также настроить IRM для использования локального сервера [AD RMS,](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)но мы настоятельно рекомендуем перейти на [Azure RMS,](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) чтобы использовать новые функции, такие как безопасная совместная работа с другими организациями.

При защите данных клиентов с помощью Azure RMS Azure RMS использует 2048-битный асимметричный ключ RSA с алгоритмом hash SHA-256 для шифрования данных. Симметричный ключ для документов и электронной почты Office — 128-битный AES. Для каждого документа или электронной почты, защищенных службой Azure RMS, Azure RMS создает один ключ AES (ключ содержимого), который внедряется в документ и сохраняется в выпусках документа. Ключ содержимого защищен ключом RSA организации (ключом клиента Azure Information Protection) в рамках политики в документе, а политика также подписана автором документа. Этот ключ клиента является общим для всех документов и электронных писем, защищенных службой Azure RMS для организации, и этот ключ может изменить только администратор Azure Information Protection, если в организации используется ключ клиента, управляемый клиентом. Дополнительные сведения о криптографических средствах управления, используемых службой Azure RMS, см. в сведениях о [том, как azure RMS работает? Под хламом.](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)

В реализации Azure RMS по умолчанию корпорация Майкрософт создает и управляет корневым ключом, уникальным для каждого клиента. Клиенты могут управлять жизненным циклом корневого ключа в Azure RMS с помощью служб Azure Key Vault Services с помощью метода управления ключами под названием [Bring Your Own Key (BYOK),](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) который позволяет создавать ключ в локальной службе HSM (аппаратных модулях безопасности) и контролировать этот ключ после передачи в SSM fiPS 140-2 уровня 2. Доступ к корневому ключу не предоставляется персоналу, так как ключи невозможно экспортировать или извлечь из HSM, которые их защищают. Кроме того, вы можете получить доступ к журналу в режиме реального времени, в котором в любой момент отображается весь доступ к корневому ключу. Дополнительные сведения см. в [журнале и анализе использования azure Rights Management.](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)

Azure Rights Management помогает устранять такие угрозы, как касание по проводам, атаки "человек в середине", кража данных и непреднамеральные нарушения политик общего доступа организации. В то же время любой несанкционированный доступ к данным клиента при передаче или в неавторизованном окне неавторизованного пользователя, который не имеет соответствующих разрешений, предотвращается с помощью политик, которые следуют этим данным, тем самым снижая риск попадания этих данных в неподходящие руки либо намеренно, либо не зная их, и предоставляя функции защиты от потери данных. Если используется как часть Azure Information Protection, Azure RMS также предоставляет возможности классификации и маркировки данных, маркировки содержимого, отслеживания доступа к документам и отзыва доступа. Дополнительные сведения об этих возможностях см. в руководстве "Что такое [Azure Information Protection",](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)в обзоре развертывания [Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)и кратком руководстве по началу работы с Azure Information [Protection.](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) — это стандарт для шифрования открытых ключей и цифровой подписи данных MIME. S/MIME определен в RFCs 3369, 3370, 3850, 3851 и других. Он позволяет пользователю шифровать сообщения электронной почты и подписывать их цифровой подписью. Сообщение электронной почты, зашифрованное с помощью S/MIME, может быть расшифровываться только получателем электронной почты с помощью его закрытого ключа, доступного только этому получателю. Поэтому сообщения электронной почты не может расшифровать никто, кроме получателя сообщения.

[Корпорация Майкрософт поддерживает S/MIME.](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx) Общедоступные сертификаты распространяются в локальной службе Active Directory клиента и хранятся в атрибутах, которые можно реплицировать в клиент Microsoft 365. Закрытые ключи, соответствующие открытым ключам, остаются в локальной службе и никогда не передаются в Office 365. Пользователи могут составлять, шифровать, расшифровывать, читать и подписывать сообщения электронной почты между двумя пользователями в организации с помощью Outlook, Outlook в Интернете и Exchange ActiveSync клиентах. Дополнительные сведения см. в сообщении о [шифровании S/MIME в Office 365.](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)

## <a name="office-365-message-encryption"></a>Шифрование сообщений Office 365

[Шифрование сообщений Office 365](https://products.office.com/exchange/office-365-message-encryption) (OME), построенное на основе [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP), позволяет отправлять зашифрованную и защищенную правами почту всем пользователям. OME устраняет такие угрозы, как касание по проводу и атаки "человек в середине", а также другие угрозы, например несанкционированный доступ к данным несанкционированным пользователем, у которого нет соответствующих разрешений. Мы сделали инвестиции, которые обеспечивают более простой, интуитивно понятный и безопасный интерфейс электронной почты, построенный на основе Azure Information Protection. Вы можете защитить сообщения, отправленные из Microsoft 365 всем внутри или за пределами организации. Эти сообщения можно просматривать в различных почтовых клиентах с помощью любого удостоверения, включая Azure Active Directory, учетную запись Майкрософт и идентификаторы Google ID. Дополнительные сведения о том, как ваша организация может использовать зашифрованные сообщения, см. в сообщении [шифрования office 365.](https://docs.microsoft.com/microsoft-365/compliance/ome)

## <a name="transport-layer-security"></a>Протокол TLS.   

Если вы хотите обеспечить безопасное взаимодействие с партнером, вы можете использовать входящие и исходящие соединители для обеспечения безопасности и целостности сообщений. С помощью сертификата можно настроить принудительное использование TLS для входящие и исходящие подключения для каждого соединители. Использование зашифрованного канала SMTP может предотвратить кражу данных путем атаки "человек в середине". Дополнительные сведения см. в сведениях о том, как [Exchange Online использует TLS для защиты подключений к электронной почте.](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="domain-keys-identified-mail"></a>Почта с идентифицированным ключами домена

Exchange Online Protection (EOP) и Exchange Online поддерживают входящие проверки сообщений DKIM. DKIM позволяет проверить, отправлено ли сообщение из заявленного домена и не подделали ли его. Оно связывает сообщение электронной почты с организацией, ответственной за его отправку, и является частью более крупной парадигмы шифрования электронной почты. Дополнительные сведения о трех частях этой парадигмы см. в:

- [Настройка SPF для предотвращения спуфинга](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Используйте DKIM для проверки исходящей электронной почты, отправленной с вашего пользовательского домена](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Использование протокола DMARC для проверки электронной почты](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
