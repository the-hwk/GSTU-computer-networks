## Компьютерные сети

**Код для выполнения консольных команд**
```Python
import subprocess
import chardet

class CommandLine:
    @staticmethod
    def __decode(bytes_obj:bytes) -> str:
        encoding = chardet.detect(bytes_obj)['encoding']
        return bytes_obj.decode(encoding)

    @staticmethod
    def exec(command:str) -> str:
        process = subprocess.run(command, stdout=subprocess.PIPE, shell=True)
        return CommandLine.__decode(process.stdout)
```

Выполнить поиск всех узлов в подсети.
Выполнение: в цикле вызвать `ping` для всех ip-адресов в подсети. Путем обработки строки, возвращаемой командой `ping`, можно выяснить есть ли такой узел или нет (подсказка: выполните команду `ping` в командной строке и посмотрите чем отличается вывод этой команды когда пингуемый узел есть и когда его нет).
