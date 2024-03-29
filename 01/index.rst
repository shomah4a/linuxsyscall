
===============================
 Linux システムコール読書会 #1
===============================


Linux システムコール読書会 #1
=============================

.. s6:: styles

    h2: {fontSize:'120%', textAlign:'center', marginTop:'10%'},


プロセス管理編 #1 〜getpid〜
----------------------------

2012/07/12

@shomah4a


.. s6:: styles

    h3: {fontSize:'80%', textAlign:'center', marginTop:'0%'},
    p: {fontSize:'50%', textAlign:'center', marginLeft: 'auto', marginRight: 'auto', marginBottom: '5px', marginTop: '5px'},
    'p[0]': {marginTop: '100px'},
    'p[1]': {marginBottom: '40px'},
    

今日やること
============

- ご挨拶

  - 会場説明
  
- 目的とか

  - 開催目的

- 内容

  - 進め方
  - システムコールとは
  - 今日のサンプルコード
  - 読む

.. s6:: styles

   'ul': {marginLeft: '5%', fontSize: '60%'},
   'ul/li/ul': {marginLeft: '5%'},


ご挨拶
======


会場説明
========

- トイレはエレベータ横
- 喫煙所は建物の外
- 無線 LAN の AP 名と Password はホワイトボード
- わからなければ中の人まで


開催目的
========

- 自分たちが Linux の内部についての知識を得るため


進め方
======

- 自己紹介タイム

- ソースを読む

  - ソースは `サイト <http://linuxsyscall.readthedocs.org/en/latest/index.html>`_ から

- 本を見る

  - `Linux カーネル 2.6 解読室 <http://www.amazon.co.jp/dp/4797338261>`_
  - 全体を把握するための参考書


.. s6:: styles

   'ul': {marginLeft: '5%'},
   'ul/li/ul': {marginLeft: '5%'},

   
自己紹介タイム
==============


システムコールとは
==================

  システムコールとは、プロセスがカーネルに明示的にサービスを要求するインターフェイスのことです。
  このインターフェイスを使用して、プロセスはファイルに対する読み書きや新たなプロセスの生成といったカーネルサービスを要求します。

Linux カーネル 2.6 解読室 P.94 より


.. s6:: styles

    blockquote: {'fontSize':'60%', marginTop: '10%'},


システムコールとは
==================

システムコール == カーネルの API


.. s6:: styles

   div: {textAlign: 'center'},
   p: {fontSize:'80%', textAlign:'center', marginTop: '20%'}


getpid って何?
==============

::

   NAME
          getpid, getppid - get process identification

   SYNOPSIS
          #include <sys/types.h>
          #include <unistd.h>

          pid_t getpid(void);
          pid_t getppid(void);

   DESCRIPTION
          getpid() returns the process ID of the calling process.  (This is often used by routines that generate unique temporary filenames.)

          getppid() returns the process ID of the parent of the calling process.


.. s6:: styles

   div: {fontSize: '50%', wordWrap: 'break-all', width: '100%'},


今日のサンプルコード
====================


.. literalinclude:: _static/sample.c
   :language: c

:download:`サンプルコード <_static/sample.c>`

.. s6:: styles

   div: {fontSize: '80%', marginTop: '5%'}


読む
====


