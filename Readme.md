# Hello World Action by Hitomiblood

![GitHub Action](https://img.shields.io/badge/GitHub-Action-blue.svg)
![Node.js](https://img.shields.io/badge/Node.js-20-green.svg)

Una acción simple de GitHub que imprime "Hello, World!" y proporciona la hora actual como salida.

## Descripción

Esta acción de GitHub te permite saludar a alguien o algo, e imprime el payload del evento que activó el flujo de trabajo. También proporciona la hora actual como una salida que se puede utilizar en pasos posteriores del flujo de trabajo.

## Inputs

### `who-to-greet`

**Requerido**: No  
**Valor predeterminado**: `'World'`  
**Descripción**: Define a quién o qué saludar. Por ejemplo, si el valor es 'Pedro', la acción imprimirá 'Hello Pedro!'.

## Outputs

### `time`

**Descripción**: La hora en la que se ejecutó la acción.

## Ejemplo de uso

### Uso básico

```yaml
steps:
  - name: Hello World 
    uses: username/hello-world-action@v1.0
    
  # Este paso usará el valor predeterminado 'World'
  # La salida será: Hello World!
```

### Personalización del saludo

```yaml
steps:
  - name: Hello GitHub
    uses: username/hello-world-action@v1
    with:
      who-to-greet: 'GitHub'
    
  # La salida será: Hello GitHub!
```

### Usar la salida en pasos posteriores

```yaml
steps:
  - name: Hello World Step
    id: hello
    uses: username/hello-world-action@v1
    
  - name: Obtener la hora
    run: echo "La acción se completó a las ${{ steps.hello.outputs.time }}"
```

## Desarrollo

Esta acción está construida con [JavaScript GitHub Actions](https://docs.github.com/es/actions/creating-actions/creating-a-javascript-action) y utiliza Node.js 20.

### Dependencias principales

- [@actions/core](https://github.com/actions/toolkit/tree/main/packages/core): Módulo principal para interactuar con las variables y comandos de GitHub Actions
- [@actions/github](https://github.com/actions/toolkit/tree/main/packages/github): Módulo para interactuar con la API de GitHub y acceder al contexto del evento

## Licencia

Este proyecto está licenciado bajo la licencia ISC - ver el archivo [LICENSE](LICENSE) para más detalles.

## Autor

Hitomiblood
