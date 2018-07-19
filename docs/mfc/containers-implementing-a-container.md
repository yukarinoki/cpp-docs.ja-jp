---
title: 'コンテナー: コンテナーの実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 066c032a18b2fedc88884b7e6eee55f07fcf43ad
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930076"
---
# <a name="containers-implementing-a-container"></a>コンテナー : コンテナーの実装
ここでは、コンテナーを実装する手順を概説し、詳細な説明については、コンテナーの実装を提供する他の記事を紹介します。 実装することもいくつかのオプションの OLE 機能やこれらの機能を説明する記事も一覧表示されます。  
  
#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp の派生クラスを準備するには  
  
1.  OLE ライブラリを呼び出すことによって初期化`AfxOleInit`で、`InitInstance`メンバー関数。  
  
2.  呼び出す`CDocTemplate::SetContainerInfo`で`InitInstance`埋め込みアイテムが使用されているリソースをメニューとアクセラレータを割り当てるには、インプレースをアクティブ化します。 このトピックの詳細については、次を参照してください。[アクティベーション](../mfc/activation-cpp.md)です。  
  
 これらの機能は、MFC アプリケーション ウィザードを使用して、コンテナー アプリケーションを作成するときに自動的に提供します。 参照してください[MFC アプリケーション ウィザードを作成する](../mfc/reference/mfc-application-wizard.md)です。  
  
#### <a name="to-prepare-your-view-class"></a>ビュー クラスを作成するには  
  
1.  選択したアイテムを指すポインターを保持の追跡またはボックスの一覧を選択した項目の複数の選択をサポートする場合のポインターのです。 `OnDraw`関数は、すべての OLE 項目を描画する必要があります。  
  
2.  オーバーライド`IsSelected`に渡された項目が現在選択されているかどうかを確認します。  
  
3.  実装する`OnInsertObject`を表示するメッセージ ハンドラー、**オブジェクトの挿入** ダイアログ ボックス。  
  
4.  実装する`OnSetFocus`メッセージ ハンドラー フォーカスを移動するビューから、インプレース アクティブ ole 埋め込みアイテムです。  
  
5.  実装する`OnSize`OLE に通知するメッセージ ハンドラーの埋め込みをアイテムを含むビューのサイズの変更を反映するように、四角形を変更する必要があります。  
  
 これらの機能の実装が次の 1 つのアプリケーションと大幅に異なりますので、アプリケーションのウィザードは、基本的な実装のみを提供します。 これらの関数をアプリケーションを正常に機能をカスタマイズする必要が可能性があります。 この例は、次を参照してください。、[コンテナー](../visual-cpp-samples.md)サンプルです。  
  
#### <a name="to-handle-embedded-and-linked-items"></a>埋め込みまたはリンクされた項目を処理するには  
  
1.  クラスを派生[COleClientItem](../mfc/reference/coleclientitem-class.md)です。 このクラスのオブジェクトに埋め込まれているまたは OLE ドキュメントにリンクされている項目を表します。  
  
2.  オーバーライド`OnChange`、 `OnChangeItemPosition`、および`OnGetItemPosition`です。 これらの関数は、サイズ変更、配置、および埋め込みまたはリンクされた項目の変更を処理します。  
  
 アプリケーションのウィザードは、クラスが派生されますが、オーバーライドする必要があります`OnChange`し、他の関数がそれに前の手順では、手順 2. で一覧表示します。 スケルトンの実装は、次の 1 つのアプリケーションからこれらの関数は異なる方法で実装されているため、ほとんどのアプリケーション用にカスタマイズする必要があります。 この例については、MFC のサンプルを参照してください。 [DRAWCLI](../visual-cpp-samples.md)と[コンテナー](../visual-cpp-samples.md)です。  
  
 OLE をサポートするために、コンテナー アプリケーションのメニュー構造を項目の数を追加する必要があります。 これらの詳細については、次を参照してください。[メニューとリソース: コンテナーの変更点](../mfc/menus-and-resources-container-additions.md)です。  
  
 コンテナー アプリケーションで、次の機能の一部をサポートすることがあります。  
  
-   埋め込みアイテムの編集時に、インプレース アクティブ化  
  
     詳細については、次を参照してください。[アクティベーション](../mfc/activation-cpp.md)です。  
  
-   OLE アイテムの作成にドラッグして、サーバー アプリケーションから選択範囲を削除しています。  
  
     詳細については、次を参照してください。[ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)です。  
  
-   埋め込みオブジェクトやコンテナー/サーバー アプリケーションの組み合わせにリンクします。  
  
     詳細については、次を参照してください。[コンテナー: 高度な機能](../mfc/containers-advanced-features.md)します。  
  
## <a name="see-also"></a>関連項目  
 [コンテナー](../mfc/containers.md)   
 [コンテナー: クライアント アイテム](../mfc/containers-client-items.md)

