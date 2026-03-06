# Documento de Pruebas

## 1. Descripcion del Sistema
La plataforma de gestión de eventos universitarios permite registrar estudiantes, validar su código institucional y gestionar la inscripción a eventos. El sistema tiene restricciones como edad válida del estudiante, formato del código estudiantil y disponibilidad de cupos en eventos. 

## 2. Requerimientos a Evaluar
RF-01 Registro de Estudiante
El sistema permite registrar estudiantes que su edad esté entre 16 y 65 años.

RF-02 Código de Estudiante
El código del estudiante debe cumplir con ciertos requisitos:
Tener exactamente 8 caracteres
Iniciar con la letra E
Los 7 restantes deben ser números.

RF-03 Inscripción a Evento
Un estudiante puede inscribirse si:
Está registrado
El evento tiene cupos disponibles
No está inscrito previamente

## 3. Tecnicas de Prueba Aplicadas
RF-01 = Análisis de Valor Límite
Justificación
El requerimiento es de un rango numérico específico (16–65).
El análisis de valor límite permite probar los valores de por debajo, en el límite y por encima del rango permitido para verificar como se comporta el sistema.

RF-02 = Particion de equivalencia
Justificación
El código del estudiante tiene reglas de formato.
La partición de equivalencia permite dividir los requisitos en grupos válidos e inválidos para reducir el número de pruebas.

RF-03 = Tabla de Decisión

Justificación

La inscripción depende de varias condiciones.
Las tablas de decisión permiten evaluar todas las combinaciones posibles de condiciones y el resultado esperado.

## 4. Casos de Prueba Diseñados
| Caso | Codigo | Tipo | 
|----|------------|----------|
| Caso 01 | 15 | Rechazado |
| Caso 02 | 16 | Aceptado |

| Caso | Codigo | Tipo | Resultado esperado |
|----|------------|----------|----------|
| Caso 01 | E1234567 | Válido | Aceptado |
| Caso 02 | E123456 | Longitud menor | Rechazado |
| Caso 03 | E12345678 | Longitud mayor | Rechazado |
| Caso 04 | A1234567 | No inicia con E | Rechazado |


Condiciones:
C1: Estudiante registrado
C2: Evento con cupos
C3: Ya inscrito
| Caso | Registrado | Cupos dispo | Ya inscrito | Resultado |
|----|------------|----------|----------| ----------|
| Caso 01 | si | si | no | Aceptado |
| Caso 02 | no | si | no | Rechazado |
| Caso 03 | si | no | no | Rechazado |
| Caso 04 | si | si | si | Rechazado |
| Caso 05 | no | no | no | Rechazado |

## 5. Trazabilidad

| Requerimiento | Tecnica |  
|----|------------|
| RF-01 | Valor Límite |
| RF-02 | Partición de Equivalencia |
| RF-03 | Tabla de Decisión |

## 6. Gestion de Versiones (GitFlow)

Para el desarrollo del documento se utilizó el modelo GitFlow.
Se creó inicialmente la rama develop a partir de main.
Posteriormente se trabajó en una rama feature específica:
feature/rf01
feature/rf02
feature/rf03
Cada rama desarrolló su sección correspondiente del documento y posteriormente se realizaron Pull Requests hacia develop.
Finalmente, cuando el documento estuvo completo y revisado, se realizó un Pull Request de develop hacia main.
