# ATP2026

### TPC3 ###

**Autor**: Inês Cristina de Castro Barreto, a114394 <img align="right" width="100" height="100"  alt="Foto Ines 180x180" src="https://github.com/user-attachments/assets/b0bf8671-1aa8-4eb5-b8cf-58c734b96889" />
 
**Resumo**: O TPC3 consiste na criação de um programa python, do jogo "Corrida para o 100", onde o utilizador e o computador alternam apostas de 1 a 10. Estes números serão somados entre si até atingir exatamente 100 valores. O primeiro que atingir esse valor ganha. 

**Lista dos resultados**: 


 ```
import random 

def jogar(): 
    total = 0

    #Definir quem começa a jogar 
    ordem = int(input("Quem é que começa a jogar? (1 o computador ou 2 o utilizador)"))
    
        # O computador começa a jogar, logo o computador tem que vencer
        # Para garantir a vitoria, o computador tem que jogar de inicio o número 1 
    if ordem == 1:
        x = 1 
        total = total + x 
        print (f"Ocomputador jogou {x} e o total é {total}")

        while total < 100 : 
            y = 0 
            while y < 1 or y > 10 or total + y > 100: 
                y = int(input("Qual a sua aposta? (1 a 10)"))
                if y < 1 or y > 10 :   
                    print ("Aposta inválida! Escolha um número entre 1 e 10.")

                elif total + y > 100: 
                    print ("Aposta inválida! O total não pode ultrapassar 100.")

            total = total + y
            print (f"O utilizador jogou {y} e o total é {total}")

            if total == 100: 
                print ("O utilizador ganhou!")

            else:  
                x = 11 - y 
                total = total + x 
                print (f"O computador jogou {x} e o total é {total}")

            if total == 100:
                print ("O computador ganhou!")
 
    else: 
        while total < 100: 
            x = 0 
            resto = total % 11  
            while x < 1 or x > 10 or total + x > 100 :
                x = int(input("Qual a sua aposta? (1 a 10)"))
                if x < 1 or x > 10 : 
                    print ("Aposta inválida! Escolha um número entre 1 e 10.")

                elif total + x > 100: 
                    print ("Aposta inválida! O total não pode ultrapassar 100.")

            total = total + x
            print (f"O utilizador jogou {x} e o total é {total}")

            if total == 100: 
                print ("O utilizador ganhou!")

            elif resto != 0 :
                y = 11 - resto 
                total = total + y 
                print (f"O computador jogou {y} e o total é {total}")

            else : 
                y = random.randint(1,10) 
                total = total + y 
                print (f"O computador jogou {y} e o total é {total}")
                if total == 100:
                    print ("O computador ganhou!")
        
jogar()

```
