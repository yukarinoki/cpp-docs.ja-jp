---
title: コンテナー:コンテナーの実装
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
ms.openlocfilehash: 0ab91316c9ee07296fbc46f9f17b3c46c71ee96f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271425"
---
# <a name="containers-implementing-a-container"></a>コンテナー:コンテナーの実装

この記事では、コンテナーを実装する手順を概説し、コンテナーの実装についての説明の詳細を提供するその他の記事へのリンクします。 オプションの OLE 機能を実装することも、これらの機能を説明する記事も一覧表示されます。

#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp から派生したクラスを準備するには

1. OLE ライブラリを呼び出すことによって初期化`AfxOleInit`で、`InitInstance`メンバー関数。

1. 呼び出す`CDocTemplate::SetContainerInfo`で`InitInstance`埋め込み項目が使用されているリソースをメニューとアクセラレータを割り当てるには、インプレースをアクティブ化します。 このトピックの詳細については、次を参照してください。[アクティベーション](../mfc/activation-cpp.md)します。

これらの機能は、MFC アプリケーション ウィザードを使用して、コンテナー アプリケーションを作成するときに自動的に提供します。 参照してください[MFC アプリケーション ウィザードを作成する](../mfc/reference/mfc-application-wizard.md)します。

#### <a name="to-prepare-your-view-class"></a>ビュー クラスを作成するには

1. 選択した項目のポインターを維持することでの追跡または一覧の選択項目への複数選択をサポートしている場合、ポインター。 `OnDraw`関数は、すべての OLE 項目を描画する必要があります。

1. オーバーライド`IsSelected`を渡された項目が現在選択されているかどうかを確認します。

1. 実装を`OnInsertObject`を表示するメッセージ ハンドラー、**オブジェクトの挿入** ダイアログ ボックス。

1. 実装を`OnSetFocus`メッセージに埋め込まれた項目をビューから、インプレース アクティブ OLE にフォーカスを転送するハンドラー。

1. 実装を`OnSize`OLE に通知するメッセージ ハンドラーが含まれているそのビューのサイズの変更を反映するように、四角形を変更する必要がある埋め込みアイテム。

これらの機能の実装が次の 1 つのアプリケーションと大幅に異なりますので、アプリケーション ウィザードは、基本的な実装のみを提供します。 これらの関数を適切に機能するアプリケーションの取得をカスタマイズする必要があります可能性があります。 これの例は、次を参照してください。、[コンテナー](../visual-cpp-samples.md)サンプル。

#### <a name="to-handle-embedded-and-linked-items"></a>埋め込みおよびリンクされた項目を処理するには

1. クラスを派生[COleClientItem](../mfc/reference/coleclientitem-class.md)します。 このクラスのオブジェクトに埋め込まれたまたは、OLE ドキュメントにリンクされている項目を表します。

1. オーバーライド`OnChange`、 `OnChangeItemPosition`、および`OnGetItemPosition`します。 これらの関数は、サイズ変更、配置、および埋め込みおよびリンクされた項目の変更を処理します。

アプリケーション ウィザードでは、クラスを派生させ、されますが、オーバーライドする必要があります`OnChange`し、手順 2. で、前の手順とその他の関数が一覧表示します。 スケルトンの実装は、これらの関数は、次の 1 つのアプリケーションから異なる方法で実装されるため、ほとんどのアプリケーションでカスタマイズする必要があります。 この例については、MFC のサンプルを参照してください。 [DRAWCLI](../visual-cpp-samples.md)と[コンテナー](../visual-cpp-samples.md)します。

項目の数は、OLE をサポートするために、コンテナー アプリケーションのメニュー構造に追加する必要があります。 これらの詳細については、次を参照してください。[メニューとリソース。コンテナーの変更点](../mfc/menus-and-resources-container-additions.md)します。

コンテナー アプリケーションで、次の機能の一部をサポートすることもします。

- 埋め込みアイテムを編集するときに、インプレース アクティブ化

   詳細については、次を参照してください。[アクティベーション](../mfc/activation-cpp.md)します。

- OLE アイテムの作成をドラッグ アンド サーバー アプリケーションから選択をドロップします。

   詳細については、次を参照してください。[ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)します。

- 埋め込みオブジェクトやコンテナー/サーバー アプリケーションの組み合わせへのリンク。

   詳細については、次を参照してください。[コンテナー。機能の高度な](../mfc/containers-advanced-features.md)します。

## <a name="see-also"></a>関連項目

[コンテナー](../mfc/containers.md)<br/>
[コンテナー:クライアント アイテム](../mfc/containers-client-items.md)
