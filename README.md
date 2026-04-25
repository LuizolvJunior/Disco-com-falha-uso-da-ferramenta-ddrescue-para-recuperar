# Disco-com-falha-uso-da-ferramenta-ddrescue-para-recuperar
O problema começou quando o HD não foi mais reconhecido pelo sistema operacional, perdendo assim o acesso aos meus arquivos, fotos, vídeos e material de estudo

O problema começou quando ao ligar meu computador o disco apresentou o seguinte status


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
