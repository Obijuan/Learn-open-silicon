# Diseño de Chips

Hemos visto cómo los chips se construyen a partir de **capas**, unas encima de otras. En cada capa hay unas **zonas**, que tienen un **tamaño** determinado. En las capa de los conductores se realizan las **interconexiones** entre todos los elementos. El **ingeniero diseñador** de los chips es la persona que define la **posición** de todas las zonas, sus **tamaños**, y las **interconexiones**, de manera que el chip tenga la funcionalidad requerida

¿Qué **tamaños mínimos** podemos usar para las zonas? ¿Cuántos niveles de interconexiones se pueden usar? ¿Qué distancias mínimas tiene que haber entre los diferentes elementos?. Todos los parámetros mínimos que necesita el diseñador para construir el chips están determinados por la **tecnología de fabricación**, que la proporciona el **fabricante**. Con unos fabricantes se pueden construir chips con transistores más grandes, mientras que con otros más pequeños (y por tanto caben más)

## PDK (Process Design Kit)

Es el fabricante el que proporciona todas las **reglas de diseño**, tamaños, archivos y modelos necesarios para que un **diseñador** pueda **fabricar** su chip. Es lo que se conoce con el nombre de [PDK](https://en.wikipedia.org/wiki/Process_design_kit) (Process Design Kit), que se puede traducir como Paquete de diseño de proceso

Puedes encontrar más información (en inglés) sobre el [concepto de PDK](https://www.zerotoasiccourse.com/terminology/pdk/) en la web del curso [Zero to Asic](https://www.zerotoasiccourse.com/) de Matthew Venn

Por tanto, para fabricar un chip, lo primero es tener acceso al **PDK del fabricante**. Y aquí es donde **surge el problema**. El fabricante considera esta información como **confidencial** y hace firmar un **acuerdo de confidencialidad** con los usuarios. Además, el PDK incluye librerías softare con licencias privativas. Por ello **no es posible compartir los diseños** ni distribuir la información...

...¡Hasta que nacieron los **PDKs libres!**


### Skywater 130nm

Las **tecnologías de fabricación** de chips reciben diferentes nombres, para diferenciarlas y poder ver cómo evolucionan. En los años 2000 exístía la [tecnología de 130nm](https://en.wikipedia.org/wiki/130_nm_process) usada por empresas como IBM, Intel, Texas Instrument...  

En el 2020 surgió la **iniciativa SkyWater 130nm**, fomentada por Google, el fabricante de chips [Skywater Techonology](https://www.skywatertechnology.com/) y el fabricante efabless (que ha sido comprado por [Chipfoundry](https://chipfoundry.io/efabless) en el 2026). Liberaron el **PDK de 130nm**, con el nombre de **sky130**. Se trata del **primer PDK Industrial Libre** de la historia. Un hito histórico

Gracias a esto, estudiantes, investigadores, ingenieros y cualquier persona interesada **tenemos acceso a la tecnología de creación de chips**, y podemos **diseñar nuestros propios chips!!** Y lo más importante, podemos **compartirlos** con la comunidad para que otros aprendan y construyan chips más avanzados a partir de este conocimiento

Toda la información del **PDK sky130** está disponible en estos enlaces:
* [Documentación](https://skywater-pdk.readthedocs.io/en/main/)
* [Repositorio en Github](https://github.com/google/skywater-pdk)

En esta figura se resumen los **parámetros** más importantes de **Sky130**, así como los diferentes **niveles** de capas y las **vías** de interconexión entre capas

![](images/103-pdk-sky130.png)  


## Diseño a Bajo nivel

¿Cómo se diseña al más bajo nivel? Es decir, ¿cómo se diseñan los chips de la forma más cercana a la realidad? La labor del diseñador es **definir los transistores**, dimensionando y posicionando sus diferentes zonas, y realizar la **interconexión** de todos ellos. Esta parte del diseño, que típicamente se hace **gráficamente** se denomina **el Layout**. Lo podríamos traducir como el **plano del trazado**

Este es un ejemplo del layout de un **mosfet N**, diseñado con **Magic**

![](images/104-layout-1.png)  

El **layout** se encuentra en uno o más archivos. El diseñador los crea utilizando **herramientas EDA** para chips. Una de las más antiguas y conocidas es [Magic VLSI](https://opencircuitdesign.com/magic/). Antiguamente este proceso se creaba mediante **dibujos físicos**. El diseñador lo dibujaba en papel

A partir del **Layout** se obtiene el **Fichero de fabricación** que típicamente está en el formato [GDS](https://en.wikipedia.org/wiki/GDSII). Este fichero contiene **toda la información necesaria** para construir **todas** las capas del chips. Es el archivo que lee la máquina de construcción de chips

Además, el Layout lo podemos **simular** para comprobar que funciona adecuadamente, antes de su fabricación, y también lo podemos **renderizar en 3D** para ver la estructura interna del chip

Este es un pantallazo del renderizado 3D del fichero GDS generado a partir del layout del MOSFET N anterior. Se ha renderizado con la herramienta **KLayout**

![](images/105-layout-GDS-3D.png)  

El Layout se diseña con diferentes herramientas. Nosotros vamos a usar 2 diferentes, para tener intuición sobre cómo es el proceso

### Layout en Siliwiz


[Siliwiz](https://app.siliwiz.com/) es un programa que corre on-line para aprender los fundamentos del diseño de chips, desarrollado por [Matt Venn](https://zerotoasiccourse.com/matt_venn/) para su curso [Zero to asic](https://zerotoasiccourse.com/)

![alt text](images/106-tutorial-siliwiz-mosfget.png)

Si tienes curiosidad por cómo se hacen los Layouts de manera genérica, sin aplicar a una tecnología específica para que sea más sencillo, puedes seguir este **tutorial**

* [Tutorial de Siliwz: Construyendo un Mosfet N desde cero](https://obijuan.github.io/Tutorial-Siliwiz/)


### Layout en Magic

🚧 DEBUG 🚧
