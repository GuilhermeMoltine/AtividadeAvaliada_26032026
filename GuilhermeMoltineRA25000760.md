## Regras de Negócio
### RN01 – Controle de Estoque
Um produto não pode ser vendido se não houver quantidade suficiente em estoque.
### RN02 – Atualização Automática de Estoque
Toda movimentação (venda, compra, devolução, perda, transferência) deve atualizar o estoque automaticamente.
### RN03 – Venda a Prazo
Vendas a prazo devem gerar automaticamente um registro em Contas a Receber.
### RN04 – Compras Geram Contas a Pagar
Toda compra realizada deve gerar automaticamente um lançamento em Contas a Pagar.
### RN05 – Produtos Controlados
Medicamentos que exigem receita só podem ser vendidos com autorização do farmacêutico.

## Requisitos Funcionais
### RF01
O sistema deve permitir o cadastro de clientes.
### RF02
O sistema deve permitir a consulta de produtos por nome, código de barras ou fabricante.
### RF03
O sistema deve registrar vendas.
### RF04
O sistema deve validar estoque antes de concluir uma venda.
### RF05
O sistema deve permitir o cadastro de produtos.
### RF06
O sistema deve registrar compras de fornecedores.
### RF07
O sistema deve controlar contas a pagar.
### RF08
O sistema deve controlar contas a receber.
### RF09
O sistema deve gerar relatórios gerenciais.
### RF10
O sistema deve emitir comprovantes de venda.

## Requisitos Não Funcionais
### RNF01 – Desempenho
O sistema deve responder consultas em até 2 segundos.
### RNF02 – Segurança
O sistema deve possuir controle de acesso baseado em perfis de usuário.
### RNF03 – Disponibilidade
O sistema deve estar disponível 99% do tempo.
### RNF04 – Usabilidade
A interface deve ser simples e intuitiva para usuários não técnicos.

## Casos de Uso
### Lista de Casos (mínimo 10)
Realizar Login
Consultar Produto
Cadastrar Cliente
Registrar Venda
Validar Receita
Registrar Venda a Prazo
Registrar Compra
Atualizar Estoque
Gerar Relatórios
Controlar Contas a Pagar
Controlar Contas a Receber

## Relações <<include>> e <<extend>>
### Includes (obrigatório 3)
Registrar Venda <<include>> Consultar Produto
Registrar Venda <<include>> Validar Estoque
Registrar Compra <<include>> Atualizar Estoque
### Extends (obrigatório 3)
Registrar Venda a Prazo <<extend>> Registrar Venda
Validar Receita <<extend>> Registrar Venda
Cadastrar Cliente <<extend>> Registrar Venda

## Exemplo de Caso de Uso Documentado
### UC04 — Registrar Venda
### Ator Principal

Atendente

### Objetivo

Registrar a venda de produtos ao cliente.

### Pré-condições
Usuário autenticado
Produto cadastrado
### Pós-condições
Venda registrada
Estoque atualizado
Comprovante emitido
### Fluxo Principal
Atendente inicia venda
Sistema solicita produto
Atendente informa produto
Sistema verifica estoque
Atendente informa quantidade
Sistema calcula valor
Atendente finaliza venda
Sistema registra venda
Sistema atualiza estoque
Sistema emite comprovante
### Fluxos Alternativos
4A – Produto sem estoque
Sistema informa indisponibilidade
Venda não é concluída
2A – Cliente não cadastrado
Sistema permite cadastro rápido (<<extend>> Cadastrar Cliente)

## Exemplo de Diagrama de Atividade (descrição)
### Registrar Venda
Início
Selecionar produto
Verificar estoque
[Decisão] Tem estoque?
Não → Exibir erro → Fim
Sim → Informar quantidade
Calcular valor
Finalizar venda
Atualizar estoque
Emitir comprovante
Fim

## Diagrama de Caso de Uso

1. Diagrama de Casos de Uso
<img width="449" height="1109" alt="image" src="https://github.com/user-attachments/assets/4ce7c6e9-f6da-4052-9b40-6fc941db752d" />

2. Diagrama de Atividade — Registrar Venda
<img width="531" height="651" alt="image" src="https://github.com/user-attachments/assets/2b5a6e76-688b-43fd-b2b5-55234b3123bd" />

3. Diagrama de Atividade — Venda a Prazo
<img width="295" height="477" alt="image" src="https://github.com/user-attachments/assets/37399376-3edf-43a2-8b92-a451706c0369" />

4. Diagrama de Atividade — Registrar Compra
<img width="163" height="523" alt="image" src="https://github.com/user-attachments/assets/77a6126f-6373-4ec4-b28d-0882a61d2137" />

5. Diagrama de Atividade — Contas a Receber
<img width="317" height="405" alt="image" src="https://github.com/user-attachments/assets/6ac33ee5-ed5f-4642-895f-c3c0cfa3e395" />

6. Diagrama de Atividade — Contas a Pagar
<img width="209" height="434" alt="image" src="https://github.com/user-attachments/assets/81496ad8-0638-42cd-a85f-397cc6bbe7b9" />

7. Diagrama de Atividade — Cadastro de Cliente
<img width="224" height="312" alt="image" src="https://github.com/user-attachments/assets/97ebf0b4-3806-4469-b565-99349020db4e" />

8. Diagrama de Atividade — Gerar Relatórios
<img width="215" height="312" alt="image" src="https://github.com/user-attachments/assets/603589e9-e1db-4a78-9279-0f32b3a7606c" />





