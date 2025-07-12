# 🧪 Laboratorio 1: Introducción a ANTLR

## 📋 Descripción General

En este laboratorio trabajarás con **ANTLR**, un generador de analizadores sintácticos. Hemos proporcionado un `Dockerfile` para ayudarte a configurar el entorno rápidamente. Utilizaremos Python para hacer pruebas, ya que es más sencillo que Java para pruebas pequeñas.

* **Modalidad: Individual**

## 🧰 Instrucciones de Configuración

1. **Construir y Ejecutar el Contenedor Docker**Desde el directorio raíz de este laboratorio, ejecuta el siguiente comando para construir la imagen y lanzar un contenedor interactivo:

   ```bash
   docker build --rm . -t lab1-image && docker run --rm -ti -v "$(pwd)/program":/program lab1-image
   ```
2. **Entender el Entorno**

   - El directorio `program` se monta dentro del contenedor.
   - Este contiene la **gramática de ANTLR**, un archivo `Driver.py` (punto de entrada principal) y un archivo `program_test.txt` (entrada de prueba).
3. **Generar Archivos de Lexer y Parser**Dentro del contenedor, compila la gramática ANTLR a Python con:

   ```bash
   antlr -Dlanguage=Python3 MiniLang.g4
   ```
4. **Ejecutar el Analizador**
   Usa el driver para analizar el archivo de prueba:

   ```bash
   python3 Driver.py program_test.txt
   ```

   - ✅ Si el archivo es sintácticamente correcto, **no se mostrará ningún resultado**.
   - ❌ Si existen errores, ANTLR los mostrará en la consola.
   - **Next Step:** Jueguen editando el archivo y vean los cambios en los resultados de compilación.