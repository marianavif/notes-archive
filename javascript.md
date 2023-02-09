# Javascript - comandos e funções


declarando variáveis e constantes:

	    const nome
    		declara uma constante chamada nome
    	var nome 
		
    	let nome
		

estruturas condicionais:

	if(condição){
		comando;
	}
			se condição for verdadeira, comando será executado.
    
	if(condição){
		comando;
	} else {
		comando2;
	}
			se condição for verdadeira, comando será executado. 
			se não for, comando2 será executado.
    
	if(condição){
		comando;
	} else if(condição2){
		comando2;
	} else {
		comando3;
	}
			se condição for verdadeira, comando será executado.
			se não for, se condição2 for verdadeira, comando2 será executado.
			se condição e condição2 não forem verdadeiras, comando3 será executado.
    
	switch (variável) {
		case ('valor'):
			comando;
			break;
		case ('valor2'): 
			comando2;
			break;
		default:
			comando3
	}
				se o valor de variável for 'valor', executará comando; caso seja 'valor2', executará comando2; 
				por padrão(default) executará comando3;


operadores:
	
	==
		igual
	!=
		diferente
	===
		estritamente igual (tipo de dado e valor do dado iguais)
	>=
		maior ou igual
	<=
		menor ou igual
	>
		maior
	<
		menor
	+
		soma
	-
		subtração
	*
		multiplicação
	/
		divisão
	%
		módulo (resto da divisão de dois inteiros)
	++
		incremento de 1
	+= numero
		incremento de numero
	--
		decremento de 1
	-= numero
		decremento de numero
		
	&&
		AND
	||
		OR
	
	condição ? (expressao1) : (expressao2)
		operador ternário; se condição for verdadeira, executar expressao1. se condição for falsa, executar expressao2

Estruturas de repetição:
	
	while(condição){
		comando
	}
			enquanto condição for verdadeira, executa o comando. verifica se condição é verdadeira antes de executar o comando


Funções: 

*var pode ser número, string ou variável contendo número ou string

	console.log(var) 
		Exibe o valor de var no console do navegador


	document.write(var) 
		Escreve no corpo do documento o valor de var
			"<br>" 
				pula linha
			`string ${variável numérica}` 
				passa string concatenada com variável numérica


	alert(var) 
		Cria um alerta na forma de pop-up com o valor de var


	prompt(var) 
		Cria um pop-up com o valor de var e uma caixa de texto para inserir dados


	parseInt(var) 
		Torna em inteiro o valor numérico de var


	parseFloat(var)
		Torna em float o valor numérico de var
