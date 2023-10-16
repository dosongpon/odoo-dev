

## relation back to header
```python
    order_id = fields.Many2one(
        comodel_name='sale.order',
        string="Order Reference",
        required=True, ondelete='cascade', index=True, copy=False)
```

## many2one with domain

```python
partner_id = fields.Many2one('res.partner', string='Insurance',
                                 domain=[('industry_id.name', '=', 'INS')])
```
## many2many with domain and autogenerate table for m2m relation
if not provide **relation** args  odoo will auto generate table for relation 
```python
    product_ids = fields.Many2many('product.product',
                                   string='Models',
                                   domain=[('categ_id.name', '=', 'M')])
```

## one2many 
sale.order.line.order_id > m2o this table
```python
    order_line = fields.One2many(
        comodel_name='sale.order.line',
        inverse_name='order_id',
        string="Order Lines",
        copy=True, auto_join=True)
```

## selection
```python
    state = fields.Selection([
        ('draft', 'Draft'),
        ('in', 'Incoming'),
        ('ready', 'Ready'),
        ('sold', 'Sold'),
    ], string='Status', default='sold')
```

## group access in models field
example show field boolean which allow group to access

```python
is_need_gas = fields.Boolean('Need GAS',
                                 groups='doh3_pdi.group_user')
```

## allow search fields from many2one

**_rec_names_search**
given list of fields to combine in many2one search without create function name_search

```python
class pdi_claim_group(models.Model):
    _name = 'pdi.claim.group'
    _description = 'Claim Group'
    _rec_names_search = ['code', 'name']
```
