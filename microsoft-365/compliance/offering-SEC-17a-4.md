---
title: Правила для ценных бумаг и Комиссии Exchange (с) правило 17A-4 (f), Соединенные Штаты
description: Независимая оценка — Проверка того, что Azure и Office 365 могут помочь финансовым фирмам в секунду хранить записи 17A-4 (f), а также неизменяемые требования к хранению.
keywords: Microsoft 365, соответствие требованиям, предложения
localization_priority: None
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: c0abd8db3084630a6f848f740f5b1387dc58b704
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208191"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>Правила для ценных бумаг и Комиссии Exchange (с) правило 17A-4 (f), Соединенные Штаты

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft и SEC Rule 17A-4 (f)

[Ценные бумаги США и Комиссия Exchange (с)](https://www.sec.gov/) — это независимый орган федерального правительства США и основной оверсир и стабилизатора ценных бумаг США. ИТ – права на обеспечение безопасности в федеральных законодательствах по ценным бумагам, предлагает новые правила для ценных бумаг и заменяют рыночную норму ценного в отрасли.

В разделе SEC определены строгие и явные требования для регулируемых сущностей, которые позволяют хранить книги и записи на носителе с электронным хранилищем. Он установил [17 CFR 240.17 a – 3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3) и [17 CFR 240.17 a – 4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64) для регулирования рекордкипинг, включая сроки хранения, для брокера ценных бумаг (дилеров). Позже, с [измененным](https://www.sec.gov/rules/interp/34-47806.htm) 17 CFR 240.17 a-4 абзаца (f), вызвав два интерпретированных выпуска, чтобы разрешить хранение книг и записей на носителе электронных данных до тех пор, пока были выполнены определенные условия.

Система электронных хранилищ отвечает этим условиям, если она не позволяет внести изменения или стирание записей для требуемого периода хранения. Срок хранения от трех до шести лет зависит от типов записей, с немедленным доступом, указанным в первых двух годах. Кроме того, для одного из интерпретированных выпусков необходимо, чтобы система хранения сохраняла записи за период хранения за секунду, чтобы соответствовать субпоенас, юридическим удержаниям или другим таким требованиям.

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft и SEC Rule 17A-4 (f)

Клиенты финансовых служб, представляющие одну из самых интенсивно регулируемых отраслей в мире, могут быть сложными, такими как хранение финансовых транзакций и связанных коммуникаций в неизменяемом и неизменяемом состоянии. Среди наиболее подправности правило 17A-4 (f) для безопасности США и Комиссии (с), которое определяет строгие требования для регулируемых сущностей, которые позволяют хранить книги и записи на носителе с электронным хранилищем. Сохраняемые записи должны быть подтверждать без возможности изменять или удалять их до определенного периода хранения.

Неизменное хранилище больших двоичных объектов Microsoft Azure с блокировкой политики и Microsoft Office 365 с блокировкой сохранения могут помочь финансовым учреждениям удовлетворить неизменяемые требования к хранению в секунду Rule 17A-4 (f).

Чтобы оценить соответствие требованиям Azure и Office 365, используя правило 17A-4 (f), корпорация Майкрософт сохранила независимую оценку, специализирующуюся на управлении записями и информационном управлении, Кохассет Associates. В полученном отчете для:

- **Azure**: [SEC 17A-4 (f) Оценка соответствия требованиям: служба хранилища Microsoft Azure](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), Кохассет проверила, что [неизменное хранилище больших двоичных объектов Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) с параметром Lock политики, при использовании для хранения больших двоичных объектов на основе времени в неудаляемом и неизменяемом (Worm) формате, соответствует неизменяемым требованиям к хранению правила sec. Каждый BLOB-объект (запись) защищен от изменений, перезаписывается или удаляется до истечения срока действия требуемого периода хранения и освобождения всех связанных юридических удержаний. Поставщики программного обеспечения и партнеры с конфиденциальными рабочими нагрузками теперь могут полагаться на неизменное хранилище больших двоичных объектов Azure в качестве облачного решения онестоп для хранения записей и неизменяемого хранилища. Теперь финансовые учреждения могут создавать собственные приложения, используя преимущества этих функций, в то же время обеспечивая их соответствие требованиям.
- **Office 365**: [Используйте Exchange Online для согласования с 17A-4](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4), Кохассет проверено [, что Office 365 с блокировкой сохранения](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) включает функции архивации, которые позволяют поднадзорным клиентам, в том числе брокерам брокера, хранить данные способом, которые помогают им соответствовать требованиям к хранению записей. Политики хранения в Office 365 помогают сохранить широкий спектр данных, в том числе электронную почту, голосовую почту, Общие документы, мгновенные сообщения и сторонние данные. В частности, архивация в Office 365 позволяет клиентам задавать глобальные политики хранения сообщений для хранения данных за определенный период, а не в неизменяемом формате без удаления.

## <a name="microsoft-in-scope-cloud-services"></a>Поддерживаемые облачные службы Майкрософт

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>Аудит, отчеты и сертификаты

### <a name="azure--sec-rule-17"></a>Правило Azure & SEC 17

[С 17A-4 (f) & КФТК 1,31 (c-d) Оценка соответствия требованиям хранилища Azure](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Office 365 & правило 17

[С 17A-4 (f) Оценка соответствия требованиям: центр безопасности Майкрософт & центр соответствия требованиям Exchange Online](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>Методика реализации

### <a name="financial-services-regulation"></a>Регламентированные финансовые услуги

Карта соответствия требованиям ключевых норм США для облачных вычислений и Microsoft Online Services. [Подробнее](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>Руководство по оценке риска & соответствие требованиям

Создание модели управления для оценки рисков облачных служб Майкрософт и уведомления стабилизатора. [Подробнее](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>Финансовые варианты использования

Используйте обзоры вариантов, учебные пособия и другие ресурсы для создания решений Azure для финансовых служб. [Подробнее](https://docs.microsoft.com/azure/industry/financial/)

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Оценка риска с помощью диспетчера соответствия требованиям (Майкрософт)

[Диспетчер соответствия требованиям (Майкрософт](compliance-manager.md) ) — это функция в [центре соответствия требованиям Microsoft 365](microsoft-365-compliance-center.md) , которая поможет вам оценить уровень соответствия требованиям организации и предпринять меры по снижению рисков. Диспетчер соответствия требованиям предоставляет расширенный шаблон для создания оценки этих нормативных требований. Найдите шаблон на странице " **шаблоны оценки** " в диспетчере соответствия требованиям. Узнайте, как [создавать оценки в диспетчере соответствия требованиям](compliance-manager-assessments.md).

## <a name="resources"></a>Ресурсы

- [Архивация в Microsoft Office 365, хранение данных и правило 17A — 4](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)
- [Соответствие финансовым службам Майкрософт](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Программа обеспечения соответствия Microsoft Business Cloud Services и финансовые услуги](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Соответствие финансовых услуг требованиям в Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Средство оценки облачных рисков для финансовых услуг в Azure](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Политики хранения Microsoft Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Блог финансовых услуг Майкрософт](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Соответствие требованиям в центре управления безопасностью Майкрософт](https://www.microsoft.com/trust-center/compliance/compliance-overview)
