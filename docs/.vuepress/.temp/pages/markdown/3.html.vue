<template><div><h1 id="docker和传统虚拟机" tabindex="-1"><a class="header-anchor" href="#docker和传统虚拟机" aria-hidden="true">#</a> docker和传统虚拟机</h1>
<nav class="table-of-contents"><ul><li><router-link to="#linux内核下的docker">linux内核下的docker</router-link></li><li><router-link to="#传统虚拟机和容器的对比">传统虚拟机和容器的对比</router-link></li><li><router-link to="#在后台的docker-windows和linux的区别">在后台的Docker：Windows和Linux的区别</router-link></li></ul></nav>
<p>[toc]</p>
<h2 id="linux内核下的docker" tabindex="-1"><a class="header-anchor" href="#linux内核下的docker" aria-hidden="true">#</a> linux内核下的docker</h2>
<blockquote>
<p><code v-pre>runc</code> 是一个 Linux 命令行工具，用于根据 <a href="https://github.com/opencontainers/runtime-spec" target="_blank" rel="noopener noreferrer">OCI容器运行时规范<ExternalLinkIcon/></a> 创建和运行容器。</p>
<p><code v-pre>containerd</code> 是一个守护程序，它管理容器生命周期，提供了在一个节点上执行容器和管理镜像的最小功能集。</p>
</blockquote>
<p><strong>Docker</strong> 在容器的基础上，进行了进一步的封装，从文件系统、网络互联到进程隔离等等，极大的简化了容器的创建和维护。使得 <code v-pre>Docker</code> 技术比虚拟机技术更为轻便、快捷。</p>
<p>下面的图片比较了 <strong>Docker</strong> 和传统虚拟化方式的不同之处。<strong>传统虚拟机技术是虚拟出一套硬件后，在其上运行一个完整操作系统，在该系统上再运行所需应用进程；而容器内的应用进程直接运行于宿主的内核，容器内没有自己的内核，而且也没有进行硬件虚拟。因此容器要比传统虚拟机更为轻便。</strong></p>
<p><strong>传统虚拟化：</strong></p>
<img src="http://sm.nsddd.top//typora/spaces_-M5xTVjmK7ax94c8ZQcm_uploads_git-blob-6e94771ad01da3cb20e2190b01dfa54e3a69d0b2_virtualization.png?mail:3293172751@qq.com" alt="a" style="zoom:80%;" />
<p><strong>Docker：</strong></p>
<img src="http://sm.nsddd.top//typora/spaces_-M5xTVjmK7ax94c8ZQcm_uploads_git-blob-5c1a41d44b8602c8f746e8929f484a701869ca25_docker.png?mail:3293172751@qq.com" alt="b" style="zoom:80%;" />
<h2 id="传统虚拟机和容器的对比" tabindex="-1"><a class="header-anchor" href="#传统虚拟机和容器的对比" aria-hidden="true">#</a> 传统虚拟机和容器的对比</h2>
<p>传统的VMware从开始到运行，很慢，而且内存很大</p>
<ul>
<li>资源占用多</li>
<li>冗余步骤多</li>
<li>启动慢</li>
</ul>
<div class="custom-container warning"><p class="custom-container-title">linux容器</p>
<p><strong>linux容器不是模拟一个完整的操作系统，而是对进程进行隔离。有了容器，就可以将软件运行所需要的所有资源打包到有个隔离的容器中。容器和虚拟机不同，不需要捆绑一整套的操作系统，只需要软件工作所需要的库和资源和设置。</strong></p>
<ul>
<li>docker容器是在 <strong>操作系统层面实现虚拟化</strong>，直接复用本地主机的操作系统，所用的同一个内核，容器之间相互隔离，进程互不影响。</li>
<li>传统虚拟机是在 <strong>硬件层面实现虚拟化</strong>，然后运行一个完整的操作系统</li>
</ul>
<blockquote>
<p>即docker的优势体现为启动速度快，占用体积小</p>
</blockquote>
<p><strong>docker作为 内核级虚拟化，不像传统虚拟化技术一样需要额外的hypervisor支持，所以在一台物理机上可以运行很多个容器实例，可以大大提升CPU和内存利用率.</strong></p>
<img src="@source/markdown/images/image-20220906174618397.pngmail3293172751@qq.png" alt="image-20220906174618397" style="zoom:40%;" />
</div>
<h2 id="在后台的docker-windows和linux的区别" tabindex="-1"><a class="header-anchor" href="#在后台的docker-windows和linux的区别" aria-hidden="true">#</a> 在后台的Docker：Windows和Linux的区别</h2>
<p>在Windows和Linux系统中安装Docker的方法只有一个不同。在Linux系统上安装Docker时，只需要安装Docker引擎和管理工具，而不需要创建虚拟机或者虚拟网络，因为你的容器将会为你创建环境。其实docker启动的应用，还是直接运行在宿主机上，<strong>和普通的程序一样，直接调用宿主机的内核；--</strong>-- 在宿主机上，通过ps可以看到docker启动的应用进程 （这也就是为什么说，docker只启动一个进程的原因）；</p>
<div class="language-text ext-text line-numbers-mode"><pre v-pre class="language-text"><code>docker ps 
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div></div></div><div class="custom-container danger"><p class="custom-container-title">提醒</p>
<p>Docker在Windows系统上安装是不同的。在安装时，Docker会创建一个基于Linux的虚拟机，叫做MobyLinux虚拟机，这个虚拟机是基于Alpine Linux的。Docker应用程序会连接到此虚拟机，你便可以开始创建具有必要操作组件的容器了。</p>
<p>为了与本地网络和NAT（网络地址转换）进行通信，在Docker安装中会为虚拟机配置一个子网，以便你的容器在应用程序中使用。</p>
<p>因为所有这些步骤都发生在后台，身为用户的你不必为这些步骤操心。不过，事实上Docker是在Windows后台运行虚拟机，这也是Docker在Windows和Linux的另外一个主要区别。</p>
</div>
</div></template>


