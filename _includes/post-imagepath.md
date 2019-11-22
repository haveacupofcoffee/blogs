{%- assign page_dir = page.date | date: "%Y-%m-%d" -%}
{%- assign images_files = site.static_files | where: "image", true | where_exp:"item","item.path contains page_dir" -%}
{%- assign all_images_path = "" -%}
{%- for image in images_files -%}
  {%- assign relative_image_path = image.path | relative_url  -%}
  {%- assign all_images_path = all_images_path | append: relative_image_path | append: "," -%}
{%- endfor -%}

{%- assign images = all_images_path | split: "," -%}
