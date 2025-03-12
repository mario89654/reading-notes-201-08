# Verdad o Mito: Prototipos en JavaScript

Este documento analiza afirmaciones sobre la herencia y los prototipos en JavaScript, determinando si son **Verdad** o **Mito** con sus respectivas justificaciones.

## 1. "El `prototype` de una función y el `__proto__` de un objeto son exactamente lo mismo."
**Mito**

 **Justificación:**
- `prototype` es una propiedad de las funciones constructoras que define los métodos y propiedades que heredarán las instancias creadas con `new`.
- `__proto__` es una propiedad de los objetos que apunta al prototipo del cual heredan.
- Aunque `obj.__proto__ === Constructor.prototype` es usualmente `true`, esto no significa que sean idénticos.

 **Referencia:** [MDN - Prototype Chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Inheritance_and_the_prototype_chain)

---

## 2. "La cadena de prototipos permite la reutilización de métodos y propiedades, lo cual es esencial para la herencia en JavaScript."
 **Verdad**

 **Justificación:**
- La cadena de prototipos permite que los objetos hereden métodos y propiedades de otros objetos.
- Cuando una propiedad no está presente en un objeto, la búsqueda sube por la cadena de prototipos.

 **Referencia:** [MDN - Working with Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects)

---

## 3. "Las funciones constructoras son obsoletas y no se usan en el desarrollo moderno de JavaScript."
**Mito**

 **Justificación:**
- Aunque las clases (`class`) introducidas en ES6 proporcionan una sintaxis más clara, las funciones constructoras siguen siendo válidas.
- JavaScript internamente sigue usando prototipos, incluso con la sintaxis de clases.
- En algunos casos, las funciones constructoras pueden ser útiles, especialmente en entornos sin transpilers.

 **Referencia:** [MDN - Inheritance and the Prototype Chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Inheritance_and_the_prototype_chain)

---

## 4. "Manipular correctamente `__proto__` puede mejorar la reutilización de código, pero su uso inadecuado puede generar problemas de seguridad y mantenimiento."
**Verdad**

 **Justificación:**
- `__proto__` permite modificar la cadena de prototipos en tiempo de ejecución, pero se recomienda evitarlo en producción.
- Puede afectar el rendimiento y generar vulnerabilidades si se modifica sin control.
- Se recomienda `Object.create()` en su lugar para una mejor gestión de la herencia.

 **Referencia:** [MDN - Working with Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects)

---

## 5. "Modificar el `prototype` de una función siempre afecta a todas las instancias existentes sin excepción."
**Mito**

 **Justificación:**
- Modificar `prototype` de una función afecta a futuras instancias, pero **no a las ya creadas** si estas ya tienen su propia copia de la propiedad o método.

 **Referencia:** [MDN - Prototype Chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Inheritance_and_the_prototype_chain)

---

###  Conclusión
 La comprensión adecuada del modelo de prototipos permite escribir código más eficiente y seguro. 
