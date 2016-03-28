# Sobre o Projeto InfantON

Sistema Online para escolas de educação infantil que terá como finalidade o gerenciamento de dados, video chat, monitoramento online em tempo real, histórico de atividades(agenda pública), emissão de boletos e projetos realizados ao longo do ano da Escola de Educação infantil Recanto do Jardim.

Este projeto terá código opensource e o objetivo será construir uma ferramenta completa e melhor que todas disponíveis no mercado e que todos os módulos da aplicação serão gratuitos apenas para escolas pública e que 50% da rentabilidade será destinado para abrir novas creches pelo Brasil com modelo de franquia.

As tecnologia aplicadas no projeto irão rodar na plataforma Node.js e o banco de dados com NoSQL MongoDB, ou seja, todo o código de back end será inscrito em javascript e no front end html/css/javascript. 

Para as operações de CRUD usarei o mongoose. O banco de dados será Model, tabela serão collections e linhas da tabelas serão documentos.
Em NoSQL documentos são objetos representados entre chaves:
 {  
	nome:”vagner” 
	, documentos: { 
		cpf:”999.99999.99”
		, rg:”8888,9888888” 
    } 
 }.

Como padrão de arquitetura vou seguir modelo MVC com framework express. Para o monitoramento online usarei a tecnologia de webrtc para vídeo chat. Para a camada de front end usarei o gulp como automatizador de tarefa executando e organizando o código sass e gerar um arquivo css compilado e minificado,
além de usar outras bibliotecas para auxiliar na construção e estilização do html, tais como jeet.js, compass etc.. o uso dessas bibliotecas é para organizar o código e criar componentes html além de melhorar performace do código de carregamento no browser e aumentar SEO do site.

***

 
# Problemas
 
- Atualmente todos os dados referente aos alunos estão salvos em planilhas salvas no computador, 
em agendas dos próprios alunos e folhas de oficio. A idéia inicial é melhorar essa gestão desses dados.

- Não queremos excluir o uso das agendas, mas as mesmas informaçõe das agendas devem estar
disponivel online de forma fácil e rápida em tempo real.

- Dados coletados devem ser atividades recreativas, o que o aluno se alimentou, e outras opçoes..(vou complementar),
podem haver vária anotações. Não sei se seperadas ou todas em um unico aviso. 

- Atualmente o comprovante dos pagamentos referente as mensalidade são através de promissórias,
precisamos automatizar isso e liberar um recurso que emita um boleto online, o mesmo pode ser gerado
pelos pais ou pelo gestor do site. 

- Os pais podem monitorar seus filhos em tempo real.

# Solução


# Requisitos

1 - Requisitos Funcionais:

	- O sistema deve ter um arquivo .txt com histórico de logs;
	- O sistema deve usar a biblioteca do passaport para o sistema de login.
		 Tratamento de validação campos email e senha; 
		 A senha deve ser preenchida com no mínimo 5 caracteres, caso um desses campos não for enviado para api de login o sistema deve retornar mensagens de erros, especificando qual(is) campo(s) não foram validados.
	-  Formulário para /recuperar_senha com o campo de email.
	   Resposta de erro da api, caso o email não exista ou resposta de  sucesso, retornando “sua senha foi enviada para seu email”;

   - O usuário logado pode editar e atualizar os campos email e senha;

   - O sistema deve possuir 3 níveis de permissões: as de aluno, de professor e    administrador que serão importantes para restringir alguns acessos e elementos de front end;


 Tecnologia webrtc para acessar as webcam instaladas na escola e acompanhar ao vivo as atividades dentro da escola;


 O Sistema deve permitir que o responsável do aluno faça uma vídeo conferencia;
  
 Todo código css vai ser compilado com sass.

Operações de CRUD:




Validação nos schemas, sempre que for enviado algum tipo de dado diferente ou não for enviado um campo obrigatório etc... a api deve retornar um objeto de erro.
 
Módulo para gerenciar as Pessoas cadastradas no sistema:
Quando uma pessoa é cadastrada o sistema deve solicitar se é do tipo ALUNO ou FUNCIONÁRIO. Se for aluno, o sistema vai solicitar dados do responsável, turma, e demais campos importantes para a ficha de matricula, se o usuário for do tipo funcionário o sistema deve solicitar dados profissionais.


É obrigatório cadastrar a data que o aluno de fato vai iniciar as atividades, o sistema vai automatizar o campo status_matrícula assim que a data atual for igual a data do inicio das atividades, esse dado será importante para manter um controle de caixa da escola, essa verificação pode ser disparada sempre que sistema realizar uma busca por aluno e o status ainda for inativo;


Módulo de Pagamento:
O sistema deve integrar com o pagseguro(ver na documentação) quais procedimentos;


O módulo de pagamento vai precisar carregar os dados do Aluno e valor da mensalidade;


Campo status_pagamento deve ficar true assim que o pagamento for confirmado pelo pagseguro;

Módulo da Agenda Online:
Cadastrar dados da agenda com os campos data, id, título, descrição, foto e  id_anotação_referente, através deste último campo será possível  organizar o histórico de conversa das anotações;


Além dos campos acima as anotações vão precisar  cadastrar id_do_aluno e id_professor(se necessário);  


Módulo do Calendário Escolar:
Aplicação vai permitir um histórico de eventos da escola durante ano- letivo. Os campos são: id, titulo, descrição, galeria de fotos, id_responsavel;


Módulo das turmas
O sistema vai possuir uma Collection para armazenar os dados da turma, nome_da_turma, turno, id_professora e valor;

 