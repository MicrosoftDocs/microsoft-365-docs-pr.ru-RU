---
title: Этап 4. Office 365 профессиональный плюс
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру Office 365 профессиональный плюс для Microsoft 365 корпоративный.
ms.openlocfilehash: 5c32257fb9066f170da1f1a3cfe4b865e383cfcb
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646404"
---
# <a name="phase-4-office-365-proplus"></a>Этап 4. Office 365 профессиональный плюс

![Этап 4. Office 365 профессиональный плюс](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Этот этап применяется к планам E3 и E5 Microsoft 365 корпоративный и Microsoft 365 для образования.*

В состав Microsoft 365 корпоративный входит Office 365 профессиональный плюс — версия Office, доступная по подписке. Как и Office 2019, Office 365 профессиональный плюс включает все приложения Office, устанавливающиеся непосредственно на клиентских устройствах. В отличие от Office 2019, Office 365 профессиональный плюс регулярно обновляется с добавлением новых возможностей и использует модель лицензирования на основе пользователей, позволяющую устанавливать Office на нескольких устройствах. Дополнительные сведения см. в статье [Office 365 профессиональный плюс на предприятии](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

На этом этапе мы развернем Office 365 профессиональный плюс на клиентских устройствах в составе Microsoft 365 корпоративный. Помимо этого руководства, рекомендуем использовать [Microsoft Fastrack](https://fasttrack.microsoft.com/office) для развертывания. 

Если вы уже развернули Office 365 профессиональный плюс, см. [критерии выхода](office365proplus-exit-criteria.md) для этого этапа, чтобы убедиться, что выполнены обязательные условия для Microsoft 365 корпоративный.

>[!Note]
>Для совместного развертывания Windows 10 Корпоративная и Office 365 профессиональный плюс обратитесь к статье [Центр развертывания компьютеров](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Шаг 1. Оценка среды

Перед развертыванием Office 365 профессиональный плюс следуйте инструкциям из статьи [Оценка среды и требований для развертывания Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Эта оценка включает проверку требований к системе, сведений о клиентских устройствах (например, архитектурах и необходимых языках), требований к лицензированию, сетевых возможностей и совместимости приложений. Эта проверка поможет вам принять ключевые решения в ходе планирования развертывания.

## <a name="step-2-plan-your-deployment"></a>Действие 2. Планирование развертывания

После оценки среды следуйте инструкциям из статьи [Планирование развертывания Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus), чтобы создать план развертывания. Этот план включает следующие решения: 

- способ развертывания Office, в том числе используемое средство (например, System Center Configuration Manager или средство развертывания Office) и источник, из которого устанавливается Office;
- способ управления обновлениями Office;
- используемые каналы обновления (каналы обновления Office определяют, как часто пользователи получают обновления функций своих приложений Office);
- установочные пакеты и группы развертывания Office, которые требуется использовать, в том числе приложения Office и языки, которые требуется установить для тех или иных пользователей.

В [статье, посвященной планированию](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus), представлены рекомендации по всем этим вопросам, включая управление развертыванием, управление обновлениями, определение установочных пакетов и создание групп развертывания. 

## <a name="step-3-deploy"></a>Действие 3. Развертывание

В соответствии с планом развертывания выберите способ развертывания.

- **[Развертывание Office 365 профессиональный плюс с помощью System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** управляйте развертыванием с помощью Configuration Manager, скачав и установив Office из точек распространения в сети.

- **[Развертывание Office 365 профессиональный плюс с помощью ODT из облака](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** управляйте развертыванием с помощью ODT, установив Office на клиентских устройствах непосредственно из сети CDN Office
 
- **[Самостоятельная установка Office 365 профессиональный плюс с портала Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** управляйте развертыванием на портале Office. Пользователи будут устанавливать Office на своих клиентских устройствах непосредственно с портала.

Во многих организациях для разных пользователей используются разные варианты. Например, для большинства пользователей развертывание Office может быть выполнено с помощью Configuration Manager, но для небольшая группа сотрудников, которые нечасто подключаются ко внутренней сети, установит Office самостоятельно. 

Если в вашей организации используется Configuration Manager, рекомендуем выполнить обновление до Current Branch и текущего выпуска. Дополнительные сведения см. в статье [Какую ветвь Configuration Manager следует использовать?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Как корпорация Майкрософт реализует Microsoft 365 корпоративный

Узнайте, как эксперты Майкрософт [развертывают обновления для Office 365 профессиональный плюс и управляют ими](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Как корпорация Contoso реализовала Microsoft 365 корпоративный

См. статью с описанием показательного примера [развертывания Office 365 профессиональный плюс](contoso-o365pp.md) корпорацией Contoso — вымышленной глобальной организацией.

![Корпорация Contoso](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующий шаг

[Условия, при выполнении которых можно считать инфраструктуру Office 365 профессиональный плюс настроенной](office365proplus-exit-criteria.md)
