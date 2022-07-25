---
title: 从对象到 iframe - 其他嵌入技术
slug: Learn/HTML/Multimedia_and_embedding/Other_embedding_technologies
translation_of: Learn/HTML/Multimedia_and_embedding/Other_embedding_technologies
---
<div>{{LearnSidebar}}</div>

<div>{{PreviousMenuNext("Learn/HTML/Multimedia_and_embedding/Video_and_audio_content", "Learn/HTML/Multimedia_and_embedding/Adding_vector_graphics_to_the_Web", "Learn/HTML/Multimedia_and_embedding")}}
</div>

<p>到目前为止，你应该掌握了将图像、视频和音频嵌入到网页上的诀窍了。此刻，让我们继续深入学习，来看一些能让你在网页中嵌入各种内容类型的元素：{{htmlelement("iframe")}}, {{htmlelement("embed")}}
  和 {{htmlelement("object")}} 元素。<code>&lt;iframe&gt;</code>用于嵌入其他网页，另外两个元素则允许你嵌入 PDF，SVG，甚至 Flash —
  一种正在被淘汰的技术，但你仍然会时不时的看到它。</p>

<table>
  <tbody>
    <tr>
      <th scope="row">预备知识：</th>
      <td>基本的计算机知识、<a href="/zh-CN/docs/Learn/Getting_started_with_the_web/Installing_basic_software">安装基础软件</a>、<a
          href="/zh-CN/docs/Learn/Getting_started_with_the_web/Dealing_with_files">文件处理</a>的基本知识、熟悉 HTML 基础知识（阅读
        <a href="/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Getting_started">开始学习 HTML</a>）以及本模块中以前的文章。
      </td>
    </tr>
    <tr>
      <th scope="row">学习目标：</th>
      <td>要了解如何使用 <a href="/zh-CN/docs/Web/HTML/Element/object"><code>&lt;object&gt;</code></a>、<a href="/zh-CN/docs/Web/HTML/Element/embed"><code>&lt;embed&gt;</code></a>
        以及 <a href="/zh-CN/docs/Web/HTML/Element/iframe"><code>&lt;iframe&gt;</code></a>
        元素，在网页中嵌入部件，例如 PDF 文档和其它外部网页。
      </td>
    </tr>
  </tbody>
</table>

<h2 id="嵌入的简史">嵌入的简史</h2>

<p>很久以前，很流行在网络上使用<strong>框架</strong>创建网站——网站的一小部分存储于单独的 HTML
  页面中。这些被嵌入在一个称为<strong>框架集</strong>的主文档中，它允许你指定每个框架能够填充在屏幕上的区域，非常像调整表格的列和行的大小。这些做法在 90 年代中期至 90
  年代后期被认为是比较酷的，有证据表明，将网页分解成较小的块，这样有利于下载速度——尤其是在那时网络连接速度太慢的情况下更为明显。然而，这些技术有很多问题，随着网络速度越来越快，这些技术带来的问题远超过它们带来的积极因素，所以你再也看不到它们被使用了。
</p>

<p>一小段时间之后（20 世纪 90 年代末，21 世纪初），插件技术变得非常受欢迎，例如 <a href="/zh-CN/docs/Glossary/Java">Java Applet</a> 和
  <a href="/zh-CN/docs/Glossary/Adobe_Flash">Flash</a>——这些技术允许网络开发者将丰富的内容嵌入到网页中，例如视频和动画等，这些内容不能通过 HTML
  单独实现。嵌入这些技术是通过诸如 <a href="/zh-CN/docs/Web/HTML/Element/object"><code>&lt;object&gt;</code></a> 和较少使用的 <a
    href="/zh-CN/docs/Web/HTML/Element/embed"><code>&lt;embed&gt;</code></a> 元素来实现的，当时它们非常有用。由于许多问题，包括可访问性、安全性、文件大小等，它们已经过时了; 如今，大多数移动设备不再支持这些插件，桌面端也逐渐不再支持。
</p>

<p>最后，<a href="/zh-CN/docs/Web/HTML/Element/iframe"><code>&lt;iframe&gt;</code></a> 元素出现了（连同其他嵌入内容的方式，如
  <a href="/zh-CN/docs/Web/HTML/Element/canvas"><code>&lt;canvas&gt;</code></a>、<a
    href="/zh-CN/docs/Web/HTML/Element/video"><code>&lt;video&gt;</code></a> 等），它提供了一种将整个 web
  页嵌入到另一个网页的方法，看起来就像那个 web 页是另一个网页的一个 {{htmlelement("img")}} 或其它元素一样。{{htmlelement("iframe")}} 现在经常被使用。</p>

<p>了解完历史之后，让我们继续往下看以了解如何使用它们。</p>

<h2 id="自主学习：嵌入类型的使用">自主学习：嵌入类型的使用</h2>

<p>在这篇文章中，我们将直接进入自主学习部分，让你立即体会到嵌入技术的实用性。大家都非常熟悉<a href="https://www.youtube.com/">Youtube</a>，但很多人不了解它所提供的一些分享功能。让我们来看看
  Youtube 如何让我们通过<a href="/zh-CN/docs/Web/HTML/Element/iframe"><code>&lt;iframe&gt;</code></a>在页面中嵌入喜欢的视频。</p>

<ol>
  <li>首先，去 Youtube 找一个喜欢的视频。</li>
  <li>在视频下方，你会看到一个<em>共享</em>按钮 - 点击查看共享选项。</li>
  <li>选择“ <em>嵌入”</em>选项卡，你将得到一些 <code>&lt;iframe&gt;</code> 代码——复制一下。</li>
  <li>粘贴到下面的<em>输入</em>框里，看看<em>输出</em>结果是什么。</li>
</ol>

<p>此外，你还可以试试在示例中嵌入 <a href="https://www.google.com/maps/">Google 地图</a>：</p>

<ol>
  <li>去 Google 地图找一个喜欢的地图。</li>
  <li>点击 UI 左上角的“汉堡菜单”（三条水平线）。</li>
  <li>选择<em>共享或嵌入地图</em>选项。</li>
  <li>选择嵌入地图选项，这将给你一些<code>&lt;iframe&gt;</code>代码 - 复制一下。</li>
  <li>粘贴到下面的<em>输入</em>框，看看<em>输出</em>结果是什么。</li>
</ol>

<p>如果你犯了某些错误，你可以点击 <em>Reset</em> 按钮以重置编辑器。如果你确实被卡住了， 按下 <em>Show solution</em> 按钮以借鉴答案。</p>

<pre class="brush: html hidden">&lt;!DOCTYPE html&gt; &lt;html lang="zh-CN"&gt; &lt;head&gt; &lt;meta charset="utf-8"&gt; &lt;style&gt; body { font-family: '微软雅黑', Helvetica, Arial, sans-serif; margin: 10px; background: #f5f9fa; } h2 { font-size: 16px; } code, textarea { font-family: Consolas, Menlo, monospace; } .output { min-height: 200px; } .input { min-height: 100px; width: 95%; } .a11y-label { margin: 0; text-align: right; font-size: 0.7rem; width: 98%; } .controls { width: 96%; text-align: right; } &lt;/style&gt; &lt;/head&gt; &lt;body&gt; &lt;h2&gt;实时输出&lt;/h2&gt; &lt;div class="output"&gt;&lt;/div&gt; &lt;h2&gt;可编辑代码&lt;/h2&gt; &lt;p class="a11y-label"&gt;按 ESC 退出编辑区域，按 Tab 可插入制表符 &lt;code&gt;'\t'&lt;/code&gt; &lt;/p&gt; &lt;textarea id="code" class="input"&gt;&lt;/textarea&gt; &lt;div class="controls"&gt; &lt;button id="btn-reset"&gt;重置&lt;/button&gt; &lt;button id="btn-solution"&gt;显示答案&lt;/button&gt; &lt;/div&gt; &lt;script&gt; const btnReset = document.getElementById('btn-reset'); const btnSolution = document.getElementById('btn-solution'); const blockOutput = document.querySelector('.output'); const blockInput = document.querySelector('.input'); const original = '&lt;p&gt;改革春风吹满地&lt;/p&gt;'; const answer = `&lt;iframe src="https://player.bilibili.com/player.html?aid=19390801&amp;cid=31621681&amp;page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"&gt; &lt;/iframe&gt; &lt;p&gt;改革春风吹满地&lt;/p&gt;`; let userEntry = ""; init(); btnReset.addEventListener('click', init); btnSolution.addEventListener('click', () =&gt; { if (btnSolution.textContent === '显示答案') { blockInput.value = blockOutput.innerHTML = answer; btnSolution.textContent = '隐藏答案'; } else { blockInput.value = blockOutput.innerHTML = userEntry; btnSolution.textContent = '显示答案'; } }); blockInput.addEventListener('keydown', (e) =&gt; { switch (e.key) { case 'Tab': e.preventDefault(); insertAtCursor('\t'); break; case "Escape": blockInput.blur(); break; } }); blockInput.addEventListener('keyup', () =&gt; { userEntry = blockInput.value; blockOutput.innerHTML = blockInput.value; if (btnSolution.textContent === '隐藏答案') { btnSolution.textContent = '显示答案'; } }); function init() { userEntry = blockOutput.innerHTML = blockInput.value = original; btnSolution.textContent = '显示答案'; } function insertAtCursor(text) { const scrollPos = blockInput.scrollTop; const cursorPos = blockInput.selectionStart; const front = blockInput.value.substring(0, cursorPos); const back = blockInput.value.substring( blockInput.selectionEnd, blockInput.value.length); blockInput.value = front + text + back; blockInput.selectionStart = blockInput.selectionEnd = cursorPos + text.length; blockInput.focus(); blockInput.scrollTop = scrollPos; } &lt;/script&gt; &lt;/body&gt; &lt;/html&gt;</pre>

<p>{{ EmbedLiveSample('自主学习：嵌入类型的使用', 700, 600, "", "", "hide-codepen-jsfiddle") }}</p>

<h2 id="Iframe详解">Iframe 详解</h2>

<p>是不是很简单又有趣呢？<a href="/zh-CN/docs/Web/HTML/Element/iframe"><code>&lt;iframe&gt;</code></a> 元素旨在允许你将其他 Web
  文档嵌入到当前文档中。这很适合将第三方内容嵌入你的网站，你可能无法直接控制，也不希望实现自己的版本——例如来自在线视频提供商的视频，<a
    href="https://disqus.com/">Disqus</a> 等评论系统，在线地图提供商，广告横幅等。你通过本课程使用的实时可编辑示例就是使用 <code>&lt;iframe&gt;</code> 实现的。
</p>

<p>我们会在后面提到，关于 <code>&lt;iframe&gt;</code> 有一些严重的<a
    href="#安全隐患">安全隐患</a>需要考虑，但这并不意味着你不应该在你的网站上使用它们——它只需要一些知识和仔细地思考。让我们更详细地探索这些代码。假设你想在其中一个网页上加入 MDN 词汇表，你可以尝试以下方式：</p>

<pre class="brush: html">&lt;iframe src="https://developer.mozilla.org/zh-CN/docs/Glossary"
        width="100%" height="500" frameborder="0"
        allowfullscreen sandbox&gt;
  &lt;p&gt; &lt;a href="https://developer.mozilla.org/zh-CN/docs/Glossary"&gt;
    Fallback link for browsers that don't support iframes
  &lt;/a&gt; &lt;/p&gt;
&lt;/iframe&gt;
</pre>

<p>此示例包括使用以下所需的 <code>&lt;iframe&gt;</code> 基本要素：</p>

<dl>
  <dt><code><a href="/zh-CN/docs/Web/HTML/Element/iframe#attr-allowfullscreen">allowfullscreen</a></code></dt>
  <dd>如果设置，<code>&lt;iframe&gt;</code>则可以通过<a href="/zh-CN/docs/Web/API/Fullscreen_API">全屏 API</a> 设置为全屏模式（稍微超出本文的范围）。
  </dd>
  <dt><code><a href="/zh-CN/docs/Web/HTML/Element/iframe#attr-frameborder">frameborder</a></code></dt>
  <dd>如果设置为 1，则会告诉浏览器在此框架和其他框架之间绘制边框，这是默认行为。0 删除边框。不推荐这样设置，因为在 <a href="/zh-CN/docs/Glossary/CSS">CSS
      中</a>可以更好地实现相同的效果。<a href="/zh-CN/docs/Web/CSS/border"><code>border</code></a><code>: none;</code></dd>
  <dt><code><a href="/zh-CN/docs/Web/HTML/Element/iframe#attr-src">src</a></code></dt>
  <dd>该属性与 <a
      href="/zh-CN/docs/Web/HTML/Element/video"><code>&lt;video&gt;</code></a>/<code><a href="/zh-CN/docs/Web/HTML/Element/img"> 元素表示文档中的图像。">&lt;img&gt;</a></code>一样包含指向要嵌入文档的
    URL 路径。</dd>
  <dt>
    <code><a href="/zh-CN/docs/Web/HTML/Element/iframe#attr-width">width</a></code> 和 <code><a href="/zh-CN/docs/Web/HTML/Element/iframe#attr-height">height</a></code>
  </dt>
  <dd>这些属性指定你想要的 iframe 的宽度和高度。</dd>
  <dt>备选内容</dt>
  <dd>与 <a href="/zh-CN/docs/Web/HTML/Element/video"><code>&lt;video&gt;</code></a> 等其它类似元素相同，你可以在
    <code>&lt;iframe&gt;&lt;/iframe&gt;</code> 标签之间包含备选内容，如果浏览器不支持 <code>&lt;iframe&gt;</code>，将会显示备选内容，这种情况下，我们已经添加了一个到该页面的链接。现在你几乎不可能遇到任何不支持
    <code>&lt;iframe&gt;</code> 的浏览器。
  </dd>
  <dt><code><a href="/zh-CN/docs/Web/HTML/Element/iframe#attr-sandbox">sandbox</a></code></dt>
  <dd>该属性需要在已经支持其它 <code>&lt;iframe&gt;</code> 功能（例如 IE 10 及更高版本）但稍微更现代的浏览器上才能工作，该属性可以提高安全性设置；我们将在下一节中更加详细地谈到。</dd>
</dl>

<div class="note">
  <p><strong>备注：</strong> 为了提高速度，在主内容完成加载后，使用 JavaScript 设置 iframe 的 <code>src</code>
    属性是个好主意。这使你的页面可以更快地被使用，并减少你的官方页面加载时间（重要的 <a href="/zh-CN/docs/Glossary/SEO">SEO</a> 指标）。</p>
</div>

<h3 id="安全隐患">安全隐患</h3>

<p>以上我们提到了安全问题——现在我们来详细介绍一下这一点。我们并不期望你第一次就能完全理解所有内容;
  我们只想让你意识到这一问题，在你更有经验并开始考虑在你的实验和工作中使用 <code>&lt;iframe&gt;</code> 时为你提供参考。此外，没有必要害怕和不使用<code>&lt;iframe&gt;</code>—你只需要谨慎一点。继续看下去吧...
</p>

<p>浏览器制造商和 Web 开发人员了解到网络上的坏人（通常被称为<strong>黑客</strong>，或更准确地说是<strong>破解者</strong>），如果他们试图恶意修改你的网页或欺骗人们进行不想做的事情时常把 iframe
  作为共同的攻击目标（官方术语：<strong>攻击向量</strong>），例如显示用户名和密码等敏感信息。因此，规范工程师和浏览器开发人员已经开发了各种安全机制，使<code>&lt;iframe&gt;</code>更加安全，这有些最佳方案值得我们考虑 -
  我们将在下面介绍其中的一些。</p>

<div class="note">
  <p><strong>备注：</strong> <a href="https://en.wikipedia.org/wiki/Clickjacking">单击劫持</a>是一种常见的 iframe 攻击，黑客将隐藏的 iframe
    嵌入到你的文档中（或将你的文档嵌入到他们自己的恶意网站），并使用它来捕获用户的交互。这是误导用户或窃取敏感数据的常见方式。</p>
</div>

<p>一个快速的例子——尝试在浏览器中加载上面的例子——你也可以<a
    href="https://mdn.github.io/learning-area/html/multimedia-and-embedding/other-embedding-technologies/iframe-detail.html">在
    Github 上找到它</a>（<a
    href="https://github.com/mdn/learning-area/blob/gh-pages/html/multimedia-and-embedding/other-embedding-technologies/iframe-detail.html">参见源代码</a>）。你将不会看到任何内容，但如果你点击<a
    href="/zh-CN/docs/Learn/Common_questions/What_are_browser_developer_tools">浏览器开发者工具</a>中的<em>控制台</em>，你会看到一条消息，告诉你为什么没有显示内容。在
  Firefox 中，你会<em>被告知：“X-Frame-Options 拒绝加载 https://developer.mozilla.org/zh-CN/docs/Glossary”</em>。这是因为构建 MDN
  的开发人员已经在网站页面的服务器上设置了一个不允许被嵌入到<code>&lt;iframe&gt;</code>的设置（请参阅<a
    href="#配置_csp_指令">配置 CSP 指令</a>）这是有必要的——整个
  MDN 页面被嵌入在其它页面中没有多大意义，除非你想要将其嵌入到你的网站上并将其声称为自己的内容，或尝试通过单击劫持来窃取数据，这都是非常糟糕的事情。此外，如果每个人都这样做，所有额外的带宽将花费 Mozilla
  很多资金。</p>

<h4 id="只有在必要时嵌入">只有在必要时嵌入</h4>

<p>有时嵌入第三方内容（例如 YouTube
  视频和地图）是有意义的，但如果你只在完全需要时嵌入第三方内容，你可以省去很多麻烦。网络安全的一个很好的经验法则是<em>“你怎么谨慎都不为过，如果你决定要做这件事，多检查一遍；如果是别人做的，在被证明是安全的之前，都假设这是危险的。”</em>
</p>

<p>除了安全问题，你还应该意识到知识产权问题。无论在线内容还是离线内容，绝大部分内容都是有版权的，甚至是一些你没想到有版权的内容（例如，<a
    href="https://commons.wikimedia.org/wiki/Main_Page">Wikimedia
    Commons</a>上的大多数图片）。不要在网页上展示一些不属于你的内容，除非你是所有者或所有者给了你明确的、书面的许可。对于侵犯版权的惩罚是严厉的。再说一次，你再小心也不为过。</p>

<p>如果内容获得许可，你必须遵守许可条款。例如，MDN 上的内容是<a href="/zh-CN/docs/MDN/About#版权和许可">在
    CC-BY-SA 下许可的</a>，这意味着，如果你要引用我们的内容，就必须<a
    href="https://wiki.creativecommons.org/wiki/Best_practices_for_attribution">用适当的方式注明来源</a>，即使你对内容做了实质性的修改。
</p>

<h4 id="使用_HTTPS">使用 HTTPS</h4>

<p><a href="/zh-CN/docs/Glossary/HTTPS">HTTPS</a> 是 <a href="/zh-CN/docs/Glossary/HTTP">HTTP</a> 的加密版本。你应该尽可能使用 HTTPS
  为你的网站提供服务：</p>

<ol>
  <li>HTTPS 减少了远程内容在传输过程中被篡改的机会，</li>
  <li>HTTPS 防止嵌入式内容访问你的父文档中的内容，反之亦然。</li>
</ol>

<p>使用 HTTPS 需要一个安全证书，这可能是昂贵的（尽管 <a href="https://letsencrypt.org/">Let's Encrypt</a> 让这件事变得更容易），如果你没有，可以使用 HTTP
  来为你的父文档提供服务。但是，由于 HTTPS 的第二个好处，<em>无论成本如何，你绝对不能使用 HTTP 嵌入第三方内容</em>（在最好的情况下，你的用户的 Web 浏览器会给他们一个可怕的警告）。所有有声望的公司，例如
  Google Maps 或 Youtube，当你嵌入内容时，<code>&lt;iframe&gt;</code>将通过 HTTPS 提供 -
  查看<code>&lt;iframe&gt;</code> <code>src</code>属性内的 URL。</p>

<div class="note">
  <p><strong>备注：</strong> <a href="/zh-CN/docs/Learn/Common_questions/Using_Github_pages">Github 页面</a>允许默认情况下通过 HTTPS
    提供内容，因此对托管内容很有用。如果你正在使用不同的托管，并且不确定，请向你的托管服务商询问。</p>
</div>

<h4 id="始终使用_sandbox_属性">始终使用 <code>sandbox</code> 属性</h4>

<p>想尽可能减少攻击者在你的网站上做坏事的机会，那么你应该给嵌入的内容仅能完成自己工作的权限。当然，这也适用于你自己的内容。一个允许包含在其里的代码以适当的方式执行或者用于测试，但不能对其他代码库（意外或恶意）造成任何损害的容器称为<a
    href="https://en.wikipedia.org/wiki/Sandbox_(computer_security)">沙盒</a>。</p>

<p>未沙盒化（Unsandboxed）内容可以做得太多（执行 JavaScript，提交表单，弹出窗口等）默认情况下，你应该使用没有参数的 <code>sandbox</code> 属性来强制执行所有可用的限制，如我们前面的示例所示。
</p>

<p>如果绝对需要，你可以逐个添加权限（<code>sandbox=""</code>属性值内）——请参阅 <code><a href="/zh-CN/docs/Web/HTML/Element/iframe#attr-sandbox">sandbox</a></code> 所有可用选项的参考条目。其中重要的一点是，你<em>永远不</em>应该同时添加<code>allow-scripts</code>和<code>allow-same-origin</code>到你的<code>sandbox</code>属性中——在这种情况下，嵌入式内容可以绕过阻止站点执行脚本的同源安全策略，并使用 JavaScript 完全关闭沙盒。</p>

<div class="note">
  <p><strong>备注：</strong> 如果攻击者可以欺骗人们直接访问恶意内容（在 iframe 之外），则沙盒无法提供保护。如果某些内容可能是恶意的（例如，用户生成的内容），请保证其是从不同的<a
      href="/zh-CN/docs/Glossary/domain">域</a>向你的主站点提供的。</p>
</div>

<h4 id="配置_csp_指令">配置 CSP 指令</h4>

<p><a href="/zh-CN/docs/Glossary/CSP">CSP</a>代表<strong><a href="/zh-CN/docs/Web/Security/CSP">内容安全策略</a></strong>，它提供<a
    href="/zh-CN/docs/Web/Security/CSP/CSP_policy_directives">一组 HTTP 标头</a>（由 web 服务器发送时与元数据一起发送的元数据），旨在提高 HTML
  文档的安全性。在<code>&lt;iframe&gt;</code>的安全性方面，你可以<em><a
      href="/zh-CN/docs/Web/HTTP/Headers/X-Frame-Options">将服务器配置为发送适当的<code>X-Frame-Options</code>
      标题。</a></em>这样做可以防止其他网站在其网页中嵌入你的内容（这将导致<a
    href="https://en.wikipedia.org/wiki/clickjacking">点击</a>和一系列其他攻击），正如我们之前看到的那样，MDN 开发人员已经做了这些工作。</p>

<div class="note">
  <p><strong>备注：</strong> 你可以阅读 Frederik Braun 的帖子<a
      href="https://blog.mozilla.org/security/2013/12/12/on-the-x-frame-options-security-header/">在
      X-Frame-Options 安全性头上</a>来获取有关此主题的更多背景信息。显然，在这篇文章中已经解释得很清楚了。</p>
</div>

<h2 id="&lt;embed>和&lt;object>元素">&lt;embed&gt; 和 &lt;object&gt; 元素</h2>

<p><a
    href="/zh-CN/docs/Web/HTML/Element/embed"><code>&lt;embed&gt;</code></a>和<code><a href="/zh-CN/docs/Web/HTML/Element/object">&lt;object&gt;</a></code>元素的功能不同于<code><a href="/zh-CN/docs/Web/HTML/Element/iframe">&lt;iframe&gt;</a></code>—— 这些元素是用来嵌入多种类型的外部内容的通用嵌入工具，其中包括像
  Java 小程序和 Flash，PDF（可在浏览器中显示为一个 PDF 插件）这样的插件技术，甚至像视频，SVG 和图像的内容！</p>

<div class="note">
  <p><strong>备注：</strong> <strong>插件</strong>是一种对浏览器原生无法读取的内容提供访问权限的软件。</p>
</div>

<p>然而，你不太可能使用这些元素——Applet 几年来一直没有被使用；由于许多原因，Flash 不再受欢迎（见下面的<a
    href="#针对插件的情况">插件案例</a>）；PDF
  更倾向于被链接而不是被嵌入；其他内容，如图像和视频都有更优秀、更容易元素来处理。插件和这些嵌入方法真的是一种传统技术，我们提及它们主要是为了以防你在某些情况下遇到问题，比如内部网或企业项目等。</p>

<p>如果你发现自己需要嵌入插件内容，那么你至少需要一些这样的信息：</p>

<table>
  <thead>
    <tr>
      <th scope="col"></th>
      <th scope="col">{{htmlelement("embed")}}</th>
      <th scope="col">{{htmlelement("object")}}</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>嵌入内容的<a href="/zh-CN/docs/Glossary/URL">网址</a></td>
      <td>{{htmlattrxref('src','embed')}}</td>
      <td>{{htmlattrxref('data','object')}}</td>
    </tr>
    <tr>
      <td>嵌入内容的<em>准确</em><a href="/zh-CN/docs/Glossary/MIME_type">媒体类型</a></td>
      <td>{{htmlattrxref('type','embed')}}</td>
      <td>{{htmlattrxref('type','object')}}</td>
    </tr>
    <tr>
      <td>由插件控制的框的高度和宽度（以 CSS 像素为单位）</td>
      <td>{{htmlattrxref('height','embed')}}<br>
        {{htmlattrxref('width','embed')}}</td>
      <td>{{htmlattrxref('height','object')}}<br>
        {{htmlattrxref('width','object')}}</td>
    </tr>
    <tr>
      <td>名称和值，将插件作为参数提供</td>
      <td>具有这些名称和值的 ad hoc 属性</td>
      <td>单标签<a
          href="/zh-CN/docs/Web/HTML/Element/param"><code>&lt;param&gt;</code></a>元素，包含在内<code>&lt;object&gt;</code>
      </td>
    </tr>
    <tr>
      <td>独立的 HTML 内容作为不可用资源的回退</td>
      <td>不支持（<code>&lt;noembed&gt;</code>已过时）</td>
      <td>包含在元素<code>&lt;object&gt;</code>之后<code>&lt;param&gt;</code></td>
    </tr>
  </tbody>
</table>

<div class="note">
  <p><strong>备注：</strong> <code>&lt;object&gt;</code>需要<code>data</code>属性，<code>type</code>属性或两者。如果你同时使用这两个，你也可以使用该<code><a href="/zh-CN/docs/Web/HTML/Element/object#attr-typemustmatch">typemustmatch</a></code>属性（仅在 Firefox
    中实现，在本文中）。<code>typemustmatch</code>保持嵌入文件不运行，除非<code>type</code>属性提供正确的媒体类型。<code>typemustmatch</code>因此，当你嵌入来自不同<a
      href="/zh-CN/docs/Glossary/Origin">来源的</a>内容（可以防止攻击者通过插件运行任意脚本）时，可以赋予重要的安全优势。
  </p>
</div>

<p>下面是一个使用该<a href="/zh-CN/docs/Web/HTML/Element/embed"><code>&lt;embed&gt;</code></a>元素嵌入
  Flash 影片的示例（请参阅此处的<a
    href="https://mdn.github.io/learning-area/html/multimedia-and-embedding/other-embedding-technologies/embed-flash.html">Github</a>，并<a
    href="https://github.com/mdn/learning-area/blob/gh-pages/html/multimedia-and-embedding/other-embedding-technologies/embed-flash.html">检查源代码</a>）：
</p>

<pre class="brush: html">&lt;embed src="whoosh.swf" quality="medium"
       bgcolor="#ffffff" width="550" height="400"
       name="whoosh" align="middle" allowScriptAccess="sameDomain"
       allowFullScreen="false" type="application/x-shockwave-flash"
       pluginspage="http://www.macromedia.com/go/getflashplayer"&gt;</pre>

<p>很可怕，不是吗。Adobe Flash 工具生成的 HTML
  往往更糟糕，使用嵌入<code>&lt;object&gt;</code>元素的<code>&lt;embed&gt;</code>元素来覆盖所有的基础（查看一个例子）。甚至有一段时间，Flash 被成功地用作 HTML5
  视频的备用内容，但是这种情况越来越被认为是不必要的。</p>

<p>现在来看一个<code>&lt;object&gt;</code>将 PDF 嵌入一个页面的例子（参见<a
    href="https://mdn.github.io/learning-area/html/multimedia-and-embedding/other-embedding-technologies/object-pdf.html">实例</a>和<a
    href="https://github.com/mdn/learning-area/blob/gh-pages/html/multimedia-and-embedding/other-embedding-technologies/object-pdf.html">源代码</a>）：
</p>

<pre class="brush: html">&lt;object data="mypdf.pdf" type="application/pdf"
        width="800" height="1200" typemustmatch&gt;
  &lt;p&gt;You don't have a PDF plugin, but you can &lt;a href="myfile.pdf"&gt;download the PDF file.&lt;/a&gt;&lt;/p&gt;
&lt;/object&gt;</pre>

<p>PDF 是纸与数据之间重要的阶梯，但它们<a href="https://webaim.org/techniques/acrobat/acrobat">在可访问性上有些问题</a><a
    href="https://webaim.org/techniques/acrobat/acrobat">，</a>并且可能难以在小屏幕上阅读。它们在一些圈子中仍然受欢迎，我们最好是用链接指向它们，而不是将其嵌入到网页中，以便它们可以在单独的页面上被下载或被阅读。
</p>

<h3 id="针对插件的情况">针对插件的情况</h3>

<p>以前，插件在网络上是不可或缺的。还记得你必须安装 Adobe Flash Player 才能在线观看电影的日子吗？并且你还会不断地收到关于更新 Flash Player 和 Java 运行环境的烦人警报。Web
  技术已经变得更加强大，那些日子已经结束了。对于大多数应用程序，现在是停止依赖插件传播内容，开始利用 Web 技术的时候了。</p>

<ul>
  <li><strong>扩大你对大家的影响力</strong>。每个人都有一个浏览器，但插件越来越少，特别是在移动用户中。由于 Web 在很大程度上不需要依赖插件而运行，所以人们宁愿只是去竞争对手的网站而不是安装插件。</li>
  <li><strong>从 Flash 和其他插件附带的<a href="https://webaim.org/techniques/flash/">额外的可访问性问题</a>中摆脱</strong>。</li>
  <li><strong>避免额外的安全隐患</strong>。即使经过无数次补丁<a
      href="http://www.cvedetails.com/product/6761/Adobe-Flash-Player.html?vendor_id=53">，</a> Adobe Flash 也是<a
      href="http://www.cvedetails.com/product/6761/Adobe-Flash-Player.html?vendor_id=53">非常不安全的</a>。2015
    年，Facebook 的首席安全官 Alex Stamos 甚至<a
      href="http://www.theverge.com/2015/7/13/8948459/adobe-flash-insecure-says-facebook-cso">要求 Adobe 停止
      Flash。</a></li>
</ul>

<p>那你该怎么办？如果你需要交互性，HTML 和<a href="/zh-CN/docs/Glossary/JavaScript">JavaScript</a>可以轻松地为你完成工作，而不需要 Java 小程序或过时的 ActiveX /
  BHO 技术。你可以使用<a href="/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content">HTML5
    视频</a>来满足媒体需求，矢量图形<a
    href="/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Adding_vector_graphics_to_the_Web">SVG</a>，以及复杂图像和动画<a
    href="/zh-CN/docs/Web/API/Canvas_API/Tutorial">画布</a>。<a
    href="https://plus.google.com/+PeterElst/posts/P5t4pFhptvp">彼得·埃尔斯特（Peter Elst）几年前已经提到</a>，对于工作 Adobe Flash
  极少是正确的工具，除了专门的游戏和商业应用。对于 ActiveX，即使微软的<a href="/zh-CN/docs/Glossary/Microsoft_Edge">Edge</a>浏览器也不再支持。</p>

<h2 id="总结">总结</h2>

<p>在 Web 文档中嵌入其他内容这一主题可以很快变得非常复杂，因此在本文中，我们尝试以一种简单而熟悉的方式来介绍它，这种介绍方式将立即显示出相关性，同时仍暗示了一些涉及更高级功能的技术。刚开始，除了嵌入第三方内容（如地图和视频），你不太可能在网页上使用到嵌入技术。当你变得更有经验时，你可能会开始为他们找到更多的用途。
</p>

<p>除了我们在这里讨论的那些外，还有许多涉及嵌入外部内容的技术。我们看到了一些在前面的文章中出现的，如<a
    href="/zh-CN/docs/Web/HTML/Element/video"><code>&lt;video&gt;</code></a>，<a
    href="/zh-CN/docs/Web/HTML/Element/audio"><code>&lt;audio&gt;</code></a>和<a
    href="/zh-CN/docs/Web/HTML/Element/img"><code>&lt;img&gt;</code></a>，但还有其它的有待关注，如 <a
    href="/zh-CN/docs/Web/HTML/Element/canvas"><code>&lt;canvas&gt;</code></a> 用于 JavaScript
  生成的 2D 和 3D 图形，<code><a href="/zh-CN/docs/Web/SVG/Element/svg">&lt;svg&gt;</a></code> 用于嵌入矢量图形。我们将在此学习模块的下一篇文章中学习<a
    href="/zh-CN/docs/Web/SVG">SVG</a>。</p>

<p>{{PreviousMenuNext("Learn/HTML/Multimedia_and_embedding/Video_and_audio_content", "Learn/HTML/Multimedia_and_embedding/Adding_vector_graphics_to_the_Web", "Learn/HTML/Multimedia_and_embedding")}}</p>