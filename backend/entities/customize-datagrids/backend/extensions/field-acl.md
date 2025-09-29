<a id="customize-datagrids-extensions-acl"></a>

# Field ACL Extension

<a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/DataGridBundle/Extension/FieldAcl/FieldAclExtension.php" target="_blank">Field ACL extension</a> allows to check access to grid columns. Currently it is implemented only for the ORM datasource.

To enable field ACL protection for a column, use the `field_acl` section in a datagrid declaration:

```none
fields_acl:                     #section name
    columns:
         name:                  #column name
            data_name: a.name   #the path to a field which ACL should be used to protect the column
```

Please note that now only fields from the root entity of a datagrid’s ORM query are supported.

<!-- Frontend -->
