
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
## simple div with condition
```xml
<label for="seats_limited" string="Limit Registrations"/>
<div>
    <field name="seats_limited"/>
    <span attrs="{'invisible': [('seats_limited', '=', False)], 'required': [('seats_limited', '=', False)]}">to <field name="seats_max" class="oe_inline o_input_9ch"/> Confirmed Attendees</span>
</div>
```
![Alt text](assets/field_div_bool_hide_show.gif)

## data range
```xml
<label for="date_start" string="Date"/>
<div class="o_row">
    <field name="date_start" widget="daterange" nolabel="1" class="oe_inline" options="{'related_end_date': 'date_end'}"/>
    <i class="fa fa-long-arrow-right mx-2" aria-label="Arrow icon" title="Arrow"/>
    <field name="date_end" widget="daterange" nolabel="1" class="oe_inline" options="{'related_start_date': 'date_start'}"/>
</div>
```
![](assets/widget_date_range.png)


## many2one with address

```xml
<field name="partner_id" widget="res_partner_many2one"
    context="{'res_partner_search_mode': 'customer', 'show_address': 1, 'show_vat': True}"
    options='{"always_reload": True}'/>
```
![](/assets/widget_res_partner_many2one.png)



## many2many_tags
support form/tree
```xml
<field name="product_ids" widget="many2many_tags" />
```
![Alt text](assets/widget_many2many_tags.png)


## widget radio for selection

```xml
 <field name="type" widget="radio"/>
```

## attrs hide and show 
can use in field,group,page
```xml
<field name="ins_driver_mode" widget="redio" />
<field name="ins_driver_one_name" 
    attrs="{'invisible': [('ins_driver_mode','=','specific')]}"/>
```


## groups access

```xml
<field name="company_id" groups="base.group_multi_company" optional="show" readonly="1"/>
<field name="company_id" groups="!base.group_multi_company" invisible="1"/>
```

## group arrange with 4 colums

```xml
<group>
    <group name="group_book_car" string="รายละเอียดการจองรถ">
        <field name="booking_id" />
        <field name="booking_date" />
        <field name="si_invoice_ref" />
        <field name="si_invoice_date" />
    </group>
    <group class="mt48">
        <field name="engine_no" />
        <field name="vehicle_id" />
        <field name="actual_delivery_date" />
    </group>
</group>
```
![Alt text](assets/form_group_4_col.png)


## tree column hide / invisible
 need field in period record
```xml
<field name="partner_id"
    optional="show"
    domain="['|', ('parent_id', '=', False), ('is_company', '=', True)]"
    attrs="{'column_invisible': [('parent.move_type', '!=', 'entry')]}"/>
```