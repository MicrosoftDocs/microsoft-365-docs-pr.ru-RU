---
title: Шаг 2. Настройка классификации для среды
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить различные способы классификации данных в организации.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870637"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Шаг 2. Настройка классификации для среды

*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

На этом шаге вы проведете работу с юридическим отделом и отделом соответствия требованиям и определите схему классификации данных в своей организации.

## <a name="microsoft-classifications"></a>Классификация Корпорации Майкрософт

В Microsoft 365 имеются три указанных ниже типа классификации.

- Типы конфиденциальной информации для Office 365
- Метки Office 365
- Метки и защита Azure Information Protection

### <a name="sensitive-information-types-for-office-365"></a>Типы конфиденциальной информации для Office 365

Типы конфиденциальной информации для Office 365 определяют порядок распознавания определенных типов информации, например номеров службы здравоохранения или номеров кредитных карт, автоматическими процессами, например функцией поиска. Вы можете использовать типы конфиденциальной информации для поиска конфиденциальных данных и их защиты с помощью правил и политик защиты от потери данных. Дополнительные сведения см. в статье [Обзор политик защиты от потери данных](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Например, типы конфиденциальной информации особенно полезны для обеспечения соответствия требованиям и выполнения требований нормативных актов, например Общего регламента по защите данных (GDPR).

### <a name="office-365-labels"></a>Метки Office 365
Вы можете использовать метки Office 365 для личных данных и для файлов, являющихся объектом строгого регулирования или коммерческой тайны и хранящихся в SharePoint Online и OneDrive для бизнеса. Дополнительные сведения (в том числе о том, как создавать такие типы) см. в статье [Общие сведения о метках](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).

Если вы решите использовать метки Office 365, вам следует настроить хотя бы одну метку для каждого уровня защиты. Например, вы можете создать три метки для указанных ниже уровней.

- Базовый уровень
- Конфиденциальный
- Строго регулируемый уровень

### <a name="azure-information-protection-labels-and-protection"></a>Метки и защита Azure Information Protection

Вы можете использовать метки Azure Information Protection для классификации и (необязательно) защиты документов и электронных писем вашей организации. Эти метки можно применять к документам, хранящимся за пределами Office 365. Эти метки можно применять автоматически (это делают администраторы, задающие правила и условия), вручную (это делают пользователи) или в смешанном порядке, когда пользователям предоставляют необходимые рекомендации.

Чтобы спланировать и развернуть метки Azure Information Protection, выполните указанные ниже действия.

1. Изучите [требования для Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Выполните [стратегический план развертывания для классификации, маркирования и защиты](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Дополнительные сведения см. в [документации по библиотеке Azure Information Protection](https://docs.microsoft.com/information-protection/).

## <a name="classification-for-gdpr"></a>Классификация для GDPR

Пример схемы классификации, включающей личные данные для GDPR, см. в статье [Разработка архитектуры схемы классификации для персональных данных](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: классификация данных](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step3), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Настройка усиленной защиты для Office 365](infoprotect-configure-increased-security-office-365.md)|

