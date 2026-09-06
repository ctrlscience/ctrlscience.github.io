---
title: "Algoritmos bioinspirados: 3,800 millones de años de evolución comprimidos en un ciclo for"
date: 2026-09-06
categories: [Ciencia, Computación]
tags: [algoritmos bioinspirados, biología, inteligencia artificial, divulgación]
image:
  path: /assets/img/posts/banner.jpg
toc: true
comments: true
math: false
mermaid: false
---

> Los algoritmos bioinspirados son, básicamente, optimizar soluciones que ya existen, pero mejoradas, usando como inspiración a la naturaleza.
{: .prompt-tip }

He estado aprendiendo últimamente un punto de convergencia que no conocía entre la informática y la biología: **los algoritmos bioinspirados**.

![Hormigas siguiendo un rastro de feromona](/assets/img/posts/ants.jpg)
_Sin GPS, sin jefa, sin junta de Zoom — y aun así encuentran la ruta más corta._

Imagínate una hormiga. Una nomás, saliendo del hormiguero sin GPS, sin Google Maps, sin ni siquiera una idea clara de a dónde chingados va. Esa hormiga no sabe nada del universo, no sabe que existen las estrellas, no sabe ni que existe ella misma como concepto. Y aun así, en cuestión de minutos, ella y sus miles de hermanas van a encontrar la ruta más corta entre el hormiguero y la migaja de pan que se le cayó a alguien en el parque. Sin jefe. Sin plan. Sin junta de Zoom para decidir la estrategia.

Esa capacidad de un montón de cosas simples, sin inteligencia individual de sobra, para resolver problemas complicadísimos nomás por seguir unas reglas sencillas y repetirlas un chingo de veces, es, en el fondo, todo lo que necesitas entender para saber qué es un algoritmo bioinspirado. Lo demás son detalles.

---

## Un poco de historia

La idea es más vieja que las computadoras mismas. Ya en la década de 1940, incluso antes de que existieran máquinas capaces de ejecutarlas, había ideas de usar los principios darwinianos para automatizar la resolución de problemas. Fue Alan Turing quien, en 1948, acuñó la frase *"búsqueda genética o evolutiva"* — la primera vez que alguien conectó explícitamente evolución biológica con cómputo. En los años 50, Alex Fraser publicó una serie de artículos sobre simulación de selección artificial, y en 1962 Bremermann llevó a cabo los primeros experimentos computacionales de "optimización por evolución y recombinación".

En la década de los 60 pasó algo bien curioso: **tres grupos distintos inventaron la misma vaina al mismo tiempo**, en tres esquinas del mundo y sin conocerse:

1. 🇺🇸 En **Michigan**, John Holland parió los algoritmos genéticos.
2. 🇺🇸 En **San Diego**, Lawrence Fogel investigó la programación evolutiva mutando máquinas de estados finitos.
3. 🇩🇪 En **Berlín**, dos estudiantes de ingeniería, Rechenberg y Schwefel, crearon las estrategias evolutivas para optimizar toberas de aviones a chorro en un túnel de viento.

Durante quince años cada quien jaló por su lado, hasta que en los 90 la academia se dio cuenta de que todos hablaban el mismo idioma con diferente acento, y lo bautizaron como **computación evolutiva**.

---

## Ok pero, ¿cómo funcionan?

Empecemos definiendo un algoritmo: es una serie de pasos, solo eso, algo así como una receta de cocina. Y **optimizar**, para que no te espantes con la palabra, quiere decir nada más esto: de todas las soluciones posibles a un problema, encontrar la mejor (o una lo suficientemente buena) sin tener que probarlas todas una por una, porque probarlas todas nos llevaría más tiempo del que le queda al universo antes de apagarse.

Piénsalo así. Si yo te digo "encuéntrame el camino más corto entre tu casa y la tienda de la esquina, entre 200 rutas posibles", tú agarras y las revisas todas, tardas cinco minutos y ya. Pero si te digo "encuéntrame la ruta más corta que visite las 200 tiendas de toda tu colonia sin repetir ninguna", ahí ya no alcanza ni la paciencia ni la voluntad.

> El número de combinaciones posibles crece tan rápido que ni todas las computadoras del planeta juntas, corriendo desde el Big Bang, terminarían de revisarlas.
{: .prompt-warning }

A esos problemas la ciencia de la computación les puso un nombre elegante y aterrador: **problemas NP-duros** (NP significa *Polinomio No Determinista*, *Non-deterministic Polynomial*). Y aquí viene lo incómodo: la mayoría de los problemas del mundo real —acomodar rutas de reparto, diseñar una red eléctrica, encontrarle la forma a un parásito escondido en una gota de sangre— son, sin excepción, de este tipo de problemas donde no existe un método perfecto ni garantizado para resolverlos rápido.

### Entonces, si no hay método perfecto, ¿qué hacemos?

Aquí es donde entra la parte hermosa del asunto: en vez de buscar la solución perfecta (que probablemente no existe o tardaríamos siglos en encontrar), buscamos una solución suficientemente buena, en un tiempo razonable, usando ensayo y error inteligente. A ese tipo de estrategias se les llama **metaheurísticas**, y no, no hay garantía de que encuentren la mejor respuesta posible. Ni siquiera sabemos del todo por qué funcionan cuando funcionan. Lo que sí sabemos es que casi siempre funcionan lo suficientemente bien, y eso, en un mundo de problemas imposibles, ya es un chingo.

<!--
Ruta sugerida: /assets/img/posts/abejas.jpg
-->
![La naturaleza como maestra de optimización](/assets/img/posts/abejas.jpg)
_3,800 millones de años de experiencia en optimización, sin cobrar regalías._

Y aquí es donde la naturaleza, que lleva probando cosas desde hace 3,800 millones de años sin parar ni un segundo a cobrar regalías, se vuelve la maestra más barata y más sabia que existe. Porque resulta que la evolución, las colonias de hormigas, los enjambres de abejas, las bandadas de pájaros e incluso las bacterias más humildes del planeta ya llevan resolviendo, sin saberlo, el mismo problema al que se enfrenta cualquier algoritmo de optimización: cómo buscar lo suficiente para no quedarte estancado, pero sin perder tanto tiempo buscando que nunca aproveches lo que ya encontraste.

---

## El corazón de todo: buscar cosas nuevas vs. aprovechar lo que ya tienes

Todo algoritmo bioinspirado —sin excepción— vive atrapado en la misma tensión existencial que cualquier persona indecisa un viernes por la noche: ¿me quedo en el antro que ya conozco porque ahí la está pasando bien, o me arriesgo a ir al que no conozco porque a lo mejor está mejor?

A eso, en la jerga de la optimización, se le llama **exploración y explotación**:

| | Qué es | El riesgo si abusas |
|---|---|---|
| 🧭 **Exploración** (diversificación) | El algoritmo se avienta a lo desconocido, prueba soluciones distintas, se pasea por rincones del problema que todavía no ha visto | Nunca se compromete con nada; salta de solución en solución sin refinar jamás |
| 🔍 **Explotación** (intensificación) | El algoritmo deja de andar de vago explorando y se pone a exprimir a fondo la mejor zona que ya encontró | Se enamora de la primera solución decente y se queda ahí, sin saber que hay algo mejor tres cuadras más allá |

> Quedarse atrapado en un **óptimo local** es creer que ya llegaste a la cima, cuando en realidad nomás subiste la colina más chiquita y hay una montaña enorme que ni siquiera volteaste a ver.
{: .prompt-info }

El chiste —el verdadero, el único secreto detrás de todos estos algoritmos con nombres de animalitos— es encontrar el balance correcto entre andar de exploradores y ponerse a explotar lo bueno. Ese balance es, literalmente, la diferencia entre un algoritmo que funciona y uno que es una pérdida de tiempo computacional.

### ¿Y por qué copiarle a la naturaleza y no inventar algo desde cero?

Porque la naturaleza ya hizo el trabajo sucio por nosotros, gratis, durante miles de millones de años. Una bandada de pájaros vuela en formación sin que ningún pájaro sea el líder supremo: cada uno nomás ajusta su posición viendo a sus vecinos más cercanos, y de esa ley simple emerge algo tan elegante como una bandada completa moviéndose como si fuera un solo organismo.

![Bandada de estorninos en murmuración](/assets/img/posts/bandada-aves.jpg)
Crédito: fotografía tomada por Walter Baxter. Licencia Creative Commons Attribution-Share Alike 2.0 Gereric.
Los algoritmos bioinspirados permiten modelar comportamientos gregarios complejos para tareas de optimización (Márquez Vera, 2023).
Ruta sugerida: /assets/img/posts/aves.jpg
_De reglas individuales estúpidamente simples, emerge algo colectivamente inteligente._

Ese es el truco: de reglas individuales estúpidamente simples emergen soluciones colectivas sorprendentemente inteligentes. Ni la hormiga ni el pájaro entienden el problema completo. Nadie ahí arriba tiene el plan maestro. Y aun así, entre todos, lo resuelven mejor que si un solo cerebro superpoderoso lo intentara resolver solo.

No hace falta una inteligencia superior, ni un diseño perfecto, ni un plan cósmico bajado de las estrellas. Solo un montón de piezas simples, siguiendo reglas simples, con la paciencia infinita del tiempo evolutivo de su lado. Somos polvo de estrellas organizado en patrones que aprendieron, a punta de ensayo y error, a no repetir el mismo error dos veces. Y ahora agarramos ese mismo truco y lo metemos en una computadora para que nos ayude a acomodar rutas de camiones, diseñar antenas, entrenar redes neuronales o —como hago yo todos los días— encontrarle la forma exacta a un parásito microscópico escondido en una gota de sangre.

> No es magia. Es billones de años de prueba y error, comprimidos en un ciclo `for`.
{: .prompt-tip }

---

## Tipos de algoritmos bioinspirados

En toda la literatura hay más de **540 algoritmos metaheurísticos** conocidos, y aunque cada autor le pone su propio nombre a lo que hace, la mayoría de los revisores coincide en que se pueden agrupar en un puñado de categorías según su fuente de inspiración.

### 1. Algoritmos evolutivos (evolution-based)

Se inspiran en la teoría de la evolución de Darwin: selección natural, herencia y variación genética. El más popular es el **algoritmo genético (GA)** de Holland (1975), que introdujo las operaciones de selección, cruza y mutación para guiar el proceso de optimización. Dentro de esta familia también están la evolución diferencial (Storn y Price, 1995), el backtracking search algorithm (Pinar, 2013) y algoritmos más recientes como Jaya (Rao, 2016).

### 2. Algoritmos de enjambre (swarm-based)

Se inspiran en el comportamiento social colectivo de animales que actúan en grupo sin un líder central. Aquí entra la **optimización por enjambre de partículas (PSO)** de Kennedy y Eberhart (1995), inspirada en bandadas de aves o cardúmenes de peces. También pertenecen a esta familia el Grey Wolf Optimizer (Mirjalili, 2014) y el Whale Optimization Algorithm (Mirjalili, 2016).

### 3. Algoritmos basados en fenómenos físicos (physics-based)

Se inspiran en leyes o procesos de la física: gravedad, electromagnetismo, termodinámica, óptica. No están construidos sobre comportamiento biológico, sino sobre principios físicos formalizados matemáticamente.

### 4. Algoritmos basados en comportamiento humano (human-based)

Imitan procesos, hábitos o dinámicas sociales humanas. Por ejemplo, el **Deep Sleep Optimizer**, que imita patrones humanos de sueño para encontrar soluciones óptimas, o el Dragon Boat Optimization, inspirado en la coordinación colectiva de un equipo de remo.

---

## Dónde jala esto en la vida real

Si quitamos el folclor, la herramienta funciona, y funciona muy cabrón:

- **Imágenes médicas** — donde el ruido, las sombras y la variabilidad biológica vuelven locos a los métodos tradicionales, las metaheurísticas bioinspiradas limpian, segmentan y extraen características donde el ojo humano ya se cansó de buscar.
- **Machine Learning y Deep Learning** — optimizando hiperparámetros para afinar diagnósticos de cáncer, cardiopatías o diabetes.
- **Ingeniería y logística** — resolviendo broncas de red eléctrica, turbulencias, diseño de estructuras o trazando rutas de transporte para no tirar diésel a lo pendejo.
- **Bioinformática** — estimando parámetros en redes bioquímicas y modelando sistemas vivos.

---

## El dilema: el zoológico de vanidades y el "boom" del paper fácil

Pero no todo es miel sobre hojuelas. A partir del año 2000, el campo entró en una fase de crecimiento descontrolado y francamente ridículo. Hoy existen más de 540 metaheurísticas registradas y catálogos que parecen el libro de monstruos de Harry Potter, con más de 200 variantes solo en la rama bioinspirada.

<!--
📸 ESPACIO PARA IMAGEN
Sugerencia: collage tipo "bestiario" — lobo, ballena, luciérnaga, murciélago, gota de agua, ilustrado o en formato meme académico
Ruta sugerida: /assets/img/posts/bestiario-algoritmos.jpg
-->

Y aquí hay que meter el dedo en la llaga: estamos en el auge del *publish or perish*, donde la raza publica porque se puede, no porque aporte.

Llegó un punto en que cualquier documental de Animal Planet servía de pretexto para aventarse un paper: algoritmos inspirados en el cortejo de las luciérnagas, el ataque del tiburón, murciélagos, gotas de agua inteligentes y hasta músicos improvisando jazz. En 2021, la bomba explotó cuando investigadores como Thomas Stützle y el mismísimo Marco Dorigo firmaron una carta abierta titulada sin pelos en la lengua: **"El elefante en el cuarto"**.

> Llevamos dos décadas tragándonos refritos. Un análisis taxonómico demostró que, de 145 algoritmos supuestamente "novedosos", el 51% tenían una superposición estructural tan idéntica con métodos viejos que matemáticamente eran la misma gata, pero revolcada.
{: .prompt-danger }

Le cambian los nombres a las variables de la ecuación: en vez de "velocidad" le ponen "salto del lobo", y en vez de "azar" le llaman "vuelo del pájaro". Vocabulario decorativo para inflar el currículum con publicaciones rápidas. Metáforas inútiles.

---

## La convergencia obligada: devolverle la vida a la bioinspiración

Es aquí donde la cosa se pone interesante, pero también donde camina sobre una cuerda floja bien peligrosa.
Esta es mi pedrada personal, hablando desde mi trinchera: soy microbióloga y ahora ando metida hasta el cuello en una maestría en ciencias de la computación. Si te asomas a ver quiénes están proponiendo y adaptando estos algoritmos, casi siempre son ingenieros en sistemas, matemáticos o físicos. Gente brillante para tirar líneas de código, despejar ecuaciones y plantear matrices pesadísimas, pero que muchas veces entienden la biología como una anécdota de primaria. Se quedan con la cáscara del fenómeno, sin entender la complejidad ecológica, fisiológica y evolutiva que sostiene a ese organismo en el mundo real.

Y del otro lado de la banqueta, la culpa está igual de repartida: en las ciencias biológicas abunda un desinterés pasmoso y hasta cierta soberbia frente a la informática. Mucha gente de bata ve a las computadoras como simples cajas negras o de plano le saca la vuelta al código. Se quejan de que los ingenieros deforman los conceptos biológicos, pero tampoco hacen el esfuerzo por sentarse a entender una matriz o aprender a programar para señalar las correcciones.

Y ahí es donde está el verdadero tiro, el punto de convergencia que nadie quiere tocar a fondo: la computación no puede seguir jugando a solas a inventarse metáforas estériles en el pizarrón. Porque la naturaleza no optimiza en un vacío matemático donde todo es limpio y perfecto. Un organismo compite bajo escasez brutal, estrés metabólico, con un ruido ambiental que te cagas y metido en sistemas interconectados donde nada sobra, nada falta y nada es gratis. La supervivencia no es un capricho estético; es una economía celular despiadada. Traducir esa lógica a un modelo matemático requiere a alguien que de verdad hable el idioma de la célula, de la membrana, del tejido, del parásito y de las presiones de selección que no vienen en los libros de cálculo.

Sí, la literatura ya demostró hasta el cansancio que estamos atascados en una redundancia cínica: el mismo algoritmo de siempre disfrazado con cincuenta nombres de animales distintos nomás para inflar artículos. Pero el estancamiento no significa que la idea esté agotada; usando lo que acabamos de aprender, significa que llegamos a un óptimo local. Para salir de ahí, la computación debe dejar de calcar la superficie de los animales y modelar los sistemas biológicos reales —con todo su ruido, restricciones y complejidad—, mientras que la biología debe perderle el miedo al código y meter las manos a la programación. El verdadero avance no vendrá de inventar nombres de bichos para inflar el currículum, sino de cruzar la biología viva con matemáticas serias dentro de un ciclo for.

## Para seguir leyendo (fuentes)

- **Yang, X.-S.** — Sobre metaheurísticas, problemas NP-duros y el par exploración/explotación como componentes centrales de todo algoritmo metaheurístico (Blum y Roli, 2003).
- **Kennedy, J. & Eberhart, R. (1995)**. *Particle Swarm Optimization* — El enjambre de partículas inspirado en bandadas de aves.
- **Slowik, A. & Kwasnicka, H. et al.** — *Intelligent Computing: The Latest Advances, Challenges and Future*, sobre Turing (1948) y los tres orígenes de la computación evolutiva. [arXiv:2211.11281](https://arxiv.org/pdf/2211.11281).
- **Eiben, A. E.** — *Evolutionary Computing* (notas de curso sobre historia paralela de EP, GA y ES). [arXiv:cs/0511004](https://arxiv.org/pdf/cs/0511004).
- **Collet, P.** — *A Quick Presentation of Evolutionary Computation* (Fogel's "Fossil Record", orígenes desde 1953). IGI Global. [Enlace](https://www.igi-global.com/chapter/quick-presentation-evolutionary-computation/44380).
- **Beyer, H.-G. & Schwefel, H.-P.** — *Evolution Strategies: A Comprehensive Introduction* (historia detallada de las ES en Berlín). [PDF](https://saksagan.ceng.metu.edu.tr/courses/ceng713/documents/Evolution%20strategies%20a%20comprehensive%20introduction.pdf).
- **Bäck, T., Hammel, U. & Schwefel, H.-P. (1997)**. *Evolutionary Computation: Comments on the History and Current State*. IEEE Transactions on Evolutionary Computation. [PDF](https://sci2s.ugr.es/sites/default/files/files/Teaching/OtherPostGraduateCourses/Metaheuristicas/01%20-%20EC-History-IEEETEC-1-1-1997.pdf).
- **Kirkpatrick, S., Gelatt, C. D. & Vecchi, M. P. (1983)**. *Optimization by Simulated Annealing*. Science.
- **Dorigo, M. (1992)**. *Optimization, Learning and Natural Algorithms* (tesis doctoral). Politecnico di Milano.
- **Yang, W., Liu, H. & Zhang, Y. (2023)**. *A Novel Human-Based Meta-Heuristic Algorithm: Dragon Boat Optimization* (dato de +540 algoritmos conocidos). [arXiv:2311.15539](https://arxiv.org/pdf/2311.15539).
- **Aranha, C. et al. incl. Dorigo, M. & Stützle, T. (2021)**. *Metaphor-based metaheuristics, a call for action: the elephant in the room*. Swarm Intelligence. [Springer](https://link.springer.com/10.1007/s11721-021-00202-9).
- **Taxonomía metaphor-free de 145 metaheurísticas (2025)**. Springer. [Artículo](https://link.springer.com/article/10.1007/s10462-025-11456-8).
- *Bio-Inspired Algorithms Used in Medical Image Processing* (2024). IGI Global. [Capítulo](https://irma-international.org/chapter/bio-inspired-algorithms-used-in-medical-image-processing/338083/).
- *Bio-inspired algorithms in machine learning and deep learning for disease detection* (2025). CRC Press. [Publicación](https://research.ajman.ac.ae/en/publications/bio-inspired-algorithms-in-machine-learning-and-deep-learning-for/).
- *O que são algoritmos bioinspirados?* — Panorama de aplicaciones en redes, seguridad, robótica, ingeniería biomédica y sistemas de energía. [eCycle](https://www.ecycle.com.br/algoritmos-bioinspirados/amp/).
- **Márquez Vera, M. A. (2023)**. *Inteligencia de enjambre: de los sistemas naturales a los artificiales*. Revista Digital Universitaria, 24(1). [DOI](https://doi.org/10.22201/cuaieed.16076079e.2023.24.1.11).

---



🧬 + 💻 = ⚡

<em>ctrl+Science — donde la ciencia se explica sin anestesia</em>

</div>
