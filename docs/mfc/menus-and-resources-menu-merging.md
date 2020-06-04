---
title: 'メニューとリソース : メニューの結合'
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
ms.openlocfilehash: 149af83bd53b7a97fd264bd6b18701fc9f64ea1f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364771"
---
# <a name="menus-and-resources-menu-merging"></a>メニューとリソース : メニューの結合

この資料では、OLE ドキュメント アプリケーションがビジュアル編集とインプレース アクティベーションを適切に処理するために必要な手順について詳しく説明します。 インプレース アクティベーションは、コンテナー アプリケーションとサーバー (コンポーネント) アプリケーションの両方にとって課題となります。 ユーザーは同じフレーム ウィンドウ (コンテナー ドキュメントのコンテキスト内) に残りますが、実際には別のアプリケーション (サーバー) を実行しています。 これには、コンテナー アプリケーションとサーバー アプリケーションのリソース間の調整が必要です。

この記事で扱うトピックは次のとおりです。

- [メニューレイアウト](#_core_menu_layouts)

- [ツールバーとステータス バー](#_core_toolbars_and_status_bars)

## <a name="menu-layouts"></a><a name="_core_menu_layouts"></a>メニューレイアウト

最初の手順は、メニューレイアウトを調整することです。 コンテナー アプリケーションでは、埋め込みアイテムが有効な場合にのみ使用する新しいメニューを作成する必要があります。 このメニューは、少なくとも以下の順序で構成する必要があります。

1. ファイルが開いているときに使用されるファイル メニューと同じ。 (通常、他のメニュー項目は次の項目の前に配置されません。

1. 2 つの連続した区切り記号。

1. ファイルが開いているときに使用されるウィンドウ メニューと同じ (MDI アプリケーションのコンテナー アプリケーションの場合のみ)。 アプリケーションによっては、このグループに属する [オプション] メニューなどの他のメニューが含まれている場合があります。

    > [!NOTE]
    >  [ズーム] など、コンテナー ドキュメントのビューに影響する他のメニューが存在する場合があります。 これらのコンテナー メニューは、このメニュー リソースの 2 つの区切り記号の間に表示されます。

サーバー (コンポーネント) アプリケーションでは、インプレース アクティブ化専用の新しいメニューも作成する必要があります。 ファイルを開いているときに使用するメニューと同じで、データではなくサーバー文書を操作するファイルやウィンドウなどのメニュー項目は含まれていなければなりません。 通常、このメニューは次の要素で構成されます。

1. ファイルを開くときに使用されるメニューと同じ編集メニュー。

1. 区切り 記号。

1. Scribble サンプル アプリケーションの [ペン] メニューなどのオブジェクト編集メニュー。

1. 区切り 記号。

1. [ヘルプ] メニュー。

例として、コンテナーとサーバーのインプレース メニューのサンプルのレイアウトを見てみましょう。 各メニュー項目の詳細は、例を明確にするために削除されました。 コンテナーのインプレース メニューには、次のエントリがあります。

```
IDR_CONTAINERTYPE_CNTR_IP MENU PRELOAD DISCARDABLE
BEGIN
    POPUP "&File C1"
    MENUITEM SEPARATOR
    POPUP "&Zoom C2"
    MENUITEM SEPARATOR
    POPUP "&Options C3"
    POPUP "&Window C3"
END
```

連続する区切り記号は、サーバーのメニューの最初の部分がどこに向かうべきかを示します。 次に、サーバーのインプレース メニューを確認します。

```
IDR_SERVERTYPE_SRVR_IP MENU PRELOAD DISCARDABLE
BEGIN
    POPUP "&Edit S1"
    MENUITEM SEPARATOR
    POPUP "&Format S2"
    MENUITEM SEPARATOR
    POPUP "&Help S3"
END
```

ここでの区切り記号は、コンテナ メニュー項目の 2 番目のグループの配置先を示します。 このサーバーのオブジェクトがこのコンテナー内でアクティブ化されると、結果のメニュー構造は次のようになります。

```
BEGIN
    POPUP "&File C1"
    POPUP "&Edit S1"
    POPUP "&Zoom C2"
    POPUP "&Format S2"
    POPUP "&Options C3
    POPUP "&Window C3"
    POPUP "&Help S3"
END
```

ご覧のとおり、区切り記号は各アプリケーションのメニューの異なるグループに置き換えられています。

インプレース メニューに関連付けられているアクセラレータ テーブルも、サーバー アプリケーションによって提供される必要があります。 コンテナーは、コンテナーを独自のアクセラレータ テーブルに組み込みます。

埋め込みアイテムが所定の位置でアクティブになると、フレームワークはインプレース メニューを読み込みます。 次に、サーバー アプリケーションにインプレース アクティブ化のメニューを要求し、区切り記号がある場所に挿入します。 これは、メニューを組み合わせる方法です。 ファイルとウィンドウの配置を操作するためのコンテナーからメニューを取得し、アイテムを操作するためのサーバーからメニューを取得します。

## <a name="toolbars-and-status-bars"></a><a name="_core_toolbars_and_status_bars"></a>ツールバーとステータス バー

サーバー アプリケーションでは、新しいツール バーを作成し、そのビットマップを別のファイルに格納する必要があります。 アプリケーション ウィザードで生成されたアプリケーションは、このビットマップを ITOOLBAR というファイルに格納します。Bmp。 新しいツールバーは、サーバーの項目が所定の位置でアクティブ化されたときにコンテナー アプリケーションのツールバーに置き換わります。

このツール バーは、`COleIPFrameWnd`アプリケーション ウィザードによって作成された派生クラスに読み込まれます。 ステータス バーは、コンテナー アプリケーションによって処理されます。 インプレース フレーム ウィンドウの実装の詳細については、「[サーバー : サーバーの実装](../mfc/servers-implementing-a-server.md)」を参照してください。

## <a name="see-also"></a>関連項目

[メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[アクティブ化](../mfc/activation-cpp.md)<br/>
[サーバー](../mfc/servers.md)<br/>
[Containers](../mfc/containers.md)
