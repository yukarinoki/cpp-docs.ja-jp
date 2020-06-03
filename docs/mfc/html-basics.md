---
title: HTML の基礎
ms.date: 11/04/2016
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
ms.openlocfilehash: 6d3a692eab47a1309ee0248b51ab8563fb077d5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377244"
---
# <a name="html-basics"></a>HTML の基礎

ほとんどのブラウザでは、参照するページの HTML ソースを調べる機能があります。 ソースを表示すると、テキストが散在する山かっこ (<>) で囲まれた HTML (ハイパーテキスト マークアップ言語) タグが多数表示されます。

以下の手順では、HTML タグを使用して単純な Web ページを作成します。 次の手順では、メモ帳でファイルにプレーン テキストを入力し、いくつかの変更を加え、ファイルを保存し、ブラウザーでページを再読み込みして変更を確認します。

#### <a name="to-create-an-html-file"></a>HTML ファイルを作成するには

1. メモ帳または任意のテキスト エディタを開きます。

1. [**ファイル]** メニューの [**新規作成**] をクリックします。

1. 次の行を入力します。

    ```html
    <HTML>
    <HEAD>
    <TITLE>Top HTML Tags</TITLE>
    </HEAD>
    </HTML>
    ```

1. [**ファイル]** メニューの [**保存**] をクリックし、ファイルを c:\webpages\First.htm として保存します。 ファイルをエディタで開いたままにします。

1. ブラウザに切り替え、[**ファイル]** メニューの [**開く**] をクリックするか、ブラウザの URL 編集ボックスに*file://C:/webpages/first.htm*を入力します。 ウィンドウのキャプションが 「上位 HTML タグ」の空白ページが表示されます。

   タグがペアになり、山かっこに含まれていることに注意してください。 タグは大文字と小文字を区別しませんが、タグを目立たせるために大文字と小文字を区別することがよくあります。

   タグ\<HTML>は、ドキュメントを開始し\<、タグ /HTML>はそれを終了します。 終了タグ (必ずしも必須ではありません) は開始タグと同じですが、タグの前にスラッシュ (/) が付いています。 山かっこ (<) とタグの先頭の間にスペースを入れてはいけない。

1. メモ帳に戻り、/HEAD \<>行の後に次のように入力します。

    ```html
    <BODY>
        HTML is swell.
        Life is good.
    </BODY>
    ```

1. [**ファイル]** メニューの [**保存**] をクリックします。

1. ブラウザに戻り、ページを更新します。

   ブラウザのウィンドウのクライアント領域に、単語が表示されます。 キャリッジ リターンが無視されることに注意してください。 改行を設定する場合は、最初の行の後に`<BR>`タグを付ける必要があります。

   次の手順の場合は、BODY>と\<\</BODY>の間の任意の場所にテキストを挿入し、ドキュメントの本文に追加します。

1. ヘッダーを追加します。

    ```html
    <H3>Here's the big picture</H3>
    ```

1. ページと同じディレクトリに保存された .gif ファイルを使用して、イメージを追加します。

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

1. 代わりにリストに番号を付けるには\<、UL \<> タグと /UL \<> タグ\<の代わりに、ペアの OL>と /OL> タグを使用します。

それはあなたが始める必要があります。 Web ページに優れた機能が表示される場合は、HTML ソースを調べることで、そのページがどのように作成されたかを確認できます。 フロント ページなどの HTML エディタを使用して、単純なページと高度なページの両方を作成できます。

作成したファイルの HTML ソース全体を次に示します。

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

タグ、属性、および拡張機能の詳細については、ハイパーテキスト マークアップ言語 (HTML) の仕様を参照してください。

W3C.org[の最新の HTML バージョン](https://www.w3.org/TR/html/)。

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)
