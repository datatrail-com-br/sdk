# Documentação de instalação da DataTrail SDK Tag

### Copie e cole no GTM o trecho de codigo a seguir e cole, no código html que apareça em todas as sessões do seu site. Por exemplo o cabeçalho

```
<script type="text/javascript" src="https://api.datatrail.com.br/sdk/tracker.min.js"></script>
```

### Login

```
<script>
    tracker
        .onProfile('Código da conta')        
        .onCustomer({email: "email do cliente"});
</script> 
```

### Para a captação dos dados de navegação em páginas de produtos, configure da seguinte forma

```
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

### Carrinho
```
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

### Checkout 
```
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
### Finalização do pedido
```
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
| productCategory | String            | Para inserir multiplas categorias utilizar "\|" como separador, por exemplo: "Categotia 1 \| Categoria 2 \| Categoria 3"                                                                                    |
| productBrand    | String            | Idem ao productCategory                       |
| productImage    | String            |                                               |
| quantity        | Integer           | Quantidade de produto no carrinho ou checkout |
| orderId         | Integer           | Id do pedido na tela de confirmação da compra |