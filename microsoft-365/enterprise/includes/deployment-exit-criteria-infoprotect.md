<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Обязательное требование: определены уровни безопасности и защиты информации в организации

Вы запланировали и определили уровни безопасности, необходимые вашей организации. Эти уровни определяют минимальный уровень безопасности и дополнительные уровни для конфиденциальной информации и требуемой защиты данных.

Вы используете не менее трех указанных ниже уровней безопасности.

- Базовый уровень
- Конфиденциальный
- Строго регулируемый уровень

Чтобы выполнить это требование, см. [шаг 1](../infoprotect-define-sec-infoprotect-levels.md) (при необходимости). 

<a name="crit-infoprotect-step3"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a>Обязательное требование: настроена усиленная защита для Microsoft 365

Вы настроили указанные ниже параметры [для повышения безопасности Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Политики управления угрозами в Центре безопасности Microsoft 365
- Дополнительные параметры, используемые во всем клиенте Exchange Online
- Политики общего доступа для всего клиента в центре администрирования SharePoint Online
- Параметры в Azure Active Directory (Azure AD)

Вы также [включили Office 365 Advanced Threat Protection для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Чтобы выполнить это требование, см. [шаг 3](../infoprotect-configure-increased-security-office-365.md) (при необходимости). 

<a name="crit-infoprotect-step2"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>Необязательное требование: в используемой вами среде настроена классификация

Совместно с юридическим отделом и отделом соответствия требованиям вы разработали соответствующую классификацию и схему маркировки для управления данными вашей организации и политик безопасности. 

Эти политики соответствуют настройке и развертыванию следующих элементов:

- Типы конфиденциальных данных
- Метки хранения
- Метки конфиденциальности
- Метки Azure Information Protection

Чтобы выполнить это требование, см. [шаг 2](../infoprotect-configure-classification.md) (при необходимости). 


<a name="crit-infoprotect-step4"></a>
### <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Необязательно: Windows Information Protection развернуто в вашей среде

На ваших зарегистрированных устройствах Windows 10 Корпоративная развернута и применена политика Intune, которая определяет:

- Какие приложения следует защищать.
- Уровень защиты.
- На что распространяется защита.

Чтобы выполнить это требование, см. [шаг 4](../infoprotect-deploy-windows-information-protection.md) (при необходимости). 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>Необязательно: развернута служба защиты от потери данных (DLP) Office 365

Вы проанализировали, протестировали, а затем развернули набор политик DLP с указанием местоположений и правил с условиями и действиями, требуемых вашей организацией для защиты данных клиентов и других типов конфиденциальных данных, а также для соблюдения отраслевых и региональных норм и требований.

Ваши сотрудники, ответственные за соблюдение норм и безопасность данных, используют панель мониторинга безопасности и соответствия требованиям Office 365 для контроля инцидентов с DLP.

Чтобы выполнить это требование, см. [шаг 5](../infoprotect-data-loss-prevention.md) (при необходимости). 


<a name="crit-infoprotect-step6"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>Необязательное требование: настроено управление привилегированным доступом для Office 365

С помощью сведений в статье [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) вы включили привилегированный доступ и создали одну или несколько политик привилегированного доступа в организации. Вы настроили эти политики и включили своевременный доступ для получения доступа к конфиденциальным данным или важным параметрам конфигурации.

Чтобы выполнить это требование, см. [шаг 6](../infoprotect-configure-privileged-access-management.md) (при необходимости). 
