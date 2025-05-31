---

database-plugin: basic

---

```yaml:dbfolder
name: CA-db
description: Databse for All Current Affairs
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
    position: 1
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
      wrap_content: true
  Topic:
    input: tags
    accessorKey: Topic
    key: Topic
    id: Topic
    label: Topic
    position: 3
    skipPersist: false
    isHidden: false
    sortIndex: -1
    options:
      - { label: "AI", value: "AI", color: "hsl(26, 95%, 90%)"}
      - { label: "Places in News", value: "Places in News", color: "hsl(281, 95%, 90%)"}
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
  Syllabus_Link:
    input: text
    accessorKey: Syllabus_Link
    key: Syllabus_Link
    id: Syllabus_Link
    label: Syllabus Link
    position: 4
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
  Relevance:
    input: tags
    accessorKey: Relevance
    key: Relevance
    id: Relevance
    label: Relevance
    position: 100
    skipPersist: false
    isHidden: false
    sortIndex: -1
    options:
      - { label: "Optional", value: "Optional", color: "hsl(263, 95%, 90%)"}
      - { label: "GS1", value: "GS1", color: "hsl(308, 95%, 90%)"}
      - { label: "GS2", value: "GS2", color: "hsl(204, 95%, 90%)"}
      - { label: "GS3", value: "GS3", color: "hsl(189, 95%, 90%)"}
      - { label: "GS4", value: "GS4", color: "hsl(96, 95%, 90%)"}
      - { label: "ESSAY", value: "ESSAY", color: "hsl(317, 95%, 90%)"}
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
  cell_size: wide
  sticky_first_column: true
  group_folder_column: 
  remove_empty_folders: true
  automatically_group_files: true
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
  row_templates_folder: Obsidian-files/Templates
  current_row_template: 
  pagination_size: 10
  font_size: 10
  enable_js_formulas: false
  formula_folder_path: /
  inline_default: false
  inline_new_position: top
  date_format: yyyy-MM-dd
  datetime_format: "yyyy-MM-dd HH:mm:ss"
  metadata_date_format: "yyyy-MM-dd HH:mm:ss"
  enable_footer: true
  implementation: default
filters:
  enabled: false
  conditions:
```