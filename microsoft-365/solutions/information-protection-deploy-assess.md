---
title: Оценка рисков конфиденциальности данных и определение конфиденциальных элементов с помощью Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Определите правила конфиденциальности данных, соответствующие сценарии, готовность и типы конфиденциальной информации, которые находятся в Microsoft 365 среде.
ms.openlocfilehash: 8e41dccea3569573d45b2e07e8ab7f122c44b311
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229315"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Оценка рисков конфиденциальности данных и определение конфиденциальных элементов с помощью Microsoft 365

Оценка правил конфиденциальности данных и рисков, которые могут быть подвергнуты вашей организации, является ключевым первым шагом перед реализацией любых связанных действий по улучшению, в том числе достижимых с Microsoft 365 функциями и службами.

## <a name="potentially-applicable-data-privacy-regulations"></a>Потенциально применимые правила конфиденциальности данных

Сведения о более широкой нормативной базе для правил конфиденциальности данных см. в статье Портал доверия к службам Майкрософт и ряд статей по регулированию общих правил защиты данных [(GDPR),](/compliance/regulatory/gdpr)а также другие материалы по нормативным актам, которые могут быть подчинены вашей отрасли или региону. [](https://servicetrust.microsoft.com/)

### <a name="gdpr"></a>GDPR

GDPR, наиболее известный и цитируемый из правил конфиденциальности данных, регулирует сбор, хранение, обработку и обмен любыми персональными данными, которые относятся к идентифицированным или идентифицируемым естественным лицам, проживающим в Европейском союзе (ЕС).

В соответствии со статьей 4 GDPR:

- "персональные данные" означает любую информацию, связанную с идентифицированным или идентифицируемым естественным лицом ("субъект данных"); идентифицируемое физическое лицо — это физическое лицо, которое может быть идентифицировано прямо или косвенно, в частности по ссылке на идентификатор, такой как имя, идентификационный номер, данные о расположении, онлайн-идентификаторе или одном или нескольких факторах, связанных с физической, физиологической, генетической, умственной, экономической, культурной или социальной идентичностью этого физического лица.

### <a name="iso-27001"></a>ISO 27001

Соблюдение других стандартов, таких как ISO 27001, также было признано несколькими европейскими надзорными органами в качестве допустимого прокси-сервера намерений для людей, процессов и спектра технологий. Указанные в нем стандарты, которые накладываются на механизмы защиты, управляемые isO-27001, можно считать прокси-сервером, который выполняет некоторые обязательства по конфиденциальности в определенных обстоятельствах.

### <a name="other-data-privacy-regulations"></a>Другие правила конфиденциальности данных

Другие важные правила конфиденциальности данных также указывают требования к обработке персональных данных.

В Соединенных Штатах к ним относятся Закон о защите прав потребителей в Калифорнии[(CCPA),](/compliance/regulatory/ccpa-faq)HIPAA-HITECH (закон о конфиденциальности здравоохранения США) и закон Грэма Лич Блили (GLBA). Кроме того, на месте или в разработке находятся дополнительные нормативные акты, регламентные для конкретного состояния.

Во всем мире в качестве дополнительных примеров можно привести Национальный закон Германии о реализации GDPR (BDSG), Бразильский закон о защите данных (LGPD) и многие другие.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Сопоставление правил для Microsoft 365 категорий технического контроля

Многие из нормативных положений, связанных с конфиденциальностью данных, имеют перекрывающиеся требования, поэтому необходимо понять, к какому регулированию они подлежат до разработки любой схемы технического управления.

Для более поздней ссылки в статьях этого общего решения в этой таблице приводятся выдержки из выборки правил конфиденциальности данных.

| Регулирование | Статья/раздел | Выдержка | Применимые категории технического управления |
|:-------|:-----|:-------|:-------|
| GDPR | Статья 5(1)(f) | Персональные данные обрабатываются таким образом, чтобы обеспечить соответствующую безопасность персональных данных, включая защиту от несанкционированной или незаконной обработки, а также от случайных потерь, разрушений или повреждений с использованием соответствующих технических или организационных мер ("целостность и конфиденциальность").  |  (Все) <br> Удостоверение <br> Устройство <br> Защита от угроз <br> Защита информации <br> Управление информацией <br> Обнаружение и реагирование |
|  | Статья (32)(1)(a) | Учитывая состояние искусства, затраты на реализацию и характер, область, контекст и цели обработки, а также риск различной вероятности и серьезности для прав и свобод естественных лиц, контролер и обработчик должны осуществлять соответствующие технические и организационные меры для обеспечения уровня безопасности, соответствующего риску. , в том числе в качестве соответствующего псевдонима: a) псевдонимизация и шифрование персональных данных. | Защита информации |
|  | Статья (13)(2)(a) | "... в момент получения персональных данных контролер должен предоставить субъекту данных следующие дополнительные сведения, необходимые для обеспечения справедливой и прозрачной обработки: а) период хранения персональных данных или, если это невозможно, критерии, используемые для определения этого периода. | Управление информацией |
|  | Статья (15)(1)(e) | Субъект данных имеет право получить от диспетчера подтверждение того, обрабатываются ли персональные данные, касающиеся него или ее, и где это имеет место, доступ к персональным данным и следующим данным: (e) наличие права запрашивать у диспетчера исправление или стирание персональных данных или ограничение обработки персональных данных в отношении субъекта данных или возражение против такого обработка | Обнаружение и реагирование |
| LGPD | Статья 46 | Агенты обработки должны принимать меры безопасности, технические и административные меры, способные защитить персональные данные от несанкционированных доступов и случайных или незаконных ситуаций уничтожения, потери, изменения, связи или любого типа неправильной или незаконной обработки. | Защита информации <br> Управление информацией <br> Обнаружение и реагирование|
|  | Статья 48 | Оператор должен сообщать органам государственной власти и субъектам данных об инцидентах безопасности, которые могут повлечь за собой риски или соответствующий ущерб для субъектов данных. | Обнаружение и реагирование |
| HIPPA-HITECH | 45 CFR 164.312(e)(1) | Реализуйте технические меры безопасности для защиты от несанкционированного доступа к охраняемой электронной медицинской информации, которая передается по сети электронных коммуникаций. | Защита информации |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Реализуйте механизм шифрования охраняемой электронной медицинской информации, когда это будет сочтено целесообразным. | Защита информации |
|  | 45 CFR 164.312 (c) (2) | Реализуйте электронные механизмы, позволяющие убедиться, что охраняемая медицинская информация в электронном виде не была изменена или удалена несанкционированным образом. | Управление информацией |
|  | 45 CFR 164.316(b)(1)(i) | Если документировать действие, действия или оценку требуется, чтобы этот подгруппа задокументировала, сохраните запись (которая может быть электронной) о действии, действии или оценке. | Управление информацией |
|  | 45 CFR 164.316(b)(1)(ii) | Храните документацию, необходимую согласно требованиям из параграфа (b)(1) данного раздела, в течение 6 лет с даты ее создания или окончания срока ее действия (смотря какая из них наступит позже). | Управление информацией |
|  | 45 C.F.R. 164.308(a)(1)(ii)(D) | Внедрение процедур для регулярного просмотра записей о деятельности информационной системы, таких как журналы аудита, отчеты о доступе и отчеты об инцидентах безопасности | Обнаружение и реагирование |
|  | 45 C.F.R. 164.308(a)(6)(ii) | Выявляйте и реагируйте на предполагаемые или известные нарушения безопасности; смягчайте, насколько это практически возможно, вредные последствия нарушений безопасности, о которых известно соответствующему субъекту или деловому партнеру; документируйте нарушения безопасности и их последствия. | Обнаружение и реагирование |
|  | 45 C.F.R. 164.312(b) | Реализация аппаратных, программных и процедурных механизмов, которые регистрировали и проверяли действия в информационных системах, содержащих или используюх электронные защищенные сведения о состоянии здоровья. | Обнаружение и реагирование |
| CCPA | 1798.105(c) | Предприятие, которое получает проверяемый запрос от потребителя на удаление персональных данных потребителя в соответствии с разделом (a) этого раздела, удаляет личную информацию потребителя из его записей и направляет любым поставщикам услуг удалять личную информацию потребителя из записей. | Обнаружение и реагирование |
|  | 1798.105(d) | (исключения 1798.105(c) <br> Бизнес или поставщик услуг не должны выполнять запрос потребителя на удаление персональных данных потребителя, если это необходимо для бизнеса или поставщика услуг для поддержания персональных данных потребителя, чтобы: (обратитесь к текущему правилу для получения дополнительных сведений). | Обнаружение и реагирование |
|||||

> [!IMPORTANT]
> Этот список не является исчерпывающим. Дополнительные [](../compliance/compliance-manager.md) сведения о применимости указанных разделов к перечисленным категориям технического контроля обратитесь к диспетчеру соответствия требованиям или консультанту по правовым вопросам или консультанту по вопросам соответствия требованиям.

## <a name="knowing-your-data"></a>Знание данных

Независимо от правил, в которых различные типы пользовательских данных внутри и за пределами организации взаимодействуют с вашими системами, это все важные факторы, которые могут повлиять на общую стратегию защиты персональных данных с учетом отраслевых и правительственных правил, которые применяются к вашей организации. Это включает в себя хранение персональных данных, их тип и их количество, а также сведения о том, при каких обстоятельствах они были собраны.

![Знание данных: какой тип и сколько их существует, и при каких обстоятельствах они были собраны](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Перенос данных

Данные также перемещаются со временем по мере их обработки, уточнения и иных версий. Начальный снимок никогда не бывает достаточным. Необходимо постоянно зная ваши данные. Это одна из самых больших проблем для крупных организаций, которые обрабатывают значительные объемы персональных данных. Организации, не регулирующие проблему "знать свои данные", потенциально могут получить очень высокий риск и возможные штрафы со стороны регулирующих органов.

![Жизненный цикл данных](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)

### <a name="where-the-personal-data-is"></a>Где персональные данные

Чтобы решить вопросы конфиденциальности данных, нельзя полагаться на общие представления о том, где, по вашему мнению, могут существовать персональные данные, как сейчас, так и в будущем. Правила конфиденциальности данных требуют, чтобы организации доказали, что они знают, где персональные данные на постоянной основе. Это делает важным сделать начальный снимок всех источников данных для возможного хранения личной информации, в том числе Microsoft 365 среды, и создать механизмы постоянного мониторинга и обнаружения.

Если вы еще не оценили общую готовность и риск, связанный с правилами конфиденциальности данных, используйте следующую трехшаговую структуру для начала работы.

![Действия по оценке общей готовности и риска, связанных с правилами конфиденциальности данных](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

> [!NOTE]
> Эта статья и ее содержимое не предназначены для того, чтобы занять место юридических консультационных служб. Он просто предоставляет некоторые основные рекомендации и ссылки на инструменты, которые могут быть помощь на ранних этапах вашей оценки.

## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Шаг 1. Разработка фундаментального понимания сценариев персональных данных организации

Необходимо оценить степень риска конфиденциальности данных в зависимости от типа личных данных, которыми он управляет в настоящее время, где они хранятся, на каких защитных средствах на них размещены средства управления, как управляется жизненный цикл и кто имеет к нему доступ.

В качестве отправной точки важно указать, какие типы персональных данных существуют в Microsoft 365 среде. Используйте эти категории:

- Данные сотрудников, необходимые для выполнения бизнес-функций
- Данные о своих бизнес-клиентах, партнерах и других взаимоотношениях в сценарии бизнес-к-бизнесу (B2B)
- Данные организации о клиентах, которые предоставляют информацию сетевым службам, которыми организация управляет в сценарии "бизнес-клиент" (B2C).

Вот пример различных типов данных для типичных отделов организации.

![Типы персональных данных](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Большая часть персональных данных, которые подлежат регулированию конфиденциальности данных, обычно собираются и хранятся за пределами Microsoft 365. Любые персональные данные из веб-или мобильных приложений, с которыми сталкиваются пользователи, должны были экспортироваться из таких приложений в Microsoft 365, чтобы они подвергались проверке конфиденциальности данных в Microsoft 365.

Ваша конфиденциальность данных в Microsoft 365 может быть более ограниченной по отношению к вашим веб-приложениям и CRM-системам, которые это решение не решает.

При оценке профиля риска важно также помнить о следующих распространенных проблемах с соблюдением конфиденциальности данных.

 - **Распространение персональных данных.** Насколько рассеяны сведения о заданной теме? Достаточно ли хорошо известно, чтобы убедить контролирующие органы в том, что необходимые элементы управления на месте? Можно ли его при необходимости расследовать и устранять?
- **Защита от эксфильтрации.** Как защитить персональные данные того или иного типа или источника от скомпрометации и как реагировать на них?
- **Защита и риск.** Какие механизмы защиты информации подходят по отношению к риску и как поддерживать непрерывность и производительность бизнеса и минимизировать влияние конечных пользователей, если требуется вмешательство конечных пользователей? Например, следует ли использовать ручную классификацию или шифрование?
- **Хранение персональных данных.** Как долго необходимо хранить сведения, содержащие персональные данные, по веские бизнес-причинам и как избежать прошлых практических действий навсегда, сбалансированных с потребностями хранения для непрерывности бизнеса?
- **Обработка запросов субъекта данных.** Какие механизмы будут необходимы для обработки запросов субъекта данных (DSRs) и любых действий по исправлению, таких как анонимизация, исправление и удаление?
- **Постоянный мониторинг и отчетность.** Какие методы мониторинга, расследования и отчетности доступны для различных типов и источников данных?
- **Ограничения на обработку данных.** Существуют ли ограничения на использование данных для информации, собираемой или хранимой с помощью этих методов, которые организация должна отражать в средствах управления конфиденциальностью? Например, обязательства по тому, что персональные данные не будут использоваться сотрудниками отдела продаж, могут потребовать от вашей организации создать механизмы для предотвращения передачи или хранения этих сведений в системах, связанных с организацией продаж.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Данные сотрудников, необходимые для выполнения бизнес-функций

Организации по своей природе должны собирать данные о сотрудниках в целях электронной идентификации и управления персоналом с учетом того, на что они соглашаются в своих соглашениях о сотрудниках. Пока человек работает в компании, это, как правило, не является проблемой. Организации может потребоваться создать механизмы для предотвращения эксфильтрации или утечки персональных данных сотрудников злоумышленниками.

Если человек покидает компанию, организации обычно имеют процедуры, процедуры, а также графики хранения и удаления учетных записей пользователей, вывода из эксплуатации почтовых ящиков и личных дисков, а также изменения состояния сотрудников в таких вещах, как системы людских ресурсов. В ситуациях, когда речь идет о судебном разбирательстве, у сотрудника или другого участника судебного расследования могут быть веские причины для получения сведений о персональных данных, хранимых в системах организации. В некоторых случаях эта сторона может потребовать удалить или обезличить такие данные.

Для решения таких потребностей организации должны иметь процессы и процедуры, которые устраняют профилактические, детективные и восстановительные потребности, чтобы облегчить такие запросы, заметив, что некоторые сведения о сотруднике можно разумно считать критически важными для непрерывности бизнеса. Например, сведения о том, что человек является автором файла или выполнял функцию.

> [!NOTE]
> Для методов расследования и восстановления персональных данных в Microsoft 365 см. статью [монитор и ответ](information-protection-deploy-monitor-respond.md). Кроме того, может потребоваться использовать автоматизированные схемы классификации и защиты, чтобы убедиться, что персональные данные контролируются во время работы в организации, а также не допустить их выхода из организации в вредоносных ситуациях. Дополнительные [сведения см. в статье Protect](information-protection-deploy-protect-information.md) information.

### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Данные организации о своих бизнес-клиентах в сценарии B2B

Сбор B2B-сведений также является проблемой, так как вашей организации может потребоваться вести учет имен клиентов и транзакций в различных системах для обеспечения непрерывности бизнеса, но при этом защищать эти сведения от непреднамеренного или вредоносного эксфильтрации. Как и данные сотрудников, организации должны иметь политики, процедуры и технические средства управления для защиты таких данных, а также их старение в соответствии с определенными графиками хранения и удаления.

Как правило, контракты с внешними клиентами, партнерами и другими организациями, с которыми организация работает, будут иметь языковые возможности для обработки таких данных, включая защиту, хранение и удаление как во время, так и после того, как объект имеет отношение к организации.

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Данные организации о потребителях, которые предоставляют информацию сетевым службам, которыми управляет организация в сценарии B2C

Эта категория является одной из наиболее думают о конфиденциальности данных, из-за многих общедоступных экземпляров утечки данных клиента. Это может быть преднамеренно, например, третья сторона по контракту с поставщиком или непреднамеренное, например эксфильтрация вредоносным субъектом. Защита данных потребителей является одной из основных причин, по которой ЕС и другие страны приняли эти правила. Правила конфиденциальности данных, такие как GDPR и CCPA, требуют планирования:

- [Планы действий](/compliance/regulatory/gdpr-action-plan) [и контрольные списки готовности к ответственности](/compliance/regulatory/gdpr-arc-Office365)
- [Оценки воздействия на защиту данных](/compliance/regulatory/gdpr-data-protection-impact-assessments)
- [Уведомления о нарушении](/compliance/regulatory/gdpr-breach-Office365)
- [Запросы субъектов данных](/compliance/regulatory/gdpr-dsr-Office365)

Если ваша организация не делает много прямых сборов данных от потребителей, эта категория может быть меньше проблем. Однако для достижения соответствия требованиям может потребоваться пройти процедуры, описанные в этих статьях.

### <a name="step-1-summary"></a>Сводка шаг 1

Понимание риска и регулирования конфиденциальности данных — это важный первый шаг, основанный на понимании сценариев персональных данных организации.

Если у вас нет персональных данных от потребителей в Microsoft 365 среде или они ограничиваются определенными частями среды, а необходимость технического контроля зависит от того, существует ли воздействие данных потребительского типа, то технический контроль может потребоваться использовать только в частях среды с высоким уровнем риска, а не везде.

В то время как рекомендации внешней организации или стандартного набора управления, например от диспетчера соответствия требованиям в Microsoft 365, могут помочь в информировании о стратегии управления, выбор реализации должен быть обусловлен осведомленность о инвентаризации данных для количественной оценки реальной подверженности риску.

Большинство организаций будут иметь некоторый контакт с одним из вышеуказанных сценариев. Важно использовать комплексный подход к оценке.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Шаг 2. Оценка готовности к соблюдению правил конфиденциальности данных

Несмотря на специфику GDPR, вопросы, заданные в бесплатном средстве оценки [GDPR](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) Майкрософт, дают хороший старт для понимания общей готовности к конфиденциальности данных.

Организации, подпав под другие правила конфиденциальности данных, такие как CCPA в США или LGPD Бразилии, также могут воспользоваться инвентаризацией готовности этого средства из-за дублирования положений с GDPR.

Оценка GDPR состоит из этих разделов:

| Section | Описание |
|:-------|:-----|
| Управление | <ol><li>В вашей политике конфиденциальности четко ого- ется, какие данные обрабатываются? </li><li>Регулярно ли вы проводите оценки влияния конфиденциальности (PIAs)? </li><li> Используется ли средство управления личными данными (PI)? </li><li> Имеете ли вы юридические полномочия для ведения бизнеса с использованием данных PI для любого конкретного человека? Отслеживает ли вы согласие на данные? </li><li> Отслеживаете, реализуете и управляете средствами управления аудитом? Отслеживает ли вы утечки данных? </li></ol>|
| Удаление и уведомление | <ol><li>Вы даете четкие инструкции по доступу к данным пользователей? </li><li> Есть ли у вас документированные процессы обработки отказа от согласия? </li><li> Есть ли у вас процесс автоматического удаления данных? </li><li>   Есть ли у вас процесс проверки удостоверений при работе с клиентом? </li></ol>|
| Смягчение рисков и информационная безопасность | <ol><li>Используются ли средства для сканирования неструктурированных данных? </li><li>Все ли серверы устарели и используют ли брандмауэры для их защиты? </li><li>Регулярное резервное копирование серверов? </li><li>Ведете ли вы активный мониторинг утечки данных? </li><li>Шифруете ли вы данные в покое и в передаче? </li></ol>|
| Управление политиками | <ol><li>Как управлять обязательными корпоративными правилами (BCRs)? </li><li>Отслеживает ли вы согласие на данные? </li><li> По шкале от 1 до 5, 5 полностью охвачены, ваши контракты охватывают классификации данных и требования обработки? </li><li>Вы регулярно тестировали план реагирования на инциденты? </li><li>Какую политику вы используете для управления доступом? </li></ol>|
|||

## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Шаг 3. Определение типов конфиденциальной информации, которые возникают в Microsoft 365 среде.

Этот шаг включает идентификацию определенных типов конфиденциальных сведений, которые подлежат определенному регулированию, а также их появление в Microsoft 365 среде.

Поиск контента в среде, содержащего личный, может быть сложной задачей, которая ранее была связана с сочетанием использования поиска соответствия требованиям, обнаружения электронных данных, Advanced eDiscovery, DLP и аудита.

С новым  решением классификации данных в центре администрирования соответствия требованиям Майкрософт это значительно упростилось с возможностями [Обозревателя](../compliance/data-classification-content-explorer.md) контента, который работает со встроенными или настраиваемыми типами конфиденциальной информации, в том числе связанными с персональными данными.

### <a name="sensitive-information-types"></a>Типы конфиденциальной информации

Центр администрирования соответствия требованиям Майкрософт предварительно загружен более чем со 100 типами конфиденциальной информации, большинство из которых связано с определением и поиском персональных данных. Эти встроенные типы конфиденциальной информации могут помочь определить и защитить номера кредитных карт, номера банковских счетов, номера паспортов и другие, основываясь на шаблонах, определенных регулярным выражением (regex) или функцией. Дополнительные сведения см. в статье [Что позволяют искать типы конфиденциальной информации](../compliance/sensitive-information-type-entity-definitions.md).

Если необходимо определить и защитить конфиденциальные элементы определенного для организации или региона типа, например пользовательский формат для идентификации сотрудников или другие персональные данные, не охваченные встроенным типом конфиденциальной информации, с помощью этих методов можно создать настраиваемый тип конфиденциальной информации:

- PowerShell
- Настраиваемые правила с точным совпадением данных (EDM)
- С помощью пользовательского интерфейса центра администрирования Центра соответствия требованиям, как повеяно в статье [Use Compliance Score and Compliance Manager](information-protection-deploy-compliance.md)

Вы также можете настроить существующий встроенный тип конфиденциальной информации.

Дополнительные сведения см. в статьях:

- [Настройка встроенных типов конфиденциальной информации](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Сведения о типах конфиденциальной информации](../compliance/sensitive-information-type-learn-about.md)
- [Создание пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям](../compliance/create-a-custom-sensitive-information-type.md)
- [Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Создание пользовательских типов конфиденциальной информации с помощью классификации на основе точного совпадения данных](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Обозреватель контента

Важным средством, определяющим появление конфиденциальных элементов в [](../compliance/data-classification-content-explorer.md) среде, является новый обозреватель контента в центре администрирования Microsoft 365 соответствия требованиям. Это автоматический инструмент для начального и текущего сканирования всей подписки Microsoft 365 для появления типов конфиденциальной информации и отображения результатов.

Новый инструмент Обозреватель контента позволяет быстро определять расположение конфиденциальных элементов в среде, используя встроенные типы конфиденциальной информации или настраиваемые. Это может включать создание процесса и возложение ответственности за регулярное изучение наличия и расположения конфиденциальных элементов.

Наряду с другими шагами, которые выделены в этой статье, это служит отправной точкой для определения общей подверженности риску, готовности и расположения конфиденциальных элементов для защиты с помощью запланированной конфигурации Microsoft 365 мониторинга.

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Другие методы идентификации персональных данных в среде

Помимо обозревателя контента, организации имеют доступ к возможности поиска контента для создания настраиваемого поиска для поиска персональных данных в своей среде с использованием расширенных критериев поиска и настраиваемого фильтра.

Подробные рекомендации по использованию поиска контента для обнаружения персональных данных предоставляются в [этой статье.](/compliance/regulatory/gdpr) Поиск контента и другие методы обнаружения также изучаются в [DSR для GDPR и CCPA.](/compliance/regulatory/gdpr-dsr-Office365#introduction-to-dsrs)

Дополнительные сведения о методах расследования и восстановления персональных данных в Microsoft 365 в статье монитор и [ответ](information-protection-deploy-monitor-respond.md).

> [!NOTE]
> Чтобы узнать, какие конфиденциальные сведения имеются в файлах, хранимых в локальном хранилище, обратитесь к [Azure Information Protection.](/azure/information-protection/quickstart-findsensitiveinfo)