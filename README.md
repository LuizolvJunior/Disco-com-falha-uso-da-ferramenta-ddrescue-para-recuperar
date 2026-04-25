# Disco-com-falha-uso-da-ferramenta-ddrescue-para-recuperar
O problema começou quando o HD não foi mais reconhecido pelo sistema operacional, perdendo assim o acesso aos meus arquivos, fotos, vídeos e material de estudo

![O problema começou quando ao ligar meu computador o disco apresentou o seguinte status](1.png)

<br>

Usando o Gerenciador de disco pude notar que o sistema de arquivo está diferente dos demais, com um tipo "RAW"
![](2.png)

[DICA]
O sistema de arquivo do tipo "RAW" significa que o Windows não consegue reconhecer o formato do disco ou partição, indicando corrupção, falha de formatação ou danos físicos. A unidade torna-se inacessível e, geralmente, é necessário recuperar os dados com softwares especializados antes de formatá-la (converter para NTFS/FAT32)

Foi exatamente isso que eu fiz, pesquisei e encontrei o SystemRescue, fiz o download da ISO, criei um pendrive bootável, configurei na BIOS o boot pelo pendrive e executei o sistema operacional baseado no linux e seguir alguns poucos passos para resolver o meu problema.


🔧 Procedimento completo
🔹 ETAPA 1 — Preparar o ambiente
1. Baixar a ISO do SystemRescue
2. Criar pendrive bootável
Use: Rufus

Configuração padrão já funciona.

🔹 ETAPA 2 — Boot
Inicie pelo pendrive
Escolha opção padrão do SystemRescue
Ele já entra pronto (root, sem senha)
🔹 ETAPA 3 — Identificar discos (CRÍTICO)
Rode:
lsblk -o NAME,SIZE,MODEL

🚀 EXECUÇÃO — CLONAGEM COM GNU ddrescue
🔹 Passo 1 — Primeira passada (rápida e segura)
ddrescue -f -n /dev/sda /dev/sdb /root/log.log

⏭️ Próximo passo (automático ou manual)

Quando terminar essa fase:

👉 você executa:

ddrescue -d -r3 /dev/sda /dev/sdb /root/log.log

Isso vai:

voltar nos erros
tentar recuperar setores ruins
