//Prova ADS - Guilherme Gabriel Barros - ra: 190975 

package provaads;

import java.util.Scanner;

public class ProvaADS { public static void main(String[] args) throws InterruptedException {

     Scanner ler= new Scanner(System.in);
     
     double saldo = 1000,dep,sac,trans;
     int cont=0,n=0,op;
     boolean verifica=false;
     String cpf,senha,conta,agencia,banco; 
    
    while(true) { // voltar p/ inicio novamente!
        
    System.out.println("BEM-VINDO CLITENTE!\n"); // tela de bem-vindo
     
    do{
        System.out.printf("Informe seu CPF: "); // colher informaçoes CPF
        cpf = ler.next();
        if("123.456.789-00".equals(cpf))
           verifica=true;
        else{  
           System.out.println("Cpf Invalido!");
        }
    }while(verifica==false); // verificação cpf // sair do looping
    
   verifica = false;   // deixando verifica falso! p nova repetição de senha!
     
    do{
        System.out.printf("Informe sua senha: "); //colher iformaçoes senha
        senha=ler.next();
        if("01020304".equals(senha)){
            verifica=true;
        }else{
            System.out.println("Senha inválida");
            cont++;
        }
        if(cont==3){
            System.out.println("Conta bloqueada\n");  // CONTA BLOQUEADA REINICIO O CÓDIGO
            System.out.println("Tente novamente! // REINICIE O CÓDIGO!");
        }
                 
    }while(verifica==false); // verificação senha // sair do looping
    
    do{
        System.out.println("   Menu   \n -> 1 <- Saldo\n -> 2 <- Depósito \n -> 3 <- Saque\n -> 4 <- Tranferencias \n-> 0 <- Sair\n");
        System.out.println("Opção: ");
        op = ler.nextInt();
        
        switch(op){
            
            case 1:
                System.out.printf("Saldo: "+saldo);
                System.out.println("\n");
                Thread.sleep(1000);
                break;
            case 2:
                System.out.printf("Digite o valor para depósito: ");
                dep=ler.nextDouble();
                saldo+=dep;
                Thread.sleep(1000);
                System.out.println("Depósitado!\n");
                break;
            case 3:
                do{
                System.out.printf("Digite o valor para saque: ");
                sac=ler.nextDouble();
                if(sac>saldo)
                   System.out.printf("Impossivel sacar!\n");
                }while(saldo<sac);
                saldo-=sac;
                Thread.sleep(1000);
                System.out.println("Saque efetuado\n");
                break;
                
            //Fazer Transferência: deverá solicitar o valor da transferência, a conta, agência e o banco (simular
            //valores) e atualizar o saldo    
                
              case 4:     // DESAFIO 1
                
                  do{
                  System.out.println("Qual valor da tranferencia?");
                  trans = ler.nextDouble();
                  
                  if(trans>saldo)
                   System.out.printf("Não é possível fazer a transferência, "+"não há esse dinheiro suficiente na conta\n");
                  }while(trans>saldo);

                     System.out.printf("Digite o numero da conta: "); // colher informaçoes CONTA
                     conta = ler.next();

                     System.out.printf("Digite o numero da Agencia: "); // colher informaçoes agencia
                     agencia = ler.next();
                     
                     System.out.println("Informe o banco: ");
                     banco = ler.next();
                     
                    saldo-=trans; 
                    
                    System.out.println("Numero da Conta: "+conta+"\nAgencia: "+agencia+"\nBanco: "+banco+"\n");
                    System.out.println("Tranferencia Efetuado com Suscesso.\nDinheiro já debitado do seu Saldo.");
     
              break;    
                
                
            case 0:
                System.out.println("Saindo\n");
                n=1;
                break;
            default:
                System.out.println("Opção não valída!");
                Thread.sleep(1000);
                break;
        }
        
        }while(n==0);
    
    Thread.sleep(1000);
    System.out.println("FIM :)"); 
    
    
    }
    } 
}



