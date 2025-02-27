# Reversi Move Validator en VHDL

## Descripción
Este proyecto implementa un módulo en VHDL capaz de analizar un tablero de Reversi y determinar las posiciones en las que se pueden colocar fichas negras. Para lograrlo, se diseña una red iterativa en la que cada celda recibe información de su celda anterior en una determinada dirección, así como el contenido de una posición del tablero, para identificar si una jugada es válida y transmitir la información a la siguiente celda.

El objetivo es construir una macro-celda capaz de operar en las 8 direcciones posibles del juego. Finalmente, esta macro-celda se integrará en un circuito combinacional que procesará todo el tablero en paralelo.

## Características
- Implementación en **VHDL**.
- Diseño basado en una **red iterativa**.
- Cada celda analiza una dirección y transmite información a la siguiente.
- Construcción de una **macro-celda** que opera en 8 direcciones simultáneamente.
- Procesamiento paralelo de todo el tablero.

## Archivos del Proyecto
- `celda_base.vhd`: Implementación de la celda básica.
- `macro_celda.vhd`: Implementación de la macro-celda.
- `matriz_celdas.vhd`: Módulo combinacional que procesa todo el tablero.
- `test_microcelda.vhd`: Banco de pruebas para verificar el correcto funcionamiento de la celda básica.
- `sim_matrix.vhd`: Banco de pruebas para verificar el correcto funcionamiento del diseño.

## Requisitos
Para simular y sintetizar el diseño se necesita:
### Linux:
- **GHDL** para simulación.
- **GTKWave** para visualizar las señales.
### Windows:
- **Modelsim** para simular y visualizar.

## Instalación y Uso
1. Clona el repositorio:
   ```sh
   git clone https://github.com/DonJulve/VHDL-REVERSI.git
   cd VHDL-REVERSI
   ```
2. Ejecuta la simulación con GHDL:
   ```sh
   ghdl -a *.vhd
   ghdl -e sim_matrix
   ghdl -r sim_matrix --vcd=output.vcd
   ```
3. Visualiza la salida con GTKWave:
   ```sh
   gtkwave output.vcd
   ```
