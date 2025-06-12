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
      - { label: "Civil Services Reforms", value: "Civil Services Reforms", color: "hsl(136, 95%, 90%)"}
      - { label: "Capacity Building", value: "Capacity Building", color: "hsl(138, 95%, 90%)"}
      - { label: "Good Governance", value: "Good Governance", color: "hsl(52, 95%, 90%)"}
      - { label: "National Development Programs", value: "National Development Programs", color: "hsl(35, 95%, 90%)"}
      - { label: "Constitutional Bodies", value: "Constitutional Bodies", color: "hsl(344, 95%, 90%)"}
      - { label: "Parliament of India", value: "Parliament of India", color: "hsl(331, 95%, 90%)"}
      - { label: "Indian Judiciary", value: "Indian Judiciary", color: "hsl(292, 95%, 90%)"}
      - { label: "Prominent Personalities", value: "Prominent Personalities", color: "hsl(61, 95%, 90%)"}
      - { label: "Government Policies and Interventions", value: "Government Policies and Interventions", color: "hsl(64, 95%, 90%)"}
      - { label: "Welfare Schemes", value: "Welfare Schemes", color: "hsl(220, 95%, 90%)"}
      - { label: "Inclusive Growth", value: "Inclusive Growth", color: "hsl(296, 95%, 90%)"}
      - { label: "National Development", value: "National Development", color: "hsl(338, 95%, 90%)"}
      - { label: "Government Policies", value: "Government Policies", color: "hsl(344, 95%, 90%)"}
      - { label: "Social Empowerment", value: "Social Empowerment", color: "hsl(52, 95%, 90%)"}
      - { label: "Bhakti Movement", value: "Bhakti Movement", color: "hsl(7, 95%, 90%)"}
      - { label: "Indian Philosophy", value: "Indian Philosophy", color: "hsl(338, 95%, 90%)"}
      - { label: "Social Reform Movements", value: "Social Reform Movements", color: "hsl(12, 95%, 90%)"}
      - { label: "Indian Society", value: "Indian Society", color: "hsl(329, 95%, 90%)"}
      - { label: "Economic Growth and Development", value: "Economic Growth and Development", color: "hsl(9, 95%, 90%)"}
      - { label: "Government Policies and Initiatives", value: "Government Policies and Initiatives", color: "hsl(308, 95%, 90%)"}
      - { label: "Ease of Living", value: "Ease of Living", color: "hsl(19, 95%, 90%)"}
      - { label: "Climate Change Mitigation", value: "Climate Change Mitigation", color: "hsl(342, 95%, 90%)"}
      - { label: "Government Schemes", value: "Government Schemes", color: "hsl(274, 95%, 90%)"}
      - { label: "Election Commission of India", value: "Election Commission of India", color: "hsl(338, 95%, 90%)"}
      - { label: "Electoral Reforms", value: "Electoral Reforms", color: "hsl(59, 95%, 90%)"}
      - { label: "International Organizations", value: "International Organizations", color: "hsl(49, 95%, 90%)"}
      - { label: "Electoral Process", value: "Electoral Process", color: "hsl(38, 95%, 90%)"}
      - { label: "Agricultural Policies", value: "Agricultural Policies", color: "hsl(247, 95%, 90%)"}
      - { label: "Farmer Welfare Schemes", value: "Farmer Welfare Schemes", color: "hsl(255, 95%, 90%)"}
      - { label: "Technological Interventions in Agriculture", value: "Technological Interventions in Agriculture", color: "hsl(300, 95%, 90%)"}
      - { label: "Sustainable Agriculture", value: "Sustainable Agriculture", color: "hsl(259, 95%, 90%)"}
      - { label: "Agricultural Schemes", value: "Agricultural Schemes", color: "hsl(121, 95%, 90%)"}
      - { label: "Farmer Welfare", value: "Farmer Welfare", color: "hsl(315, 95%, 90%)"}
      - { label: "Agricultural Research", value: "Agricultural Research", color: "hsl(153, 95%, 90%)"}
      - { label: "Indian Economy and issues relating to growth", value: "Indian Economy and issues relating to growth", color: "hsl(78, 95%, 90%)"}
      - { label: "development", value: "development", color: "hsl(132, 95%, 90%)"}
      - { label: "Government policies and interventions for development in various sectors", value: "Government policies and interventions for development in various sectors", color: "hsl(173, 95%, 90%)"}
      - { label: "Environmental pollution and degradation", value: "Environmental pollution and degradation", color: "hsl(227, 95%, 90%)"}
      - { label: "Trade and exports", value: "Trade and exports", color: "hsl(64, 95%, 90%)"}
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