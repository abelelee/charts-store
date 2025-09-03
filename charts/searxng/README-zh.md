.. SPDX-License-Identifier: AGPL-3.0-or-later

----

.. figure:: https://raw.githubusercontent.com/searxng/searxng/master/client/simple/src/brand/searxng.svg
   :target: https://docs.searxng.org/
   :alt: SearXNG
   :width: 100%
   :align: center

----

注重隐私、可定制的 `元搜索引擎`_

Searx.space_ 提供了可直接使用的运行实例列表。

用户手册、管理员手册和开发者手册可在主页_上查阅。

|SearXNG install|
|SearXNG homepage|
|SearXNG wiki|
|AGPL License|
|Issues|
|commits|
|weblate|
|SearXNG logo|

----

.. _searx.space: https://searx.space
.. _user: https://docs.searxng.org/user
.. _admin: https://docs.searxng.org/admin
.. _developer: https://docs.searxng.org/dev
.. _homepage: https://docs.searxng.org/
.. _元搜索引擎: https://en.wikipedia.org/wiki/Metasearch_engine

.. |SearXNG logo| image:: https://raw.githubusercontent.com/searxng/searxng/master/client/simple/src/brand/searxng-wordmark.svg
   :target: https://docs.searxng.org/
   :width: 5%

.. |SearXNG install| image:: https://img.shields.io/badge/-install-blue
   :target: https://docs.searxng.org/admin/installation.html

.. |SearXNG homepage| image:: https://img.shields.io/badge/-homepage-blue
   :target: https://docs.searxng.org/

.. |SearXNG wiki| image:: https://img.shields.io/badge/-wiki-blue
   :target: https://github.com/searxng/searxng/wiki

.. |AGPL License|  image:: https://img.shields.io/badge/license-AGPL-blue.svg
   :target: https://github.com/searxng/searxng/blob/master/LICENSE

.. |Issues| image:: https://img.shields.io/github/issues/searxng/searxng?color=yellow&label=issues
   :target: https://github.com/searxng/searxng/issues

.. |PR| image:: https://img.shields.io/github/issues-pr-raw/searxng/searxng?color=yellow&label=PR
   :target: https://github.com/searxng/searxng/pulls

.. |commits| image:: https://img.shields.io/github/commit-activity/y/searxng/searxng?color=yellow&label=commits
   :target: https://github.com/searxng/searxng/commits/master

.. |weblate| image:: https://translate.codeberg.org/widgets/searxng/-/searxng/svg-badge.svg
   :target: https://translate.codeberg.org/projects/searxng/


联系方式
=======

你可以在以下平台向SearXNG社区提问或聊天（这不是一个聊天机器人）：

IRC
  `#searxng on libera.chat <https://web.libera.chat/?channel=#searxng>`_
  该频道也桥接到了Matrix。

Matrix
  `#searxng:matrix.org <https://matrix.to/#/#searxng:matrix.org>`_


安装设置
=====

- 提供了维护良好的 `Docker镜像`_，并支持ARM64和ARM/v7架构。
- 另外，我们还提供了*最新*的 `安装脚本`_。
- 如需手动安装，请参考我们的详细 `逐步安装指南`_。
- 要对你的实例进行微调，请查看 `管理员文档`_。

.. _管理员文档: https://docs.searxng.org/admin/index.html
.. _逐步安装指南: https://docs.searxng.org/admin/installation-searxng.html
.. _安装脚本: https://docs.searxng.org/admin/installation-scripts.html
.. _Docker镜像: https://github.com/searxng/searxng-docker

翻译
============

.. _Weblate: https://translate.codeberg.org/projects/searxng/searxng/

帮助我们翻译SearXNG，请访问 `Weblate`_

.. figure:: https://translate.codeberg.org/widgets/searxng/-/multi-auto.svg
   :target: https://translate.codeberg.org/projects/searxng/


贡献代码
============

.. _开发快速入门: https://docs.searxng.org/dev/quickstart.html
.. _开发者文档: https://docs.searxng.org/dev/index.html

你是开发者吗？请查看我们的 `开发快速入门`_ 指南，参与贡献非常简单。此外我们还提供了完整的 `开发者文档`_。


Codespaces
==========

你可以使用 `GitHub Codespaces`_ 在浏览器中进行贡献：

- Fork 仓库
- 点击 ``<> Code`` 绿色按钮
- 点击 ``Codespaces`` 标签页，而不是 ``Local``
- 点击 ``Create codespace on master``
- VSCode 将会在浏览器中启动
- 等待终端显示并自动执行完 ``git pull && make install``
- 你每月拥有 `120小时免费使用时间`_（详见你的 `现有Codespaces列表`_）
- 你可以在终端中运行 ``make run`` 或按下 ``Ctrl+Shift+B`` 来启动 SearXNG

.. _GitHub Codespaces: https://docs.github.com/en/codespaces/overview
.. _120小时免费使用时间: https://github.com/settings/billing
.. _现有Codespaces列表: https://github.com/codespaces