# 🛒 Lista de Compras Inteligente

**Lista de Compras Inteligente** é um aplicativo web (PWA) para controle de compras e estoque doméstico.  
Foi projetado para ser leve, responsivo e funcional tanto **offline** quanto **online**, podendo ser usado diretamente no navegador de **tablets, celulares ou PCs**.

---

## 🌐 Visão Geral

O objetivo é automatizar e simplificar o processo de compras, oferecendo:

- Controle de **itens, quantidades, preços e categorias**
- **Atualização automática de status** conforme o estoque
- Cálculo automático de **quantidade a comprar**
- Registro de **histórico de compras** e **gastos mensais**
- **Filtros por data e frequência** (semanal, mensal, trimestral)
- **Dashboard resumido** de gastos e consumo
- Sincronização opcional com **Google Sheets**
- Funcionalidade **PWA** (instalável e funcional offline)

---

## 🧩 Estrutura de Módulos

| Módulo | Descrição |
|--------|------------|
| **Lista de Compras** | Itens pendentes para compra, status e quantidades automáticas |
| **Estoque Atual** | Controle de produtos e níveis de estoque mínimos |
| **Histórico** | Registro de compras realizadas, datas e valores |
| **Dashboard** | Totais, gráficos e análises mensais |
| **Comparativo de Marcas/Lojas** | Controle opcional de preços e preferências |

---

## 🧱 Campos de Dados

| Campo | Tipo | Descrição |
|--------|------|-----------|
| **Item** | Texto | Nome do produto |
| **Categoria** | Seleção | Ex: Hortifruti, Limpeza, Laticínios |
| **Quantidade mínima (mín.)** | Número | Quantidade mínima ideal em estoque |
| **Quantidade atual (estoque)** | Número | Quantidade disponível atualmente |
| **Quantidade a comprar** | Automático | Calculado se estoque < mínimo |
| **Status** | Automático | "Suficiente", "Comprar", "Em falta" |
| **Preço unitário** | Número | Valor por unidade |
| **Custo total** | Automático | Preço × Quantidade |
| **Data da última compra** | Data | Registro da última compra |
| **Frequência** | Seleção | Semanal, Mensal, Trimestral |
| **Marca / Loja** | Texto | Campo opcional para controle de marca |
| **Observações** | Texto | Notas adicionais |

---

## ⚙️ Lógicas e Cálculos

### 🧮 Cálculos automáticos
- **Quantidade a comprar:** `mínimo - estoque`
- **Status:**  
  - Estoque < mínimo → “Comprar”  
  - Estoque = mínimo → “Limite”  
  - Estoque > mínimo → “Suficiente”
- **Custo total:** `preço × quantidade`
- **Gasto mensal:** soma dos custos das compras realizadas no mês

### 🔔 Regras inteligentes
- Itens abaixo do mínimo são **destacados visualmente**
- Atualização automática de status ao alterar estoque
- Histórico é gerado ao marcar item como “comprado”
- Salvamento local e persistente (`localStorage`)

---

## 🧮 Estrutura de Arquivos

```
/lista-compras/
│
├── index.html             # Interface principal
├── app.js                 # Lógica e cálculos automáticos
├── style.css              # Estilos e layout
├── manifest.json          # Configuração PWA
├── service-worker.js      # Cache e modo offline
├── /assets/               # Ícones e imagens
└── /data/                 # (opcional) arquivos CSV de exemplo
```

---

## 💾 Armazenamento de Dados

Os dados são salvos localmente via **localStorage**, permitindo:
- uso offline sem perda de dados;
- atualização automática de status e quantidades;
- exportação/importação manual em CSV.

No futuro, o app poderá se integrar ao **Google Sheets API** para sincronização em nuvem.

---

## 🧰 Tecnologias

| Tecnologia | Função |
|-------------|---------|
| **HTML5 / CSS3 / JavaScript** | Base do aplicativo |
| **localStorage** | Persistência local de dados |
| **IndexedDB (futuro)** | Armazenamento estruturado |
| **Google Sheets API (futuro)** | Sincronização online |
| **GitHub Pages** | Hospedagem gratuita |
| **PWA (manifest + service worker)** | Instalação e funcionamento offline |

---

## 📱 Funcionalidades Principais

- Adicionar / editar / excluir itens  
- Calcular automaticamente a quantidade a comprar  
- Atualizar status conforme estoque  
- Registrar compras e atualizar histórico  
- Filtrar por data e frequência  
- Calcular e exibir total de gastos  
- Exportar lista em CSV  
- Funcionar offline e como app instalado no dispositivo  

---

## 🔄 Fluxo de Uso

1. Adicione os itens com nome, categoria e quantidade mínima.  
2. Atualize o estoque sempre que usar ou comprar algo.  
3. O app indica automaticamente o que precisa ser comprado.  
4. Durante a compra, registre os preços — o total é calculado automaticamente.  
5. Ao concluir, marque como **“Comprado”** para atualizar o estoque e gerar histórico.  
6. Os dados permanecem salvos mesmo offline.  

---

## 🌐 Hospedagem

O projeto é hospedado via **GitHub Pages**, podendo ser acessado em:

```
https://hcerqueira.github.io/lista-compras/
```

Você pode publicar novos módulos em repositórios separados, por exemplo:
```
https://hcerqueira.github.io/estoque/
https://hcerqueira.github.io/dashboard/
```

---

## 📊 Fases de Desenvolvimento (Backlog)

### Fase 1 — Estrutura Base
- [ ] Interface e tabela principal  
- [ ] Salvamento local  
- [ ] Adição, edição e exclusão de itens  
- [ ] Cálculos automáticos de quantidade e status  

### Fase 2 — Funcionalidades Inteligentes
- [ ] Histórico de compras  
- [ ] Filtros por data e categoria  
- [ ] Alerta visual de estoque crítico  
- [ ] Totais e gastos mensais  

### Fase 3 — PWA e Deploy
- [ ] Adicionar manifest e service worker  
- [ ] Publicar no GitHub Pages  
- [ ] Testar instalação em Android/iOS  

### Fase 4 — Integrações e Dashboards
- [ ] Conexão com Google Sheets  
- [ ] Dashboard com gráficos e relatórios  
- [ ] Exportação CSV / Importação automática  

---

## 📈 Possíveis Expansões Futuras

- Login com conta Google  
- Backup automático em nuvem  
- Compartilhamento de lista entre usuários  
- Notificações push para alertas de estoque  
- Dashboard em tempo real  

---

## 👨‍💻 Autor

**Desenvolvido por:** [@hcerqueira](https://github.com/hcerqueira)  
**Projeto:** Lista de Compras Inteligente  
**Plataforma:** GitHub Pages  
**Licença:** Uso pessoal / open-source  

---

> 🧠 *“Controle seu consumo, economize e automatize seu dia a dia — direto do navegador.”*
