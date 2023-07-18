# CalculadoraSalarioMensalEmPython

# Este código surgiu de um exercício em que deveria ser criado uma calculadora de salário mensal de funcionários, tendo como base os atributos de nome e e-mail para a classe funcionários, além de calcular a quantia paga em salário de acordo com dias e horas trabalhadas pelos funcionários de uma determinada empresa.


class Funcionario:

def __init__(self,nome,email):
self.nome= nome
self.email= email
self.horas= {}
self.salario_hora= {}

def cadastro_hora(self,mes,horas):
if (mes not in self.horas):
self.horas[mes] = horas

def cadastro_salario_hora(self,mes,valor):
if (mes not in self.salario_hora):
self.salario_hora[mes]= valor

def calcula_salario (self,mes):
if (mes not in self.horas) or (mes not in self.salario_hora):
print (‘Mês Inexistente!!’)
else:
return self.horas[mes] *self.salario_hora[mes]

def __repr__(self):
return f’Funcionário:{self.nome},\nEmail:{self.email},\nhoras/mês:{self.horas},\nsalário-hora:{self.salario_hora}’

# Para finalizar o preenchimento dos dados dos funcionários, será necessário criar um outro arquivo Python, para importar os dados e realizar o preenchimento dos valores para obter o cálculo do salário mensal dos trabalhadores de uma determinada empresa.

from funcionarios import Funcionario

funcionario= Funcionario(‘Matheus’,‘matheus@blablabla.com.br’)

funcionario.cadastro_hora(‘Jan’,300)
funcionario.cadastro_hora(‘Fev’,200)
funcionario.cadastro_salario_hora(‘Jan’,30)
funcionario.cadastro_salario_hora(‘Fev’,30)
print(funcionario)
print(funcionario.calcula_salario(‘Jan’))
print(funcionario.calcula_salario(‘Fev’))
