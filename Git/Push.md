### **O que é o `git push`?**

O comando `git push` é usado para **enviar suas alterações** locais para um repositório remoto, como o GitHub. Isso geralmente é feito depois de você ter feito alterações no código, criado novos commits e deseja compartilhar essas mudanças com outros colaboradores ou atualizar o repositório remoto com seu progresso.

### **1. Verificando o Status do Repositório Local**

Antes de fazer o `git push`, é bom verificar o status do repositório local e garantir que não há alterações pendentes.

Abra o terminal e digite o comando:

`git status`

Isso vai mostrar se há algum arquivo modificado ou novo que ainda precisa ser adicionado, comitado ou se está tudo pronto para ser enviado.

### **2. Adicionando Arquivos ao Commit**

Se você tem alterações que ainda não foram adicionadas ao commit, você precisa usar `git add` para incluir esses arquivos.

- Para adicionar **todos os arquivos modificados**:
    
    `git add .`
    
- Para adicionar **arquivos específicos**:
    
    `git add nome-do-arquivo`
    

### **3. Criando um Commit**

Depois de adicionar os arquivos ao commit, o próximo passo é criar um commit. O commit é um ponto de registro das mudanças feitas no código.

Execute o comando:

`git commit -m "Mensagem do commit"`

Substitua `"Mensagem do commit"` por uma descrição breve sobre as mudanças que você fez, como:

`git commit -m "Corrigido erro de validação no formulário"`

### **4. Enviando as Alterações com o `git push`**

Agora que você tem seu commit pronto, é hora de enviar essas alterações para o repositório remoto.

Se você estiver na branch principal, use o seguinte comando:

`git push origin main`

Aqui:

- **`origin`** é o nome do repositório remoto (por padrão, o nome é `origin`).
- **`main`** é o nome da branch para a qual você está enviando as alterações. Se você estiver usando outra branch, substitua `main` pelo nome da sua branch.

Por exemplo, se você estiver trabalhando na branch `develop`, o comando seria:

`git push origin develop`

### **5. Autenticação (se necessário)**

Quando você usar o comando `git push` pela primeira vez ou após um período de inatividade, o Git pode pedir para autenticar sua identidade.

Se você estiver usando **chaves SSH**, isso será feito automaticamente, desde que sua chave SSH esteja configurada corretamente.

Se você estiver usando **HTTPS**, você precisará fornecer seu **nome de usuário** e **token de autenticação** (em vez da sua senha do GitHub) para concluir a autenticação.

### **6. Verificando o Status Após o Push**

Após o `git push` ser concluído, você pode verificar se suas mudanças foram enviadas corretamente com:

`git status`

Se o `git push` foi bem-sucedido, o status deve mostrar que sua branch local está atualizada com o repositório remoto.

Você também pode visitar o repositório remoto (por exemplo, no GitHub) e verificar se o commit aparece no histórico.

### **7. Resolvendo Problemas Comuns**

#### **7.1. Atualizando sua Branch Local Antes de Push**

Às vezes, quando você tenta fazer `git push`, pode ocorrer um erro dizendo que sua branch local está desatualizada em relação à branch remota (por exemplo, "non-fast-forward" ou "behind").

Isso significa que alguém fez alterações no repositório remoto enquanto você estava trabalhando. Para resolver isso, você deve **fazer um pull** para atualizar sua branch local antes de empurrar suas próprias mudanças.

Execute:

`git pull origin main`

Depois de resolver qualquer conflito (se houver) e de atualizar sua branch local, você pode tentar o `git push` novamente.

#### **7.2. Erro de Permissões**

Se você encontrar um erro de **permissão negada** (por exemplo, "Permission denied (publickey)"), isso indica que sua chave SSH não está configurada corretamente ou que sua chave não está associada ao seu repositório remoto. Você precisará corrigir isso, configurando corretamente sua chave SSH ou autenticando com o HTTPS.

### **8. Dicas Importantes**

- **Push Frequente:** Tente fazer `git push` regularmente para manter seu repositório remoto atualizado e evitar perder alterações importantes.
- **Branches:** Sempre faça push para a branch correta (por exemplo, `main`, `develop`, ou qualquer outra branch em que você está trabalhando).
- **Boa Prática de Mensagens de Commit:** Use mensagens de commit claras e descritivas, pois elas ajudam os outros desenvolvedores a entender o que foi alterado.

### **9. Resumo dos Comandos**

- **Adicionar todos os arquivos para commit:**
    
    `git add .`
    
- **Criar um commit:**
    
    `git commit -m "Mensagem do commit"`
    
- **Enviar alterações para o repositório remoto:**
    
    `git push origin main`
    
- **Enviar alterações para uma branch específica:**
    
    `git push origin nome-da-branch`