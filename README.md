# IntroducaoaMachine - professor Caio

obs: olha esse site Kaggle

IntroducaoaMachine23abril2023

https://dontpad.com/109infinity

https://github.com/BaimaCaio/aula01-machinelearning/archive/refs/heads/master.zip


#### 1 - Carregue o conjunto de dados Titanic (train.csv) em um DataFrame do pandas e calcule a média, mediana e desvio padrão da idade dos passageiros.

#### 2 - Crie um histograma da idade dos passageiros para visualizar a distribuição.
##### import matplotlib.pyplot as plt
##### plt.hist()

#### 3 - Calcule a correlação entre a idade dos passageiros e a tarifa que pagaram.

#### 4 - Calcule a média da idade dos passageiros que sobreviveram e que não sobreviveram.

#### 5 - Calcule a mediana da tarifa que os passageiros pagaram.

#### 6 - Crie uma tabela dinâmica para mostrar a média da idade dos passageiros por classe.
##### use o método pivot_table()

#### 7 - Crie um gráfico de barras para mostrar o número de passageiros por porto de embarque.
##### use o método .bar() utilizando plt




import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

sns.set()

pd.options.display.max_columns = None

import pandas as pd
titanic = pd.read_csv('train.csv')

titanic.describe()

media_idade=titanic['Age'].mean()
media_idade

mediana_idade= titanic['Age'].median()
mediana_idade

 2 - Crie um histograma da idade dos passageiros para visualizar a distribuição.

resposta:
import matplotlib.pyplot as plt
plt.hist(titanic['Age'])

3 - Calcule a correlação entre a idade dos passageiros e a tarifa que pagaram.

resposta:
titanic['Age'].corr(titanic['Fare'])

 4 - Calcule a média da idade dos passageiros que sobreviveram e que não sobreviveram.
 
PassengerId: Número de identificação do passageiro
Survived: Informa se o passageiro sobreviveu ao desastre
    0 = Não
    1 = Sim
Pclass: Classe do bilhete
    1 = 1ª Classe
    2 = 2ª Classe
    3 = 3ª Classe
Name: Nome do passageiro
Sex: Sexo do passageiro
Age: Idade do passageiro
SibSp: Quantidade de cônjuges e irmãos a bordo
Parch: Quantidade de pais e filhos a bordo
Ticket: Número da passagem
Fare: Preço da Passagem
Cabin: Número da cabine do passageiro
Embarked: Porto no qual o passageiro embarcou
    C = Cherbourg
    Q = Queenstown
    S = Southampton
 
resposta:
titanic.head()

resposta:
sobreviventes = titanic.loc[titanic['Survived']== 1]
sobreviventes['Age'].mean()

Outra linha de respota:
morreram = titanic.loc[titanic['Survived']==0]
morreram['Age'].mean()

Outra linha de respota:
titanic.loc[titanic['Survived']==0,'Age'].mean()



5 - Calcule a mediana da tarifa que os passageiros pagaram.

titanic['Fare'].median()

6 - Crie uma tabela dinâmica para mostrar a média da idade dos passageiros por classe.
##### use o método pivot_table()

titanic.pivot_table(index='Pclass', values='Age', aggfunc='mean')

7 - Crie um gráfico de barras para mostrar o número de passageiros por porto de embarque.
##### use o método .bar() utilizando plt

titanic['Embarked'].value_counts().plot.bar(rot=0)
plt.show


 

