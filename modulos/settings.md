# ⚙ Configuración del Sistema - Settings

Panel de configuración avanzada para **CotareloManage**

---

## 🎛 Configuración General

El módulo de configuración permite personalizar todos los aspectos del sistema educativo según las necesidades específicas de cada institución.

---

## 🏫 Información del Centro

| Campo     | Valor Actual                                                | Tipo     | Requerido |
| --------- | ----------------------------------------------------------- | -------- | --------- |
| Nombre    | IES Armando Cotarelo                                        | Texto    | ✅        |
| Código    | 28001234                                                    | Numérico | ✅        |
| Dirección | C/ Educación, 123                                           | Texto    | ✅        |
| Teléfono  | +34 91 123 4567                                             | Tel      | ✅        |
| Email     | [info@iestecmadrid.edu.es](mailto:info@iestecmadrid.edu.es) | Email    | ✅        |
| Web       | [www.iestecmadrid.edu.es](http://www.iestecmadrid.edu.es/)  | URL      | ❌        |

---

## 🎓 Configuración Académica

### Sistema de Calificaciones

El sistema utiliza múltiples escalas de evaluación:

**Escala Numérica (Por defecto):**

- 📊 0-10 con decimales
- 🎯 Mínimo aprobado: **5.0**
- ⭐ Excelente: **9.0+**

**Escala Alfabética (Opcional):**

- 🅰 A (Sobresaliente): 9-10
- 🅱 B (Notable): 7-8.9
- 🅲 C (Bien): 6-6.9
- 🅳 D (Suficiente): 5-5.9
- 🅵 F (Insuficiente): 0-4.9

---

### Cálculo de Promedios

La nota final se calcula usando la fórmula:

```plaintext
         n
NF =  Σ (Ei × Pi) / Σ Pi
        i=1
```

````

Donde:

- **NF** = Nota Final
- **Ei** = Evaluación
- **Pi** = Peso de la evaluación
- **n** = Número de evaluaciones

Para asignaturas con evaluación continua:

```plaintext
NC = 0.4 × P1 + 0.4 × P2 + 0.2 × PF
```

Siendo:

- **P1, P2** = parciales
- **PF** = prueba final

---

⚙ **Importante:** Reinicia el sistema después de cambios críticos en la configuración.

¿Necesitas ayuda con la configuración?
Consulta nuestro [centro de soporte](https://support.cotarelomanage.es/) o contacta al administrador del sistema.

---

✨ Configuración flexible para cada institución educativa 🎛

```

```
````
