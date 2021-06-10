---
title: Удостоверение для корпорации Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о том, как Contoso использует службу "удостоверение как услуга" (IDaaS) и предоставляет облачную проверку подлинности для сотрудников, а также федеративную проверку подлинности для партнеров и клиентов.
ms.openlocfilehash: f3c8746345683652ce601400ae7297e96fff2ee3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051524"
---
# <a name="identity-for-the-contoso-corporation"></a>Удостоверение для корпорации Contoso

Корпорация Майкрософт предоставляет identity as a Service (IDaaS) через облачные предложения Azure Active Directory Azure AD. Чтобы Microsoft 365 для предприятия, решение Contoso IDaaS должно было использовать локального поставщика удостоверений и включить федеральную проверку подлинности с существующими доверенными сторонними поставщиками удостоверений.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Лес служб доменных служб Contoso Active Directory

Contoso использует один лес служб домена Active Directory (AD DS) для contoso com с семью поддоменами, по одному для каждого региона \. мира. Главный офис, региональные и вспомогательные офисы содержат контроллеры доменов для локальной проверки подлинности и авторизации.

Вот лес Contoso с региональными доменами для различных частей мира, которые содержат региональные концентраторы.

![Лес Contoso и домены по всему миру](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso решила использовать учетные записи и группы в лесу contoso com для проверки подлинности и авторизации для Microsoft 365 рабочих \. нагрузок и служб.

## <a name="the-contoso-federated-authentication-infrastructure"></a>Инфраструктура федераированной проверки подлинности Contoso

Корпорация Contoso разрешает:

- Клиенты используют свои учетные записи Microsoft, Facebook или Google Mail для входов на общедоступный веб-сайт компании.
- Поставщики и партнеры используют свои учетные записи LinkedIn, Salesforce или Google Mail для регистрации в партнерской экстрасети компании.

Вот dmZ Contoso, содержащий общедоступный веб-сайт, партнерская экстрасеть и набор серверов федерации Active Directory (AD FS). DmZ подключен к Интернету, в который входят клиенты, партнеры и интернет-службы.

![Поддержка Contoso для федератированной проверки подлинности для клиентов и партнеров](../media/contoso-identity/contoso-identity-fig2.png)
 
Серверы AD FS в DMZ облегчают проверку подлинности учетных данных клиентов поставщиками удостоверений для доступа к общедоступным веб-сайтам и учетным данным партнеров для доступа к партнерской экстрасети.

Contoso решил сохранить эту инфраструктуру и посвятить ее проверке подлинности клиентов и партнеров. Архитекторы удостоверений Contoso изучают преобразование этой инфраструктуры для решений Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) и [B2C](/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Гибридное удостоверение с синхронизацией хэша пароля для облачной проверки подлинности

Contoso хотел использовать свой лес AD DS на локальной основе для проверки подлинности для Microsoft 365 облачных ресурсов. Было принято решение использовать синхронизацию хеш-кодов паролей (PHS).

PhS синхронизирует лес AD DS на локальной основе с клиентом Azure AD Microsoft 365 для корпоративной подписки, копирования учетных записей пользователей и групп, а также с хашизированной версией паролей учетных записей пользователей.

Для синхронизации каталогов Contoso развернула средство Azure AD Подключение на сервере в парижском центрах обработки данных.

Вот сервер, на Подключение Azure AD, который оповещает лес Contoso AD DS для изменений, а затем синхронизирует эти изменения с клиентом Azure AD.

![Инфраструктура синхронизации каталогов каталогов Contoso PHS](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Политики условного доступа для доступа к удостоверению и устройству

В Contoso создан набор [политик условного доступа](../security/defender-365-security/identity-access-policies.md) Azure AD и Intune для трех уровней защиты:

- *Базовые* защиты применяются для всех учетных записей пользователей.
- *Конфиденциальные* меры защиты применяются к старшему руководству и исполнительному персоналу.
- *Строго регламентированная* защита применяется к конкретным пользователям в финансовых, юридических и исследовательских отделах, которые имеют доступ к строго регулируемым данным.

Ниже приводится набор политик условного доступа к удостоверениям и устройствам Contoso.

![Политики условного доступа к удостоверениям и устройствам в Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Следующий шаг

Узнайте, как Contoso использует Microsoft Endpoint Configuration Manager инфраструктуру для развертывания и сохраняемой Windows 10 Корпоративная [всей](contoso-win10.md) организации.

## <a name="see-also"></a>См. также

[Стратегия удостоверений для Microsoft 365](identity-roadmap-microsoft-365.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Руководства по лаборатории тестирования](m365-enterprise-test-lab-guides.md)