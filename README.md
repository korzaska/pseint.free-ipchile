# pseint.free-ipchileAlgoritmo EvaluacionVentas
	// 1. leer losdatos de ventas mensuales
	
	Definir ventas, totalVentas, promedioVentas, umbralVentas Como Real;
	Definir numMeses, mesesSobreUmbral, mesMaxVenta, i Como Entero;
	Definir nombreMes Como Cadena;
	
	Dimension ventas[100];
	
	Escribir "Ingrese el número de meses a evaluar:";
	Leer numMeses;
	
	Para i <- 1 Hasta numMeses Hacer
		Escribir "Ingrese las ventas del mes ", i, ":";
		Leer ventas[i];
	FinPara
	
	totalVentas <- 0;
	Para i <- 1 Hasta numMeses Hacer
		totalVentas <- totalVentas + ventas[i];
	FinPara
	
	promedioVentas <- totalVentas / numMeses;
	
	
	Escribir "Ingrese el umbral de ventas:";
	Leer umbralVentas;
	
	mesesSobreUmbral <- 0;
	Para i <- 1 Hasta numMeses Hacer
		Si ventas[i] > umbralVentas Entonces
			mesesSobreUmbral <- mesesSobreUmbral + 1;
		FinSi
	FinPara 
	
	mesMaxVenta <- ventas[1];
	nombreMes <- "Enero"; 
	mesMaxVentaIndice <- 1;
	
	Para i <- 2 Hasta numMeses Hacer
		Si ventas[i] > mesMaxVenta Entonces
			mesMaxVenta <- ventas[i];
			mesMaxVentaIndice <- i;
		FinSi
	FinPara
	
	
	Segun mesMaxVentaIndice Hacer
		1: nombreMes <- "Enero"
		2: nombreMes <- "Febrero"
		3: nombreMes <- "Marzo"
		4: nombreMes <- "Abril"
		5: nombreMes <- "Mayo"
		6: nombreMes <- "Junio"
		7: nombreMes <- "Julio"
		8: nombreMes <- "Agosto"
		9: nombreMes <- "Septiembre"
		10: nombreMes <- "Octubre"
		11: nombreMes <- "Noviembre"
		12: nombreMes <- "Diciembre"
		De Otro Modo:
			nombreMes <- "Mes " + ConvertirATexto(mesMaxVentaIndice);
	FinSegun
	
	Escribir "Total de ventas: ", totalVentas;
	Escribir "Promedio mensual de ventas: ", promedioVentas;
	Escribir "Número de meses con ventas superiores al umbral: ", mesesSobreUmbral;
	Escribir "El mes con la venta más alta fue ", nombreMes, " con: ", mesMaxVenta;
	
FinAlgoritmo
