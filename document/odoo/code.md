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
        - <sub> When you use _inherit and add new fields, those fields will be added inside inherited object. No other table will be created in database </sub>
        <sub>For example I want to add one or more field(s) or I want to add/override method in sale.order then I will use:</sub>

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

