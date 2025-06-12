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
    width: 240
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
    width: 286
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
      - { label: "Indian Civil Services", value: "Indian Civil Services", color: "hsl(135, 95%, 90%)"}
      - { label: "Administrative Reforms", value: "Administrative Reforms", color: "hsl(104, 95%, 90%)"}
      - { label: "Governance and Public Administration", value: "Governance and Public Administration", color: "hsl(322, 95%, 90%)"}
      - { label: "Parliament and State Legislatures", value: "Parliament and State Legislatures", color: "hsl(134, 95%, 90%)"}
      - { label: "Constitutional Posts", value: "Constitutional Posts", color: "hsl(213, 95%, 90%)"}
      - { label: "Prominent Indian Personalities", value: "Prominent Indian Personalities", color: "hsl(120, 95%, 90%)"}
      - { label: "Government policies and interventions", value: "Government policies and interventions", color: "hsl(244, 95%, 90%)"}
      - { label: "Welfare schemes for vulnerable sections", value: "Welfare schemes for vulnerable sections", color: "hsl(272, 95%, 90%)"}
      - { label: "Public service delivery", value: "Public service delivery", color: "hsl(202, 95%, 90%)"}
      - { label: "Economic Development", value: "Economic Development", color: "hsl(136, 95%, 90%)"}
      - { label: "Social Reformers", value: "Social Reformers", color: "hsl(74, 95%, 90%)"}
      - { label: "Cultural Heritage", value: "Cultural Heritage", color: "hsl(292, 95%, 90%)"}
      - { label: "Infrastructure", value: "Infrastructure", color: "hsl(54, 95%, 90%)"}
      - { label: "Indian Economy", value: "Indian Economy", color: "hsl(20, 95%, 90%)"}
      - { label: "Environmental Conservation", value: "Environmental Conservation", color: "hsl(249, 95%, 90%)"}
      - { label: "Electoral System and Process", value: "Electoral System and Process", color: "hsl(206, 95%, 90%)"}
      - { label: "International Cooperation", value: "International Cooperation", color: "hsl(281, 95%, 90%)"}
      - { label: "Agricultural Policies and Schemes", value: "Agricultural Policies and Schemes", color: "hsl(114, 95%, 90%)"}
      - { label: "Farmer Welfare Initiatives", value: "Farmer Welfare Initiatives", color: "hsl(214, 95%, 90%)"}
      - { label: "Sustainable Agriculture Practices", value: "Sustainable Agriculture Practices", color: "hsl(292, 95%, 90%)"}
      - { label: "Agriculture", value: "Agriculture", color: "hsl(181, 95%, 90%)"}
      - { label: "Rural development", value: "Rural development", color: "hsl(224, 95%, 90%)"}
      - { label: "Indian Economy and issues relating to growth and employment", value: "Indian Economy and issues relating to growth and employment", color: "hsl(122, 95%, 90%)"}
      - { label: "Effects of liberalization on the economy", value: "Effects of liberalization on the economy", color: "hsl(89, 95%, 90%)"}
      - { label: "changes in industrial policy", value: "changes in industrial policy", color: "hsl(293, 95%, 90%)"}
      - { label: "International trade agreements", value: "International trade agreements", color: "hsl(172, 95%, 90%)"}
      - { label: "Bilateral relations", value: "Bilateral relations", color: "hsl(77, 95%, 90%)"}
      - { label: "Foreign direct investment", value: "Foreign direct investment", color: "hsl(76, 95%, 90%)"}
      - { label: "Economic diplomacy", value: "Economic diplomacy", color: "hsl(110, 95%, 90%)"}
      - { label: "Fiscal Policy", value: "Fiscal Policy", color: "hsl(353, 95%, 90%)"}
      - { label: "Inflation Management", value: "Inflation Management", color: "hsl(237, 95%, 90%)"}
      - { label: "Consumer Protection", value: "Consumer Protection", color: "hsl(194, 95%, 90%)"}
      - { label: "Trade Policy", value: "Trade Policy", color: "hsl(296, 95%, 90%)"}
      - { label: "Maritime Security", value: "Maritime Security", color: "hsl(157, 95%, 90%)"}
      - { label: "Disaster Management", value: "Disaster Management", color: "hsl(39, 95%, 90%)"}
      - { label: "Marine Pollution", value: "Marine Pollution", color: "hsl(24, 95%, 90%)"}
      - { label: "Exclusive Economic Zone", value: "Exclusive Economic Zone", color: "hsl(160, 95%, 90%)"}
      - { label: "National Cadet Corps (NCC)", value: "National Cadet Corps (NCC)", color: "hsl(293, 95%, 90%)"}
      - { label: "Youth Development", value: "Youth Development", color: "hsl(262, 95%, 90%)"}
      - { label: "Government Initiatives", value: "Government Initiatives", color: "hsl(339, 95%, 90%)"}
      - { label: "Adventure Sports", value: "Adventure Sports", color: "hsl(161, 95%, 90%)"}
      - { label: "India and its neighbourhood relations", value: "India and its neighbourhood relations", color: "hsl(141, 95%, 90%)"}
      - { label: "Bilateral defence cooperation", value: "Bilateral defence cooperation", color: "hsl(325, 95%, 90%)"}
      - { label: "Regional security issues", value: "Regional security issues", color: "hsl(110, 95%, 90%)"}
      - { label: "Military diplomacy", value: "Military diplomacy", color: "hsl(127, 95%, 90%)"}
      - { label: "Military Exercises", value: "Military Exercises", color: "hsl(139, 95%, 90%)"}
      - { label: "Peacekeeping Operations", value: "Peacekeeping Operations", color: "hsl(353, 95%, 90%)"}
      - { label: "International environmental agreements", value: "International environmental agreements", color: "hsl(175, 95%, 90%)"}
      - { label: "Blue Economy", value: "Blue Economy", color: "hsl(26, 95%, 90%)"}
      - { label: "Marine resource management", value: "Marine resource management", color: "hsl(174, 95%, 90%)"}
      - { label: "Fisheries Sector Development", value: "Fisheries Sector Development", color: "hsl(5, 95%, 90%)"}
      - { label: "Aquaculture Technologies", value: "Aquaculture Technologies", color: "hsl(25, 95%, 90%)"}
      - { label: "Rural Livelihoods", value: "Rural Livelihoods", color: "hsl(256, 95%, 90%)"}
      - { label: "Social security schemes", value: "Social security schemes", color: "hsl(252, 95%, 90%)"}
      - { label: "Labour welfare", value: "Labour welfare", color: "hsl(101, 95%, 90%)"}
      - { label: "Public healthcare", value: "Public healthcare", color: "hsl(104, 95%, 90%)"}
      - { label: "Labour Reforms and Social Security", value: "Labour Reforms and Social Security", color: "hsl(153, 95%, 90%)"}
      - { label: "Employment and Unemployment Trends", value: "Employment and Unemployment Trends", color: "hsl(84, 95%, 90%)"}
      - { label: "International Labour Organization (ILO)", value: "International Labour Organization (ILO)", color: "hsl(17, 95%, 90%)"}
      - { label: "Gig Economy", value: "Gig Economy", color: "hsl(42, 95%, 90%)"}
      - { label: "International organizations and agreements", value: "International organizations and agreements", color: "hsl(30, 95%, 90%)"}
      - { label: "Public Health Initiatives", value: "Public Health Initiatives", color: "hsl(132, 95%, 90%)"}
      - { label: "Community Welfare", value: "Community Welfare", color: "hsl(164, 95%, 90%)"}
      - { label: "Voluntary Organizations", value: "Voluntary Organizations", color: "hsl(190, 95%, 90%)"}
      - { label: "Civic Responsibility", value: "Civic Responsibility", color: "hsl(66, 95%, 90%)"}
      - { label: "Renewable Energy", value: "Renewable Energy", color: "hsl(26, 95%, 90%)"}
      - { label: "Green Financing", value: "Green Financing", color: "hsl(236, 95%, 90%)"}
      - { label: "Capital Markets", value: "Capital Markets", color: "hsl(121, 95%, 90%)"}
      - { label: "Public Sector Undertakings", value: "Public Sector Undertakings", color: "hsl(18, 95%, 90%)"}
      - { label: "Mechanisms for grievance redressal", value: "Mechanisms for grievance redressal", color: "hsl(71, 95%, 90%)"}
      - { label: "Digital India", value: "Digital India", color: "hsl(312, 95%, 90%)"}
      - { label: "E-governance", value: "E-governance", color: "hsl(198, 95%, 90%)"}
      - { label: "Public transport systems", value: "Public transport systems", color: "hsl(99, 95%, 90%)"}
      - { label: "Railway Infrastructure Development", value: "Railway Infrastructure Development", color: "hsl(111, 95%, 90%)"}
      - { label: "Sustainable Transportation", value: "Sustainable Transportation", color: "hsl(62, 95%, 90%)"}
      - { label: "PM-Gati Shakti", value: "PM-Gati Shakti", color: "hsl(310, 95%, 90%)"}
      - { label: "Union Public Service Commission (UPSC)", value: "Union Public Service Commission (UPSC)", color: "hsl(241, 95%, 90%)"}
      - { label: "Indian Forest Service (IFS) Examination", value: "Indian Forest Service (IFS) Examination", color: "hsl(67, 95%, 90%)"}
      - { label: "Civil Services (Preliminary) Examination", value: "Civil Services (Preliminary) Examination", color: "hsl(345, 95%, 90%)"}
      - { label: "Examination Process and Procedures", value: "Examination Process and Procedures", color: "hsl(258, 95%, 90%)"}
      - { label: "Public Administration", value: "Public Administration", color: "hsl(121, 95%, 90%)"}
      - { label: "Recruitment Process", value: "Recruitment Process", color: "hsl(61, 95%, 90%)"}
      - { label: "Government Examinations", value: "Government Examinations", color: "hsl(262, 95%, 90%)"}
      - { label: "Statutory bodies", value: "Statutory bodies", color: "hsl(115, 95%, 90%)"}
      - { label: "Anti-corruption institutions", value: "Anti-corruption institutions", color: "hsl(6, 95%, 90%)"}
      - { label: "Transparency and accountability mechanisms", value: "Transparency and accountability mechanisms", color: "hsl(171, 95%, 90%)"}
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