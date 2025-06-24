def datos_primera_linea(linea):
    nombre = linea[0:20]
    codigo_identificacion = linea[20:30]
    codigo_orden_de_pago = linea[30:40]
    monto_nominal = linea[40:50]
    calculo_comision = linea[50:52]
    calculo_impositivo = linea[52:54]



    return nombre, codigo_identificacion , codigo_orden_de_pago, monto_nominal, calculo_comision, calculo_impositivo


def identificador_de_moneda(codigo_orden_de_pago):
    moneda = None
    contador_de_monedas = 0

    if "ARS" in codigo_orden_de_pago:
        moneda = "ARS"
        contador_de_monedas += 1

    if "USD" in codigo_orden_de_pago:
        moneda = "USD"
        contador_de_monedas += 1

    if "EUR" in codigo_orden_de_pago:
        moneda = "EUR"
        contador_de_monedas += 1

    if "GBP" in codigo_orden_de_pago:
        moneda = "GBP"
        contador_de_monedas += 1

    if "JPY" in codigo_orden_de_pago:
        moneda = "JPY"
        contador_de_monedas += 1

    if contador_de_monedas == 1:
        return moneda
    else:
        moneda = "Moneda no valida"
        return moneda



def principal():
    archivo = open("ordenes25.txt")
    linea = archivo.readlines()
    archivo.close()
    
    datos_primera_linea(linea)
 
    #lectura y procesamiento del archivo
    linea_1 = True
    
    for linea in archivo:
        if linea_1 is True:
            datos_primera_linea(linea)
            linea_1 = False
            continue

        if identificador_de_moneda(codigo_orden_de_pago) == "Moneda no valida":
            contador_de_monedas_no_autorizadas += 1

    archivo.close()

    def r1():
        if moneda =



principal()






