这个版本非常给力，只有一个bug
xadmin/plugins/importexport.py
需要把文件内48行改成：from import_export.admin import DEFAULT_FORMATS, ImportMixin
107行-117行修改成：
    def get_skip_admin_log(self):
        if self.skip_admin_log is None:
            return ImportMixin.skip_admin_log
        else:
            return self.skip_admin_log

    def get_tmp_storage_class(self):
        if self.tmp_storage_class is None:
            return ImportMixin.tmp_storage_class
        else:
            return self.tmp_storage_class
