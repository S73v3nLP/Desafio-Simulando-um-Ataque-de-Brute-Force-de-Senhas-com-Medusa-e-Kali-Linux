# Ataque Simulado utilizando BruteForce, Enumeração de Vulnerabilidade e _Password Spraying_ a um Servico SMB

## Simulação de um ambiente em que o atacante já conseguiu acesso à rede e descobriu um Servidor SMB. Os próximos passos: Enumerar as vulnerabilidades e depois testar usuários e senhas para invadir o Servidor

1. Iniciamos com a ferramenta _enum4linux_ que efetua todos as tecnicas de enumeração disponíveis, ela vai gravar o resultado em um arquivo para anlisarmos e verificar as informações disponíveis
<img width="680" height="586" alt="image" src="https://github.com/user-attachments/assets/9a857759-3402-4ef7-8ae7-416364fbda01" />

2. Agora vamos ler o arquivo utilizando o comando _less_, nele existem várias informações, mas no momento vamos nos fixar nos nomes de usuários apresentados
<img width="1261" height="879" alt="image" src="https://github.com/user-attachments/assets/4e3d5367-ae4d-49e5-a80c-eaa93227708c" />

3. Vamos nos ater aos nomes mais genéricos e padrão do sistema, esses são os melhores candidatos para o ataque
4. Vamos criar agora a wordlist de usuários e de senhas:
<img width="598" height="188" alt="image" src="https://github.com/user-attachments/assets/9e92437d-4a4c-464d-95be-c2fc0a2f988c" />
<img width="612" height="182" alt="image" src="https://github.com/user-attachments/assets/e307a06f-9402-4091-9d2b-2898a29f8afe" />

5. Veja que vamos testar vários usuários em poucas senhas em cada, esse é a técnica de _Password Spraying_, utilizando senhas comuns e de uso costumeiro procurando um usuário padrão esquecido ou com senhas fracas.
6. Vamos utilizar novamente a ferramenta __MEDUSA__ que é rápida e confiável para esse tiop de ataque:
<img width="811" height="455" alt="image" src="https://github.com/user-attachments/assets/009953c8-3040-4176-8441-2f01113176b4" />

7. Veja o resultado do ataque, ele usa várias tentativas com __CHECK__ e a que nos interessa é a que está assinalada como __FOUND__
<img width="1187" height="375" alt="image" src="https://github.com/user-attachments/assets/a7182ed7-763d-4a3f-a242-6e5c2f2e1303" />

8. Vamos agora validar o usuário e senha acessando o serviço utilizando o comando _smbclient_:
<img width="796" height="351" alt="image" src="https://github.com/user-attachments/assets/593bfa5d-151f-4015-a6ad-b24ff6aa213f" />

9. Acesso validado, estamos dentro do servidor SMB!
