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

Valores da saída:

Valores no nulos en la DCT original: 64
Valores no nulos en la DCT cuantificada escala 1: 14
Valores no nulos en la DCT cuantificada escala 0.25: 33
Valores no nulos en la DCT cuantificada escala 4: 7

Según os resultados que nos deron, canto maior sea o factor de escalado, máis nulos ten a matriz.
A matriz ca imaxen orixinal dividese pola matriz de cuantificacióncuantificación, como esta última crece conforme maior sea o número do factor de cuantificación, obtemos una matriz resultante con valores cada vez máis pequenos (máis cercanos a cero).

### **Cuestion 6.2:** ¿Por qué se vuelven nulos algunos valores de las matrices cuantizadas pero no otros?

Os valores nulos son o resultado da división mencionada anteriormente. Estes valores nulos foron escollidos para ser eliminados, xa que ao descartalos afórrase espazo.

### **Cuestión 7.1:** ¿Los valores recuperados diferentes de cero, tienen el mismo valor que en la DCT original? ¿Por qué?

Na maioría dos casos si. Hai algúns píxeles que amosan un valor diferente debido ao redondeo, pero, como a división ten a propiedade conmutativa, na maioría dos casos pódense recuperar os valores orixinais.

### **Cuestión 8.1:** A la vista de las dos imágenes, ¿Ves alguna similitudes entre ambas? ¿A qué es debido?

Tal e como se ve, o fondo da imaxen apenas ten valores parte xa que é a parte máis homoxénea mentras que na zona onde esta o paxaro hai valores, podendo destinguir ben a silueta (xa que é a parte da imaxen onde hai cambios de intensidade)


### **Cuestión 9.1:** Comparando esta imágen con la del pájaro, ¿Qué diferencias observas en cuanto al número de coeficientes de la DCT no nulos? ¿Qué nos dice eso con respecto a la naturaleza (predominio de frecuencias altas o bajas) de cada imagen?

Na imaxe do paxaro, parece que hai unha maior cantidade de valores nulos. Algo similar ocorre en áreas da imaxe do libro, como por exemplo no marxe, onde tamén se observan valores nulos. Isto suxire que a imaxe do libro ten unha frecuencia xeral máis baixa, o que leva a descartar menos coeficientes ao procesala.

Na área do plumaxe do peito do paxaro ou nas ás, onde se deberían mostrar frecuencias altas, atopamos moitos valores nulos. Pola contra, na zona do texto, onde se esperaría unha menor frecuencia debido ao seu menor detalle visual, hai poucos valores nulos. Isto parece contraditorio respecto ao que se esperaría pola natureza das frecuencias nesas áreas.

### **Cuestión 10.1:** ¿Se parecen las versiones cuantizadas entre sí? ¿Cual es la diferencia entre ellas? ¿A qué es debido?

As imáxenes parecense, pero hai certos cambios cando cambiamos de factor de cuntificación. 
Os bloques teñen valores que se dividen pola matriz de cuantización multiplicada polo factor de escala. Cando o factor de escala aumenta, a matriz de cuantización tamén aumenta, facendo que os valores divididos sexan máis pequenos. Se o resultado da división é moi pequeno, convértese en nulo. Por iso, a medida que o factor de escala crece, xéranse máis valores nulos no bloque entón diferencianse entre elas por este motivo.


### **Cuestion 12.1:** Viendo la imagen en la que solo queda el coeficiente de DC tras la cuantificación, ¿Qué es lo que observas? ¿A qué es debido?

Este componente representa o valor medio de intensidade dun bloque de píxeles. Se eliminamos todos os valores e deixamos ese píxel específico, a imaxe resultante parecería ter un só píxel grande que contén o cor medio de todos os píxeles eliminados.

### **Cuestion 12.2:** Observando las otras dos gráficas, ¿por qué se parece más al original la imagen con solo 3 coeficientes que la que usa 61? ¿Qué es lo que se estaría viendo realmente en esta última con respecto a las diferentes frecuencias que componen la imagen?

FALTA EXPLICAR
FALTA EXPLICAR
FALTA EXPLICAR

É normal que na imaxen donde temos o compoñente importate e uns pixeles máis se pareza mais

### **Cuestión 13.1:** ¿Cual es la versión con mayor calidad?¿A qué se debe?

Según esta táboa (sacada dos archivo Jupyter):

20< pSNR(dB)     → mala calidad.
20≤	pSNR(dB) <30 → calidad aceptable.
30≤	pSNR(dB) <40 → calidad buena.
	pSNR(dB) ≥40 → calidad muy buena.

Resultado do exercicio:

pSNR(Y), escalado 1:    	 33.37 dB
pSNR(Y), escalado 0.25: 	 40.77 dB
pSNR(Y), escalado 4:    	 29.24 dB

Si comparamos a táboa de arriba cos resultados, vemos con escalado 0.25 obtemos a mellor calidad mentras que con escalado 4 obtemos a peor calidade. Esto débese a que con factor de cuantificacion 0.25, comprimimos a imaxen con menos diferencias que a imaxen orixinal polo que MSE tamén é menor.

### **Cuestion 14.1:** ¿Qué version consigue el menor tamaño? ¿A qué se debe esto?

Con escala 4 obtemos un tamaño meno xa que ten poucos no nulos, polo que ao comprimir, comprimense mais nulos que no resto de escalados



