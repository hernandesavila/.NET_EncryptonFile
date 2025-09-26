# 🔐 EncryptonFile

EncryptonFile é um aplicativo Windows Forms escrito em VB.NET no .NET Framework 4.5.1 para criptografar e descriptografar arquivos utilizando a biblioteca SharpAESCrypt.

A interface permite selecionar o arquivo de origem, indicar o destino e acessar as ações de Criptografar/Desriptografar a partir de botões e menu Sair centralizados em uma janela fixa.

---

## 🛠️ Tecnologias Utilizadas

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dot-net/dot-net-original.svg" alt=".NET" width="30" height="30"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" alt="Visual Studio" width="30" height="30"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/windows8/windows8-original.svg" alt="Windows" width="30" height="30"/>
</p>

- **VB.NET** – linguagem principal do formulário Windows e dos eventos de criptografia.
- **.NET Framework 4.5.1** – plataforma alvo definida no projeto.
- **Windows Forms** – interface gráfica com diálogos de arquivo e menu principal.
- **Visual Studio 2013** – ambiente de desenvolvimento configurado na solução.
- **SharpAESCrypt.dll** – biblioteca utilizada para criptografar e descriptografar os arquivos.

---

## 📂 Estrutura do Projeto

- `EncryptonFile/EncryptonFile.sln` – solução do Visual Studio 2013.
- `EncryptonFile/EncryptonFile/EncryptonFile.vbproj` – projeto Windows Forms com referências e configurações principais.
- `EncryptonFile/EncryptonFile/Main.vb` – lógica da tela, validações e chamadas de criptografia.
- `EncryptonFile/EncryptonFile/Main.Designer.vb` – layout do formulário, botões, menus e diálogos de arquivo.
- `EncryptonFile/EncryptonFile/App.config` – definição da versão do runtime .NET utilizada na execução.
- `EncryptonFile/EncryptonFile/My Project/*` – arquivos gerados do Visual Basic para recursos, configurações e inicialização do aplicativo.
- Referência externa para `SharpAESCrypt.dll`, necessária para as rotinas de criptografia AES.

---

## ✅ Pré-requisitos

- Windows com **.NET Framework 4.5.1+** instalado para executar o aplicativo.
- **Visual Studio 2013** (ou versão compatível) para abrir, compilar e depurar a solução.
- Disponibilizar a biblioteca **SharpAESCrypt.dll** junto com os binários compilados.

---

## ⚙️ Configuração

1. **Chave de criptografia** – A constante `_STR_KEY` em `Main.vb` define a senha padrão compartilhada entre criptografia e descriptografia; ajuste-a conforme a política de segurança da sua distribuição.
2. **Diálogos e validações** – O formulário usa `OpenFileDialog` e `SaveFileDialog` para escolher arquivos e só habilita os botões após uma seleção válida, limpando a tela quando necessário.
3. **Biblioteca SharpAESCrypt** – Garanta que `SharpAESCrypt.dll` esteja acessível no diretório de execução ou em um caminho configurado para que as chamadas `Encrypt`/`Decrypt` funcionem corretamente.

---

## 🛠️ Compilação

1. Abra `EncryptonFile.sln` no **Visual Studio 2013**.
2. Escolha a configuração desejada (`Debug` ou `Release`).
3. Compile o projeto `EncryptonFile` (`Build > Build EncryptonFile`). Os binários são gerados em `bin\Debug` ou `bin\Release`, conforme a configuração selecionada.

---

## ▶️ Execução

1. Execute o aplicativo pelo Visual Studio ou abra o executável gerado (`EncryptonFile.exe`).
2. Clique em `...` para escolher o **Arquivo de Origem**, habilitando as ações de criptografar e descriptografar.
3. Utilize **Criptografar** ou **Desriptografar** para criar o arquivo de saída escolhido, recebendo mensagens de sucesso ao final.
4. Use o menu **Sair** para fechar rapidamente o aplicativo quando necessário.

---

## 🔎 Funcionamento

- As ações de criptografar e descriptografar chamam diretamente `SharpAESCrypt.SharpAESCrypt.Encrypt` e `Decrypt`, sempre com a mesma chave constante e validação prévia do arquivo de saída.
- Após cada operação, `ClearScreen` restaura o estado inicial da interface, desabilitando os botões até uma nova seleção válida de arquivo.
- Mensagens amigáveis (`MsgBox`) informam o usuário sobre sucessos e possíveis erros durante o fluxo.

---

## 📌 Observações

- A janela possui tamanho fixo, inicia centralizada e tem o botão de maximizar desabilitado para manter o layout simples.
- O menu superior contém apenas a opção **Sair**, encerrando o aplicativo com `End` e liberando recursos do formulário.
- Considere distribuir um instalador que inclua `SharpAESCrypt.dll` e ajuste os textos do formulário caso deseje localizar o aplicativo.

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
