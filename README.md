# Fiestas y Eventos Tarragona

Aplicación web para calcular el cobro de las fiestas realizadas por la compañía **Tarragona** durante un mes y consultar el consolidado de la compañía.

Producto del **Taller # 4 – Elaboración de informe escrito del producto informático** (Ingeniería de Sistemas).

🔗 **Demo en línea:** `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`

## ¿Qué hace?

Por cada fiesta se ingresan la **cédula del contratante**, la **cantidad de invitados** y las **horas de duración**. La aplicación:

- Valida los datos (cédula numérica, invitados ≥ 1, horas ≥ 1, enteros).
- Calcula el monto a cancelar.
- Muestra el detalle de cada fiesta (cédula, invitados, horas y monto).
- Muestra el consolidado de la compañía: total de invitados, total de horas, cantidad de fiestas por rango de horas (1–3, 4–6 y más de 6) y, como indicador complementario, el total facturado.
- Permite reiniciar el mes.

## Reglas de negocio

```
Monto = (invitados × tarifa por invitado) + cuota por duración
```

| Invitados | Valor por invitado (COP) |
|---|---|
| 1 a 100 | 8.000 |
| 101 a 500 | 6.000 |
| Más de 500 | 4.000 |

| Duración | Cuota adicional (COP) |
|---|---|
| 1 a 3 horas | 100.000 |
| 4 a 6 horas | 200.000 |
| Más de 6 horas | 300.000 |

La tarifa por invitado se aplica a **todos** los invitados (no es escalonada).

## Casos de prueba (valores límite)

| Invitados / Horas | Monto esperado (COP) |
|---|---|
| 50 / 2 | 500.000 |
| 100 / 3 | 900.000 |
| 101 / 4 | 806.000 |
| 500 / 6 | 3.200.000 |
| 501 / 7 | 2.304.000 |

Si registras los casos 1, 3 y 5, el consolidado debe dar: 652 invitados, 13 horas, una fiesta en cada rango y $3.610.000 facturados.

## Tecnologías

HTML5, CSS3 y JavaScript puro. Sin dependencias, sin servidor y sin base de datos. Arquitectura en tres capas:

| Capa | Implementación |
|---|---|
| Presentación | Formulario, tabla de detalle y panel de consolidado |
| Lógica de negocio | `tarifaInvitados()`, `cuotaHoras()`, `calcularMonto()`, `registrarFiesta()` |
| Datos | Arreglo de objetos en memoria, respaldado en `localStorage` |

## Almacenamiento de datos

No hay base de datos. Las fiestas se guardan en el **`localStorage` de cada navegador**, por lo que:

- Los datos sobreviven al recargar o cerrar la página.
- Cada navegador y cada dispositivo tiene sus propios datos; no se comparten entre usuarios.
- Borrar los datos del sitio en el navegador elimina las fiestas registradas.

## Cómo ejecutarla

**Localmente:** descarga el repositorio y abre `index.html` en el navegador.

**Publicarla con GitHub Pages:**

1. Sube `index.html` y `README.md` a un repositorio de GitHub.
2. Ve a **Settings → Pages**.
3. En *Build and deployment*, elige **Deploy from a branch**, selecciona la rama `main` y la carpeta `/ (root)`.
4. Guarda y espera uno o dos minutos. El enlace aparecerá en esa misma pantalla.

## Limitaciones

- Los datos son locales a cada navegador.
- Solo maneja un mes; no conserva historial.
- Las tarifas están definidas en el código.
- Solo admite horas enteras y no registra la fecha de cada fiesta.
- No tiene control de acceso.

## Estructura del repositorio

```
├── index.html   # Aplicación completa (HTML + CSS + JS)
└── README.md    # Este archivo
```

## Autor

Tu nombre – Ingeniería de Sistemas – 2026
