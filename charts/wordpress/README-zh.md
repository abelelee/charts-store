---
<!DOCTYPE html>
<html lang="zh-CN">
<head>
	<meta name="viewport" content="width=device-width" />
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<meta name="robots" content="noindex,nofollow" />
	<title>WordPress &#8250; 自述文件</title>
	<link rel="stylesheet" href="wp-admin/css/install.css?ver=20100228" type="text/css" />
</head>
<body>
<h1 id="logo">
	<a href="https://wordpress.org/"><img alt="WordPress" src="wp-admin/images/wordpress-logo.png" /></a>
</h1>
<p style="text-align: center">语义化个人发布平台</p>

<h2>首要事项</h2>
<p>欢迎。对我而言，WordPress 是一个非常特别的项目。每一位开发者和贡献者都为它带来了独特的元素，我们一起创造出了令我自豪的优秀作品。成千上万个小时被投入到 WordPress 上，我们致力于让它每天变得更好。感谢你让它成为你世界的一部分。</p>
<p style="text-align: right">&#8212; Matt Mullenweg</p>

<h2>安装：著名的5分钟安装</h2>
<ol>
	<li>将压缩包解压到一个空目录中，并上传所有文件。</li>
	<li>在浏览器中打开 <span class="file"><a href="wp-admin/install.php">wp-admin/install.php</a></span>，它将引导你创建一个包含数据库连接信息的 <code>wp-config.php</code> 文件。
		<ol>
			<li>如果由于某些原因无法运行，不要担心。它可能在某些主机上无法正常运行。使用类似 WordPad 的文本编辑器打开 <code>wp-config-sample.php</code> 文件，并填写你的数据库连接信息。</li>
			<li>将文件保存为 <code>wp-config.php</code> 并上传。</li>
			<li>在浏览器中再次打开 <span class="file"><a href="wp-admin/install.php">wp-admin/install.php</a></span>。</li>
		</ol>
	</li>
	<li>配置文件设置完成后，安装程序将为你创建站点所需的数据库表。如果出现错误，请仔细检查你的 <code>wp-config.php</code> 文件，然后重试。如果仍然失败，请前往 <a href="https://wordpress.org/support/forums/">WordPress 支持论坛</a>，并尽可能提供详细的信息。</li>
	<li><strong>如果你没有输入密码，请注意系统为你生成的密码。</strong> 如果你没有提供用户名，它将默认为 <code>admin</code>。</li>
	<li>安装程序随后会将你引导至 <a href="wp-login.php">登录页面</a>。使用你在安装过程中选择的用户名和密码登录。如果系统为你生成了密码，你可以点击“个人资料”来修改密码。</li>
</ol>

<h2>更新</h2>
<h3>使用自动更新程序</h3>
<ol>
	<li>在浏览器中打开 <span class="file"><a href="wp-admin/update-core.php">wp-admin/update-core.php</a></span>，并按照提示操作。</li>
	<li>你还想要更多操作？就这样了！</li>
</ol>

<h3>手动更新</h3>
<ol>
	<li>在更新之前，请确保备份你修改过的文件，例如 <code>index.php</code>。</li>
	<li>删除旧的 WordPress 文件，保留你修改过的文件。</li>
	<li>上传新的文件。</li>
	<li>在浏览器中访问 <span class="file"><a href="wp-admin/upgrade.php">/wp-admin/upgrade.php</a></span>。</li>
</ol>

<h2>从其他系统迁移</h2>
<p>WordPress 可以 <a href="https://developer.wordpress.org/advanced-administration/wordpress/import/">从多个系统导入内容</a>。在使用 <a href="wp-admin/import.php">我们的导入工具</a> 之前，你需要先按照上述步骤安装并运行 WordPress。</p>

<h2>系统要求</h2>
<ul>
	<li><a href="https://www.php.net/">PHP</a> 版本 <strong>7.2.24</strong> 或更高。</li>
	<li><a href="https://www.mysql.com/">MySQL</a> 版本 <strong>5.5.5</strong> 或更高。</li>
</ul>

<h3>推荐配置</h3>
<ul>
	<li><a href="https://www.php.net/">PHP</a> 版本 <strong>8.3</strong> 或更高。</li>
	<li><a href="https://www.mysql.com/">MySQL</a> 版本 <strong>8.0</strong> 或更高，或 <a href="https://mariadb.org/">MariaDB</a> 版本 <strong>10.6</strong> 或更高。</li>
	<li><a href="https://httpd.apache.org/docs/2.2/mod/mod_rewrite.html">mod_rewrite</a> Apache 模块。</li>
	<li><a href="https://wordpress.org/news/2016/12/moving-toward-ssl/">HTTPS</a> 支持。</li>
	<li>在你的网站上添加一个指向 <a href="https://wordpress.org/">wordpress.org</a> 的链接。</li>
</ul>

<h2>在线资源</h2>
<p>如果你有任何未在本文档中解答的问题，请充分利用 WordPress 的丰富在线资源：</p>
<dl>
	<dt><a href="https://wordpress.org/documentation/">帮助中心（HelpHub）</a></dt>
		<dd>HelpHub 是关于 WordPress 的百科全书，是目前最全面的 WordPress 信息来源。</dd>
	<dt><a href="https://wordpress.org/news/">WordPress 博客</a></dt>
		<dd>这里是你可以找到的 WordPress 最新更新和新闻的地方。最近的 WordPress 新闻会默认显示在你的管理仪表盘中。</dd>
	<dt><a href="https://planet.wordpress.org/">WordPress 行星（Planet）</a></dt>
		<dd>WordPress Planet 是一个新闻聚合器，汇集了来自网络上 WordPress 博客的文章。</dd>
	<dt><a href="https://wordpress.org/support/forums/">WordPress 支持论坛</a></dt>
		<dd>如果你已经查找了所有地方仍然找不到答案，可以访问活跃的支持论坛，那里有庞大的社区成员愿意帮助你。为了帮助他们更好地帮助你，请确保使用描述性的主题标题，并尽可能详细地描述你的问题。</dd>
	<dt><a href="https://make.wordpress.org/support/handbook/appendix/other-support-locations/introduction-to-irc/">WordPress <abbr>IRC</abbr>（互联网中继聊天）频道</a></dt>
		<dd>有一个在线聊天频道供 WordPress 用户进行讨论，偶尔也涉及支持话题。上面的维基页面将指引你正确的方向。（<a href="https://web.libera.chat/#wordpress">irc.libera.chat #wordpress</a>）</dd>
</dl>

<h2>最后说明</h2>
<ul>
	<li>如果你有任何建议、想法或评论，或者（天哪！）发现了 bug，请加入我们 <a href="https://wordpress.org/support/forums/">支持论坛</a>。</li>
	<li>WordPress 拥有一个强大的插件 <abbr>API</abbr>（应用程序编程接口），使得扩展代码变得简单。如果你是开发者并有兴趣使用它，请参阅 <a href="https://developer.wordpress.org/plugins/">插件开发者手册</a>。你不应该修改任何核心代码。</li>
</ul>

<h2>分享你的喜爱</h2>
<p>WordPress 没有数百万美元的营销活动或名人赞助，但我们有更好的东西——你。如果你喜欢 WordPress，请考虑告诉朋友、为不太懂技术的人安装它，或者给忽略了我们的媒体文章作者写信表达你的看法。</p>

<p>WordPress 是 b2/caf&#233;log 的正式延续，后者由 Michel V 开发。该项目的工作由 <a href="https://wordpress.org/about/">WordPress 开发团队</a> 继续维护。如果你愿意支持 WordPress，请考虑 <a href="https://wordpress.org/donate/">捐款</a>。</p>

<h2>许可证</h2>
<p>WordPress 是自由软件，根据 <abbr>GPL</abbr>（GNU 通用公共许可证）第 2 版或（由你选择）任何更高版本的条款发布。请参见 <a href="license.txt">license.txt</a>。</p>

</body>
</html>