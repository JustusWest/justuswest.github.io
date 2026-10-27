---
title: "PatchScout: Thematic Web Data Collection on the Live Web"
excerpt: "Many research questions call for a collection rather than an answer: every program, posting or policy matching a theme, scattered across thousands of independent websites. This project began with one such problem, finding every U.S. college that hosts an Autism Support Program (ASP), and grew into a general framework for thematic web data collection. It includes PatchScout (NeurIPS 2026), a multi-agent system that treats collection as long-horizon information foraging, and an interactive, human-in-the-loop collection system demonstrated at VLDB 2026.<br/><img src='/images/vldb-2026-poster.png' alt='VLDB 2026 demo poster' style='max-width: 300px;'>"
collection: portfolio
---

## Overview

Web agents and search tools are usually built to answer a question: they gather just enough evidence for one response and stop. Many real workflows need something different, a comprehensive collection of documents that share a theme but are scattered across heterogeneous, structurally disconnected regions of the web. University programs, municipal policy pages and job postings are all examples. I call this problem **thematic web data collection**, and this project develops methods and systems for it, motivated throughout by a concrete social science application.

## How the project developed

**Discovering autism support programs.** The project started with a practical need from an interdisciplinary NSF-funded team at Temple: there was no up-to-date, comprehensive list of which U.S. colleges host Autism Support Programs, what services they offer, or how students access them. I built an automated search, retrieval and classification pipeline to find these programs from college websites. It identified 49 schools hosting ASPs that past literature searches had missed, and our team used the results to characterize program admissions, cost, structure and supports ([JADD 2025](/publication/JADD2025)).

**Understanding how students find them.** To understand the human side of the problem, I interviewed 34 students, parents, counselors and staff about how autistic students discover, choose and experience these programs ([Frontiers in Education 2026](/publication/Frontiers2026)).

**Generalizing the problem: PatchScout.** Building the ASP dataset showed that existing tools fall short. Classical focused crawlers rely on fixed seeds and local traversal, while LLM-driven web agents stop once they have an answer. PatchScout formulates thematic collection as a budget-constrained information foraging problem over query-induced semantic patches, where the central decision is when to keep exploiting the current region of the web and when to re-seed into a new one. It uses three cooperating agents: a **Scout** that generates queries to open new patches, a **Forager** that explores links within the current patch and triggers re-seeding when it becomes unproductive, and a **Critic** that judges page relevance and feeds that signal back to the other two. On four live-web topics, PatchScout improves document yield, domain coverage and collection diversity over classical crawlers and deep-research agents. Applied back to the ASP setting, it discovered 102 previously unidentified entities ([NeurIPS 2026](/publication/NeurIPS2026)).

**Keeping a human in the loop.** The VLDB 2026 demonstration turns this architecture into an interactive system. A user describes a theme in natural language, optionally provides example pages, and then steers the collection as it runs by correcting relevance labels and writing guidance that the query, relevance and navigation agents absorb. Results stream back live and can be exported, paused and resumed ([VLDB 2026 demo](/publication/VLDB2026Demo)).

## VLDB 2026 demonstration poster

[![VLDB 2026 demonstration poster: A Demo of Interactive Thematic Data Collection on the Live Web](/images/vldb-2026-poster.png)](/files/vldb_poster_A1_west_v7.pdf)

*Click the poster to open the full-resolution PDF.*

## Code

Code and artifacts are available at [github.com/JustusWest/Web-Data-Discovery](https://github.com/JustusWest/Web-Data-Discovery).

## Publications

West, M., & Dragut, E. (2026). PatchScout: Thematic Web Data Collection via Information Foraging. In *Advances in Neural Information Processing Systems (NeurIPS)*. To appear. [[link]](/publication/NeurIPS2026)

West, M., & Dragut, E. (2026). A Demo of Interactive Thematic Data Collection on the Live Web. *Proceedings of the VLDB Endowment*, 19(12), 4554-4557. [[link]](/publication/VLDB2026Demo)

West, M., Kostin, K., Tincani, M., Hantula, D., & Dragut, E. (2026). Evaluating Autism Support Programs in Higher Education Through the Perspectives of Students, Parents, Counselors and Staff. *Frontiers in Education*, 11, 1921007. [[link]](/publication/Frontiers2026)

West, M., Tincani, M., Hantula, D., Hong, S. R., Vucetic, S., & Dragut, E. (2025). Applying Data Science Practices to Identify Characteristics of Postsecondary Autism Support Programs From Their Websites. *Journal of Autism and Developmental Disorders*, 1-47. [[link]](/publication/JADD2025)

*This work was supported in part by the U.S. National Science Foundation awards III-2107213, 2026513, and ITE-2333789.*
