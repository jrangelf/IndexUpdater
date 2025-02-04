# **IndexUpdater** :rocket:

![Logo do Projeto](https://via.placeholder.com/800x200?text=IndexUpdater+Logo)

**IndexUpdater** é um programa desenvolvido em Python que automatiza a atualização de índices monetários, indexadores e taxas de juros armazenados em um banco de dados PostgreSQL. Ele foi projetado para garantir que suas tabelas estejam sempre atualizadas com os valores mais recentes fornecidos pela API do Banco Central.

---

## **Funcionalidades Principais**

- **Verificação Automática de Atualizações:**  
  O programa verifica diariamente, em horários pré-definidos, a data do último registro em cada tabela do banco de dados `indices`. Ele compara essa data com a data atual para identificar quais tabelas estão desatualizadas.

- **Integração com a API do Banco Central:**  
  Para as tabelas desatualizadas, o programa consulta a API do Banco Central e obtém os valores mais recentes dos indexadores (como IPCA, Selic, TR, etc.).

- **Atualização Eficiente do Banco de Dados:**  
  Após buscar os dados necessários, o programa atualiza as tabelas correspondentes no banco de dados PostgreSQL. Cada tabela que depende de um indexador específico é atualizada automaticamente, garantindo consistência e precisão nos registros.

---

## **Como Funciona?**

1. **Verificação de Datas:**  
   O programa busca a data do último registro em cada tabela do banco de dados `indices` e a compara com a data atual.

2. **Consulta à API do Banco Central:**  
   Se uma tabela estiver desatualizada, o programa faz uma requisição à API do Banco Central para obter os valores mais recentes dos indexadores.

3. **Atualização das Tabelas:**  
   Os novos valores são inseridos nas tabelas correspondentes, garantindo que todas as informações estejam sincronizadas com os dados oficiais.

---

## **Benefícios**

- **Automação Completa:**  
  Elimina a necessidade de atualizações manuais, economizando tempo e reduzindo erros humanos.

- **Precisão Garantida:**  
  Todos os dados são obtidos diretamente da fonte oficial (API do Banco Central), assegurando a confiabilidade das informações.

- **Escalabilidade:**  
  O programa pode ser facilmente adaptado para incluir novos indexadores ou tabelas, conforme necessário.

---

## **Requisitos**

Para executar o **IndexUpdater**, você precisará dos seguintes componentes instalados:

- Python 3.x
- Bibliotecas Python: `psycopg2` (para interação com o PostgreSQL) e `requests` (para consultas à API do Banco Central)
- Um banco de dados PostgreSQL configurado com as tabelas de índices e indexadores.
- Acesso à API do Banco Central (certifique-se de ter uma chave de API válida, se necessário).

---

## **Instalação e Uso**

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/IndexUpdater.git
   cd IndexUpdater
