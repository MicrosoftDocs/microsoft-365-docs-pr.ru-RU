---
title: Развертывание Microsoft 365 Lighthouse базовых показателей
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
description: Для поставщиков управляемых служб (MSP) с помощью Microsoft 365 Lighthouse узнайте, как развернуть Microsoft 365 Lighthouse базовых данных.
ms.openlocfilehash: 0bda7edec2a200e51e734db64e2b703a027e57bb
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395365"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>Развертывание Microsoft 365 Lighthouse базовых показателей 

> [!NOTE]
> Функции, описанные в этой статье, подлежат изменениям и доступны только партнерам, которые соответствуют [требованиям.](m365-lighthouse-requirements.md) Если в организации нет Microsoft 365 Lighthouse, [см.](m365-lighthouse-sign-up.md)в Microsoft 365 Lighthouse.

Microsoft 365 Lighthouse позволяет развертывать стандартные управляемые конфигурации клиента для защиты пользователей, устройств и данных клиента. Существует шесть базовых конфигураций по умолчанию, которые являются стандартными с Microsoft 365 Lighthouse:

- Требовать MFA для администраторов
- Требовать MFA для конечных пользователей
- Блокировка проверки подлинности в устаревших версиях
- Настройка регистрации устройств в Microsoft Endpoint Manager - Azure AD Join
- Настройка антивирусной политики Defender для Windows устройств
- Настройка политики соответствия требованиям для Windows устройств

## <a name="before-you-begin"></a>Прежде чем начать

Убедитесь, что вы и клиенты соответствуют требованиям, указанным в требованиях [к Microsoft 365 Lighthouse.](m365-lighthouse-requirements.md)

## <a name="learn-more-about-the-default-baseline"></a>Дополнительные данные о базовой линии по умолчанию

Выберите **Базовые параметры** из левой области навигации, чтобы открыть страницу Базовые. Вы увидите, что базовый уровень по умолчанию уже добавлен в группу клиентов по умолчанию (все клиенты). Чтобы просмотреть базовые конфигурации по умолчанию, выберите **базовый просмотр,** чтобы открыть базовую страницу по умолчанию. Конфигурации перечислены в качестве этапов развертывания. Выберите любой из этапов развертывания, чтобы просмотреть сведения о развертывании и влияние пользователя.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Снимок экрана базовой страницы по умолчанию.>.":::

## <a name="deploy-a-baseline-configuration"></a>Развертывание базовой конфигурации  

1. На левой странице навигации выберите **"Клиенты",** чтобы просмотреть список ваших бортовых клиентов.

2. Выберите клиента, в который необходимо развернуть базовую конфигурацию.

3. Выберите **вкладку План** развертывания, чтобы увидеть все этапы развертывания из базовой базы, добавленной в план развертывания клиента.

4. Выберите шаг развертывания, чтобы открыть страницу шаг развертывания.

5. Выберите **Применить,** чтобы применить выбранный шаг развертывания к клиенту. Если на шаге развертывания указано: "Это действие требует ручного шага", выполните ручной шаг, чтобы шаг развертывания был применен правильно.

## <a name="related-content"></a>См. также:

[Обзор использования базовых данных для развертывания стандартных конфигураций клиента](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (статья)\
[Microsoft 365 Lighthouse (статья)](m365-lighthouse-faq.yml)