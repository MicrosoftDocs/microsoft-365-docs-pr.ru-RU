---
title: Правило для финансовых органов здравоохранения (ФИНРА) 4511 (c) США
description: Независимая оценочная проверка того, что Azure и Office 365 могут помочь финансовым фирмам в соответствии с 4511 правилами ФИНРА для хранения и неизменяемыми требованиями к хранению.
keywords: Microsoft 365, соответствие требованиям, предложите
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 80114436580e388afce0508f69dc892c0eaaf435
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690899"
---
# <a name="compliance-offering-financial-industry-regulatory-authority-finra-rule-4511c-united-states"></a>Предложение о соответствии требованиям: правило для законодательных органов здравоохранения (ФИНРА) 4511 (c) США

## <a name="about-finra-rule-4511"></a>О правиле ФИНРА 4511

[Орган финансовой индустрии нормативных актов (финра)](https://www.finra.org/#/) — это самый крупный независимый набор ценных бумаг, в котором изучается более 4 500 брокерских компаний в США. Она была авторизована нами конгресс "для защиты инвесторов в Америке, убедившись, что в отрасли брокерского дилера работает достаточно и хонестли".

В 2011, Комиссия по безопасности США и Exchange (с) утвердили правила внедрения ФИНРА в секунду, регулирующие хранение книг и записей на носителе с электронным хранилищем. [Финра Rule 4511 (c)](https://www.finra.org/sites/default/files/NoticeDocument/p123548.pdf) указывает, что все книги и записи, которые должны быть выполнены в соответствии с правилами финра, должны сохраняться в формате и на носителе, который соответствует правилу "море сообщений Exchange" (ACT) 17A-4 ".

Кроме того, правило ФИНРА 4511 (c) требует компаний, которые должны храниться в течение не менее шести лет в книгах и записях, для которых нет указанного периода хранения в соответствующих правилах ФИНРА или SEA. Фактически, если книги и записи относятся к учетной записи, срок хранения задается в течение шести лет после закрытия учетной записи. В противном случае срок хранения составляет шесть лет после создания таких книг и записей.

## <a name="microsoft-and-finra-rule-4511c"></a>Правила Microsoft и ФИНРА 4511 (c)

Клиенты финансовых служб, представляющие одну из самых интенсивно регулируемых отраслей в мире, могут быть сложными, такими как хранение финансовых транзакций и связанных коммуникаций в неизменяемом и неизменяемом состоянии. Среди них правилом является правило 4511 для законодательных органов здравоохранения (ФИНРА), которое определяет строгие требования для регулируемых сущностей, которые позволяют хранить книги и записи на носителе с электронным хранилищем. Сохраняемые записи должны быть подтверждать без возможности изменять или удалять их до определенного периода хранения.

Неизменное хранилище больших двоичных объектов Microsoft Azure с блокировкой политики и Microsoft Office 365 с блокировкой сохранения могут помочь финансовым учреждениям удовлетворить неизменяемые требования к хранению ФИНРА правила 4511 (c).

## <a name="microsoft-azure"></a>Microsoft Azure

Чтобы оценить соответствие требованиям Azure с ФИНРА правилом 4511 (c), корпорация Майкрософт сохранила независимую оценку, специализирующуюся на управлении записями и сведениями, а также в Кохассет партнерах. Полученный отчет в [секунду 17A-4 (f) & кфтк 1,31 (c-d) Оценка соответствия требованиям: хранилище Microsoft Azure](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)включает в себя соответствие Azure с финра правилом 4511 (c), что задерживается с требованиями к формату и мультимедиа в секунду Rule 17A-4 (f).

Кохассет проверила, что [Azure неизменное хранилище больших двоичных объектов](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) с параметром Lock политики, при использовании для хранения больших двоичных объектов на основе времени в несъемных и неизменяемых (Worm) форматах соответствует соответствующим требованиям к хранилищу финра. Каждый BLOB-объект (запись) защищен от изменений, перезаписывается или удаляется до истечения срока действия требуемого периода хранения и освобождения всех связанных юридических удержаний.

Поставщики программного обеспечения и партнеры с конфиденциальными рабочими нагрузками теперь могут использовать неизменяемое хранилище больших двоичных объектов Azure в качестве однорангового облачного решения для хранения записей и неизменяемого хранилища. Теперь финансовые учреждения могут создавать собственные приложения, используя преимущества этих функций, в то же время обеспечивая их соответствие требованиям.

## <a name="microsoft-office-365"></a>Microsoft Office 365

Чтобы оценить соответствие требованиям Office 365 с помощью правила ФИНРА 4511 (c), корпорация Майкрософт сохраняла начальная независимая фирма, специализирующаяся на нормативных проблемах, Ковингтон & Бурлинг, ЛЛП. В полученном отчете, архивации в Microsoft Office 365, хранения данных и правиле 17A – 4 Ковингтон проверено, что [Office 365 с блокировкой сохранения](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) включает функции архивации, которые позволяют поднадзорным клиентам, в том числе брокерам брокера, хранить данные так, чтобы они соответствовали требованиям финра для хранения записей.

Архивация в Office 365 помогает сохранять широкий спектр данных, в том числе электронную почту, голосовую почту, Общие документы, мгновенные сообщения и сторонние данные. В частности, архивация в Office 365 позволяет клиентам настраивать глобальные и детализированные политики хранения сообщений для хранения данных за определенный период, а не в неизменяемом формате без удаления.

## <a name="microsoft-in-scope-cloud-services"></a>Облачные службы Майкрософт в области

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9f756cce-b15d-45a9-94d7-6a583dee4401&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

## <a name="audits-reports-and-certificates"></a>Аудиты, отчеты и сертификаты

### <a name="azure--finra-rule-4511c"></a>Azure & правило ФИНРА 4511 (c)

[С 17A-4 (f) & КФТК 1,31 (c-d) Оценка соответствия требованиям хранилища Azure](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--finra-rule-4511c"></a>Office 365 & правило ФИНРА 4511 (c)

[Архивация в Office 365, хранение данных и в секунду правило соответствия требованиям 17A – 4](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)

## <a name="how-to-implement"></a>Реализация

- **Регламентированные финансовые услуги**: карта соответствия требованиям основных принципов и норм США для облачных вычислений и Microsoft Online Services. [Подробнее](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- **Оценка риска & соответствие требованиям**: создание модели управления для оценки рисков облачных служб Майкрософт и уведомления стабилизатора. [Подробнее](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- **Финансовые варианты использования**: обзоры вариантов, учебные пособия и другие ресурсы для создания решений Azure для финансовых служб.

[Подробнее](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>Ресурсы

- [Программа Microsoft Financial Services для обеспечения соответствия требованиям](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Облачные службы и финансовые службы Microsoft Business](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Соответствие финансовых служб в Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Средство оценки рисков облачных служб Azure](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Политики хранения Microsoft Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Блог по финансовым службам Майкрософт](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Соответствие требованиям в центре управления безопасностью Майкрософт](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Загрузка фонового рисунка предложения

Нужен фоновый документ для этого предложения? Скачайте [PDF-файл](https://download.microsoft.com/download/6/B/2/6B20520B-E264-4B58-9EE2-DD6C87D9E254/FINRA-Compliance.pdf).
