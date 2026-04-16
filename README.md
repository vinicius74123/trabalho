<!DOCTYPE html>
<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> 📚 Sistema escolar</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: "Segoe UI", Arial, sans-serif;
            background: linear-gradient(135deg, #2e0101, #310000);
        }

        .titulo {
            text-align: center;
            padding: 40px 20px 10px;
        }

        .titulo h1 {
            font-size: 26px;
            color: #140707;
        }

        .titulo p {
            color: #64748b;
            margin-top: 5px;
        }

        .menu {
            background-color: var(--soft-blue);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 40px;
            height: 60px;
            box-shadow: 0 4px 10px rgb(255, 255, 255);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .menu-esquerda {
            flex: 1;
            display: flex;
            align-items: center;
            color: var(--white);
            font-weight: bold;
            font-size: 1.2rem;
        }

        .menu-esquerda::before {
            content: "🏫 ";
        }

        .menu-centro {
            flex: 2;
            display: flex;
            justify-content: center;
            gap: 25px;
        }

        .menu-centro span {
            color: #cbd5e0;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            padding: 8px 12px;
            border-radius: 6px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .menu-centro span:hover {
            color: var(--white);
            background-color: rgba(52, 152, 219, 0.2);
        }

        .menu-direita {
            flex: 1;
            display: flex;
            justify-content: flex-end;
        }

        .menu-direita span {
            background-color: var(--accent-blue);
            color: var(--white);
            padding: 8px 25px;
            border-radius: 20px;
            font-weight: bold;
            font-size: 14px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .menu-direita span:hover {
            background-color: #2980b9;
        }


        .pagina {
            background: #360101;
            width: 380px;
            padding: 35px 30px;
            border-radius: 20px;
            margin: 25px auto;
            box-shadow: 0 20px 50px rgba(243, 243, 243, 0.08);
            transition: 0.3s;
            display: none;
        }
        .pagina-ativa{
            display: block;
        }
        .pagina input {
            width: 100%;
            padding: 12px 14px;
            border-radius: 12px;
            border: 1px solid #3d096d;
            background: #631663;
            font-size: 14px;
            transition: all 0.25s ease;
        }

        .pagina input::placeholder {
            color: #94a3b8;
        }

        .cadastrar {
            display: block;
            margin-top: 30px;
            padding: 14px;
            border-radius: 14px;
            border: none;
            background: linear-gradient(135deg, #6366f1, #4f46e5);
            color: rgb(228, 13, 163);
            font-size: 15px;
            font-weight: 600;
            cursor: pointer;
            transition: 0.25s;
            margin: auto;
        }

        .cadastrar:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(99, 102, 241, 0.25);
        }

        .resultado {
            display: none;
            background: rgb(105, 3, 97);
            width: 520px;
            margin: 25px auto;
            padding: 25px;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(253, 253, 253, 0.08);
            line-height: 1.6;
            color: #f3f3f3;
        }

        .resultado h2 {
            margin-bottom: 10px;
            font-size: 20px;
        }
        .menu span{cursor: pointer;}

        @media (max-width: 600px) {

            .formulario,
            .resultado {
                width: 90%;
            }
        }
        .card{
            background-color: #0c028f;
            padding: 20px;
            border-radius: 4px;
            text-align: center;
            box-shadow: 0 6px 10px rgba(241, 6, 6, 0.959);
            margin-top: 36px;
            margin-bottom: 10px;
        }
        #dashboard{
            box-sizing: border-box;
            flex-direction: column;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }

    </style>
</head>

<body>
    <div class="menu">
        <div class="menu-esquerda">EEB DOM JAIME</div>
        <div class="menu-centro">
            <span onclick="navegar('dashboard')">Início</span>
            <span onclick="navegar('alunos')">Alunos</span>
            <span onclick="navegar('professores')">Professores</span>
            <span onclick="navegar('funcionarios')">Funcionários</span>

        </div>
        <div class="menu-direita">
            <span>Login</span>
        </div>
    </div>

    <div id="dashboard" class="pagina pagina-ativa">
        <div class="card">
            <h2>Alunos Cadastrados</h2>
            <p>0</p>
        </div>

        <div class="card">
            <h2>Docentes lecionando na unidade</h2>
            <p>0</p>
        </div>

        <div class="card">
            <h2>Funcionarios</h2>
            <p>0</p>
        </div>
    </div>

    <div id="alunos" class="pagina">
        <div class="titulo">
            <h1>EEB Dom Jaime de Barros Camara</h1>
            <p>Cadastro de alunos</p>
        </div>
        <form>
            <label>Nome</label>
            <input type="text" id="nome">

            <label>Data de Nascimento</label>
            <input type="date" id="dataNasc">

            <label>CPF</label>
            <input type="text" id="cpf">

            <label>Email</label>
            <input type="text" id="email">

            <label>Cidade</label>
            <input type="text" id="cidade">

            <label>Estado</label>
            <input type="text" id="estado">

            <label>Idade</label>
            <input type="number" id="idade">

            <button type="button" class="cadastrar" onclick="mostrarDados()">Cadastrar</button>
        </form>
    </div>

    <div id="professores" class="pagina">
        <div class="titulo">
            <h1>EEB Dom Jaime de Barros Camara</h1>
            <p>Professores</p>
        </div>
        <form>
            <label>Jaula</label>
            <input type="text" id="nome">

            <label>Data de Nascimento</label>
            <input type="date" id="dataNasc">

            <label>CPF</label>
            <input type="text" id="cpf">

            <label>Email</label>
            <input type="text" id="email">

            <label>Cidade</label>
            <input type="text" id="cidade">

            <label>Estado</label>
            <input type="text" id="estado">

            <label>Idade</label>
            <input type="number" id="idade">

            <button type="button" class="cadastrar" onclick="mostrarDados()">Cadastrar</button>
        </form>
    </div>

    <div id="funcionarios" class="pagina">
        <div class="titulo">
            <h1>EEB Dom Jaime de Barros Camara</h1>
            <p>Funcionarios</p>
        </div>
        <form>
            <label>Barbaridade pae</label>
            <input type="text" id="nome">

            <label>Data de Nascimento</label>
            <input type="date" id="dataNasc">

            <label>CPF</label>
            <input type="text" id="cpf">

            <label>Email</label>
            <input type="text" id="email">

            <label>Cidade</label>
            <input type="text" id="cidade">

            <label>Estado</label>
            <input type="text" id="estado">

            <label>Idade</label>
            <input type="number" id="idade">

            <button type="button" class="cadastrar" onclick="mostrarDados()">Cadastrar</button>
        </form>
    </div>

    <div id="resultado" class="resultado"></div>

    <script>


        function navegar(pagina){
            let paginas = document.getElementsByClassName("pagina");

        
        for(let i = 0; i < paginas.length; i++){
            paginas[i].classList.remove("pagina-ativa");
        }

        
        document.getElementById(pagina).classList.add("pagina-ativa");
        }

        function mostrarDados() {
            let nome = document.getElementById("nome").value;
            let dataNasc = document.getElementById("dataNasc").value;
            let cpf = document.getElementById("cpf").value;
            let email = document.getElementById("email").value;
            let cidade = document.getElementById("cidade").value;
            let estado = document.getElementById("estado").value;
            let idade = document.getElementById("idade").value;

            let resultado = document.getElementById("resultado");
            const abaAtiva = document.querySelector('.pagina-ativa').id
            let atual = parseInt(localStorage.getItem('cont_' + abaAtiva)) || 0;
            localStorage.setItem('cont_' + abaAtiva, atual + 1);

            document.getElementById("resultado").innerHTML = "<h2>Dados Informados: </h2>" +
                "Nome: " + nome + "<br>" +
                "Data de Nascimento: " + dataNasc + "<br>" +
                "CPF: " + cpf + "<br>" +
                "Email: " + email + "<br>" +
                "Cidade: " + cidade + "<br>" +
                "Estado: " + estado + "<br>" +
                "Idade: " + idade;

            resultado.style.display = "block";
            dashboard()
        }
        window.onload = dashboard

        function ocultarResultado(){
            resultado.style.display = "none";
        }

        function dashboard(){
            const qtdAlunos = localStorage.getItem('cont_alunos') || 0;
            const qtdProfs = localStorage.getItem('cont_professores') || 0;
            const qtdFuncs = localStorage.getItem('cont_funcionarios') || 0;

            const cards = document.querySelectorAll("#dashboard .card p");

            cards [0].innerText = qtdAlunos;
            cards [1].innerText = qtdProfs;
            cards [2].innerText = qtdFuncs;

        }       
    </script>

</body>

</html>
