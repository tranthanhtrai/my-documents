# This's document about code which is need to remember
## Default_get in odoo
### Default_get là hàm default dữ liệu cho 1 field bất kỳ nào đó. 

    @api.model
    def default_get(self, fields):
        vals = super().default_get(fields)
