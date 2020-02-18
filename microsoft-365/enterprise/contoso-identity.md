---
title: Удостоверение для корпорации Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.
ms.openlocfilehash: 77c90740fd39080ccc204552bc8407aa107e354a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068472"
---
# <a name="identity-for-the-contoso-corporation"></a>Удостоверение для корпорации Contoso

Корпорация Майкрософт предоставляет удостоверение как услугу (IDaaS) в своих облачных предложениях с Azure Active Directory (Azure AD). Для перехода на Microsoft 365 Enterprise в решении IDaaS Contoso нужно было использовать локального поставщика удостоверений и по-прежнему включать федеративную проверку подлинности с помощью существующих надежных сторонних поставщиков удостоверений.

## <a name="contosos-active-directory-domain-services-forest"></a>Лес доменных служб Active Directory Contoso

Contoso использует один лес доменных служб Active Directory (AD DS) для contoso.com с семью поддоменами, по одному для каждого региона мира. Главный офис, региональные и вспомогательные офисы содержат контроллеры доменов для локальной проверки подлинности и авторизации.

Ниже показан лес Contoso с региональными доменами для разных частей света, в которых находятся региональные офисы.

![Лес Contoso и домены по всему миру](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso необходимо было использовать учетные записи и группы в лесу contoso.com для проверки подлинности и авторизации своих рабочих нагрузок и служб Microsoft 365.

## <a name="contosos-federated-authentication-infrastructure"></a>Инфраструктура федеративной аутентификации Contoso

Корпорация Contoso разрешает:

- клиентам использовать свои учетные записи Майкрософт, Facebook или Google Mail для входа на общедоступный веб-сайт;
- поставщикам и партнерам использовать свои учетные записи LinkedIn, Salesforce или Google Mail для входа в партнерскую экстрасеть.

Ниже показана сеть периметра Contoso, содержащая общедоступный веб-сайт, партнерскую экстрасеть и набор серверов служб федерации Active Directory (AD FS). Сеть периметра подключена к Интернету, в котором находятся клиенты, партнеры и Интернет-службы.

![Поддержка федеративной аутентификации клиентов и партнеров в компании Contoso](../media/contoso-identity/contoso-identity-fig2.png)
 
Серверы AD FS в DMZ выполняют проверку подлинности учетных данных клиентов с использованием поставщиков удостоверений для доступа к общедоступному веб-сайту и учетных данных партнеров в партнерской экстрасети.

Корпорация Contoso решила сохранить эту инфраструктуру и выделить ее для проверки подлинности клиентов и партнеров. Архитекторы удостоверений Contoso изучают возможность преобразования этой инфраструктуры в решения Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) и [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Гибридное удостоверение с синхронизацией хэша пароля для облачной проверки подлинности

Contoso необходимо было использовать собственный локальный лес AD DS при проверке подлинности для доступа к облачным ресурсам Microsoft 365. Было решено использовать синхронизацию хэша пароля (PHS).

PHS синхронизирует локальный лес AD DS с клиентом Azure AD подписки на Microsoft 365 Enterprise. При этом копируются учетные записи пользователей и групп, а также хэшированные версии паролей от учетных записей пользователей. 

Для постоянной синхронизации каталога Contoso развернула средство Azure AD Connect на сервере в собственном ЦОД в Париже. 

Ниже показан сервер, на котором Azure AD Connect опрашивает лес AD DS Contoso для выявления изменений и затем синхронизирует эти изменения с клиентом Azure AD.

![Инфраструктура синхронизации каталога PHS Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Политики условного доступа для доступа к удостоверению и устройству

В Contoso создан набор [политик условного доступа](identity-access-policies.md) Azure AD и Intune для трех уровней защиты:

- **Базовая** защита применяется ко всем учетным записям пользователей.
- Защита **конфиденциальных данных** применяется к старшим руководителям и руководству высшего звена
- Защита **строго регулируемых данных** применяется к определенным пользователям из финансового, юридического и исследовательского отделов, имеющим доступ к строго регулируемым данным

Ниже показан итоговый набор политик условного доступа к удостоверениям и устройствам.

![Политики условного доступа к удостоверениям и устройствам в Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Дальнейшие действия

[Узнайте,](contoso-win10.md) как в корпорации Contoso используют инфраструктуру Microsoft Endpoint Configuration Manager для развертывания Windows 10 Корпоративная в организации и поддержания этой операционной системы в актуальном состоянии.

## <a name="see-also"></a>См. также

[Удостоверение для Microsoft 365 корпоративный](identity-infrastructure.md)

[Руководство по развертыванию](deploy-microsoft-365-enterprise.md)

[Руководства по лаборатории тестирования](m365-enterprise-test-lab-guides.md)
