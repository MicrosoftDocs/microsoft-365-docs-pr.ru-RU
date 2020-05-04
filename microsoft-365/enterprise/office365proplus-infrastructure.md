---
title: Этап 4. Приложения Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру приложений Microsoft 365 для предприятий для планов подписки Microsoft 365 корпоративный.
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011951"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Этап 4. Приложения Microsoft 365 для предприятий

![Этап 4. Приложения Microsoft 365 для предприятий](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Этот этап применяется к планам E3 и E5 Microsoft 365 корпоративный и Microsoft 365 для образования.*

В состав Microsoft 365 корпоративный входят приложения Microsoft 365 для предприятий — это версия Office, доступная по подписке. Как и Office 2019, приложения Microsoft 365 для предприятий включают все приложения Office, устанавливающиеся непосредственно на клиентских устройствах. В отличие от Office 2019, приложения Microsoft 365 для предприятий регулярно обновляются с добавлением новых возможностей и используют модель лицензирования на основе пользователей, позволяющую устанавливать Office на нескольких устройствах. Дополнительные сведения см. в статье [Приложения Microsoft 365 для предприятий](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).

На этом этапе мы развернем приложения Microsoft 365 для предприятий на клиентских устройствах в составе Microsoft 365 корпоративный. Помимо этого руководства, рекомендуем использовать для развертывания [Microsoft FastTrack](https://fasttrack.microsoft.com/office). 

Если вы уже развернули приложения Microsoft 365 для предприятий, см. [критерии выхода](office365proplus-exit-criteria.md) для этого этапа, чтобы убедиться, что выполнены обязательные условия для Microsoft 365 корпоративный.

>[!Note]
>Для совместного развертывания Windows 10 Корпоративная и приложений Microsoft 365 для предприятий см. [Центр развертывания компьютеров](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Шаг 1. Оценка среды

Перед развертыванием приложений Microsoft 365 для предприятий следуйте инструкциям из статьи [Оценка среды и требований для развертывания приложений Microsoft 365](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). Эта оценка включает проверку требований к системе, сведений о клиентских устройствах (например, об архитектурах и необходимых языках), требований к лицензированию, сетевых возможностей и совместимости приложений. Эта проверка поможет вам принять ключевые решения в ходе планирования развертывания.

## <a name="step-2-plan-your-deployment"></a>Действие 2. Планирование развертывания

После оценки среды следуйте инструкциям из статьи [Планирование развертывания приложений Microsoft 365](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps), чтобы создать план развертывания. Этот план включает следующие решения: 

- способ развертывания Office, в том числе используемое средство (например, Microsoft Endpoint Configuration Manager или средство развертывания Office) и источник, из которого устанавливается Office;
- способ управления обновлениями Office;
- используемые каналы обновления (каналы обновления Office определяют, как часто пользователи получают обновления функций своих приложений Office);
- установочные пакеты и группы развертывания Office, которые требуется использовать, в том числе приложения Office и языки, которые требуется установить для тех или иных пользователей.

В [статье, посвященной планированию](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps), представлены рекомендации по всем этим вопросам, включая управление развертыванием, управление обновлениями, определение установочных пакетов и создание групп развертывания. 

## <a name="step-3-deploy"></a>Действие 3. Развертывание

В соответствии с планом развертывания выберите способ развертывания.

- **[Развертывание приложений Microsoft 365 с помощью диспетчера конфигураций](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** управляйте развертыванием с помощью диспетчера конфигураций, используя точки распространения в вашей сети для скачивания и развертывания Office

- **[Развертывание приложений Microsoft 365 из облака](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** управляйте развертыванием с помощью ODT, устанавливая Office на клиентские устройства непосредственно из сети CDN Office
 
- **[Самостоятельная установка приложений Microsoft 365 для предприятий с портала Office](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** управляйте развертыванием на портале Office. Пользователи будут устанавливать Office на своих клиентских устройствах непосредственно с портала.

Во многих организациях для разных пользователей используются разные варианты. Например, для большинства пользователей развертывание Office может быть выполнено с помощью Configuration Manager, но для небольшая группа сотрудников, которые нечасто подключаются ко внутренней сети, установит Office самостоятельно. 

Если в вашей организации используется Configuration Manager, рекомендуем выполнить обновление до Current Branch и текущего выпуска. Дополнительные сведения см. в статье [Какую ветвь Configuration Manager следует использовать?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Как корпорация Майкрософт реализует Microsoft 365 корпоративный

Узнайте, как эксперты Майкрософт [развертывают обновления для приложений Microsoft 365 для предприятий и управляют ими](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Как корпорация Contoso реализовала Microsoft 365 корпоративный

См. статью с описанием показательного примера [развертывания приложений Microsoft 365 для предприятий](contoso-o365pp.md) в корпорации Contoso — вымышленной глобальной организации.

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующий шаг

[Условия, при которых можно считать развертывание приложений Microsoft 365 для предприятий завершенным](office365proplus-exit-criteria.md)
