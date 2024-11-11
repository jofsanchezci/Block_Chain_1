
# Implementación Básica de Blockchain en Python

Esta es una implementación simple de Blockchain en Python. La cadena de bloques es un mecanismo de registro distribuido que asegura que los datos almacenados en la cadena no puedan ser alterados sin invalidar el sistema. Este código demuestra los principios básicos de cómo funciona una blockchain: la creación de bloques, el cálculo de hashes y la validación de la integridad de la cadena.

## Componentes del Código

### 1. **Clase `Block`**:
Cada bloque en la cadena tiene los siguientes atributos:
- **index**: El índice del bloque en la cadena (comienza desde 0 para el bloque génesis).
- **previous_hash**: El hash del bloque anterior, utilizado para encadenar los bloques de manera segura.
- **timestamp**: La fecha y hora en la que se creó el bloque.
- **data**: Los datos que el bloque contiene (en este caso, las transacciones o información asociada).
- **hash**: El hash calculado del bloque, utilizando la función SHA-256 para garantizar que no se altere.

### 2. **Clase `Blockchain`**:
La clase `Blockchain` gestiona la cadena de bloques y sus operaciones. Tiene los siguientes métodos:
- **`create_genesis_block()`**: Crea el primer bloque (bloque génesis) de la cadena.
- **`calculate_hash()`**: Calcula el hash de un bloque usando SHA-256.
- **`add_block(data)`**: Añade un nuevo bloque a la cadena con los datos proporcionados.
- **`is_chain_valid()`**: Verifica la integridad de la cadena de bloques. Si cualquier bloque se ha alterado, la cadena no será válida.

### 3. **Flujo Principal del Código**:
- Se crea un objeto de la clase `Blockchain`.
- Se añaden bloques con datos de ejemplo ("Transaction 1", "Transaction 2", etc.).
- Se valida si la cadena es válida usando el método `is_chain_valid()`.

### 4. **Salida Esperada**:
El programa imprimirá cada bloque en la cadena, mostrando su índice, hash anterior, hash actual, fecha y datos, y al final verificará si la cadena es válida.

## Ejemplo de uso:

```python
# Crear una nueva blockchain
blockchain = Blockchain()

# Añadir bloques a la cadena
blockchain.add_block("Transaction 1")
blockchain.add_block("Transaction 2")
blockchain.add_block("Transaction 3")

# Imprimir los bloques de la cadena
for block in blockchain.chain:
    print(block)

# Verificar si la cadena es válida
print("
Is blockchain valid?", blockchain.is_chain_valid())
```

## Requisitos:
- Python 3.x
- La librería `hashlib` está incluida en la biblioteca estándar de Python.

## Expansión:
Esta implementación es solo un ejemplo básico. Para hacerlo más robusto, se pueden añadir características como:
- **Pruebas de trabajo** (minado de bloques).
- **Redes distribuidas** para validar bloques en varios nodos.
- **Contratos inteligentes** que ejecuten transacciones automáticas.

