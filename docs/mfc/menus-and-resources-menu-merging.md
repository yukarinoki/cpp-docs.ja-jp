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
ms.openlocfilehash: 03d27443f90634b5d787eee25acc951d24178f42
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626217"
---
# <a name="menus-and-resources-menu-merging"></a>メニューとリソース : メニューの結合

この記事では、視覚的な編集と埋め込み先でのアクティブ化を適切に処理するために OLE ドキュメントアプリケーションに必要な手順について詳しく説明します。 インプレースライセンス認証では、コンテナーとサーバー (コンポーネント) アプリケーションの両方に対してチャレンジが発生します。 ユーザーは (コンテナードキュメントのコンテキスト内で) 同じフレームウィンドウに残りますが、実際には別のアプリケーション (サーバー) を実行しています。 そのためには、コンテナーとサーバーアプリケーションのリソースを調整する必要があります。

この記事では、次のトピックについて説明します。

- [メニューレイアウト](#_core_menu_layouts)

- [ツールバーとステータスバー](#_core_toolbars_and_status_bars)

## <a name="menu-layouts"></a><a name="_core_menu_layouts"></a>メニューレイアウト

最初の手順では、メニューレイアウトを調整します。 コンテナーアプリケーションでは、埋め込み項目が適切にアクティブ化されている場合にのみ使用される新しいメニューを作成する必要があります。 少なくとも、このメニューは次の順序で構成されている必要があります。

1. [ファイル] メニューは、ファイルが開いているときに使用したものと同じです。 (通常、次の項目の前に他のメニュー項目は配置されません)。

1. 2つの連続する区切り記号。

1. [ウィンドウ] メニューは、ファイルが開いているときに使用したものと同じです (MDI アプリケーションのコンテナーアプリケーションの場合のみ)。 アプリケーションによっては、[オプション] メニューなど、このグループに属する他のメニューがある場合があります。このメニューは、埋め込みアイテムが埋め込まれているときにメニューに残ります。

    > [!NOTE]
    >  [ズーム] など、コンテナードキュメントのビューに影響を与える他のメニューがある場合もあります。 これらのコンテナーメニューは、このメニューリソースの2つの区切り記号の間に表示されます。

サーバー (コンポーネント) アプリケーションでは、インプレースライセンス認証専用の新しいメニューも作成する必要があります。 これは、ファイルが開いているときに使用されるメニューに似ていますが、データではなくサーバードキュメントを操作するファイルやウィンドウなどのメニュー項目は使用しません。 通常、このメニューは次の要素で構成されています。

1. [編集] メニューは、ファイルが開いているときに使用したものと同じです。

1. セパレーター.

1. オブジェクト編集メニュー (Scribble サンプルアプリケーションの [ペン] メニューなど)。

1. セパレーター.

1. [ヘルプ] メニュー。

例については、コンテナーとサーバーのインプレースメニューのレイアウトに関する説明を参照してください。 各メニュー項目の詳細が削除され、例がわかりやすくなりました。 コンテナーのインプレースメニューには、次のエントリがあります。

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

連続する区切り記号は、サーバーのメニューの最初の部分がある場所を示します。 次に、サーバーのインプレースメニューを見てみましょう。

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

ここにある区切り記号は、コンテナーメニュー項目の2番目のグループがある場所を示しています。 このサーバーからのオブジェクトがアクティブになったときのメニュー構造は、次のようになります。

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

ご覧のとおり、区切り記号は、各アプリケーションのメニューの異なるグループに置き換えられています。

埋め込み先メニューに関連付けられているアクセラレータテーブルは、サーバーアプリケーションでも指定する必要があります。 コンテナーは、それを独自のアクセラレータテーブルに組み込みます。

埋め込みアイテムがインプレースでアクティブになると、フレームワークによって埋め込み先のメニューが読み込まれます。 次に、サーバーアプリケーションに対して、埋め込み先ライセンス認証のメニューを要求し、区切り記号が挿入された場所に挿入します。 メニューの結合方法を次に示します。 ファイルとウィンドウの配置を操作するためのメニューをコンテナーから取得し、その項目を操作するメニューをサーバーから取得します。

## <a name="toolbars-and-status-bars"></a><a name="_core_toolbars_and_status_bars"></a>ツールバーとステータスバー

サーバーアプリケーションでは、新しいツールバーを作成し、そのビットマップを別のファイルに格納する必要があります。 アプリケーションウィザードで生成されたアプリケーションは、このビットマップを ITOOLBAR という名前のファイルに格納します。.BMP. サーバーの項目が適切にアクティブ化されていて、通常のツールバーと同じ項目が含まれている必要がありますが、[ファイル] メニューと [ウィンドウ] メニューの項目を表すアイコンが削除されている場合、新しいツールバーはコンテナーアプリケーションのツールバーを置き換えます。

このツールバーは、 `COleIPFrameWnd` アプリケーションウィザードによって作成された、派生クラスで読み込まれます。 ステータスバーは、コンテナーアプリケーションによって処理されます。 埋め込み先フレームウィンドウの実装の詳細については、「サーバー [: サーバーの実装](servers-implementing-a-server.md)」を参照してください。

## <a name="see-also"></a>関連項目

[メニューとリソース (OLE)](menus-and-resources-ole.md)<br/>
[アクティブ化](activation-cpp.md)<br/>
[サーバー](servers.md)<br/>
[Containers](containers.md)
