# Javascript - comandos e funções


declarando variáveis e constantes:

	    const nome
    		declara uma constante chamada nome
    	var nome 
		
    	let nome
		

estruturas condicionais:

	if(condição){
		comandos;
	}
			se condição for verdadeira, comandos será executado.
    
	if(condição){
		comandos;
	} else {
		comandos2;
	}
			se condição for verdadeira, comandos será executado. 
			se não for, comandos2 será executado.
    
	if(condição){
		comandos;
	} else if(condição2){
		comandos2;
	} else {
		comandos3;
	}
			se condição for verdadeira, comandos será executado.
			se não for, se condição2 for verdadeira, comandos2 será executado.
			se condição e condição2 não forem verdadeiras, comandos3 será executado.
    
	switch (variável) {
		case ('valor'):
			comandos;
			break;
		case ('valor2'): 
			comandos2;
			break;
		default:
			comandos3
	}
				se o valor de variável for 'valor', executará comandos; caso seja 'valor2', executará comandos2; 
				por padrão(default) executará comandos3;


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
		comandos;
	}
			enquanto condição for verdadeira, executa os comandos. verifica se condição é verdadeira antes de executar 
			o comando
	
	for(expressao inicial; expressao final; expressao de passo){
		comandos;
	}
			executa os comandos a partir da expressão inicial atualizando a expressão inicial com a expressão de passo a cada 
			repetição. O loop se repete até que a expressão final deixe de ser verdadeira. 

declarando funções:
	
	function nome(parâmetro1,parâmetro2){
		comandos;
		return comando;
	}
			o parâmetro é a forma de passar valores externos para a função. A função pode ter um, vários, ou nenhum parâmetro.
			sempre que a função nome for chamada, comando será executado e o valor resultante será retornado para a variável 
			à qual foi atribuída a função. return não é necessário, tornando a função em apenas comandos sem valores retornando.

chamando a função nome:
	
	se tiver parâmetros:
	 	
		nome(parâmetro1,parâmetro2);
	
	se não tiver parâmetro:
		
		nome();
	
atribuindo o valor da função sem parâmetros a uma variável:
	
	var x = nome();

atribuindo o valor da função com parâmetros a uma variável:
	
	var x = nome(parâmetro1,parâmetro2);




Funções embutidas: 

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
