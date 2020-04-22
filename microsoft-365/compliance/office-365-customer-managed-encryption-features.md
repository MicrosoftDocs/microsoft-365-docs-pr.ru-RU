---
title: Функции шифрования, управляемые клиентами
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
description: 'Сводка: сведения о устойчивости данных в Microsoft 365.'
ms.openlocfilehash: 365cde7137247e20bb4fd2b57039057398deafd5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637345"
---
# <a name="customer-managed-encryption-features"></a>Функции шифрования, управляемые клиентами

Наряду с технологиями шифрования в Microsoft 365, управляемыми корпорацией Майкрософт, Microsoft 365 также работает с дополнительными технологиями шифрования, которые можно управлять и настраивать, например:

- [Управление правами Azure](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [Безопасное многоцелевое расширение почты в Интернете](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Шифрование сообщений Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Защита почтового процесса с помощью партнерской организации](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

За дополнительной информацией об этих технологиях обратитесь к [описанию службы Microsoft 365](https://technet.microsoft.com/library/office-365-service-descriptions.aspx).

## <a name="azure-rights-management"></a>Управление правами Azure

Azure [Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) — это технология защиты, используемая службой [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection). Он использует политики шифрования, идентификации и авторизации для защиты файлов и электронной почты на различных платформах и устройствах — на телефонах, планшетах и ПК. Сведения могут быть защищены как внутри, так и за пределами Организации, так как защита остается в данных. Azure RMS обеспечивает постоянную защиту всех типов файлов, защищает файлы в любом месте, поддерживает совместную работу между бизнесом и широкий спектр устройств Windows и устройств, не являющихся Windows. Защита службы управления правами Azure также может дополнить политики защиты от [потери данных (DLP)](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention). Для получения дополнительных сведений о том, какие приложения и службы могут использовать службу управления правами Azure из Azure Information Protection, Узнайте, [как приложения поддерживают службу управления правами Azure](https://docs.microsoft.com/information-protection/understand-explore/applications-support).

Azure RMS интегрирован в Microsoft 365 и доступен всем клиентам. Чтобы настроить Microsoft 365 для использования Azure RMS, ознакомьтесь со статьей Настройка управления правами [на доступ к данным Azure и Настройка управления правами на доступ к данным в центре администрирования SharePoint](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx). Если вы используете локальный сервер службы управления правами Active Directory (AD), вы также можете [настроить IRM для использования локального сервера AD RMS](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server), но мы настоятельно рекомендуем выполнить [миграцию в Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) для использования новых функций, таких как безопасная совместная работа с другими организациями.

При защите данных клиентов с помощью Azure RMS для шифрования данных в Azure RMS используется асимметричный ключ RSA 2048-bit с алгоритмом хеширования SHA-256. Симметричный ключ для документов Office и электронной почты — это AES 128-bit (режим CBC с PKCS # 7 Padding). Для каждого документа или электронной почты, защищенного службой Azure RMS, служба Azure RMS создает один ключ AES ("ключ содержимого"), а этот ключ внедряется в документ и сохраняется в выпусках документа. Ключ содержимого защищен с помощью ключа RSA в Организации ("ключ клиента Azure Information Protection") в рамках политики в документе, а политика также подписана автором документа. Этот ключ клиента является общим для всех документов и сообщений электронной почты, защищенных службой Azure RMS для Организации, и этот ключ может быть изменен только администратором Azure Information Protection, если организация использует ключ клиента, управляемый клиентом. Для получения дополнительных сведений о криптографических элементах управления, используемых Azure RMS, посмотрите, [как работает Azure RMS? Изнутри](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work).

В стандартной реализации Azure RMS Майкрософт создает корневой ключ, уникальный для каждого клиента, и управляет им. Клиенты могут управлять жизненным циклом своего корневого ключа в Azure RMS с помощью служб Azure Key Vault с помощью метода управления ключами [(бйок)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) , который позволяет создать ключ в локальной среде хсмс (аппаратные модули безопасности) и оставаться в управлении этим ключом после перехода на FIPS 140-2 уровня 2, проверенные хсмс. Доступ к корневому ключу не предоставляется каким-либо сотрудникам, так как ключи не могут быть экспортированы или извлечены из Хсмс, защищая их. Кроме того, в любое время вы можете получить доступ к ближайшему журналу в режиме реального времени, показав весь доступ к корневому ключу. Дополнительные сведения см. в статье [ведение журнала и анализ использования управления правами Azure](https://docs.microsoft.com/azure/information-protection/log-analyze-usage).

Служба управления правами Azure помогает снизить риск таких угроз, как связь по каналу связи, атаки "злоумышленник в середине", "кража данных" и непреднамеренное нарушение политик общего доступа Организации. В то же время любой неавторизованный доступ к транзитным данным клиента или при неавторизованном пользователе, не имеющему соответствующих разрешений, запрещен с помощью политик, которые подпадают под эти данные, тем самым уменьшая риск того, что эти данные попадают в неправильную или неизвестную информацию и предоставляют функции защиты от потери данных. Если используется в составе Azure Information Protection, Azure RMS также предоставляет возможности классификации данных и добавления меток, маркировку содержимого, отслеживание доступа к документам и возможности отзыва доступа. Чтобы узнать больше об этих возможностях, ознакомьтесь со статьей " [Защита информации Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)", " [Схема развертывания Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)" и [руководства по быстрому началу работы для Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial).

## <a name="secure-multipurpose-internet-mail-extension"></a>Безопасное многоцелевое расширение почты в Интернете

Протокол S/MIME (протокол S/MIME) является стандартом шифрования с открытым ключом и цифровой подписи данных MIME. S/MIME определен в документах RFC 3369, 3370, 3850, 3851 и т. д. Он позволяет пользователю шифровать электронную почту и подписывать электронную почту цифровой подписью. Сообщение электронной почты, зашифрованное с помощью S/MIME, может быть расшифровано получателем электронной почты с помощью закрытого ключа, который доступен только этому получателю. Такие сообщения не могут расшифровываться кем бы то ни было, чем получатель сообщения.

[Корпорация Майкрософт поддерживает S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Общедоступные сертификаты распространяются в локальную службу Active Directory клиента и хранятся в атрибутах, которые могут быть реплицированы в клиент Microsoft 365. Закрытые ключи, соответствующие открытым ключам, хранятся в локальной среде и никогда не передаются в Office 365. Пользователи могут создавать, шифровать, расшифровывать, читать и ставить цифровую подпись между двумя пользователями в Организации с помощью Outlook, Outlook в Интернете и клиентов Exchange ActiveSync. Дополнительные сведения см. [в статье шифрование S/MIME в Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Шифрование сообщений Office 365

В [Office 365 шифрование сообщений](https://products.office.com/exchange/office-365-message-encryption) (OME), встроенное в [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (точка административной защиты Azure), позволяет отправлять зашифрованные сообщения и сообщения, защищенные с помощью прав, всем пользователям. OME снижает риски, такие как связь по кабелю и атаки "злоумышленник в середине", а также другие угрозы, такие как несанкционированный доступ к данным неавторизованным пользователем, у которого нет соответствующих разрешений. Мы внесли инвестиции, которые упрощают, более интуитивно понятную и безопасную работу с электронной почтой на основе Azure Information Protection. Вы можете защитить сообщения, отправляемые от Microsoft 365, всем пользователям в организации или за ее пределами. Эти сообщения можно просматривать в различных почтовых клиентах с помощью любого удостоверения, в том числе Azure Active Directory, учетной записи Майкрософт и идентификаторах Google. Дополнительные сведения о том, как ваша организация может использовать зашифрованные сообщения, можно найти в статье [Шифрование сообщений в Office 365](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A).

## <a name="transport-layer-security"></a>Протокол TLS.   

Если вы хотите обеспечить безопасное соединение с партнером, вы можете использовать входящие и исходящие соединители для обеспечения безопасности и целостности сообщений. Для каждого соединителя можно настроить принудительный входящий и исходящий протокол TLS с помощью сертификата. Использование зашифрованного канала SMTP может препятствовать краже данных с помощью атаки "злоумышленник в середине". Для получения дополнительных сведений Узнайте, [как Exchange Online использует протокол TLS для защиты подключений электронной почты](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F).

## <a name="domain-keys-identified-mail"></a>Ключи домена, идентифицирующие почту

Exchange Online Protection (EOP) и Exchange Online поддерживают входящую проверку входящих сообщений электронной почты (DKIM) в ключах домена. DKIM позволяет проверить, отправлено ли сообщение из заявленного домена и не подделали ли его. Он связывает сообщение электронной почты с Организацией, ответственной за его отправку, и является частью более крупной парадигмы шифрования электронной почты. Более подробную информацию об этих трех частях этой парадигмы можно узнать в следующих статьях:

- [Настройка SPF для предотвращения спуфинга](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Проверка исходящей электронной почты, отправленной из личного домена, с помощью DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Использование протокола DMARC для проверки электронной почты](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
