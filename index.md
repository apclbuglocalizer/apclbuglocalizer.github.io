---
title: Home
layout: home
nav_order: 1
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---

# Welcome to CMIND
{: .fs-9 }

A bug localizer for memory bugs in C

{: .fs-6 .fw-300 }

<!--[Get started now](http://172.237.148.235/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }-->
<a href="http://172.237.148.235/" class="btn btn-primary fs-5 mb-4 mb-md-0 mr-2" target="_blank" rel="noopener noreferrer">
  Get started now
</a>
[View it on GitHub][MIND repo]{: .btn .fs-5 .mb-4 .mb-md-0 }

---

<!-- {: .warning }
> This website documents the features of the current `main` branch of the Just the Docs theme. See [the CHANGELOG]({% link CHANGELOG.md %}) for a list of releases, new features, and bug fixes. -->

CMIND stands for C Memory Bug Inspection based on Neural Deduction and is developed by [apcl-research](https://github.com/apcl-research) at [University of Notre Dame](https://cse.nd.edu/). It is specifically developed to localize memory bugs in C. CMIND is mainly tested on the ```o4-mini-2025-04-16``` and ```gpt-5-mini-2025-08-07``` models although you can change it to different models with cheaper/better options. You can refer to [Open AI](https://platform.openai.com/docs/models) for more information.

The author of CMIND is [Chia-Yi Su](https://chiayisu.github.io/) and [Collin McMillan](https://sdf.org/~cmc/). We are commited to keep CMIND open source. If you cannot find anything or have any question, please contact us. 

The video demonstration for [ICSE 2026](https://conf.researchr.org/track/icse-2026/icse-2026-demonstrations) is as follows.

## Key features

- **Human-like bug localizer**: Cmind is designed based on the human study from [Human Attention During Localization of Memory Bugs in C Programs](https://arxiv.org/abs/2506.00693).
- **Flexibility to submit bug report**: You can submit the bug report via our online website or deploy it in your local machines
- **Easy to retrieve results**: Cmind will return an ID after you submit the bug report. You can use this ID to submit bug report and source code  
- **Combined LLMs with guidance**: Cmind combines LLMs with guided decision making to avoid LLMs go off-track

## Citation
```bibte@article{su2025cmind,
  title     = {CMind: An AI Agent for Localizing C Memory Bugs},
  author    = {Chia-Yi Su and Collin McMillan},
  journal   = {xxx},
  volume    = {xxx},
  pages     = {xxx},
  year      = {2025}
}
```


## About the project

Just the Docs is &copy; 2025-{{ "now" | date: "%Y" }}.


### Contributing

When contributing to this repository, please first discuss the change you wish to make via issue,
email, or any other method with the owners of this repository before making a change.

<!--
#### Thank you to the contributors of Just the Docs!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"></a>
  </li>
{% endfor %}
</ul>
-->

[Jekyll]: https://jekyllrb.com
[Markdown]: https://daringfireball.net/projects/markdown/
[Liquid]: https://github.com/Shopify/liquid/wiki
[Front matter]: https://jekyllrb.com/docs/front-matter/
[Jekyll configuration]: https://jekyllrb.com/docs/configuration/
[source file for this page]: https://github.com/just-the-docs/just-the-docs/blob/main/index.md
[Just the Docs Template]: https://just-the-docs.github.io/just-the-docs-template/
[Just the Docs]: https://just-the-docs.com
[MIND repo]: https://github.com/apcl-research/CMIND
[Just the Docs README]: https://github.com/just-the-docs/just-the-docs/blob/main/README.md
[GitHub Pages]: https://pages.github.com/
[Template README]: https://github.com/just-the-docs/just-the-docs-template/blob/main/README.md
[GitHub Pages / Actions workflow]: https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/
[use the template]: https://github.com/just-the-docs/just-the-docs-template/generate
