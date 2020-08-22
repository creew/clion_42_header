# clion_42_header

Данный проект представляет собой шаблон для .c/.h файлов для учебных проектов сети 42

Для использования необходимо добавить сам шаблон в **Settings->Editor->File and Code Templates->Includes**

[42 header.h](42%20header.h)<br/>
![](/resources/file_and_code_template.png)

Прописать имя файла с шаблоном в шаблоны *.c файлов в **Settings->Editor->File and Code Templates->Files->C Source File**
```
#parse("42 header.h")
#if (${HEADER_FILENAME})
#[[#include]]# "${HEADER_FILENAME}"
#end
```
![](/resources/c_source_file.png)

и *.h файлов в **Settings->Editor->File and Code Templates->Files->C Header File**
```
#parse("42 header.h")
#[[#ifndef]]# ${INCLUDE_GUARD}
#[[# define]]# ${INCLUDE_GUARD}

#[[#endif]]#
```
![](/resources/c_header_file.png)

А также изменить строку стиля Header Guard в 
**Settings->Editor->Code Style->C/C++->Naming Convention** на
```
${FILE_NAME}_${EXT}
```
![](/resources/header_guard.png)

Из минусов - не нашел где в Apache Velocity Template получить текущую дату, поэтому время без секунд, ну и не обновляется дата при обновлении файла, потому что это всего лишь шаблон для новых файлов
