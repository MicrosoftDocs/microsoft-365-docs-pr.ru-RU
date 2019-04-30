---
title: Шаг 1. Сетевая инфраструктура для Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть сетевую инфраструктуру для Microsoft 365 корпоративный.
ms.openlocfilehash: 9b8c23d543eca97147801d70e42de7105266c52d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399963"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>Шаг 1. Сетевая инфраструктура для Microsoft 365 корпоративный

![](./media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 корпоративный включает Office 365 и Microsoft Intune в составе Enterprise Management + Security (EMS). Для обеих этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы. Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции. 

На этом шаге вы постепенно рассмотрите ключевые вопросы создания производительного подключения к облачным службам Microsoft 365 корпоративный. Общие сведения см. в статье [Принципы работы сети Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

>[!Note]
>Если вы уже развернули сетевую инфраструктуру, см. перечень обязательных и необязательных [условий](networking-exit-criteria.md), при выполнении которых можно считать сетевую инфраструктуру для Microsoft 365 корпоративный настроенной.

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Планирование и развертывание сетевой инфраструктуры Microsoft 365 корпоративный 

Чтобы создать свою сетевую инфраструктуру, соответствующую требованиям Microsoft 365 корпоративный, выполните указанные ниже шаги.

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Подготовка сети к Microsoft 365](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[Настройка локальных подключений к Интернету для всех офисов](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[Удаление разворотов пакетов](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[Настройка обхода трафика](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[Оптимизация производительности клиентов и служб Office 365](networking-optimize-tcp-performance.md)|


Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](networking-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Как корпорация Майкрософт реализует Microsoft 365 корпоративный

Загляните в корпорацию Майкрософт и узнайте, как компания подготовила и оптимизировала сеть Майкрософт для облачных служб Office 365, в этом вам поможет статья [Оптимизация производительности сети для Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Как корпорация Contoso реализовала Microsoft 365 корпоративный

Посмотрите, как корпорация Contoso, вымышленная многонациональная компания, [оптимизировала свою сеть](contoso-networking.md) для облачных служб Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Подготовка сети к Microsoft 365](networking-provide-bandwidth-cloud-services.md)|

