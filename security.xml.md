# Security and groups

```xml
<?xml version="1.0" encoding="utf-8"?>
<odoo>
    <record id="doh3_scp.module_category_root_scp" model="ir.module.category">
        <field name="name">SCP</field>
        <field name="sequence">30</field>
    </record>

    <record id="doh3_scp.user" model="res.groups">
        <field name="name">User</field>
        <field name="category_id" ref="doh3_scp.module_category_root_scp"/>
        <field name="implied_ids" eval="[(4, ref('base.group_user'))]"/>
    </record>

    <record id="doh3_scp.manger" model="res.groups">
        <field name="name">Manager</field>
        <field name="category_id" ref="doh3_scp.module_category_root_scp"/>
        <field name="implied_ids" eval="[(4, ref('doh3_scp.user'))]"/>
    </record>

</odoo>
```