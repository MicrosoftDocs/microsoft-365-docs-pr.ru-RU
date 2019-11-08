---
title: Шаг 1. Сетевая инфраструктура для Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть сетевую инфраструктуру для Microsoft 365 корпоративный.
ms.openlocfilehash: 9fe7f16aef8b9c82ded2c17ce562dffb2194eaa2
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033674"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>Шаг 1. Сетевая инфраструктура для Microsoft 365 корпоративный

![Шаг 1. Сеть](./media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 корпоративный включает Office 365, Microsoft Intune и различные службы удостоверений и безопасности Microsoft Azure. Для всех этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы. Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции. 

На этом шаге вы постепенно рассмотрите ключевые вопросы создания производительного подключения к облачным службам Microsoft 365 корпоративный. Общие сведения см. в статье [Принципы работы сети Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

>[!Note]
>Если вы уже развернули сетевую инфраструктуру, см. перечень обязательных и необязательных [условий](networking-exit-criteria.md), при выполнении которых можно считать сетевую инфраструктуру для Microsoft 365 корпоративный настроенной.

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Планирование и развертывание сетевой инфраструктуры Microsoft 365 корпоративный 

Чтобы создать свою сетевую инфраструктуру, соответствующую требованиям Microsoft 365 корпоративный, выполните указанные ниже шаги.

|||
|:-------|:-----|
|![Шаг 1](./media/stepnumbers/Step1.png)|[Подготовка сети к Microsoft 365](networking-provide-bandwidth-cloud-services.md)|
|![Шаг 2](./media/stepnumbers/Step2.png)|[Настройка локальных подключений к Интернету для всех офисов](networking-dns-resolution-same-location.md)|
|![Шаг 3](./media/stepnumbers/Step3.png)|[Удаление разворотов пакетов](networking-avoid-network-hairpins.md)|
|![Шаг 4](./media/stepnumbers/Step4.png)|[Настройка обхода трафика](networking-configure-proxies-firewalls.md)|
|![Шаг 5](./media/stepnumbers/Step5.png)|[Оптимизация производительности клиентов и служб Office 365](networking-optimize-tcp-performance.md)|


Выполнив эти шаги, перейдите к перечню обязательных и необязательных [условий](networking-exit-criteria.md) для соответствия требованиям Microsoft 365 корпоративный, при выполнении которых можно считать данный шаг завершенным.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Как корпорация Майкрософт реализует Microsoft 365 корпоративный

Познакомьтесь ближе с Майкрософт и узнайте, как компания [оптимизировала сеть Майкрософт для облачных служб](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Как корпорация Contoso реализовала Microsoft 365 корпоративный

Посмотрите, как корпорация Contoso, вымышленная представительская многонациональная компания, [оптимизировала сетевые устройства и подключения к Интернету](contoso-networking.md) для облачных служб Microsoft 365.

![Корпорация Contoso](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 1](./media/stepnumbers/Step1.png)|[Подготовка сети к Microsoft 365](networking-provide-bandwidth-cloud-services.md)|

