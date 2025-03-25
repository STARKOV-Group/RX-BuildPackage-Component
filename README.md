# RX BuildPackage Component

Используется для сборки пакетов. 

Особенности: 

Package.xml атогенерируется для избежания зависимостей проекта от загруженного xml в гит. Это позволяет избежать ситуаций с неверной генерацией при изменении состава решений и необходимости поддерживать в актуальном состоянии package.xml

Утилита с автогенерацией лежит на нашем гитлабе: http://git.starkovgrp.local/golovnev/PackageXmlGenerator

Стандартный вариант выгрузки - DebugRelease

Варианты выгрузки
1. Release 			-	Исполняемые
2. DebugRelease		-	Release + дебаг
3. Source			-	DebugRelease + передача исходников
4. SourceBase		-	Source + передача как базовый слой

Вариант выгрузки задаётся через переменную variables: BuildMode