# Security and groups

category can get from list
https://github.com/odoo/odoo/blob/16.0/odoo/addons/base/data/ir_module_category_data.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<odoo>

    <!-- Using cagtegory -->
    <record id="module_category_root_scp" model="ir.module.category">
        <field name="name">SCP</field>
        <field name="sequence">40</field>
        <field name="parent_id" ref="module_category_root_h3"/>

    </record>

    <record id="doh3_scp.user" model="res.groups">
        <field name="name">User</field>
        <field name="category_id" ref="module_category_root_scp"/>
        <field name="implied_ids" eval="[(4, ref('base.group_user'))]"/>
    </record>

    <record id="doh3_scp.manger" model="res.groups">
        <field name="name">Manager</field>
        <field name="category_id" ref="module_category_root_scp"/>
        <field name="implied_ids" eval="[(4, ref('doh3_scp.user'))]"/>
    </record>

</odoo>
```