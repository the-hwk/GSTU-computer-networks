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
