class Juego:
    def __init__(self, jugador1, jugador2):
        self.jugador1 = jugador1
        self.jugador2 = jugador2

    def comenzar(self):
        print("¡Comienza el juego!")
        print(f"{self.jugador1.nombre} vs {self.jugador2.nombre}")
        jugador_actual = random.choice([self.jugador1, self.jugador2])
        while True:
            print(f"Es el turno de {jugador_actual.nombre}.")
            if jugador_actual == self.jugador1:
                jugador_atacado = self.jugador2
            else:
                jugador_atacado = self.jugador1
            print(f"{jugador_actual.nombre} lanza un golpe a {jugador_atacado.nombre}.")
            jugador_atacado.luchador.perder_vida(30)
            print(f"{jugador_atacado.nombre} ahora tiene {jugador_atacado.luchador.vida}% de vida restante.")
            if jugador_atacado.luchador.vida <= 0:
                print(f"{jugador_atacado.nombre} ha perdido.")
                print(f"{jugador_actual.nombre} es el ganador.")
                break
            jugador_actual = jugador_atacado

class Jugador:
    def __init__(self, nombre, luchador):
        self.nombre = nombre
        self.luchador = luchador

class Luchador(Jugador):
    def __init__(self, nombre, poder):
        super().__init__(nombre, self)
        self.poder = poder
        self.vida = 100

    def perder_vida(self, cantidad):
        self.vida -= cantidad



