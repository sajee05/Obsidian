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
    width: 133
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: true
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      wrap_content: true
  Where_to_use:
    input: tags
    accessorKey: Where_to_use
    key: Where_to_use
    id: Where_to_use
    label: Where to use
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 151
    options:
      - { label: "Challenges / Issues", value: "Challenges / Issues", color: "hsl(312, 95%, 90%)"}
      - { label: "fodder points", value: "fodder points", color: "hsl(128, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      option_source: manual
      wrap_content: true
  Subjects:
    input: tags
    accessorKey: Subjects
    key: Subjects
    id: Subjects
    label: Subjects
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 147
    options:
      - { label: "ALL", value: "ALL", color: "hsl(291, 95%, 90%)"}
      - { label: "S&T", value: "S&T", color: "hsl(342, 95%, 90%)"}
      - { label: "GS3", value: "GS3", color: "hsl(335, 95%, 90%)"}
      - { label: "Sociology", value: "Sociology", color: "hsl(292, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      option_source: manual
      wrap_content: true
  What:
    input: tags
    accessorKey: What
    key: What
    id: What
    label: Type
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 151
    options:
      - { label: "Framework", value: "Framework", color: "hsl(245, 95%, 90%)"}
      - { label: "Current Affairs", value: "Current Affairs", color: "hsl(77, 95%, 90%)"}
      - { label: "fodder", value: "fodder", color: "hsl(352, 95%, 90%)"}
      - { label: "data", value: "data", color: "hsl(70, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      option_source: manual
      wrap_content: true
  Topic:
    input: tags
    accessorKey: Topic
    key: Topic
    id: Topic
    label: Topic
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    options:
      - { label: "AI", value: "AI", color: "hsl(60, 95%, 90%)"}
      - { label: "Urbanisation", value: "Urbanisation", color: "hsl(186, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      option_source: manual
      wrap_content: true
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