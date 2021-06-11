## krozzzdb

**Documentación:** [PROXIMAMENTE](https://dsc.gg/lunarserv) <br>
**Soporte:** [dsc.gg/lunarstudios](/https://dsc.gg/lunarstudios) <br>
**NPM:** [npmjs.com/krozzzdb](https://www.npmjs.com/package/krozzzdb)

KrozzzDB es una database de codigo abierto, en base de QuickDB. Todos los datos se guardan via [sqlite](https://github.com/JoshuaWise/better-sqlite3).
> **Almacenamiento** - El almacenamiento nunca se perderá, a caso que borres el archivo de `krozzz.sqlite`.

> **Funciona de inmediato**: No es necesario configurar un servidor de base de datos como en Mongoose, todos los datos se almacenan localmente en el mismo proyecto.

> **Funcionalidad**: Esta ddatabase esta hecha para que no te lies con las cosas, es bien simple!

> **Origen**: Originariamente se creó para el bot `Lunar`, pero luego se decidió hacerla publica.

## Ejemplos

```js
const krozzz = require('krozzzdb');

const db = krozzz('./krozzz.sqlite');

// Establecer un objeto
db.set('userInfo', { dificultad: 'Facil' })
// Se guardaría como - { dificultad: 'Facil' }

// Empujar un elemento a una matriz (que aún no existe) en un objeto:
db.push('userInfo.items', 'Espada')
// Se guarda como - { dificultad: 'Facil', items: ['Espada'] }

// Añadir un numero (que aún no existe) en un objeto:
db.add('userInfo.balance', 500)
// Se guarda como - { dificultad: 'Facil', items: ['Espada'], balance: 500 }

// Repitiendo los ejemplos anteriores:
db.push('userInfo.items', 'Reloj')
// Se guarda como - { dificultad: 'Facil', items: ['Espada', 'Reloj'], balance: 500 }
db.add('userInfo.balance', 500)
// Se guarda como -> { dificultad: 'Facil', items: ['Espada', 'Reloj'], balance: 1000 }

// Obteniendo propiedades individuales
db.get('userInfo.balance') // -> 1000
db.get('userInfo.items') // ['Espada', 'Reloj']
```

## Instalación

**Linux & Windows**
- `npm i krozzzdb`

***Note:** Es posible que los usuarios de Windows deban realizar pasos adicionales [listed here](https://github.com/JoshuaWise/better-sqlite3/blob/master/docs/troubleshooting.md).*

**Mac**
1. **Instalar:** XCode
2. Debes poner `npm i -g node-gyp` en la terminal
3. Luego `node-gyp --python /path/to/python2.7` (si ya tienes Python 3.x, ignora este paso)
4. Y por ultimo ponemos `npm i krozzzdb`

## Apoyanos
Trabajo en estos proyectos en mi tiempo libre, si quieres apoyarme, puedes hacerlo a través de [Patreon!](https://www.patreon.com/lunarthebot)
