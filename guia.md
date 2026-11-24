# GITHUB ACTIONS
## PRIMER PASO
1. Crear un repositorio
2. Hacer el primer commit
3. Conectarlo con un repositorio de github
4. Crear una carpeta llamada `.github/actions`
5. Escribir el workflow con su automatización
```yaml
name: Hola-mundo # clave: name  | valor: Hola-mundo
on: [push] # clave: on | valor: listan con elementos [push]

jobs: # Trabajo o acción que va a realizar la automatizacion
  primer-job: # nombre del job
    runs-on: ubuntu-latest # Maquina donde corre la automatizacion
    steps: # Pasos que realiza el job
      - name: Descargar el código
        uses: actions/checkout@v4 # clonamos el repositorio del runner

      - name: Configurar python
        uses: actions/setup-python@v5 # Instala python en la máquina de GitHub
        with:
          python-version: '3.12'

      - name: Ejecutar código
        run: python ejemplo.py # Ejecuta en la terminal de la maquina de GitHub
```
6. Crear el archivo de python
```python
print("Hola mundo")
```