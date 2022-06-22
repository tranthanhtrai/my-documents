# This's document about code which is need to remember
## Default_get in odoo
    @api.model
    def default_get(self, fields):
        vals = super().default_get(fields)
