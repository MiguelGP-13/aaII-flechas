# aaII-flechas
Estimación de ángulo de flechas en el pavimento

### Pasos:

Utilizar una red YOLO-OBB no nos sirve porque no obtendríamos la orientación, sino el rectángulo rotado que mejor encaja con el objeto.

La propuesta para obtener la orientación de las flechas consiste en diseñar una CNN ad-hoc que entrenaremos con las imágenes de las flechas extraidas por YOLO y la rotación proporcionada en los labels.

Para ello se eliminarán todas las imágenes que no tienen flechas, y de las que sí tienen se recortará cada flecha (puede haber varias y se reescalará a unas dimensiones fijas (por determinar), añadiendo el ángulo reportado en los labels.

Con ese dataset se entrenará una red tipo VGG para obtener dada una imagen de una flecha el ángulo que forma.
