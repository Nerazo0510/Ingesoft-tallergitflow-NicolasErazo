# Documento de Pruebas

## 1. Descripcion del Sistema
La plataforma de gestión de eventos universitarios permite registrar estudiantes, validar su código institucional y gestionar la inscripción a eventos. El sistema tiene restricciones como edad válida del estudiante, formato del código estudiantil y disponibilidad de cupos en eventos. 

## 2. Requerimientos a Evaluar
RF-01 Registro de Estudiante
El sistema permite registrar estudiantes que su edad esté entre 16 y 65 años.

## 3. Tecnicas de Prueba Aplicadas
RF-01 = Análisis de Valor Límite
Justificación
El requerimiento es de un rango numérico específico (16–65).
El análisis de valor límite permite probar los valores de por debajo, en el límite y por encima del rango permitido para verificar como se comporta el sistema.

## 4. Casos de Prueba Diseñados
| Caso | Edad | Resultado esperado |
|----|------------|----------|
| Caso 01 | 15 | Rechazado |
| Caso 02 | 16 | Aceptado |

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
