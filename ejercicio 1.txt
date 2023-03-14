class Estudiante:
    def __init__(self, nombre, apellido, id):
        self.nombre = nombre
        self.apellido = apellido
        self.id = id
    
    def nombre_completo(self):
        return f"{self.nombre} {self.apellido}"
    
    def informacion_completa(self):
        return f"Nombre completo: {self.nombre_completo()}, ID: {self.id}"

class Materia:
    def __init__(self, nombre, codigo):
        self.nombre = nombre
        self.codigo = codigo
        self.lista_estudiantes = []
    
    def agregar_estudiante(self, estudiante):
        self.lista_estudiantes.append(estudiante)

class Notas:
    def __init__(self, estudiante, materia):
        self.estudiante = estudiante
        self.materia = materia
        self.nota_laboratorio = 0
        self.nota_parcial = 0
    
    def agregar_notas(self, nota_laboratorio, nota_parcial):
        self.nota_laboratorio = nota_laboratorio
        self.nota_parcial = nota_parcial
    
    def informacion_completa(self):
        return f"Estudiante: {self.estudiante.nombre_completo()}, Materia: {self.materia.nombre}, Nota de laboratorio: {self.nota_laboratorio}, Nota de parcial: {self.nota_parcial}"