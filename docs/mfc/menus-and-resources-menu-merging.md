---
title: 'メニューとリソース: メニューのマージ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 252619872fc53e06629a4cbded7e3640131dc94a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351967"
---
# <a name="menus-and-resources-menu-merging"></a>メニューとリソース : メニューの結合
この記事では、ビジュアル編集を処理し、インプレース アクティブ化正しく OLE ドキュメント アプリケーションに必要な手順について説明します。 インプレース アクティブ化するという難題コンテナーとサーバーの両方 (コンポーネント) アプリケーションです。 ユーザーは、(コンテナー ドキュメントのコンテキスト) 内のフレーム ウィンドウに残りますが、実際には別のアプリケーション (サーバー) を実行しています。 これには、コンテナーとサーバー アプリケーションのリソース間の調整が必要です。  
  
 この記事で説明されているトピックは次のとおりです。  
  
- [メニューのレイアウト](#_core_menu_layouts)  
  
- [ツールバーとステータス バー](#_core_toolbars_and_status_bars)  
  
##  <a name="_core_menu_layouts"></a> メニューのレイアウト  
 最初の手順では、メニューのレイアウトを調整します。 詳細については、次を参照してください。、 **] メニューの [作成**」の「[メニュー プログラミングの考慮事項](https://msdn.microsoft.com/library/ms647557.aspx)Windows SDK に含まれています。  
  
 コンテナー アプリケーションでは、埋め込みアイテムは、インプレース アクティブ化されたときにのみ使用する新しいメニューを作成する必要があります。 少なくともこのメニューは表示されている順序で、次ので構成。  
  
1.  [ファイル] メニューと同じようにファイルを開いているときに使用します。 (通常他のメニュー項目を課しません次の項目の前にします。)  
  
2.  2 つの連続する区切り記号です。  
  
3.  [ウィンドウ] メニューと同じようにファイルを開いているときに使用 (場合にのみ、コンテナー アプリケーションを MDI アプリケーションで)。 一部のアプリケーションでは、その他のメニューの [オプション] メニューなどインプレース埋め込みアイテムがアクティブになったときメニューでは、このグループに属しているがあります。  
  
    > [!NOTE]
    >  ズームなど、コンテナー ドキュメントの表示に影響するその他のメニューである可能性があります。 このメニュー リソースの 2 つの区切り記号の間にこれらのコンテナーのメニューが表示されます。  
  
 サーバー (コンポーネント) のアプリケーションでは、インプレース アクティブ化用の新しいメニューを作成する必要がありますもできます。 ファイルと、データではなくサーバー ドキュメントを操作するウィンドウなどのメニュー項目のせずにファイルを開いているときに使用するメニューのようになります。 通常、このメニューは、次のとおり  
  
1.  [編集] メニューと同じようにファイルを開いているときに使用します。  
  
2.  区切り記号。  
  
3.  オブジェクトの Scribble サンプル アプリケーションで、[ペン] メニューなどのメニューを編集します。  
  
4.  区切り記号。  
  
5.  [ヘルプ] メニュー。  
  
 例については、コンテナーとサーバーのいくつかのサンプル インプレースでのメニューのレイアウトを確認します。 例をわかりやすくする、各メニュー項目の詳細が削除されました。 コンテナーのインプレース メニューには、次のエントリがあります。  
  
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
  
 連続する区切り記号は、サーバーのメニューの最初の部分の行き先を示しています。 これで、サーバーのインプレース メニューになります。  
  
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
  
 ここで、区切り記号は、コンテナーのメニュー項目の 2 番目のグループの移動先を示します。 このサーバーからのオブジェクトがこのコンテナー内でアクティブになると、結果として得られるメニュー構造は、このようになります。  
  
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
  
 ご覧のように、区切り記号、別のグループの各アプリケーションのメニューに置き換えられました。  
  
 インプレースでメニューに関連付けられているアクセラレータ テーブルは、サーバー アプリケーションでも指定する必要があります。 コンテナーでは、独自のアクセラレータ テーブルに組み込むことです。  
  
 インプレース埋め込みアイテムがアクティブになると、フレームワークは、[インプレース] メニューを読み込みます。 インプレースでライセンス認証のため、サーバー アプリケーション用のメニューを確認し、区切り記号が、それを挿入します。 これは、メニューの結合方法です。 コンテナーからファイルとウィンドウの配置に対する操作のためのメニューを表示し、サーバーからアイテムに対する操作のためのメニューを表示します。  
  
##  <a name="_core_toolbars_and_status_bars"></a> ツールバーとステータス バー  
 サーバー アプリケーションは、新しいツールバーを作成し、別のファイルにそのビットマップを格納する必要があります。 アプリケーション ウィザードで生成されたアプリケーションは、このビットマップを itoolbar ファイルに格納します。BMP です。 新しいツールバーは、サーバーのアイテムを標準ツールバーとして同じ項目が含まれますが、ファイルとウィンドウのメニュー上の項目を表すアイコンを削除する必要がありますとが代わりに、アクティブ化時に、コンテナー アプリケーションのツールバーを置換します。  
  
 このツールバーに読み込まれて、 `COleIPFrameWnd`-派生クラスに、アプリケーションのウィザードで作成します。 ステータス バーは、コンテナー アプリケーションによって処理されます。 埋め込み先フレーム ウィンドウの実装の詳細については、次を参照してください。[サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)です。  
  
## <a name="see-also"></a>関連項目  
 [メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)   
 [アクティブ化](../mfc/activation-cpp.md)   
 [サーバー](../mfc/servers.md)   
 [コンテナー](../mfc/containers.md)

