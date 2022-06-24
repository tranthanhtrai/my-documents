# This's document about code which is need to remember
## Default_get in odoo
Default_get là hàm default dữ liệu cho 1 field bất kỳ nào đó. 

    @api.model
    def default_get(self, fields):
        vals = super().default_get(fields)

## Action print report
self.env.ref để truy cập tới xml.id.action của report và lưu ý là modelname.aml.id.action
report_action(self) là hàm có sẵn của odoo và overwrite
    
    def print_so_report(self):
        return self.env.ref('sale.action_report_saleorder').report_action(self)
## Inherit and Inherits
1. Inherit
-When you use _inherit and add new fields, those fields will be added inside inherited object. No other table will be created in database

-For example I want to add one or more field(s) or I want to add/override method in sale.order then I will use:

``` 
    class sale_order(osv.Model):
    _inherit = 'sale.order'
    _columns = {
        'my_field': fields.char('My New Field', size=50),
    }

    def my_new_method(self, cr, uid, ids, context=None):
        ...
        ...

```
2. Inherits
- If I want to use anything (fields or methods) of any object and I want to achieve multiple inheritance, then I will use _inherits which allows you to use features of any object. That means you can directly use fields and methods of inherited object.

- When you use _inherits and new table is created in database. That will have your own fields and field ID of inherited object.

For example in hr.employee object resource.resource object is inherited. So you can see fields of hr.employee object and resource_id of resource.resource object.

Now lets talk about code you want to know.
```
def unlink(self, cr, uid, ids, context=None):
          resource_ids = []
          for employee in self.browse(cr, uid, ids, context=context):
          resource_ids.append(employee.resource_id.id)
           return self.pool.get('resource.resource').unlink(cr, uid, resource_ids, context=context)
```
This method will be called when I will delete any employee record.

When any employee record is deleted, resource record related to employee will also be deleted.
