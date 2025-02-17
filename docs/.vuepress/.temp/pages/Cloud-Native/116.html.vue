<template><div><h1 id="_116-openim-component-base" tabindex="-1"><a class="header-anchor" href="#_116-openim-component-base" aria-hidden="true">#</a> 116: OpenIM Component-Base</h1>
<p>[toc]</p>
<h1 id="openim-component-base" tabindex="-1"><a class="header-anchor" href="#openim-component-base" aria-hidden="true">#</a> OpenIM Component-Base</h1>
<p>Implement OpenIM RPC Proposal 32: https://github.com/OpenIMSDK/community/edit/main/RFC/0006-openim-component-base.md</p>
<p>Welcome to the OpenIM Component-Base repository. This repository hosts a collection of shared tools and utilities dedicated to strengthening the modular and scalable nature of the OpenIM project ecosystem.</p>
<h2 id="table-of-contents" tabindex="-1"><a class="header-anchor" href="#table-of-contents" aria-hidden="true">#</a> Table of Contents</h2>
<ol>
<li><a href="#introduction">Introduction</a></li>
<li><a href="#motivation">Motivation</a></li>
<li><a href="#getting-started">Getting Started</a></li>
<li><a href="#components">Components</a></li>
<li><a href="#contribution">Contribution</a></li>
<li><a href="#prior-art">Prior Art</a></li>
<li><a href="#license">License</a></li>
</ol>
<h2 id="introduction" tabindex="-1"><a class="header-anchor" href="#introduction" aria-hidden="true">#</a> Introduction</h2>
<p>OpenIM strives to offer a potent, streamlined, and expansive instant messaging solution. To ensure a cohesive yet modular architecture, common components are housed in this repository. This structure not only delineates clear boundaries but also facilitates the reuse of components across diverse OpenIM projects.</p>
<h2 id="motivation" tabindex="-1"><a class="header-anchor" href="#motivation" aria-hidden="true">#</a> Motivation</h2>
<p>In our journey to optimize and expand the OpenIM project, we discerned overlapping tools and utilities across repositories like chat, core, and server. To streamline dependencies and enhance reusability, the <code v-pre>component-base</code> repository was conceived, inspired by best practices from projects like Kubernetes.</p>
<h2 id="getting-started" tabindex="-1"><a class="header-anchor" href="#getting-started" aria-hidden="true">#</a> Getting Started</h2>
<p>To integrate any component from this repository:</p>
<ol>
<li>Clone the repository:</li>
</ol>
<div class="language-bash ext-sh line-numbers-mode"><pre v-pre class="language-bash"><code>   <span class="token function">git</span> clone https://github.com/OpenIM/component-base.git
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div></div></div><ol>
<li>Delve into the chosen component's directory.</li>
<li>Adhere to the designated README or documentation pertinent to that component.</li>
</ol>
<h2 id="components" tabindex="-1"><a class="header-anchor" href="#components" aria-hidden="true">#</a> Components</h2>
<p>[Mention primary components with succinct descriptions. For instance:]</p>
<ul>
<li><strong>ComponentConfig</strong>: Streamlines flag and command handling for better user interaction. <a href="/path-to-componentConfig-readme">More Details</a></li>
<li><strong>HTTPSUtility</strong>: Ensures secure HTTPS serving. <a href="/path-to-httpsUtility-readme">More Details</a></li>
<li><strong>AuthDelegate</strong>: Manages delegated authentication and authorization. <a href="/path-to-authDelegate-readme">More Details</a></li>
<li><strong>LogManager</strong>: Provides uniform logging functionalities across projects. <a href="/path-to-logManager-readme">More Details</a></li>
</ul>
<p>(Elaborate on this index with the inclusion of new components.)</p>
<h2 id="contribution" tabindex="-1"><a class="header-anchor" href="#contribution" aria-hidden="true">#</a> Contribution</h2>
<p>Our doors are always open to community contributions. If the idea of enhancing OpenIM resonates with you, do peruse our <a href="/path-to-contribution-guide">contribution guidelines</a> and embark on this collaborative voyage!</p>
<h2 id="prior-art" tabindex="-1"><a class="header-anchor" href="#prior-art" aria-hidden="true">#</a> Prior Art</h2>
<p>Our inspiration draws from Kubernetes's <code v-pre>component-base</code> repository, which embodies a consolidated platform for components, encouraging shared utilities and consistent configurations.</p>
<h2 id="license" tabindex="-1"><a class="header-anchor" href="#license" aria-hidden="true">#</a> License</h2>
<p>Embarking on a project with OpenIM Component-Base implies agreement with our <a href="/path-to-license-file">MIT License</a>. For an exhaustive understanding, we recommend perusing the LICENSE file.</p>
<h1 id="proposal" tabindex="-1"><a class="header-anchor" href="#proposal" aria-hidden="true">#</a> Proposal</h1>
<h1 id="rfc-0001-introduction-of-component-base-repository" tabindex="-1"><a class="header-anchor" href="#rfc-0001-introduction-of-component-base-repository" aria-hidden="true">#</a> [RFC #0001] Introduction of <code v-pre>component-base</code> Repository</h1>
<!--  🤖 design template: https://github.com/OpenIMSDK/community/blob/main/0000-template.md  ⚠️ After design completion, please submit a PR to https://github.com/OpenIMSDK/community/tree/main/RFC according to the specification. -->
<h2 id="meta" tabindex="-1"><a class="header-anchor" href="#meta" aria-hidden="true">#</a> Meta</h2>
<ul>
<li>Name: Introduction of <code v-pre>component-base</code> Repository</li>
<li>Start Date: 2023-08-25</li>
<li>Author(s): @cubxxw</li>
<li>Status: Draft</li>
<li>RFC Pull Request: (leave blank)</li>
<li>OpenIMSDK Pull Request: (leave blank)</li>
<li>OpenIMSDK Issue: (leave blank)</li>
<li>Supersedes: N/A</li>
</ul>
<h2 id="📇topics" tabindex="-1"><a class="header-anchor" href="#📇topics" aria-hidden="true">#</a> 📇Topics</h2>
<ul>
<li><a href="#meta">Meta</a></li>
<li><a href="#summary">Summary</a></li>
<li><a href="#motivation">Motivation</a></li>
<li><a href="#what-it-is">What it is</a></li>
<li><a href="#how-it-works">How it Works</a></li>
<li><a href="#migration">Migration</a></li>
<li><a href="#drawbacks">Drawbacks</a></li>
<li><a href="#alternatives">Alternatives</a></li>
<li><a href="#prior-art">Prior Art</a></li>
<li><a href="#unresolved-questions">Unresolved Questions</a></li>
<li><a href="#spec-changes-optional">Spec. Changes (OPTIONAL)</a></li>
<li><a href="#history">History</a></li>
</ul>
<h2 id="summary" tabindex="-1"><a class="header-anchor" href="#summary" aria-hidden="true">#</a> Summary</h2>
<p>Proposal to introduce the <code v-pre>component-base</code> repository, a centralized hub to house common tools and shared code, aimed to enhance code reusability and component coherence, inspired by Kubernetes's <code v-pre>component-base</code>.</p>
<h2 id="motivation-1" tabindex="-1"><a class="header-anchor" href="#motivation-1" aria-hidden="true">#</a> Motivation</h2>
<ul>
<li>Current repositories like chat, core, and server share multiple common tools, but dependencies aren't clearly isolated.</li>
<li>A clear, independent repository helps external contributors or platforms to leverage OpenIMSDK's tools effortlessly.</li>
<li>Achieve similar component structure like Kubernetes to maintain a modular and scalable codebase.</li>
</ul>
<h2 id="what-it-is" tabindex="-1"><a class="header-anchor" href="#what-it-is" aria-hidden="true">#</a> What it is</h2>
<p><code v-pre>component-base</code> is a repository designed to contain shared tools and utilities used across OpenIMSDK projects. This will include, but isn't limited to:</p>
<ul>
<li>ComponentConfig implementations</li>
<li>Flag and command handling</li>
<li>HTTPS serving</li>
<li>Delegated authn/z</li>
<li>Logging.</li>
</ul>
<h2 id="how-it-works" tabindex="-1"><a class="header-anchor" href="#how-it-works" aria-hidden="true">#</a> How it Works</h2>
<p>Existing shared tools and code from repositories like chat, core, and server will be migrated to <code v-pre>component-base</code>. This repository will not provide compatibility guarantees initially but will align with OpenIMSDK's branches for compatibility.</p>
<h2 id="migration" tabindex="-1"><a class="header-anchor" href="#migration" aria-hidden="true">#</a> Migration</h2>
<p>Transition involves:</p>
<ol>
<li>Identifying common tools/code from the respective repositories.</li>
<li>Refactoring and migrating them to <code v-pre>component-base</code>.</li>
<li>Adjusting dependencies in the original repositories to now point to <code v-pre>component-base</code>.</li>
</ol>
<h2 id="drawbacks" tabindex="-1"><a class="header-anchor" href="#drawbacks" aria-hidden="true">#</a> Drawbacks</h2>
<ul>
<li>Initial overhead due to refactoring.</li>
<li>Potential for issues during the migration phase.</li>
</ul>
<h2 id="alternatives" tabindex="-1"><a class="header-anchor" href="#alternatives" aria-hidden="true">#</a> Alternatives</h2>
<ul>
<li>Maintain the current structure but ensure stricter guidelines for code sharing.</li>
<li>Create separate utility repositories for each original repository instead of a single shared one.</li>
</ul>
<h2 id="prior-art-1" tabindex="-1"><a class="header-anchor" href="#prior-art-1" aria-hidden="true">#</a> Prior Art</h2>
<p>Kubernetes's <code v-pre>component-base</code> repository serves a similar purpose. They created it to have a unified, consistent base for components, promoting shared utilities and configurations.</p>
<h2 id="unresolved-questions" tabindex="-1"><a class="header-anchor" href="#unresolved-questions" aria-hidden="true">#</a> Unresolved Questions</h2>
<ul>
<li>What might be the challenges in the migration phase?</li>
<li>How do we ensure minimal disruption during the transition?</li>
</ul>
<h2 id="spec-changes-optional" tabindex="-1"><a class="header-anchor" href="#spec-changes-optional" aria-hidden="true">#</a> Spec. Changes (OPTIONAL)</h2>
<p>No specification changes as of now.</p>
<h2 id="history" tabindex="-1"><a class="header-anchor" href="#history" aria-hidden="true">#</a> History</h2>
<ul>
<li>2023-08-25: Initial draft proposed by @cubxxw</li>
</ul>
</div></template>


