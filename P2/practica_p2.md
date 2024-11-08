# Práctica 2 Servizos Multimedia

## Autores: 
Óscar Olveira Miniño

Eloy Calvo Gens


### **Cuestión 1.1:** ¿Al hacer esta transformación de color, se produce alguna pérdida de información? ¿O por el contrario se genera nueva información al pasar de 1 a 3 imágenes?

Ao facer a transformación de RGB a YCbCr non se perde nin se xenera nova información, soamente hai un cambio de modelo de cor.

### **Cuestion 2.1:** Si usamos el modo de subsampling 4:4:4,¿Estaremos perdiendo algo de información? ¿Qué porcentaje de la imagen original?

Ao usar o subsampling 4:4:4, non estaremos efectuando ningún downsampling polo que non perdemos ningunha información e teremos o 100% da imaxen orixinal.


### **Cuestion 2.2:** Si usamos el modo de subsampling 4:2:0,¿Estaremos perdiendo algo de información? ¿Qué porcentaje de la imagen original?

En este caso, estamos perdendo  información xa que estamos reducindo a resolución vertical e horizontal.
O porcentaxe de pérdida é do 50% xa que do total (4+4+4=12), con este subsampling temos 6 (4+2+0), polo que, queda  ½ da información orixinal.


### **Cuestion 3.1:** ¿Qué puedes decir acerca de las dos imágenes obtenidas tras el submuestreo? ¿A qué es debido?

A imaxen do submostreo cas crominancias (CrCb) non presenta ningún tipo de cambio mentras que no submostreo da luminancia (Y) mostrase con menos calidade. Esto débese a que o ollo humano é mais sensible a un cambio na luminancia que nas crominancias.


### **Cuestion 5.1:** ¿Observas alguna diferencia entre los valores del bloque original y los valores recuperados mediante la IDCT? ¿Qué significa eso con respecto a la DCT?

Non hai ningunha diferencia entre eles. Esto significa que si desfacemos a DCT sin cuantificar, vamos recuperar sempre a imaxen orixinal sin pérdida.


### **Cuestion 6.1:** Anota los valores de salida. A la vista de ellos, ¿Con qué nivel de cuantización se consiguen un mayor número de valores en la matriz 𝐾? ¿A qué es debido?

Cuanto menor ha sido el factor de escala, más valores no nulos.
La matriz con la imagen original se divide por la de cuantificación, como esta última crece conforme crece el factor de escala obtenemos una matriz resultante de la división con valores cada vez más pequeños.

### **Cuestion 6.2:** ¿Por qué se vuelven nulos algunos valores de las matrices cuantizadas pero no otros?

Los valores nulos salen de esa división anteriormente mencionada. Estos valores nulos fueron los que se "eligieron" para ser descartados ahorrando espacio.
