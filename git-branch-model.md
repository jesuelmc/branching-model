# GIT BRANCH MODEL
En un principio hablar de fusionar o mergear ramas era algo innombrable en especial en proyetos que utilizaban *CVS*, pero desde la aparición de git esto se volvio significatemente facil, pero trajo consigo algunas problemas sobre la forma en la cual se usuaba en especial en proyectos relativamente grandes o que necesitaran algun soporte a futuro. Entre las preocupaciones principales estaba que una rama se borrara al momento de hacer merge o que la otra se corrompa por algunos problemas agregados junto con el merge( muchas veces en las ramas destinadas a producción) y de esto se creaba la tarea de deshacer una significante cantidad de commits para poder arreglar estos problemas.

De esta manera nacieron ciertas proposiciones sobre la manera de manejar un proyecto en ramas, y poco a poco se fue conociendo mas el termino de **branching model**.

La forma commun de manejarlo se basa en 2 ramas que se suele mantener de por vida o mientras en proyecto este solventado.

>**Master branch**: Que contenia la parte del proyecto que ya era destinada a producción

>**Develop**: Contiene toda la arte del codigo de preproduccion, conocido como el lugar de reunion de todos los features

Mientras se este desarrollando el proyecto es necesario emplear otrasramas que sirvan de soporte, estas suelen durar hasta que cumplan su proposito,aunque en algunos casos se los conserva.
>**Feature**: Se utiliza para el desarrollo de alguna caracteristica nueva para el proximo lanzamiento, esta nace o se bifurca de *Develop* y termina por fusionarse al mismo *Develop* una vez terminada.

>**Release o Staging**: Su funcion es la de apoyar la preparación para el lanzamiento a producción, dando la facilidad de correguir algunos errores y preparar el uso de datos oficiales. Este se difurca de *Develop* y termina fusionandose en el *Master*; En caso de que el proyecto tengo continuidad se fusiona tambien con *Develop* para tener de esta manera ya arreglados los problemas.

>**Hotfix**: Son ramas de revision que nacen de manera no pronosticada, su importancia cae sobre la revisión y correcion de problemas o bugs cuando se esta en producción. Este se difurca de *Master* y termina por fusionarse en *Master* y *Develop* para tener los siguientes lanzamientos con el presente problema resuelto.

---

La idea principal de esto es que el trabajo se puede realizar en paralelo al menos la mayor parte del tiempo, de esta manera se optimiza el tiempo sin la necesidad de comprometer el trabajo ya realizado.
