Revisar compatibilidad

https://en.cppreference.com/w/cpp/compiler_support

| Mingw | https://winlibs.com/ |  |
| --- | --- | --- |
| Msvc |  | Viene con Microsoft VS |
| Clang llmv | https://winlibs.com/ |  |

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9963ec29-9a81-4752-a84f-440236bff2fa/6923a1a1-b7e7-42a2-8bd9-ec7164d93323/Untitled.png)

Env —> Variables del sistema —> Variables del sistema —> Copiar “C:\mingw64\bin”

“Developer command prompt”

---

C++ VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools

---

**Prueba y configuración**

```cpp
#include <iostream>

int main(){
    auto result = (10 <=> 20) > 0;
    std::cout << result << std::endl;
}
```

La salida del programa debe ser “0”

En “Terminal” —> “Configure tasks” —> “tasks.json”

### **Para Mingw y Clang**

```json
"args": [
				"-g",
				"-std=c++23",
				"${workspaceFolder}\\*.cpp",
				"${fileDirname}\\NAME.exe"
			],
```

### **Para Msvc**

```json

```

• Para correr el compilador de Microsoft se debe entrar al Developer terminar (Powershell) y abrir VSC de ahí con “code .”

---

• Ctrl + Alt + P —> >C/C++: Edit Configurations (UI)