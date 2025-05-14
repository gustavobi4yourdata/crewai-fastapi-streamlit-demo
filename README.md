# CrewAI FastAPI Streamlit Demo

## Como rodar o projeto

### 1. Clone o repositório

```sh
git clone https://github.com/seu-usuario/crewai-fastapi-streamlit-demo.git
cd crewai-fastapi-streamlit-demo
```

### 2. Crie um arquivo .env na raiz do projeto

Crie o arquivo `.env` e adicione suas variáveis de ambiente necessárias:

```env
OPENAI_API_KEY=your_openai_api_key_here
SERPER_API_KEY=your_serper_api_key_here
```

### 3. Configure a versão do Python com pyenv

```sh
pyenv install 3.12.1
pyenv local 3.12.1
```

### 4. Configure o ambiente virtual com Poetry

```sh
poetry env use 3.12.1
poetry shell
```

### 5. Instale as dependências

Se preferir instalar via pip:

```sh
pip install -r requirements.txt
```

Ou usando Poetry:

```sh
poetry install
```

### 6. Execução com Docker

#### 6.1. Construção da Imagem

No diretório raiz do projeto, execute:

```sh
docker build -t fastapicrew .
```

> A imagem é baseada no Python 3.12.4 e utiliza a configuração presente no [Dockerfile](Dockerfile).

#### 6.2. Criação do Container

Após construir a imagem, inicie o container com:

```sh
docker run -d --name fast-api-demo -p 80:80 fastapicrew
```

> O container será executado na porta 80.

### 7. Executando a Interface Streamlit

Para iniciar a interface interativa, execute:

```sh
streamlit run testeAPIStreamlit.py
```

> A interface se comunica com a API disponível na rota `/research_candidates`.

### 8. Testando a API

Você pode testar a API utilizando o script de testes:

```sh
python testeAPI.py
```

> O script envia um `POST` para a rota `/research_candidates` com os requisitos do job e exibe a resposta.

### 9. Notas Adicionais

- Certifique-se de que as chaves de API estejam corretamente definidas no arquivo `.env` ou no código (em [app/main.py](app/main.py)).
- Consulte o próprio [README.md](README.md) para informações rápidas e demais detalhes do projeto.
- O projeto utiliza o [Poetry](https://python-poetry.org/) para gerenciamento de dependências.

### 10. Agradecimentos e Contato

Agradecemos a Reginaldo Silva pelo vídeo tutorial, que serviu de inspiração para este projeto.

Vídeo de referência:
- [Assista ao vídeo no YouTube](https://www.youtube.com/watch?v=I-n9iTb6nis&list=PL_TleL_MyEBIqEZknjFf-B2Se9pTMqLcW&index=7)
