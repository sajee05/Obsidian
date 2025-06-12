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
  article_link:
    input: tags
    accessorKey: article_link
    key: article_link
    id: article_link
    label: article_link
    position: 8
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 266
    options:
      - { label: "https://thebetterindia.com/stories/", value: "https://thebetterindia.com/stories/", color: "hsl(327, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      wrap_content: true
  content:
    input: text
    accessorKey: content
    key: content
    id: content
    label: content
    position: 2
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 316
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      wrap_content: true
  date:
    input: text
    accessorKey: date
    key: date
    id: date
    label: date
    position: 3
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
  subject:
    input: tags
    accessorKey: subject
    key: subject
    id: subject
    label: subject
    position: 5
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 177
    options:
      - { label: "Society and Social issues", value: "Society and Social issues", color: "hsl(175, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  source:
    input: tags
    accessorKey: source
    key: source
    id: source
    label: source
    position: 6
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 128
    options:
      - { label: "The Better India", value: "The Better India", color: "hsl(134, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Place:
    input: text
    accessorKey: Place
    key: Place
    id: Place
    label: Place
    position: 7
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
  Subtopic:
    input: tags
    accessorKey: Subtopic
    key: Subtopic
    id: Subtopic
    label: Subtopic
    position: 4
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 238
    options:
      - { label: "Sports and youth development,Individual achievements,Challenges in sports training,Grassroots sports", value: "Sports and youth development,Individual achievements,Challenges in sports training,Grassroots sports", color: "hsl(108, 95%, 90%)"}
      - { label: "Sports and youth development", value: "Sports and youth development", color: "hsl(301, 95%, 90%)"}
      - { label: "Individual achievements", value: "Individual achievements", color: "hsl(85, 95%, 90%)"}
      - { label: "Challenges in sports training", value: "Challenges in sports training", color: "hsl(74, 95%, 90%)"}
      - { label: "Grassroots sports", value: "Grassroots sports", color: "hsl(103, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      wrap_content: true
      option_source: manual
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