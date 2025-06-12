---

database-plugin: basic

---

```yaml:dbfolder
name: new database
description: new description
columns:
  __file__:
    key: __file__
    id: __file__
    input: markdown
    label: File
    accessorKey: __file__
    isMetadata: true
    skipPersist: false
    isDragDisabled: false
    csvCandidate: true
    position: 0
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: true
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Option_1:
    input: text
    accessorKey: Option_1
    key: Option_1
    id: Option_1
    label: Option_1
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Option_2:
    input: text
    accessorKey: Option_2
    key: Option_2
    id: Option_2
    label: Option_2
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Option_3:
    input: text
    accessorKey: Option_3
    key: Option_3
    id: Option_3
    label: Option_3
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Option_4:
    input: text
    accessorKey: Option_4
    key: Option_4
    id: Option_4
    label: Option_4
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Answer:
    input: text
    accessorKey: Answer
    key: Answer
    id: Answer
    label: Answer
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Standard_Explanation_+_Tikdams:
    input: text
    accessorKey: Standard_Explanation_+_Tikdams
    key: Standard_Explanation_+_Tikdams
    id: Standard_Explanation_+_Tikdams
    label: Standard Explanation + Tikdams
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Subject:
    input: tags
    accessorKey: Subject
    key: Subject
    id: Subject
    label: Subject
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    options:
      - { label: "test", value: "test", color: "hsl(47, 95%, 90%)"}
      - { label: "(subject tag will come here)", value: "(subject tag will come here)", color: "hsl(295, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Year:
    input: tags
    accessorKey: Year
    key: Year
    id: Year
    label: Year
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    options:
      - { label: "test", value: "test", color: "hsl(77, 95%, 90%)"}
      - { label: "(year-tag will come here}", value: "(year-tag will come here}", color: "hsl(185, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  microtheme:
    input: tags
    accessorKey: microtheme
    key: microtheme
    id: microtheme
    label: microtheme
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    options:
      - { label: "microtheme tag will come here", value: "microtheme tag will come here", color: "hsl(323, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
config:
  remove_field_when_delete_column: false
  cell_size: normal
  sticky_first_column: false
  group_folder_column: 
  remove_empty_folders: false
  automatically_group_files: false
  hoist_files_with_empty_attributes: true
  show_metadata_created: false
  show_metadata_modified: false
  show_metadata_tasks: false
  show_metadata_inlinks: false
  show_metadata_outlinks: false
  show_metadata_tags: false
  source_data: current_folder
  source_form_result: 
  source_destination_path: /
  row_templates_folder: /
  current_row_template: 
  pagination_size: 10
  font_size: 16
  enable_js_formulas: false
  formula_folder_path: /
  inline_default: false
  inline_new_position: last_field
  date_format: yyyy-MM-dd
  datetime_format: "yyyy-MM-dd HH:mm:ss"
  metadata_date_format: "yyyy-MM-dd HH:mm:ss"
  enable_footer: false
  implementation: default
filters:
  enabled: false
  conditions:
```