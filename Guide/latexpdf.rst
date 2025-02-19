.. 
 Copyright (c) 2021 Jun Ebihara All rights reserved.
 Redistribution and use in source and binary forms, with or without
 modification, are permitted provided that the following conditions
 are met:
 1. Redistributions of source code must retain the above copyright
    notice, this list of conditions and the following disclaimer.
 2. Redistributions in binary form must reproduce the above copyright
    notice, this list of conditions and the following disclaimer in the
    documentation and/or other materials provided with the distribution.
 THIS SOFTWARE IS PROVIDED BY THE AUTHOR ``AS IS'' AND ANY EXPRESS OR
 IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES
 OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED.
 IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY DIRECT, INDIRECT,
 INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT
 NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
 DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
 THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
 (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF
 THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

sphinxのドキュメントをlatex経由でpdfに変換する
=================================

sphinxのインストール
--------------------

::

 # pkg_add py38-sphinx
 # ln -s /usr/pkg/bin/sphinx-build-3.8 /usr/pkg/bin/sphinx-build
 # which sphinx-build
 /usr/pkg/bin/sphinx-build


sphinxに必要なlatex環境インストール
------------------------------------

::

 # pkg_add dvipdfmx
 # pkg_add latexmk
 # pkg_add tex-platex
 # pkg_add texlive-collection-langjapanese
 # pkg_add tex-cmap
 # pkg_add tex-fancyhdr
 # pkg_add tex-titlesec
 # pkg_add tex-tabulary
 # pkg_add tex-varwidth
 # pkg_add tex-framed
 # pkg_add tex-float
 # pkg_add tex-wrapfig
 # pkg_add tex-parskip
 # pkg_add tex-upquote
 # pkg_add tex-capt-of
 # pkg_add tex-needspace
 # pkg_add tex-kvsetkeys
 # pkg_add tex-geometry
  # pkg_add tex-hyperref
   # pkg_add py-sphinxcontrib-svg2pdfconverter
 
dvipdfmx設定変更
-------------------

::

 # cd  /usr/pkg/etc/texmf/dvipdfm
 diff -u -r1.1 dvipdfmx.cfg
 --- dvipdfmx.cfg        2021/02/03 08:55:35     1.1
 +++ dvipdfmx.cfg        2021/02/03 08:56:21
 @@ -215,7 +215,7 @@
  %f psfonts.map
 
  %% Put additional fontmap files here (usually for Type0 fonts)
 -%f  cid-x.map
 +f  cid-x.map
 
  % the following file is generated by updmap(-sys) from the
  % KanjiMap entries in the updmap.cfg file.
 
sphinx でlatexpdf起動
----------------------

::

 % gmake latexpdf
 
