# 🛒 Sistema de controle de compras

## Sobre o projeto

Solução desenvolvida para um comércio que permite a gestão de compras e pagamentos.

### Arquitetura da solução

Tudo foi feito utilizando a versão 8 do .NET.

- **GestaoCompras.API**: API REST com ASP.NET em C#. Autenticação e autorização com token JWT
- **GestaoCompras.WEB**: FrontEnd Web com Blazor
- **GestaoCompras.Models**: Classes
- **GestaoCompras.DTO**: Projeto compartilhado com as DTO's utilizadas na API e no FrontEnd Web.
- **GestaoCompras.Enums**: Enumeradores
- **GestaoCompras.Utils**: Extensões e classes estáticas de uso comum em todo o projeto

### Funcionalidades

| **Funcionalidade** | **Descrição** |
| :--- | :--- |
| **Login** | Permite que um usuário faça login informando e-mail cadastrado e senha |
| **Painel de gestão de pedidos** | É a página inicial do sistema. Ao acessar o usuário visualiza campos para filtrar pedidos, um quadro de estatísticas e uma relação dos pedidos a pagar por PIX, cartão de crédito ou débito. É possível editar ou excluir pedidos |
| **Cadastro de pedidos** | Ao incluir um pedido o usuário informa o produto, fornecedor, valor unitário e quantidade. Além disso tem a opção de indicar se o pagamento será feito por boleto ou cheque para uma gestão mais específica dos pagamentos. Nesse caso deve-se informar a data de pagamento e, em caso de cheque, o número |
| **Painel de gestão de boletos ou cheques** | Ao acessar essa funcionalidade o usuário tem a opção de filtrar pedidos específicos que serão pagos com boleto ou cheque. É possível editar ou excluir pedidos |
| **Notificação de vencimento** | Na parte superior do layout principal o usuário tem uma janela de notificações que avisa sobre cheques que estão próximos da data de vencimento |

### Telas

Os dados exibidos abaixo são fictícios.

1. **Painel de gestão de pedidos**

![](https://stgabrielsrios1106.blob.core.windows.net/images/Home.png)
![](https://stgabrielsrios1106.blob.core.windows.net/images/HomeComPrecos.png)

2. **Painel de gestão de boletos ou cheques**

![](https://stgabrielsrios1106.blob.core.windows.net/images/BoletosECheques.png)

## Infraestrutura

Os recursos de infraestrutura estão no Azure, organizados da seguinte forma:

- **FrontEnd Web**: Implantado no **Azure Static Web App**
- **API**: Contêiner Docker rodando em uma máquina virtual
- **Banco de dados PostgreSQL e pgAdmin**: Ambos rodando em contêiner Docker em uma outra máquina virtual com backup

Foi necessário dividir os contêineres em duas máquinas virtuais por questões de custo.
