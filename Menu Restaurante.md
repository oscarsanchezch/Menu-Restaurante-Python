# Oscar Orlando Acosta Sanchez
# 213022_869
# Ingeniería de Telecomunicaciones
# Código Fuente: autoría propia

# Problema 2 - Gestión de precios de un menú de restaurante

# Matriz del menú:
# [Nombre del Producto, Categoría, Precio Base]

menu = [
    ["Hamburguesa", "Comida Rápida", 25000],
    ["Pizza", "Comida Rápida", 32000],
    ["Ensalada César", "Saludable", 18000],
    ["Salmón", "Mariscos", 45000],
    ["Pasta Alfredo", "Italiana", 28000],
    ["Jugo Natural", "Bebidas", 12000]
]

# Función para calcular el precio final
def calcular_precio_final(categoria, precio_base, categoria_objetivo, umbral):
    
    # Validar si cumple las condiciones para el descuento
    if categoria == categoria_objetivo and precio_base > umbral:
        descuento = precio_base * 0.15
        precio_final = precio_base - descuento
    else:
        precio_final = precio_base

    return precio_final


# Datos de la promoción
categoria_objetivo = "Comida Rápida"
umbral_precio = 20000

# Mostrar resultados
print("===== MENÚ DEL RESTAURANTE =====\n")

for producto in menu:
    nombre = producto[0]
    categoria = producto[1]
    precio_base = producto[2]

    precio_final = calcular_precio_final(
        categoria,
        precio_base,
        categoria_objetivo,
        umbral_precio
    )

    print(f"Producto: {nombre}")
    print(f"Categoría: {categoria}")
    print(f"Precio Base: ${precio_base:,.0f}")
    print(f"Precio Final: ${precio_final:,.0f}")
    print("-" * 40)


# Evita que la ventana se cierre
input("Presione ENTER para finalizar...")