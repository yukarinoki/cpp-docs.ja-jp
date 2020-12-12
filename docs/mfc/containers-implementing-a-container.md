---
description: '詳細については、「コンテナー: コンテナーの実装」を参照してください。'
title: 'コンテナー : コンテナーの実装'
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
ms.openlocfilehash: 24e3c7f7d4546ebe9b103af0e9ca0d9694b25d2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310324"
---
# <a name="containers-implementing-a-container"></a>コンテナー : コンテナーの実装

この記事では、コンテナーを実装する手順の概要を説明し、コンテナーの実装に関する詳細な説明が記載されている他の記事を紹介します。 また、実装するオプションの OLE 機能と、これらの機能について説明している記事も示しています。

#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp 派生クラスを準備するには

1. メンバー関数でを呼び出して、OLE ライブラリを初期化し `AfxOleInit` `InitInstance` ます。

1. `CDocTemplate::SetContainerInfo` `InitInstance` 埋め込み項目がインプレースでアクティブになったときに使用されるメニューおよびアクセラレータリソースを割り当てるには、を呼び出します。 このトピックの詳細については、「 [Activation](activation-cpp.md)」を参照してください。

これらの機能は、MFC アプリケーションウィザードを使用してコンテナーアプリケーションを作成するときに、自動的に提供されます。 「 [MFC EXE プログラムの作成」を](reference/mfc-application-wizard.md)参照してください。

#### <a name="to-prepare-your-view-class"></a>ビュークラスを準備するには

1. 選択された項目を、ポインター、または複数選択をサポートしている場合はポインターのリストを保持して、選択した項目を追跡します。 `OnDraw`関数は、すべての OLE 項目を描画する必要があります。

1. をオーバーライドし `IsSelected` て、渡された項目が現在選択されているかどうかを確認します。

1. `OnInsertObject`[**オブジェクトの挿入**] ダイアログボックスを表示するためのメッセージハンドラーを実装します。

1. `OnSetFocus`ビューからインプレースアクティブ OLE 埋め込みアイテムにフォーカスを移すためのメッセージハンドラーを実装します。

1. メッセージハンドラーを実装し `OnSize` て、OLE 埋め込みアイテムに四角形を変更し、それを含むビューのサイズの変更を反映する必要があることを通知します。

これらの機能の実装はアプリケーションによって大きく異なるため、アプリケーションウィザードには基本的な実装のみが用意されています。 アプリケーションを正しく機能させるには、これらの関数をカスタマイズする必要があります。 この例については、 [コンテナー](../overview/visual-cpp-samples.md) のサンプルを参照してください。

#### <a name="to-handle-embedded-and-linked-items"></a>埋め込み項目とリンクされた項目を処理するには

1. [COleClientItem](reference/coleclientitem-class.md)からクラスを派生させます。 このクラスのオブジェクトは、OLE ドキュメントに埋め込まれている、またはリンクされている項目を表します。

1. `OnChange`、 `OnChangeItemPosition` 、およびをオーバーライド `OnGetItemPosition` します。 これらの関数は、埋め込みおよびリンクされた項目のサイズ変更、配置、および変更を処理します。

クラスはアプリケーションウィザードによって派生されますが、前の手順の `OnChange` 手順 2. で一覧表示された他の関数をオーバーライドする必要がある場合があります。 スケルトン実装は、アプリケーションごとに異なる方法で実装されるため、ほとんどのアプリケーションに合わせてカスタマイズする必要があります。 この例については、MFC のサンプル [DRAWCLI](../overview/visual-cpp-samples.md) と [コンテナー](../overview/visual-cpp-samples.md)を参照してください。

OLE をサポートするには、コンテナーアプリケーションのメニュー構造に複数の項目を追加する必要があります。 これらの詳細については、「 [メニューとリソース: コンテナーの追加](menus-and-resources-container-additions.md)」を参照してください。

コンテナーアプリケーションで、次の機能の一部をサポートすることもできます。

- 埋め込み項目を編集するときのインプレースアクティブ化。

   詳細については、「 [Activation](activation-cpp.md)」を参照してください。

- サーバーアプリケーションから選択項目をドラッグアンドドロップして、OLE 項目を作成します。

   詳細については、「 [OLE ドラッグアンドドロップ](drag-and-drop-ole.md)」を参照してください。

- 埋め込みオブジェクトまたは組み合わせたコンテナー/サーバーアプリケーションへのリンク。

   詳細については、「 [コンテナー: 高度な機能](containers-advanced-features.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Containers](containers.md)<br/>
[コンテナー: クライアントアイテム](containers-client-items.md)
