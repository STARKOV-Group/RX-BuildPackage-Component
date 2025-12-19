# Сборка пакета (RX BuildPackage Component)

#### Описание:

Сборка пакета с помощью DDS и собранной [утилитой](https://git.starkovgrp.ru/golovnev/PackageXmlGenerator) xml.

##### Логика:

В зависимости от значения переменных [BuildMode](https://git.starkovgrp.ru/ci-cd-components/Completed-RXDTDeploy-Component#buildmode) и SolutionList создает xml файл для сборки пакета по адресу: \$[PackageProjectPath](https://git.starkovgrp.ru/ci-cd-components/Completed-RXDTDeploy-Component#packageprojectpath)\\packageGen.xml  
Если файл не получилось создать, то заканчивает выполнение с ошибкой

С помощью созданного файла и DDS собирает пакет разработки по адресу: \$[PackageProjectPath](https://git.starkovgrp.ru/ci-cd-components/Completed-RXDTDeploy-Component#packageprojectpath)\\package.dat  
Если пакет не получилось собрать, то заканчивает выполнение с ошибкой

В артефакты этапа кладутся логи и, если получилось его собрать, пакет. Сами артефакты хранятся в течении 1 недели

#### Переменные:

##### Пользовательские настройки

##### SolutionList

**Описание:** Список решений для сборки в пакет  
**Примечание:** В дальнейшем будет переделано на исключение указанных решений из публикации, а пока нужно указывать только если нужно собирать пакет не со всеми решениями  
**Обязательность:** Нет  
**Пример:** DirRX.DirectumTargets|DirRX.ProjectPlanning|DirRX.TeamsCommon|Sungero.DirectumRX