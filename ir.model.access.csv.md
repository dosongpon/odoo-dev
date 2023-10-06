# security models

id,name,model_id:id,group_id:id,perm_read,perm_write,perm_create,perm_unlink
access_sale_campaign,access_sale_campaign,model_sale_campaign,base.group_user,1,1,1,1

id : unique xml_id
name: description of access

| name  | description |
| ------------- | ------------- |
| id      | unique_xml_id     |
| name      | description     |
| model_id:id      | xml_id of model (sale.order > model_sale_order)     |
|group_id:id| xml_id of group |
|perm_read,perm_write,perm_create,perm_unlink| permission yes = 1, no=0 |