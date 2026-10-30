# HelmintID

Herramienta **docente** para el diagnóstico diferencial morfológico de huevos
de helmintos intestinales.

> **No es un producto sanitario.** Produce un diferencial morfológico
> orientativo sobre preparaciones de prácticas. No sustituye al informe de un
> laboratorio, y no pide ni almacena ningún dato de paciente.

## Qué hace

Se fotografía un campo microscópico y la aplicación:

1. **Comprueba si la imagen sirve.** Si está movida, quemada, vacía o el huevo
   toca el borde del campo, lo dice y no analiza. Rechazar es información, no
   un fallo.
2. **Mide** quince descriptores de forma, cubierta, color y contenido, y busca
   diez rasgos estructurales: opérculo, botón abopercular, tapones polares,
   espolón, estriación radial, filamentos polares, lado aplanado, blastómeros,
   paquete de huevos y capa mamelonada.
3. **Recorre las 44 formas de huevo** del catálogo y descarta una por una,
   guardando el motivo exacto de cada descarte.
4. Devuelve un diferencial ordenado, la ficha del taxón y un informe en PDF.

Nunca ofrece una especie cuando el huevo no permite llegar a ella: un huevo de
*Taenia* se informa como «*Taenia* spp.», porque *T. solium* y *T. saginata*
no se distinguen por el huevo. Y nunca muestra una «confianza del 99 %»: emite
un índice de concordancia con el descriptor que lo está limitando.

## Todo ocurre en el dispositivo

No hay servidor, ni cuenta, ni base de datos. El análisis entero —segmentación,
morfometría, transformadas, catálogo— corre en el navegador, dentro de un Web
Worker. **Ninguna imagen sale del dispositivo.** Una vez abierta, funciona sin
conexión; se puede instalar desde el navegador y usar en modo avión.

## Hace falta calibrar

Sin un micrómetro de platina la aplicación no puede bajar del **grupo
morfológico**, y eso no se arregla programando: un huevo de *Taenia* de 35 µm,
uno de *Ascaris* decorticado de 60, uno de *Hymenolepis diminuta* de 72 y uno
de *Paragonimus* de 100 son todos ovales, redondeados y de cubierta gruesa. Sin
la talla, sus descriptores de forma se solapan hasta ser inservibles. Calibrar
lleva diez minutos, se hace una vez por objetivo y la aplicación tiene la
pantalla preparada.

## Estado del catálogo

42 taxones y 44 formas de huevo, con las dimensiones de CDC-DPDx y de las
*Bench aids* de la OMS. **Ningún taxón está validado todavía con imágenes
reales**, y la aplicación lo dice en pantalla y en cada PDF: las bandas de
descriptores continuos se han deducido de la morfología descrita en la
bibliografía, no medidas sobre fotografías de preparaciones.

## Qué hay en este repositorio

Sólo la aplicación **ya compilada**: ficheros estáticos, sin dependencias de
servidor. El código fuente, el catálogo y las pruebas viven aparte.

Para servirla en otro sitio basta con copiar estos ficheros a cualquier
alojamiento con HTTPS. El HTTPS no es opcional: sin él el navegador no permite
instalar la aplicación ni registrar el service worker, y sin service worker no
hay funcionamiento sin conexión.

Las tipografías incluidas y su licencia, en [FUENTES.md](FUENTES.md).
