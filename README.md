# Concord — instaladores

Este repositório existe só para guardar os instaladores do Concord e o endereço
atual do servidor. O código-fonte não está aqui.

## Baixar

Pegue o `.exe` mais recente em [Releases](../../releases/latest).

Depois da primeira instalação o app se atualiza sozinho: ele confere se há
versão nova ao abrir e a cada 30 minutos, baixa em segundo plano e só aplica
quando você fechar. Nunca reinicia sozinho no meio de uma call.

## `servidor.json`

O app lê este arquivo para descobrir onde o servidor está no momento. O endereço
do túnel muda a cada vez que ele é ligado, e é por isso que o arquivo existe —
sem ele, cada sessão exigiria um instalador novo ou alguém ditando uma URL.

Não é segredo: quem tem o app já sabe o endereço. O que protege o servidor é o
login, não o endereço ser obscuro.

## Por que público

Assim o instalador não precisa carregar nenhum token do GitHub. Token embutido
num `.exe` é extraível, e o GitHub revoga token vazado — o que quebraria a
atualização automática de todo mundo de uma vez só.
