
## field one2many
for very simple

```xml
<field name="lines">
    <tree string="Insurances" editable="buttom">
        <field name="partner_id" />
        <field name="product_ids" widget="many2many_tags" />
    </tree>
</field>
```

## data range
```xml
<label for="date_start" string="Date"/>
<div class="o_row">
    <field name="date_start" widget="daterange" nolabel="1" class="oe_inline" options="{'related_end_date': 'date_end'}"/>
    <i class="fa fa-long-arrow-right mx-2" aria-label="Arrow icon" title="Arrow"/>
    <field name="date_end" widget="daterange" nolabel="1" class="oe_inline" options="{'related_start_date': 'date_start'}"/>
</div>
```