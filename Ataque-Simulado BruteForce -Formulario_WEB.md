# Simulação de Ataque utilizando o método BruteForce a um Formulário WEB

## Demonstrando como automatizar o ataque no formulário de login de sites WEB, observando se o desenvolvedor deixou alguma brecha ou pista ao receber essas tentativas de LOGON

## FERRAMENTA _MEDUSA_

1. Primeiro acessamos a página de login ao site:
<img width="1409" height="699" alt="image" src="https://github.com/user-attachments/assets/d3a07aa0-a9ce-4bee-b146-c97394405828" />

2. Depois abrimos a barra de desenvolvedor, dependendo do Browser utilizado, mas geralmente a tecla é __F12__. Depois clicamos na aba NETWORK
<img width="1419" height="701" alt="image" src="https://github.com/user-attachments/assets/b186ee21-7720-42d4-9fa6-2e8e2ad95ea5" />

3. Preenchemos os campos com usuários e senhas quaisquer, apenas para averiguar o que o sistema nos retorna como mensagem de erro:
<img width="1407" height="691" alt="image" src="https://github.com/user-attachments/assets/d0d957cb-0a37-4d63-a39c-147e52977665" />

4. Observe que foram retornados informações importantes, a mensagem de erro: __LOGIN FAILED__ e também o formato dos parâmetros que o sistema espera receber: _username_, _password_ e _LOGIN_. Em posse dessas informações fica mais claro como elaborar o formato de nosso ataque
5. Próxima etapa será criar as __wordlists_ de Usuários e Senhas para que o MEDUSA as utilize com base nos parâmetros descobertos e tente logar no Site () Para efeito de demonstração utilizamos listas bem simples, mas existem listas com milhares e até milhões de senhas e usuários):
<img width="620" height="466" alt="image" src="https://github.com/user-attachments/assets/da0e26b2-9a6e-4a6b-8f82-3f9fd8248a93" />
<img width="619" height="477" alt="image" src="https://github.com/user-attachments/assets/0be92181-37ab-4de4-a95e-02924eed7943" />

6. Rodamos o comando do MEDUSA e verificamos qual combinação obteve sucesso:
<img width="1541" height="854" alt="image" src="https://github.com/user-attachments/assets/bf8ab0d6-5669-4c0b-b7e6-db826d35e783" />
