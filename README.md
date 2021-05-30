# Loteria

programa
{
	
	funcao inicio()
	{
	    loteria()
	}
    
    funcao loteria(){
	    inteiro opcao = 0
	
		escreva("***** Bem-Vindo *****\n")
		escreva("*********************\n")
		escreva("** Escolha um jogo **\n")
		escreva("*********************\n")
		escreva("**** 1-Mega-Sena ****\n")
		escreva("**** 2-Quina     ****\n")
		escreva("**** 3-Lotomania ****\n")
		escreva("**** 4-Lotofácil ****\n")
		escreva("*********************\n")

		escreva("\nSelecione um jogo: ")
		leia(opcao)

		limpa()

		escolha(opcao){

			caso 1:
			inteiro num_de_Apostas = 0		
			inteiro dinheiro_gasto = 0
			real num_de_Dezena[16] 

			num_de_Dezena[6] = 4.50
			num_de_Dezena[7] = 31.50
			num_de_Dezena[8] = 126.00
			num_de_Dezena[9] = 378.00
			num_de_Dezena[10] = 9345.00
			num_de_Dezena[11] = 2079.00
			num_de_Dezena[12] = 4158.00
			num_de_Dezena[13] = 7722.00
			num_de_Dezena[14] = 13513.50
			num_de_Dezena[15] = 22522.50

			inteiro dezena = 0
			 
			escreva("***** Valor das Apostas: *****\n")
			escreva("*****    6 - R$4,50      *****\n")
			escreva("*****    7 - R$31,50     *****\n")
			escreva("*****    8 - R$126,00    *****\n")
			escreva("*****    9 - R$378,00    *****\n")
			escreva("*****   10 - R$9345,00   *****\n")
			escreva("*****   11 - R$2.079,00  *****\n")
			escreva("*****   12 - R$4.158,00  *****\n")
			escreva("*****   13 - R$7.722,00  *****\n")
			escreva("*****   14 - R$13.513,50 *****\n")
			escreva("*****   15 - R$22.522,50 *****\n")			
			
			escreva("\n**** Quantas dezenas deseja apostar? ****\n")
			leia(dezena)
			enquanto(dezena < 6 ou dezena > 15){
				escreva("Só é possível apostar de 6 a 15 dezenas. Tente novamente: \n")
				escreva("\n*** Quantas dezenas deseja apostar? ***\n")
				leia(dezena)
			}

			
			escreva("*** Quantas apostas deseja fazer?  ***\n")
			leia(num_de_Apostas)
			limpa()			

			//Faz o sorteio dos números
			para(inteiro k = 0; k < num_de_Apostas; k++){         
				 				
				 inteiro mega[15]
			     inteiro numSorteado

			      logico repetido = falso
			
			      para(inteiro i = 0; i < dezena; i++){
				  
				  faca {
					      numSorteado = sorteia(0, 60)
					      repetido = falso

					      para(inteiro u = 0; u < dezena; u++){
					 	     se(numSorteado == mega[u]){
					 		   repetido = verdadeiro
					 		   pare
		                     }
		                }
				}

				enquanto(repetido)

				mega[i] = numSorteado
		     }
		     //Organiza a aposta
		     inteiro auxiliar = 0

		     para(inteiro i = 0; i < 15; i++){
		     	para(inteiro u = i + 1; u < 15; u++){
		     		se(mega[u] < mega[i]){
		     			auxiliar = mega[i]
		     			mega[i] = mega[u]
		     			mega[u] = auxiliar

		                }
		           }
		     }
               //Escreve a aposta
		     para(inteiro i=0; i < dezena; i++){
		     	escreva(mega[i], " ")

		      }

		      escreva("\n")
		}
          //Calculo do valor gasto
		real valorGasto = num_de_Dezena[dezena] * num_de_Apostas

		 escreva("Você gastou um total de: R$", valorGasto)
		 
		 pare

		 caso 2:
		 inteiro dezenas2
		 inteiro num_Apostas
		 real num_Dezena[16]
		 
		num_Dezena[5] = 2.00
		num_Dezena[6] = 12.00
		num_Dezena[7] = 42.00
		num_Dezena[8] = 112.00
		num_Dezena[9] = 252.00
		num_Dezena[10] = 504.00
		num_Dezena[11] = 924.00
		num_Dezena[12] = 1584.00
		num_Dezena[13] = 2574.00
		num_Dezena[14] = 4004.00
		num_Dezena[15] = 6006.00
		 
		 escreva("***** Valor das Apostas: *****\n")
		 escreva("******************************\n")
		 escreva("*****    5 - R$2,00      *****\n")
		 escreva("*****    6 - R$12,00     *****\n")
		 escreva("*****    7 - R$42,00     *****\n")
		 escreva("*****    8 - R$112,00    *****\n")
		 escreva("*****    9 - R$252,00    *****\n")
		 escreva("*****   10 - R$504,00    *****\n")
		 escreva("*****   11 - R$924,00    *****\n")
		 escreva("*****   12 - R$1.584,00  *****\n")
		 escreva("*****   13 - R$2.574,00  *****\n")
		 escreva("*****   14 - R$4.004,00  *****\n")
		 escreva("*****   15 - R$6.006,00  *****\n")

		 escreva("\n***** Quantas dezenas deseja apostar? *****\n")
		 leia(dezenas2)
		 enquanto(dezenas2 < 5 ou dezenas2 > 15){
		 escreva("Só é possível apostar de 5 a 15 dezenas. Tente novamente: \n")
		 escreva("\n**** Quantas dezenas deseja apostar? ****\n")
		 leia(dezenas2)
		 }

		 escreva("Quantas apostas deseja fazer? \n")
		 leia(num_Apostas)
		 limpa()
		 
		 //Faz o sorteio dos números
			para(inteiro k = 0; k < num_Apostas; k++){         
				 				
				 inteiro mega[15]
			      inteiro numSorteado

			      logico repetido = falso
			
			      para(inteiro i = 0; i < dezenas2; i++){
				  
				  faca {
					      numSorteado = sorteia(0, 60)
					      repetido = falso

					      para(inteiro u = 0; u < dezenas2; u++){
					 	     se(numSorteado == mega[u]){
					 		   repetido = verdadeiro
					 		   pare
		                     }
		                }
				}

				enquanto(repetido)

				mega[i] = numSorteado
		     }
		     //Organiza a aposta
		     inteiro auxiliar = 0

		     para(inteiro i = 0; i < 15; i++){
		     	para(inteiro u = i + 1; u < 15; u++){
		     		se(mega[u] < mega[i]){
		     			auxiliar = mega[i]
		     			mega[i] = mega[u]
		     			mega[u] = auxiliar

		                }
		           }
		     }
               //Escreve a aposta
		     para(inteiro i=0; i < dezenas2; i++){
		     	escreva(mega[i], " ")

		      }

		      escreva("\n")
		}
          //Calculo do valor gasto
		real gasto = num_Dezena[dezenas2] * num_Apostas

		 escreva("Você gastou um total de: R$", gasto)
		 
		 pare


		 caso 3:
		 inteiro dezenas = 50
		 inteiro num_apostas = 0

		 escreva("**** Na Lotomania, o número de dezenas é fixo em 50 ****\n")
		 escreva("\n**** Valor da aposta: ****\n")
		 escreva("****     50 - R$2,50   ****\n")
		 escreva("\n**** Quantas apostas deseja fazer? ****\n")
		 leia(num_apostas)
		 limpa()
		 
		 		 //Faz o sorteio dos números
			para(inteiro k = 0; k < num_apostas; k++){         
				 				
				 inteiro mega[50]
			      inteiro numSorteado

			      logico repetido = falso
			
			      para(inteiro i = 0; i < dezenas; i++){
				  
				  faca {
					      numSorteado = sorteia(0, 60)
					      repetido = falso

					      para(inteiro u = 0; u < dezenas; u++){
					 	     se(numSorteado == mega[u]){
					 		   repetido = verdadeiro
					 		   pare
		                     }
		                }
				}

				enquanto(repetido)

				mega[i] = numSorteado
		     }
		     //Organiza a aposta
		     inteiro auxiliar = 0

		     para(inteiro i = 0; i < 50; i++){
		     	para(inteiro u = i + 1; u < 50; u++){
		     		se(mega[u] < mega[i]){
		     			auxiliar = mega[i]
		     			mega[i] = mega[u]
		     			mega[u] = auxiliar

		                }
		           }
		     }
               //Escreve a aposta
		     para(inteiro i=0; i < dezenas; i++){
		     	escreva(mega[i], " ")

		      }

		      escreva("\n")
		}
          //Calculo do valor gasto
		real Gasto = 2.50 * num_apostas

		 escreva("Você gastou um total de: R$", Gasto)
		 
		 pare


		 caso 4:
		 inteiro Dezenas
		 inteiro Num_aposta = 0
         inteiro Num_dezenas[21]
         
		 Num_dezenas[15] = 2.50
		 Num_dezenas[16] = 40.00
		 Num_dezenas[17] = 340.00
		 Num_dezenas[18] = 2040.00
		 Num_dezenas[19] = 9690.00
		 Num_dezenas[20] = 38760.00
         
		 escreva("***** Valor das apostas: *****\n")
		 escreva("*****   15 - R$2,50      *****\n")
		 escreva("*****   16 - R$40,00     *****\n")
		 escreva("*****   17 - R$340,00    *****\n")
		 escreva("*****   18 - R$2.040,00  *****\n")
		 escreva("*****   19 - R$9.690,00  *****\n")
		 escreva("*****   20 - R$38.760,00 *****\n")
		 
		 escreva("\n***** Quantas dezenas deseja apostar? *****\n")
		 leia(Dezenas)
		 enquanto(Dezenas < 15 ou Dezenas > 20){
		 escreva("Só é possível apostar de 15 a 20 dezenas. Tente novamente: \n")
		 escreva("\n**** Quantas dezenas deseja apostar? ****\n")
		 leia(Dezenas)
		 }

		 escreva("Quantas apostas deseja fazer? \n")
		 leia(Num_aposta)
		 limpa()
		
		//Faz o sorteio dos números
			para(inteiro k = 0; k < Num_aposta; k++){         
				 				
				 inteiro mega[20]
			     inteiro numSorteado

			      logico repetido = falso
			
			      para(inteiro i = 0; i < Dezenas; i++){
				  
				  faca {
					      numSorteado = sorteia(0, 60)
					      repetido = falso

					      para(inteiro u = 0; u < Dezenas; u++){
					 	     se(numSorteado == mega[u]){
					 		   repetido = verdadeiro
					 		   pare
		                     }
		                }
				}

				enquanto(repetido)

				mega[i] = numSorteado
		     }
		     //Organiza a aposta
		     inteiro auxiliar = 0

		     para(inteiro i = 0; i < 20; i++){
		     	para(inteiro u = i + 1; u < 20; u++){
		     		se(mega[u] < mega[i]){
		     			auxiliar = mega[i]
		     			mega[i] = mega[u]
		     			mega[u] = auxiliar

		                }
		           }
		     }
               //Escreve a aposta
		     para(inteiro i=0; i < Dezenas; i++){
		     	escreva(mega[i], " ")

		      }

		      escreva("\n")
		}
          //Calculo do valor gasto
		real gastos = Num_dezenas[Dezenas] * Num_aposta

		 escreva("Você gastou um total de: R$", gastos)
		 
		 pare
		
	}
}}
