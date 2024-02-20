# Python-MySql
Codigo de interação basica com MySql

import mysql.connector

conexao = mysql.connector.connect(
    host='localhost',
    user='root',
    password='', #Senha do servidor MySql
    database='', #Nome do Servidor
    
)

cursor = conexao.cursor()

##CREATE

nome_produto = '' #Nome do produto 
valor = ... #Valor inteiro/Float
comando = f'INSERT INTO produtos(nome_produto, valor) VALUES ("{nome_produto}", "{valor}")'
cursor.execute(comando) 
conexao.commit() 
resultado = cursor.fetchall() 


##READ

comando = f'SELECT * FROM vendas;'
cursor.execute(comando) 
resultado = cursor.fetchall() #ler o banco de dados
print(resultado )

##UPDATE

nome_produto = "toddynho"
valor = 6
comando = f'UPDATE vendas SET valor = {valor} WHERE nome_produto = "{nome_produto}"'
cursor.execute(comando) 
conexao.commit() #edita o banco de dados

##DELETE

nome_produto = "toddynho"
comando = f'DELETE FROM vendas WHERE nome_produto = "{nome_produto}"'
cursor.execute(comando) 
conexao.commit() #edita o banco de dados

cursor.close()
conexao.close()
