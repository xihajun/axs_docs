[![!CyVerse Learning Center](assets/logos/krai_logo.png "CyVerse Learning Center"){ width="400" }](https://krai.ai){target=_blank}

# Template usage
一个readthedoc简易模版，目标是同步bookdown做两个类似的网页，使用相同的内容，因为看见此模版可以直接使用markdown文件，感觉是可行的。

## How to use
如何使用：在`mkdocs.yml`文件里面，有

```{bash eval=false}
nav:
  - Home: 
    - 'Home': index.md #主页 其他的可以先不管
    - 'Before FOSS Starts': installation.md
    - 'Schedule': schedule.md
    - 'Code of Conduct': code_of_conduct.md
    - 'Glossary & Acronyms': glossary.md
  - Lessons:
    - '0. The Shell and Git': 00_basics.md
    - '1. Open Science': 01_intro_open_sci.md
    - '2. Project Management': 02_project_management.md
    - '3. Managing Data': 03_managing_data.md
    - '4. Documentation and Communication': 04_documentation_communication.md
    - '5. Version Control': 05_version_control.md
    - '6. Reproducibility I: Repeatability': 06_reproducibility_i.md
    - '7. Reproducibility II: Containers': 07_reproducibility_ii.md
  - Capstone Project:
      - 'Overview': final_project/overview.md
```

为了使`markdown`在bookdown和readthedoc都能运行，我这里就打算去掉文件夹里面的内容，或者加一个自动识别之后。

