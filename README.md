# 🚀 Controle de Frota Inteligente (Entrada e Saída)

Um sistema web leve, responsivo e focado em eficiência para o registro de quilometragem (KM) e captura de fotos de veículos em frotas corporativas. Desenvolvido para rodar direto no navegador de smartphones ou computadores dos motoristas/fiscais.

## ✨ Diferenciais do Sistema

* **🌐 Sincronização Automática (Modo Offline):** Utiliza o banco de dados interno do navegador (`IndexedDB` via Dexie.js). Se o motorista estiver em uma garagem subterrânea ou estrada sem sinal, o registro (incluindo a foto compactada) é salvo instantaneamente no aparelho. Assim que a conexão (4G ou Wi-Fi) é restaurada, o sistema envia os dados para a nuvem em segundo plano de forma transparente.
* **📸 Captura e Otimização de Imagem:** Ativa a câmera traseira do dispositivo para comprovação visual e realiza uma compactação inteligente antes do envio, evitando estouro de limite de dados do servidor.
* **🔒 Validação de Segurança de KM:** Impede erros operacionais comuns, bloqueando o salvamento caso o KM de chegada informado seja menor que o último KM registrado para aquele veículo específico.
* **📊 Banco de Dados Serverless:** Totalmente integrado ao ecossistema Google (Google Sheets para dados de texto e Google Drive para armazenamento das imagens) via Google Apps Script.

---

## 🛠️ Tecnologias Utilizadas

* **Frontend:** HTML5, CSS3 (Design moderno e responsivo) e JavaScript Assíncrono.
* **Banco de Dados Local:** [Dexie.js](https://dexie.org/) (Wrapper minimalista para IndexedDB).
* **Backend / API:** Google Apps Script (JavaScript V8).
* **Armazenamento de Dados:** Google Planilhas.
* **Armazenamento de Arquivos:** Google Drive.

---

## ⚖️ Aviso de Propriedade Intelectual e Termos de Uso

> ### ⚠️ NOTA DE DIREITOS AUTORAIS E PROTEÇÃO LEGAL
>
> Este repositório contém código-fonte, elementos de design, logomarcas, arquitetura de software e conteúdos que são de **propriedade estritamente privativa** do desenvolvedor/organização. 
>
> Fica expressamente proibida a cópia, reprodução, distribuição, modificação ou exploração comercial não autorizada, total ou parcial, de qualquer componente presente neste projeto sem prévia autorização por escrito.
>
> A utilização indevida, plágio ou cópia não autorizada deste conteúdo privativo sujeitará o infrator às sanções civis e criminais cabíveis, amparadas pela **Lei de Direitos Autorais (Lei nº 9.610/98)** e pelos artigos de proteção à propriedade e reparação de danos previstos no **Código Civil Brasileiro (Lei nº 10.406/02)**, respondendo o autor civilmente por perdas, danos e lucros cessantes.

---

## 🚀 Como Configurar

1.  **Planilha e Script:**
    * Crie uma Google Planilha.
    * Vá em `Extensões > Apps Script`, cole o código estruturado do `Código.gs` e insira o ID da sua pasta do Google Drive na variável `PASTA_ID`.
    * Configure o arquivo de manifesto `appsscript.json` para incluir os escopos necessários (`oauthScopes`).
    * Execute a função `doGet` manualmente uma vez no painel para conceder as permissões de acesso à sua conta.
    * Clique em `Implantar > Nova Implantação`, selecione **App da Web**, configure para executar como "Eu" e acesso para "Qualquer pessoa". Copie a URL gerada.

2.  **Interface Web (`index.html`):**
    * Abra o arquivo `index.html`.
    * Localize a constante `const SCRIPT_URL = "..."` e cole a URL copiada do passo anterior.
    * Substitua a propriedade `src` da tag `<img>` da logo pelo código Base64 da sua empresa.
    * Execute o arquivo em qualquer servidor estático ou publique via GitHub Pages.

---
Desenvolvido por Qually Vidros. Todos os direitos reservados © 2026.
