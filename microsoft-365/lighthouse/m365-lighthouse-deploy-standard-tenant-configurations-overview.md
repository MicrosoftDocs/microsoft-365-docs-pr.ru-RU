---
title: Обзор использования базовых данных для развертывания стандартных конфигураций клиента
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Для поставщиков управляемых служб (MSP), использующих Microsoft 365 Lighthouse, узнайте об использовании базовых показателей для развертывания стандартных конфигураций клиента.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409187"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>Обзор использования базовых данных для развертывания стандартных конфигураций клиента 

> [!NOTE]
> Функции, описанные в этой статье, подлежат изменениям и доступны только партнерам, которые соответствуют [требованиям.](m365-lighthouse-requirements.md) Если в организации нет Microsoft 365 Lighthouse, [см.](m365-lighthouse-sign-up.md)в Microsoft 365 Lighthouse.

Microsoft 365 Lighthouse базовые показатели обеспечивают повторяемый и масштабируемый способ оценки и управления Microsoft 365 параметров безопасности для нескольких клиентов. Базовые параметры также помогают отслеживать основные политики безопасности и стандарты соответствия требованиям клиентов конфигурациями, которые обеспечивает безопасность пользователей, устройств и данных.

Разработанный для того, чтобы помочь партнерам в обеспечении безопасности в их собственном темпе, Microsoft 365 Lighthouse предоставляет стандартный набор базовых параметров и заранее определенных конфигураций для Microsoft 365 служб. Эти конфигурации безопасности помогают оценить Microsoft 365 безопасности и соответствия требованиям.

Вы можете просмотреть базовый уровень по умолчанию и его этапы развертывания из Microsoft 365 Lighthouse. Чтобы применить базовые параметры к клиенту, выберите **"Клиенты"** в левой области навигации, а затем выберите клиента. Далее перейдите на **вкладку Планы развертывания** и реализуем нужную базовую линию.

## <a name="standard-baseline-security-templates"></a>Стандартные базовые шаблоны безопасности

Microsoft 365 Lighthouse стандартные базовые конфигурации для рабочих нагрузок безопасности предназначены для того, чтобы помочь всем управляемым арендаторам достичь приемлемого состояния обеспечения безопасности и соответствия требованиям.

Базовые конфигурации в следующей таблице стандартны с базовой Microsoft 365 Lighthouse по умолчанию.<br><br>

| Базовая конфигурация | Описание |
|--|--|
| Требовать MFA для администраторов | Политика условного доступа только для отчетов, требующая многофакторной проверки подлинности для администраторов. Это необходимо для всех облачных приложений. |
| Требовать MFA для конечных пользователей | Политика условного доступа только для отчетов, которая требует многофакторной проверки подлинности для пользователей. Это необходимо для всех облачных приложений. |
| Блокирование традиционной проверки подлинности | Политика условного доступа только для отчетов, чтобы заблокировать проверку подлинности устаревших клиентов. |
| Регистрация устройств в Microsoft Endpoint Manager - Azure AD Join | Регистрация устройств, чтобы позволить устройствам клиента зарегистрироваться в Microsoft Endpoint Manager. Это делается путем настройки автоматической регистрации между Azure Active Directory и Microsoft Endpoint Manager. |
| Конфигурация политики антивируса (AV) | Профиль конфигурации устройств для Windows устройств с предварительно настроенными антивирусная программа в Microsoft Defender настройками. |
| Настройка политики соответствия требованиям window 10 | Политика Windows устройств с предварительно настроенными настройками для соответствия основным требованиям соответствия требованиям. |

## <a name="related-content"></a>См. также:

[Развертывание Microsoft 365 Lighthouse](m365-lighthouse-deploy-baselines.md) (статья)\
[Microsoft 365 Lighthouse (статья)](m365-lighthouse-faq.yml)
