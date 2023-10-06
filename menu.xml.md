# Menu

## menu new structure
```xml
    <menuitem id="scp_menu_main"
        name="Supply Chain"
        web_icon="doh3_scp,static/description/scp.svg"
        active="True"
        sequence="30">
        <menuitem id="scp_campaign_menu"
            name="💌 Campaign"
            sequence="10"
            action="sale_campaign_action"
        />
        <menuitem id="scp_campaign_move_menu"
            name="💸 Campaign Moves"
            sequence="15"
            action="sale_campaign_move_action"
        />
    </menuitem>
```
