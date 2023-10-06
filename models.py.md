

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
