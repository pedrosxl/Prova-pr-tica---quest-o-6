Prova Prática Questão 6

class Animal:
    def __init__(self, nome, idade, peso=1.0):
        self.nome = nome
        self.idade = idade
        self.peso = peso

    def get_nome(self):
        return self.nome

    def get_idade(self):
        return self.idade

    def get_peso(self):
        return self.peso

    def set_nome(self, nome):
        if nome != "":
            self.nome = nome
        else:
            print("Nome inválido.")

    def set_idade(self, idade):
        if idade >= 0:
            self.idade = idade
        else:
            print("Idade inválida.")

    def set_peso(self, peso):
        if peso > 0:
            self.peso = peso
        else:
            print("Peso inválido.")

    def comer(self):
        print(self.nome, "está comendo.")

    def dormir(self):
        print(self.nome, "está dormindo.")


class Cachorro(Animal):
    def __init__(self, nome, idade, peso=1.0, raca="Vira-lata", porte="Médio", vacinado=False, nivel_energia=100):
        super().__init__(nome, idade, peso)
        self.raca = raca
        self.porte = porte
        self.vacinado = vacinado
        self.nivel_energia = nivel_energia

    def get_raca(self):
        return self.raca

    def get_porte(self):
        return self.porte

    def get_vacinado(self):
        return self.vacinado

    def get_nivel_energia(self):
        return self.nivel_energia

    def set_raca(self, raca):
        if raca != "":
            self.raca = raca
        else:
            print("Raça inválida.")

    def set_porte(self, porte):
        if porte != "":
            self.porte = porte
        else:
            print("Porte inválido.")

    def set_vacinado(self, vacinado):
        self.vacinado = vacinado

    def set_nivel_energia(self, nivel_energia):
        if 0 <= nivel_energia <= 100:
            self.nivel_energia = nivel_energia
        else:
            print("Nível de energia inválido.")


class Gato(Animal):
    def __init__(self, nome, idade, peso=1.0, cor="Cinza", castrado=False, vidas=7, gosta_de_brincar=True):
        super().__init__(nome, idade, peso)
        self.cor = cor
        self.castrado = castrado
        self.vidas = vidas
        self.gosta_de_brincar = gosta_de_brincar

    def get_cor(self):
        return self.cor

    def get_castrado(self):
        return self.castrado

    def get_vidas(self):
        return self.vidas

    def get_gosta_de_brincar(self):
        return self.gosta_de_brincar

    def set_cor(self, cor):
        if cor != "":
            self.cor = cor
        else:
            print("Cor inválida.")

    def set_castrado(self, castrado):
        self.castrado = castrado

    def set_vidas(self, vidas):
        if 0 <= vidas <= 7:
            self.vidas = vidas
        else:
            print("Quantidade de vidas inválida.")

    def set_gosta_de_brincar(self, gosta_de_brincar):
        self.gosta_de_brincar = gosta_de_brincar

from classes_animais import Animal, Cachorro, Gato


def main():
    print("TESTANDO SUPERCLASSE")

    animal1 = Animal("Bidu", 3, 12.5)

    print(animal1.get_nome())
    print(animal1.get_idade())
    print(animal1.get_peso())

    animal1.set_nome("Rex")
    animal1.set_idade(4)
    animal1.set_peso(15.0)

    animal1.comer()
    animal1.dormir()

    print("\nTESTANDO CACHORROS")

    cachorro1 = Cachorro("Thor", 2, 20.0, "Labrador")
    cachorro2 = Cachorro("Max", 1, 10.0)
    cachorro3 = Cachorro("Bob", 5)

    cachorros = [cachorro1, cachorro2, cachorro3]

    for cachorro in cachorros:
        print(cachorro.get_nome())
        cachorro.comer()
        cachorro.dormir()
        print(cachorro.get_raca())
        print(cachorro.get_porte())
        print(cachorro.get_vacinado())
        print(cachorro.get_nivel_energia())

        cachorro.set_raca("Golden Retriever")
        cachorro.set_porte("Grande")
        cachorro.set_vacinado(True)
        cachorro.set_nivel_energia(90)

    print("\nTESTANDO GATOS")

    gato1 = Gato("Mimi", 3, 4.5, "Branco")
    gato2 = Gato("Luna", 2, 3.8)
    gato3 = Gato("Nina", 1)

    gatos = [gato1, gato2, gato3]

    for gato in gatos:
        print(gato.get_nome())
        gato.comer()
        gato.dormir()
        print(gato.get_cor())
        print(gato.get_castrado())
        print(gato.get_vidas())
        print(gato.get_gosta_de_brincar())

        gato.set_cor("Preto")
        gato.set_castrado(True)
        gato.set_vidas(6)
        gato.set_gosta_de_brincar(False)


main()

        
