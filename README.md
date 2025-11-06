# Ataque simulado de BruteForce em um serviço FTP


1. Verificamos se a máquina1 (Atacante) alcança a MetaSploitable (Vulnerável):
<img width="640" height="486" alt="image" src="https://github.com/user-attachments/assets/1112bb16-da0f-4e1c-92d2-b36aba2f58f8" />


2. Obtendo a confirmação de que estamos alcançando a máquina Vulnerável, vamos para a etapa de Enumeração das falhas de configuração, Nosso foco inicial será no serviço **FTP** que pode ser uma versão antiga que ainda contenha falhas conhecidas ou simplesmente um servidor com erros de configuraçãod e segurança. Para essa finalidade fazemos uso da ferramento _NMAP_:
<img width="1217" height="600" alt="image" src="https://github.com/user-attachments/assets/b3baf710-10f5-48f1-88c0-348afd056a77" />


3. Ao rodar esse comando verificamos as portas que estão abertas e os serviços com suas versões. Notamos que o serviço FTP está rodando na porta padrão 21 que está aberta e ainda obtivemos sua __Versão 2.3.4__
4. Vamos verificar se o serviço está ativo e aceitando conexão:
<img width="612" height="354" alt="image" src="https://github.com/user-attachments/assets/9194cecf-bcd0-4964-8314-96034f41986e" />

5. Como não sabemos o _NAME_ para acessar o serviço vamos utlizar o método de BruteForce com a ferramenta _MEDUSA_ com uma lista de usuários e senhas para conseguir entrar no ambiente do FTP
6. Antes de ativar o MEDUSA precisamos criar dois arquivos com uma relação de usuários e um outro com uma lista de senhas para que a ferramenta realize as tentativas e informa qual combinação deu resultado:
7. Criando a __wordlist__ de usuários:
<img width="598" height="544" alt="image" src="https://github.com/user-attachments/assets/f15d2e59-1741-4b40-9fe9-7415f8fffc61" />

8. Vamos criar agora a __wordlist__ de senhas:
<img width="566" height="395" alt="image" src="https://github.com/user-attachments/assets/e1740489-8c55-4ea7-aa9a-a5e730ef7a26" />

9. Agora sim com esses dois arquivos bem simples podemos rodar nosso ataque:
<img width="610" height="444" alt="image" src="https://github.com/user-attachments/assets/aa878544-c52f-48c7-894a-e942e88b6302" />

10. Quando o MEDUSA terminar de rodar ele vai nos mostrar se obteve sucesso e qual combinação deu resultado:
<img width="1128" height="533" alt="image" src="https://github.com/user-attachments/assets/30a38d53-907f-4e46-bdea-e83a1c564a93" />

11. Note que foram usadas várias combinações até aplicar a seguinte _user:msfadmin_ e a _senha: msfadmin_, mostrando a mensagem __SUCCESS__
12. Agora podemos validar se realmente vamos conseguir o serviço FTP da máquina Vulnerável.
<img width="614" height="389" alt="image" src="https://github.com/user-attachments/assets/8d06463b-3467-4e83-8706-1646e693c0fe" />

13. Veja que com a utlização conseguimos acessar o FTP e navegar dentro de sua linha de comando
