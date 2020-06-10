---
title: HTML の基礎
ms.date: 11/04/2016
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
ms.openlocfilehash: 29ca2e3df4981db22a10281ba2a2938fc91d5b46
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620001"
---
# <a name="html-basics"></a>HTML の基礎

ほとんどのブラウザーには、参照するページの HTML ソースを調べる機能があります。 ソースを表示すると、複数の HTML (ハイパーテキストマークアップ言語) タグが山かっこ (<>) で囲まれ、テキストと共に表示されます。

次の手順では、HTML タグを使用して単純な Web ページを作成します。 この手順では、メモ帳でファイルにプレーンテキストを入力し、いくつかの変更を行い、ファイルを保存して、ブラウザーでページを再読み込みして変更を確認します。

#### <a name="to-create-an-html-file"></a>HTML ファイルを作成するには

1. メモ帳または任意のプレーンテキストエディターを開きます。

1. [**ファイル**] メニューの [**新規作成**] をクリックします。

1. 次の行を入力します。

    ```html
    <HTML>
    <HEAD>
    <TITLE>Top HTML Tags</TITLE>
    </HEAD>
    </HTML>
    ```

1. [**ファイル**] メニューの [**保存**] をクリックし、ファイルを c:\webpages\First.htm. として保存します。 ファイルはエディターで開いたままにしておきます。

1. ブラウザーに切り替え、[**ファイル**] メニューの [**開く**] をクリックするか、ブラウザーの URL 編集ボックスに「 *file://C:/webpages/first.htm* 」と入力します。 ウィンドウキャプションが "Top HTML Tags" である空のページが表示されます。

   タグがペアで、山かっこに囲まれていることに注意してください。 タグの大文字と小文字は区別されませんが、多くの場合、タグを目立たせるために使用されます。

   タグによって \<HTML> ドキュメントが開始され、タグが \</HTML> 終了します。 終了タグ (必ずしも必須ではない) は開始タグと同じですが、タグの前にスラッシュ (/) が含まれています。 山かっこ (<) とタグの先頭の間には空白を入れないでください。

1. メモ帳に戻り、行の後に \</HEAD> 次のように入力します。

    ```html
    <BODY>
        HTML is swell.
        Life is good.
    </BODY>
    ```

1. [**ファイル**] メニューの [**保存**] をクリックします。

1. ブラウザーに戻り、ページを更新します。

   これらの単語は、ブラウザーのウィンドウのクライアント領域に表示されます。 キャリッジリターンは無視されることに注意してください。 改行を使用する場合は、 `<BR>` 最初の行の後にタグを含める必要があります。

   次のすべての手順について、との間にテキストを挿入して、 \<BODY> \</BODY> ドキュメントの本文に追加します。

1. ヘッダーを追加します。

    ```html
    <H3>Here's the big picture</H3>
    ```

1. ページと同じディレクトリに保存されている .gif ファイルを使用して、イメージを追加します。

    ```html
    <IMG src="yourfile.gif">
    ```

1. リストを追加します。

    ```html
    <UL>Make me an unordered list.
    <LI>One programmer</LI>
    <LI>Ten SDKs</LI>
    <LI>Great Internet Apps</LI>
    </UL>
    ```

1. 代わりにリストに番号を付けるには、 \<OL> \</OL> タグとタグの代わりに、ペアとタグを使用し \<UL> \</UL> ます。

これで開始します。 Web ページに優れた機能が表示されている場合は、HTML ソースを調べて、それがどのように作成されたかを確認できます。 Microsoft Front Page などの HTML エディターを使用して、単純なページと高度なページの両方を作成できます。

次に、作成したファイルの HTML ソース全体を示します。

```html
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

タグ、属性、および拡張機能の詳細については、ハイパーテキストマークアップ言語 (HTML) の仕様を参照してください。

W3C.org で公開されている[最新の HTML バージョン](https://www.w3.org/TR/html/)。

## <a name="see-also"></a>関連項目

[MFC インターネットプログラミングの基礎](mfc-internet-programming-basics.md)
