+++
title = "Testing Scenario Library Generation for Connected and Automated Vehicle Evaluation"

# Date first published.
date = "2018-11"

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Shuo Feng", "Haowei Sun"]

# Publication type.
# Legend:
# 0 = Uncategorized
# 1 = Conference proceedings
# 2 = Journal
# 3 = Work in progress
# 4 = Technical report
# 5 = Book
# 6 = Book chapter
publication_types = ["1"]

# Publication name and optional abbreviated version.
publication = "Transportation Research Board"
publication_short = "TRB"

# Abstract and optional shortened version.
abstract = ""
abstract_short = "Testing Scenario Library Generation"

# Featured image thumbnail (optional)
image_preview = ""

# Is this a selected publication? (true/false)
selected = true

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter the filename (excluding '.md') of your project file in `content/project/`.
#   E.g. `projects = ["deep-learning"]` references `content/project/deep-learning.md`.
projects = []

# Links (optional).
url_pdf = ""
url_preprint = ""
url_code = ""
url_dataset = ""
url_project = ""
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# url_custom = [{name = "Custom Link", url = "http://example.org"}]

# Does the content use math formatting?
math = true

# Does the content use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = ""
caption = ""

+++

Testing and evaluation is a critical step in the development and deployment of connected and automated vehicles (CAVs), and yet there are no systematic ways to generate testing scenarios for evaluating CAVs. The goal of this paper is to develop a general framework that can be used to construct a testing scenario library and evaluate CAVs with the library. To this end, four research problems are identified, and a unified framework is proposed. A hierarchical structure is designed to describe testing scenarios, namely functional scenarios, logical scenarios and specific scenarios. Functional and logical scenarios are identified by investigating the crash typologies from crash databases. A new concept named valuable region is proposed to determine specific scenarios, and a searching method based on optimization and seed-fill is formulated to find the valuable region. A CAV evaluation method using the generated library is proposed, which includes a ε-greedy sampling policy, augmented reality testing environment and index evaluation. Different from previous studies that only focus on evaluating safety, a new index named functionality is proposed to evaluate the efficiency of a CAV in completing different driving tasks. Two case studies are presented to validate the proposed framework and provide guidelines for implementation.