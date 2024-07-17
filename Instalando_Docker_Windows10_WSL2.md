# Instalando o Docker no Windows 10 Home ou Professional com WSL 2

![poster](.github/thumbnails/docker-wsl2.pngg)

O Docker é uma plataforma popular para a criação, implantação e execução de aplicativos em contêineres. Se você está usando o Windows 10 Home, pode instalar o Docker com o Windows Subsystem for Linux (WSL) 2. Neste tutorial, vamos guiá-lo pelo processo de instalação passo a passo.

## 1. Verifique os pré-requisitos

Certifique-se de que você está executando pelo menos a versão Windows 10 de 64-bit, de preferência com uma licença original.

- Ative a virtualização no BIOS/UEFI do seu computador. Isso é geralmente chamado de "VT-x" ou "AMD-V".
- Também é importante garantir que você esteja executando a versão 2004, Build 19041 ou superior do Windows 10. Você pode verificar isso pressionando `Win + R`, digitando `winver` e pressionando `Enter`.

## 2. Instale o Subsistema Windows para Linux (WSL)

Abra o PowerShell como administrador e execute o seguinte comando:

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Ainda no PowerShell como administrador, execute o seguinte comando:

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

Reinicie o seu PC.

Defina a versão padrão do WSL para a versão 2:

```powershell
wsl --set-default-version 2
```

Faça o download e instalação do pacote atualizado do Kernel: [Atualizar Kernel](https://learn.microsoft.com/pt-pt/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)

## 3. Instale uma distribuição Linux

Abra a Microsoft Store e procure por uma distribuição Linux de sua escolha, como o Ubuntu.

Clique em "Obter" para baixar e instalar a distribuição.

Após a instalação, clique em "Iniciar" para configurar um nome de usuário e senha na primeira execução.

## 4. Instale o Docker Desktop

Baixe o Docker Desktop para Windows.

Execute o instalador e siga as instruções na tela.

Uma vez instalado, inicie o Docker Desktop.

Vá para Configurações > Recursos > WSL Integration no Docker Desktop e habilite a integração com a sua distribuição Linux.

## 5. Verifique a instalação

Abra um terminal WSL ou PowerShell e execute:

```bash
docker --version
```

Isso deve mostrar a versão do Docker instalada.

Teste um comando simples do Docker para garantir que tudo esteja funcionando corretamente:

```bash
docker run hello-world
```

Se tudo correu bem, você deve ver uma mensagem do Docker dizendo que sua instalação parece estar funcionando corretamente!

## Notas:

- Lembre-se de que o Docker Desktop requer virtualização habilitada no BIOS/UEFI. Se você encontrar problemas ao iniciar o Docker, verifique se a virtualização está habilitada.
- O desempenho do Docker com WSL 2 é significativamente melhor do que com a versão anterior do WSL, então vale a pena fazer essa atualização.

Espero que este tutorial tenha sido útil! Se você tiver algum problema ou dúvida, sinta-se à vontade para perguntar.
