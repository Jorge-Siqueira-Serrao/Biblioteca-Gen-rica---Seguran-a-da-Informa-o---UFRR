import itertools

# Caracteres possíveis para a wordlist (letras minúsculas e números)
caracteres = 'abcdefghijklmnopqrstuvwxyz0123456789'

# Abre um arquivo para escrever a wordlist
with open('wordlist.txt', 'w') as file:
    # Gera combinações de 6 dígitos com letras minúsculas e números
    comb = itertools.product(caracteres, repeat=6)
    for c in comb:
        # Escreve a senha no arquivo
        password = ''.join(c)
        file.write(password + '\n')

    # Gera combinações de 6 dígitos de 000000 a 999999
    for i in range(1000000):
        # Formate o número como uma string de 6 dígitos preenchidos com zeros à esquerda
        password = '{:06}'.format(i)
        # Escreve a senha no arquivo
        file.write(password + '\n')

print("Wordlist gerada com sucesso e salva no arquivo 'wordlist.txt'.")
