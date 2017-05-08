Configuración de un Programa OpenGL en Visual Studio usando GLUT

Software:
- Visual Studio 2013 Profesional or Express Edition
- Freeglut library (Windows binaries)
  + URL: http://freeglut.sourceforge.net/
  + Ir a: Martin Payne's Windows binaries (MSVC and MinGW): http://freeglut.sourceforge.net/index.php#download
  + O ir directo a: http://www.transmissionzero.co.uk/software/freeglut-devel/)
  + Descargar y descomprimir ZIP: freeglut-MSVC-3.0.0-2.mp.zip
- GLEW library
  + URL: http://glew.sourceforge.net/
  + Descargar y descomprimir ZIP (Binaries Win 32 bit): glew-2.0.0-win32.zip

Crear Proyecto de VS:
  + Nueva Aplicación de Consola de C++
  + Agregar programa principal main.cpp (Seleecionando el Proyecto, botón derecho, Add New Item, C++ File(.cpp), Name: main)

Crear Código fuente:
  + Primero probar la configuración del compilador de VS con el Programa Hello World C/C++
  + Después, copiar el Programa Hello World de OpenGL anexo (main.cpp)

Configurar en el Proyecto de VS, las librerías auxiliares de OpenGL (Freeglut y GLEW):
  + Abrir ventana de Propiedades del Proyecto
    - Seleccionado el proyecto, botón derecho Properties
  + Aplicar a todas las configuraciones
    - En Configuration, seleccionar: All Configurations (No solo Debug o Realease)
  + Agregar Path de directorios de archivos cabecera (include directories) tanto para freeglut como para glew
    -  En Configuration Properties, VC++ Directories, Include Directories
  + Agregar Path de directorios de archivos de librerías (lib directories) tanto para freeglut como para glew
    - En Configuration Properties, VC++ Directories, Library Directories
  + Agregar librerías:
    - freeglut.lib
    - glew32.lib
    - En Configuration Properties, Linker, Input, Additional Dependencies

Agregar DLL's (localizados en el directorio bin de las librerías instaladas): 
   - freeglut.dll
   - glew32.dll
   - Existen varias opciones para agregarlas:
   1. Dentro del folder del programa ejecutable (Folder Debug dentro del Folder de la Solución del Proyecto)
   2. Dentro del folder Win32 del sistema
      - Típicamente en: C:\Windows\System32
   3. Agregar al PATH del sistema la ruta de los DLL's

Correr el Programa