---
title: HTML の基礎 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c4ebbc8e792e36461f7c52c17fa23815239e323
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929091"
---
# <a name="html-basics"></a>HTML の基礎
ほとんどのブラウザーを参照するページの HTML ソースを調べる機能があります。 (ハイパー テキスト マークアップ言語) の HTML タグの数が表示されます、ソースを表示するときに、角度っこ、テキストが混在してで囲まれます。  
  
 次の手順では、HTML タグを使用して、単純な Web ページを構築します。 次の手順でするをメモ帳でファイルにプレーン テキストを入力、いくつかの変更を加える、ファイルを保存および変更内容を表示するには、ブラウザーでページを再読み込みします。  
  
#### <a name="to-create-an-html-file"></a>HTML ファイルを作成するには  
  
1.  メモ帳または任意のプレーン テキスト エディターを開きます。  
  
2.  **ファイル**] メニューの [選択**新規**です。  
  
3.  次の行に入力します。  
  
 ```  
 <HTML>  
 <HEAD>  
 <TITLE>Top HTML Tags</TITLE>  
 </HEAD>  
 </HTML>  
 ```  
  
4.  **ファイル**] メニューの [選択**保存**、c:\webpages\First.htm として、ファイルを保存します。 ファイルをエディターで開いたままにしておきます。  
  
5.  スイッチ、ブラウザーとの間、**ファイル**] メニューの [選択**開く**、または型*file://C:/webpages/first.htm*ブラウザーの URL の編集ボックス。 「上の HTML タグ」ウィンドウのキャプションを空白のページを表示する必要があります。  
  
     タグはペアになって、山かっこで含まれてください。 タグは、大文字小文字を区別できませんが、大文字と小文字はタグを目立たによく使用します。  
  
     タグ\<HTML > ドキュメント、およびタグが開始\</HTML > で終了します。 終了タグが必須ではありません) は、開始タグと同じですが、タグの前にスラッシュ (/) です。 山かっこ (<) と、タグの先頭のスペースいけません。  
  
6.  メモ帳に戻ると、後のスイッチ、 \<HEAD/> 行を入力します。  
  
 ```  
 <BODY>  
    HTML is swell.  
    Life is good.  
 </BODY>  
 ```  
  
7.  **ファイル**] メニューの [選択**保存**です。  
  
8.  お使いのブラウザーに戻り、ページを更新します。  
  
     単語は、ブラウザーのウィンドウのクライアント領域に表示されます。 キャリッジ リターンは無視されることに注意してください。 改行する場合は、する必要があります、`<BR>`最初の行の後にタグ。  
  
     すべての手順については、次の任意の場所の間でテキストを挿入\<本文 > と \< /BODY >、ドキュメントの本文に追加します。  
  
9. ヘッダーを追加します。  
  
 ```  
 <H3>Here's the big picture</H3>  
 ```  
  
10. ページと同じディレクトリに保存されている .gif ファイルを使用して、イメージを追加します。  
  
 ```  
 <IMG src="yourfile.gif">  
 ```  
  
11. 一覧を追加します。  
  
 ```  
 <UL>Make me an unordered list.  
 <LI>One programmer</LI>  
 <LI>Ten SDKs</LI>  
 <LI>Great Internet Apps</LI>  
 </UL>  
 ```  
  
12. リストを代わりに番号を使用してペアリング\<OL > と\</OL > タグの代わりに、 \<UL > と\</UL > タグ。  
  
 作業を開始するを取得する必要があります。 Web ページの優れた機能を表示する場合、HTML ソースを調べることによって作成されたかを調べることができます。 シンプルで高度なページを作成するのには、Microsoft Front Page など HTML エディターを使用できます。  
  
 構築してきたファイルの全体の HTML ソースを次に示します。  
  
```  
<HTML>  
<HEAD>  
<TITLE>Top HTML Tags</TITLE>  
</HEAD>  
<BODY>  
HTML is swell.<BR>  
Life is good.  
<H3>Here's the big picture</H3>  
<IMG src="yourfile.gif">  
<UL>Make me an unordered list.  
<LI>One programmer</LI>  
<LI>Ten SDKs</LI>  
<LI>Great Internet Apps</LI>  
</UL>  
</BODY>  
</HTML>  
```  
  
 タグ、属性、および拡張機能の詳細については、ハイパー テキスト マークアップ言語 (HTML) 仕様を参照してください。  
  
 [http://www.w3.org/pub/WWW/MarkUp/](http://www.w3.org/pub/www/markup/)  
  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)

