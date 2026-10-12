# CALCULOAREA - Calculadora de Área de Círculo

## Descripción
Programa modular en C++ que calcula el área de un círculo utilizando el enfoque Top-Down y diseño modular con funciones.

## Materia
Laboratorio de Programación (LPR) - EEST N° 1 "Eduardo Ader" - Vicente López
5° Año - Grupos A-B

## Estructura del Proyecto
```
calculoarea/
├── .gitignore
├── LICENSE
├── README.md
├── docs/
│   └── InformeProyectoCALCULOAREA.pdf
├── src/
│   └── main.cpp
└── capturas/
    ├── compilacion_area.png
    └── diagrama_flujo.png
```

## Compilación y Ejecución

### En Windows (PowerShell):
```powershell
g++ src/main.cpp -o src/area.exe
.\src\area.exe
```

### En Linux/macOS:
```bash
g++ src/main.cpp -o src/area
./src/area
```

## Enfoque Top-Down
El programa sigue un diseño modular donde:
1. Se define un prototipo de función antes del `main()`
2. El `main()` llama a la función `calcularAreaCirculo()`
3. La función realiza el cálculo y retorna el resultado

## Profesor
Prof. Mansilla Muñoz York Elías
