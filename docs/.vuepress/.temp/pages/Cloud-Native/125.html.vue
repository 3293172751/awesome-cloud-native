<template><div><h1 id="_125-openim-集群化部署提案-rfc-cluster-deployment-for-openimsdk" tabindex="-1"><a class="header-anchor" href="#_125-openim-集群化部署提案-rfc-cluster-deployment-for-openimsdk" aria-hidden="true">#</a> 125: OpenIM 集群化部署提案 [RFC] Cluster Deployment for OpenIMSDK</h1>
<blockquote>
<p><a href="https://github.com/OpenIMSDK/community/edit/main/RFC/0007-openim-cluster-deployment.md" target="_blank" rel="noopener noreferrer">RFC #0007<ExternalLinkIcon/></a> Cluster Deployment for OpenIMSDK</p>
</blockquote>
<!-- 🤖 design template: https://github.com/OpenIMSDK/community/blob/main/0000-template.md ⚠️ Please submit a PR to https://github.com/OpenIMSDK/community/tree/main/RFC according to the specification after the design is completed -->
<h2 id="meta" tabindex="-1"><a class="header-anchor" href="#meta" aria-hidden="true">#</a> Meta</h2>
<ul>
<li>Name: Cluster Deployment for OpenIMSDK</li>
<li>Start Date: 2023-09-04</li>
<li>Author(s): @cubxxw</li>
<li>Status: Draft</li>
<li>RFC Pull Request: https://github.com/OpenIMSDK/community/edit/main/RFC/0007-openim-cluster-deployment.md</li>
<li>OpenIMSDK Pull Request: (leave blank)</li>
<li>OpenIMSDK Issue: https://github.com/OpenIMSDK/Open-IM-Server/issues/1002</li>
<li>Supersedes: N/A</li>
</ul>
<h2 id="📇topics" tabindex="-1"><a class="header-anchor" href="#📇topics" aria-hidden="true">#</a> 📇Topics</h2>
<ul>
<li>RFC #0000 Cluster Deployment for OpenIMSDK
<ul>
<li><a href="#meta">Meta</a></li>
<li><a href="#summary">Summary</a></li>
<li><a href="#definitions">Definitions</a></li>
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
</li>
</ul>
<h2 id="summary" tabindex="-1"><a class="header-anchor" href="#summary" aria-hidden="true">#</a> Summary</h2>
<p>This proposal aims to provide a streamlined approach for deploying OpenIMSDK in a cluster environment, considering multiple deployment strategies, including but not limited to helm, sealos, and k3s.</p>
<h2 id="definitions" tabindex="-1"><a class="header-anchor" href="#definitions" aria-hidden="true">#</a> Definitions</h2>
<ul>
<li><strong>Cluster</strong>: A set of computers that work together to run a set of applications.</li>
<li><strong>Kubernetes (K8s)</strong>: An open-source system for automating deployment, scaling, and management of containerized applications.</li>
<li><strong>Helm</strong>: A package manager for Kubernetes.</li>
<li><strong>Sealos</strong>: An efficient Kubernetes installer.</li>
</ul>
<h2 id="motivation" tabindex="-1"><a class="header-anchor" href="#motivation" aria-hidden="true">#</a> Motivation</h2>
<ul>
<li>To streamline and standardize the OpenIMSDK deployment in various cluster environments.</li>
<li>To leverage the scalability, redundancy, and high availability offered by cluster deployments.</li>
<li>To provide clear documentation and guidance for deploying OpenIMSDK in a cluster.</li>
</ul>
<h2 id="what-it-is" tabindex="-1"><a class="header-anchor" href="#what-it-is" aria-hidden="true">#</a> What it is</h2>
<p>This feature aims to provide a guideline and tools required to deploy OpenIMSDK in a cluster. Target personas include OpenIMSDK developers, platform operators, and users who wish to deploy OpenIMSDK in a scalable and efficient manner.</p>
<h2 id="how-it-works" tabindex="-1"><a class="header-anchor" href="#how-it-works" aria-hidden="true">#</a> How it Works</h2>
<ol>
<li><strong>K8s Environment Setup</strong>: Choose the desired cluster setup tool, such as k3s, sealos, or helm. Set up the cluster according to the respective tool's documentation.</li>
<li><strong>Service Deployment</strong>: Deploy OpenIMSDK server components followed by chat components using the respective Kubernetes configurations.</li>
<li><strong>Configuration &amp; Environment Variables</strong>: Adjust configuration files and environment variables based on the deployment environment and requirements.</li>
<li><strong>Scaling &amp; Load Balancing</strong>: Based on demand, scale the services either manually or automatically using Kubernetes' horizontal pod autoscaler.</li>
<li><strong>Monitoring &amp; Logging</strong>: Use tools like Prometheus and Grafana to monitor the health and performance of the services.</li>
</ol>
<h2 id="migration" tabindex="-1"><a class="header-anchor" href="#migration" aria-hidden="true">#</a> Migration</h2>
<p>Users currently running OpenIMSDK in non-clustered environments can migrate their data to the new cluster environment. Detailed steps will be provided, including backup, transfer, and restore procedures.</p>
<h2 id="drawbacks" tabindex="-1"><a class="header-anchor" href="#drawbacks" aria-hidden="true">#</a> Drawbacks</h2>
<ul>
<li>Increased complexity in setup and maintenance.</li>
<li>Requires expertise in Kubernetes and the chosen cluster deployment tools.</li>
</ul>
<h2 id="alternatives" tabindex="-1"><a class="header-anchor" href="#alternatives" aria-hidden="true">#</a> Alternatives</h2>
<ul>
<li>Continue to support traditional non-cluster deployments.</li>
<li>Explore other cloud-native deployment tools beyond the mentioned in this proposal.</li>
</ul>
<h2 id="prior-art" tabindex="-1"><a class="header-anchor" href="#prior-art" aria-hidden="true">#</a> Prior Art</h2>
<p>Several contributors and even the official team have previously provided cluster deployment solutions:</p>
<ul>
<li><a href="https://github.com/OpenIMSDK/k8s-jenkins" target="_blank" rel="noopener noreferrer">k8s-jenkins<ExternalLinkIcon/></a></li>
<li><a href="https://github.com/OpenIMSDK/Open-IM-Server-k8s-deploy" target="_blank" rel="noopener noreferrer">Open-IM-Server-k8s-deploy<ExternalLinkIcon/></a></li>
<li><a href="https://github.com/OpenIMSDK/openim-charts" target="_blank" rel="noopener noreferrer">openim-charts<ExternalLinkIcon/></a></li>
<li><a href="https://github.com/showurl/deploy-openim" target="_blank" rel="noopener noreferrer">deploy-openim<ExternalLinkIcon/></a></li>
</ul>
<h2 id="unresolved-questions" tabindex="-1"><a class="header-anchor" href="#unresolved-questions" aria-hidden="true">#</a> Unresolved Questions</h2>
<ul>
<li>Which deployment strategy is the most efficient and reliable for OpenIMSDK?</li>
<li>How do we ensure a seamless migration experience for users transitioning from a non-clustered to a clustered environment?</li>
</ul>
<h2 id="spec-changes-optional" tabindex="-1"><a class="header-anchor" href="#spec-changes-optional" aria-hidden="true">#</a> Spec. Changes (OPTIONAL)</h2>
<p>There may be a need to introduce new configurations or environment variables specific to clustered deployments. This section will be updated as these changes are identified during the implementation phase.</p>
<h2 id="history" tabindex="-1"><a class="header-anchor" href="#history" aria-hidden="true">#</a> History</h2>
<ul>
<li>https://github.com/OpenIMSDK/Open-IM-Server/issues/601</li>
</ul>
<p><strong>Fix Issue:</strong></p>
<ul>
<li>https://github.com/OpenIMSDK/Open-IM-Server/issues/688</li>
<li>https://github.com/OpenIMSDK/Open-IM-Server/issues/621</li>
<li>https://github.com/OpenIMSDK/Open-IM-Server/issues/459</li>
</ul>
</div></template>


