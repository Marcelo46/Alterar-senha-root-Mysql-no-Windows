# Alterar-senha-root-Mysql-no-Windows
Como alterar a senha root do banco de dados Mysql no windows em ambiente local, caso perca ou precise alterar a senha. Sem utilizar permissões especiais.
### Parar serviço banco de dados
Para alterar a senha do banco de dados é necessário parar o serviço no Windows.
No campo de pesquisa busque por **Serviços**, conforme imagem.

<img src="img\servicos.png">

Em **Serviços** encontre o serviço do MySQL conforme a versão instalada em sua máquina.
Clique o botão direito do mouse e clique em **Parar**.

<img src="img\parar servico mysql.png">

### Criar arquivo de texto que será utilizado para trocar a senha do MySql

Inicie o bloco de notas como administrador. Copie e cole este trecho de código:

```ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';```

Altere a senha para a senha que desejar. Salve em C:\ com o nome de **Reset.txt**

Inicie o **CMD** do windows como administrador. Conforme imagem.

<img src="img\cmd.png">

Se seu banco de dados estiver instalado no caminho padrão, basta copiar e colar este comando no **CMD** e clicar Enter.

```cd "C:\Program Files\MySQL\MySQL Server 8.0\bin"```

Se estiver instalado em outro endereço, é necessário abrir no **CMD** o local da pasta onde o MySql está instalado.
No **CMD**, estando dentro da pasta **bin** do MySql, copie e cole este trecho de código:

```mysqld --defaults-file="C:\\ProgramData\\MySQL\\MySQL Server 8.0\\my.ini" --init-file=C:\\reset.txt```

`Este trecho de código precisa estar em apenas uma linha` `#ffffff`

Pronto! Sua senha root foi alterada. Reinicie o serviço do banco de dados no Windows. E pode iniciar o seu gerenciador de banco de dado.
Em alguns casos pode ser necessário reiniciar o computador.



