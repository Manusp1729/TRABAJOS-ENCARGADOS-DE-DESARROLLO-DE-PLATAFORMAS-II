// Calcula la comision que cobra el banco segun el monto de remesa
fun calcularComision(montoRemesa: Double): Double {
    return if (montoRemesa <= 1000.0) 5.0
    else if (montoRemesa <= 10001.0) 0.005 * montoRemesa
    else 0.015 * montoRemesa
}

// Dado el monto total T, calcula el monto de remesa, ITF y comision
fun calcularRemesa(montoTotal: Double) {
    val itf = montoTotal * 0.00005

    // T = mr + C(mr) + ITF, entonces T - ITF = mr + C(mr)
    // Despejamos mr para cada tramo. 
    val mr1 = montoTotal - itf - 5.0
    val mr2 = (montoTotal - itf) / 1.005
    val mr3 = (montoTotal - itf) / 1.015

    var montoRemesa: Double
    var tramo: Int

    if (mr1 >= 0 && mr1 <= 1000.0) {
        montoRemesa = mr1; tramo = 1
    } else if (mr2 > 1000.0 && mr2 <= 10001.0) {
        montoRemesa = mr2; tramo = 2
    } else {
        montoRemesa = mr3; tramo = 3
    }

    val comision = calcularComision(montoRemesa)

    println("\n   RESULTADOS    ")
    println("Monto Total (T):      %.2f".format(montoTotal))
    println("ITF (0.005%% de T):    %.2f".format(itf))
    println("Monto Remesa (mr):    %.2f".format(montoRemesa))
    println("Comision (tramo $tramo):   %.2f".format(comision))
    println("Verificacion:         %.2f".format(montoRemesa + comision + itf))
}

fun main() {
    var opcion: Int

    do {
        println("\n\t   CALCULO DE MONTO DE REMESA     ")
        println("1. Caso Tramo 1 (mr = 800)")
        println("2. Caso Tramo 2 (mr = 5000)")
        println("3. Caso Tramo 3 (mr = 20000)")
        println("4. Ingresar monto manualmente")
        println("5. Salir")
        print("Opcion: ")

        opcion = readLine()!!.toInt()

        when (opcion) {
            1 -> calcularRemesa(805.04)
            2 -> calcularRemesa(5025.25)
            3 -> calcularRemesa(20301.02)
            4 ->
                {
                print("Digita el monto total (T): ")
                val miMonto = readLine()!!.toDouble()
                calcularRemesa(miMonto)
            }
            5 -> println("Saliendo...")
            else -> println("Opcion no valida. Intenta de nuevo.")
        }
    } while (opcion != 5)
}
