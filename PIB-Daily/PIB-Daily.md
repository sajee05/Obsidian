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
    width: 79
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
  imp:
    input: tags
    accessorKey: imp
    key: imp
    id: imp
    label: relevance
    position: 2
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 55
    options:
      - { label: "mains-fact", value: "mains-fact", color: "hsl(265, 95%, 90%)"}
      - { label: "imp-pre", value: "imp-pre", color: "hsl(80, 95%, 90%)"}
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
  date:
    input: calendar
    accessorKey: date
    key: date
    id: date
    label: date
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
    width: 238
    options:
      - { label: "Polity and Governance", value: "Polity and Governance", color: "hsl(30, 95%, 90%)"}
      - { label: "International Relations", value: "International Relations", color: "hsl(119, 95%, 90%)"}
      - { label: "Social Justice", value: "Social Justice", color: "hsl(327, 95%, 90%)"}
      - { label: "History, art and culture", value: "History, art and culture", color: "hsl(222, 95%, 90%)"}
      - { label: "Geography", value: "Geography", color: "hsl(320, 95%, 90%)"}
      - { label: "Society and Social issues", value: "Society and Social issues", color: "hsl(336, 95%, 90%)"}
      - { label: "Environment and Ecology", value: "Environment and Ecology", color: "hsl(27, 95%, 90%)"}
      - { label: "Science and Tech", value: "Science and Tech", color: "hsl(336, 95%, 90%)"}
      - { label: "Disaster Management", value: "Disaster Management", color: "hsl(38, 95%, 90%)"}
      - { label: "Internal Security", value: "Internal Security", color: "hsl(344, 95%, 90%)"}
      - { label: "Economics", value: "Economics", color: "hsl(119, 95%, 90%)"}
      - { label: "Ethics", value: "Ethics", color: "hsl(42, 95%, 90%)"}
      - { label: "Ethics ", value: "Ethics ", color: "hsl(335, 95%, 90%)"}
      - { label: "Misc.", value: "Misc.", color: "hsl(109, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  content:
    input: text
    accessorKey: content
    key: content
    id: content
    label: Keypoints
    position: 8
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 318
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
      content_alignment: text-align-left
  difficulty:
    input: tags
    accessorKey: difficulty
    key: difficulty
    id: difficulty
    label: difficulty
    position: 3
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 26
    options:
      - { label: "easy", value: "easy", color: "hsl(298, 95%, 90%)"}
      - { label: "Hard", value: "Hard", color: "hsl(178, 95%, 90%)"}
      - { label: "Medium", value: "Medium", color: "hsl(339, 95%, 90%)"}
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
  Ministry:
    input: text
    accessorKey: Ministry
    key: Ministry
    id: Ministry
    label: Ministry
    position: 9
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
      wrap_content: true
  Place:
    input: text
    accessorKey: Place
    key: Place
    id: Place
    label: Place
    position: 10
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
      wrap_content: true
  Subtopic:
    input: tags
    accessorKey: Subtopic
    key: Subtopic
    id: date_1
    label: Main Topic
    position: 7
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 112
    options:
      - { label: "What is this article about in 1 word. (all small letters)", value: "What is this article about in 1 word. (all small letters)", color: "hsl(251, 95%, 90%)"}
      - { label: "SUBTOPIC", value: "SUBTOPIC", color: "hsl(282, 95%, 90%)"}
      - { label: "Infrastructure Development", value: "Infrastructure Development", color: "hsl(205, 95%, 90%)"}
      - { label: "Economic Growth", value: "Economic Growth", color: "hsl(4, 95%, 90%)"}
      - { label: "Sustainable Development", value: "Sustainable Development", color: "hsl(193, 95%, 90%)"}
      - { label: "Regional Connectivity", value: "Regional Connectivity", color: "hsl(119, 95%, 90%)"}
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