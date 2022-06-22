# This's document about code which is need to remember
## Default_get in odoo
Default_get là hàm default dữ liệu cho 1 field bất kỳ nào đó. 

    @api.model
    def default_get(self, fields):
        vals = super().default_get(fields)

## Action print report
self.env.ref để truy cập tới xml.id.action của report và lưu ý là modelname.aml.id.action
report_action(self) là hàm có sẵn của odoo và overrite
    
    `def print_so_report(self):
        return self.env.ref('sale.action_report_saleorder').report_action(self)`
