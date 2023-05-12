# Documentação de instalação da DataTrail SDK Tag

## Disponibilizamos duas formas de integração, manual ou automática. Abaixo exemplos de cada uma delas.

## Manual

### Configure os scripts abaixo nas sessões correspondentes do seu site.

### Página de Login

```
<script type="text/javascript" src="https://api.datatrail.com.br/sdk/tracker.min.js"></script>
<script>
    tracker
        .onProfile('Código da conta')        
        .onCustomer({email: "email do cliente"});
</script> 
```

### Página de Produto
```
<script type="text/javascript" src="https://api.datatrail.com.br/sdk/tracker.min.js"></script>
<script>
    tracker
        .onProfile('Código da conta')
        .onProduct({
            productId:       "Id do produto",
            productName:     "Descrição do produto",
            productPrice:    "Preço do produto",
            productCategory: "Categoria do produto",
            productBrand:    "Marca do produto",
            productImage:    "Endereço da imagem do produto"
        });
</script>
```

### Página de Carrinho de Compras
```
<script type="text/javascript" src="https://api.datatrail.com.br/sdk/tracker.min.js"></script>
<script>
    var products = [];
    
    products.push({
        productId:    "Id do produto",
        productPrice: "Preço do produto",
        quantity:     Quantidade do produto
    });            

    tracker
        .onProfile('Código da conta')            
        .onCart(products);
</script>     
```

### Página de Checkout ou Resumo do Pedido
```
<script type="text/javascript" src="https://api.datatrail.com.br/sdk/tracker.min.js"></script>
<script>
    var products = [];
    
    products.push({
        productId: "Id do produto",
        productPrice: "Preço do produto",
        quantity: Quantidade do produto            
    });           

    tracker
        .onProfile('Código da conta')
        .onCheckout(products);
</script>  
```
### Página de Confirmação do Pedido
```
<script type="text/javascript" src="https://api.datatrail.com.br/sdk/tracker.min.js"></script>
<script>
    tracker
        .onProfile('Código da conta')
        .onConfirmation({orderId: Id do pedido});
</script>
```

| Propriedade     | Tipo / Formato    | Descrição                                     | 
| -----------     | -----------       | -----                                         | 
| productId       | String            |                                               |
| productName     | String            |                                               |
| productPrice    | Decimal           | Utilizar o formato "1.99"                     |
| productCategory | String            | Para inserir multiplas categorias utilizar "\|" como separador, por exemplo: "Categotia 1 \| Categoria 2 \| Categoria 3"                                                                                                   |
| productBrand    | String            | Idem ao productCategory                       |
| productImage    | String            | https://urldaimagem.com.br/imagem.jpg         |
| quantity        | Integer           | Quantidade de produto no carrinho ou checkout |
| orderId         | Integer           | Id do pedido na tela de confirmação da compra |

## Automática

### Deverá colocar o script abaixo, em cada sessão do site, igualmente descrito no formato de integração manual; Por exemplo: Página de Login, Carrinho de Compras, Checkout etc.
```
<script type="text/javascript" src="https://api.datatrail.com.br/sdk/tracker.min.js"></script>
<script>
    tracker
        .onProfile('Código da conta')
        .auto();
</script>
```
