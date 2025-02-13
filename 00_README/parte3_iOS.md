# APLICACIONES iOS - SERGIO PADRINO - `UIKIT`

# CLASE 9 (1) - (12/02/25)

# ÍNDICE
## 0. Aclaración - `Auto Layout` para `UIKit` | `View Modifiers` para `SwiftUI`
## 1. Auto Layout
### 1.1. Constraints
#### 1.2. Usar `Interface Builder`
#### 1.3. `Content Hugging Priority`
#### 1.4. Ejemplos prácticos en XCode

## 0. Aclaración - `Auto Layout` para `UIKit` | `View Modifiers` para `SwiftUI`
El `Auto Layout` con `Constraints` pertenece a `UIKit` y `no` a `SwiftUI`.

+ `UIKit` → `Usa Auto Layout` con `Constraints`
• Se configura en `Storyboard` o con código usando `NSLayoutConstraint`.
• Permite definir reglas para `posicionar elementos de forma adaptable`.
• Es obligatorio en `UIKit` para que la interfaz se ajuste a distintos tamaños de pantalla.

+ `SwiftUI` → `NO usa Auto Layout`, usa `View Modifiers`
• No necesita constraints, usa `VStack, HStack, ZStack y modificadores (.frame(), .padding())` y tambien  `GeometryReader` (* más al final) cuando se necesita un control `más preciso` sobre el diseño.
• Es `declarativo`: defines la estructura y el sistema ajusta las posiciones automáticamente.
• Mucho `más fácil` de manejar que `Auto Layout`.

😸 `GeometryReader` es un contenedor especial que te da acceso al tamaño y la posición de la vista padre. Es útil cuando necesitas diseños responsivos o basados en dimensiones dinámicas.

🎯 ¿Cuándo NO usar `GeometryReader`?
🔵 Si solo necesitas alinear elementos, usa HStack, VStack o .frame() en su lugar.
🔵 Puede afectar el rendimiento si lo usas en muchas vistas anidadas.

💨 Alternativas a GeometryReader en SwiftUI
Si GeometryReader te parece complicado, puedes usar:
• `.frame(maxWidth: .infinity, maxHeight: .infinity)` → Para ocupar todo el espacio disponible.
• `.layoutPriority(1)` → Para que una vista crezca antes que otras.
• `.alignmentGuide(.leading) { d in d[.trailing] }` → Para alineaciones personalizadas.

## 1. Auto Layout
- Basado en definir `restricciones` (constraints) entre elementos de nuestra UI y que todo funcione `automágicamente`

### 1.1. Constraints
- Son las `restricciones` que aplicamos a los elementos de nuestra UI.
- Equivalen a indecuaciones con la siguiente estructura:

`element1.attribute [=|<|>] multiplier * element2.attribute + constant`

Desentructurado:
- `element1` y `element2`: elementos de nuestra UI (botones, labels...). Pueden ser el mismo.
- `attribute`: son atributos geométricos de los elementos (`top, bottom, left, right, width, height`)
- `multiplier`: multiplicador para el atributo del segundo elemento.
- `constant`: constante que siempre será sumada al resultado final.
- `[=|<|>]`: significa que podemos "pedir" a `AutoLayout` que `element1.attribute` sea igual, menor que o mayor que el resultado de la parte derecha.

#### 1.2. Usar `Interface Builder`
Dos maneras de añadir `constraints` a nuestra UI con `Interface Builder`:
- Arrastrando con el botón derecho del ratón de un elemento a otro.
Se mostrará un menú con los distintos tipos de constraints que podemos crear.
- Seleccionando un elemento y usando el botón "Add New Constraints" Se mostrará un menú con las distintas constraints que podemos crear.

#### 1.3. `Content Hugging Priority`
A `1` Si se comprima (seguramente), que ocupe lo maximo posible
A `1000` No se comprima (seguramente), que ocupe lo minimo posible

#### 1.4. Ejemplos prácticos en XCode
1. (MIN 0:45:3O - 1:07:00) `AutoLayoutBasico`. Poner en dimensiones las etiquetas tanto horizontal como verticalmente en el móvil respetando el orden y truncando las más grandes.

2. (MIN 1:13:30 - 1:21:30) `AutoLayoutBasicoCodigo`.

3. (MIN 1:28:50 - 1:42:50) `AutoLayoutAnimaciones`.

4. (MIN 1:52:15 - 2:08:50) `AutoLayoutCustomViews`.

5. (MIN 2:15:45 - 2:25:00) `AutoLayoutCustomViews`.

# CLASE 10 (2) - (13/02/25)

