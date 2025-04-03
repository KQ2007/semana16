# semana16
# Abrir el archivo en modo escritura ('w') y crearlo si no existe
def escribir_notas():
    try:
        # Abrir archivo
        archivo = open('my_notes.txt', 'w')
        
        # Escribir notas en el archivo
        notas = [
            "Nota 1: Recordar hacer ejercicio diariamente.\n",
            "Nota 2: Estudiar para el examen de Python.\n",
            "Nota 3: Comprar ingredientes para la cena.\n"
        ]
        
        for nota in notas:
            archivo.write(nota)  # Usar write() para escribir cada nota
        
        print("Notas escritas correctamente.")
        
    except Exception as e:
        print(f"Error al escribir notas: {e}")
    
    finally:
        # Cerrar el archivo después de escribir
        if 'archivo' in locals():
            archivo.close()

# Leer el contenido del archivo línea por línea
def leer_notas():
    try:
        # Abrir archivo en modo lectura ('r')
        archivo = open('my_notes.txt', 'r')
        
        # Leer línea por línea usando readline()
        linea = archivo.readline()
        while linea:
            print(linea.strip())  # strip() para eliminar el salto de línea al final
            linea = archivo.readline()
        
    except FileNotFoundError:
        print("El archivo no existe.")
    except Exception as e:
        print(f"Error al leer notas: {e}")
    
    finally:
        # Cerrar el archivo después de leer
        if 'archivo' in locals():
            archivo.close()

# Llamar a las funciones para escribir y leer notas
if __name__ == "__main__":
    escribir_notas()
    leer_notas()
