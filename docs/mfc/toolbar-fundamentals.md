---
title: ツールバーに関する基本事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RT_TOOLBAR
dev_langs:
- C++
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5240cf50b35b2e1a300071ccb6cc15a065ac364e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951638"
---
# <a name="toolbar-fundamentals"></a>ツール バーに関する基本事項
この記事では、アプリケーションのウィザードでオプションを選択して、アプリケーションに既定のツールバーを追加できる基本的な MFC 実装について説明します。 トピックは次のとおりです。  
  
-   [アプリケーション ウィザード [ツールバー] オプション](#_core_the_appwizard_toolbar_option)  
  
-   [ツールバーのコード](#_core_the_toolbar_in_code)  
  
-   [ツール バー リソースの編集](#_core_editing_the_toolbar_resource)  
  
-   [複数のツールバー](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a> アプリケーション ウィザード ツールバーのオプション  
 既定のボタンを持つ 1 つのツールバーを取得するには、標準ドッキング ツールバーで、オプションというラベルの付いたユーザー インターフェイス機能 ページを選択します。 コードをアプリケーションに追加します。  
  
-   ツール バー オブジェクトを作成します。  
  
-   ツールバーをドッキングまたはフローティングする機能を管理します。  
  
##  <a name="_core_the_toolbar_in_code"></a> ツールバーのコード  
 ツールバーは、 [CToolBar](../mfc/reference/ctoolbar-class.md)オブジェクトは、アプリケーションのデータ メンバーとして宣言されている`CMainFrame`クラスです。 つまり、ツールバーのオブジェクトは、メイン フレーム ウィンドウ オブジェクトに埋め込まれます。 これは、フレーム ウィンドウを作成およびフレーム ウィンドウが破棄されると、ツールバーの破棄時に、MFC でツールバーを作成することを意味します。 複数ドキュメント インターフェイス (MDI) アプリケーションの場合、次の部分クラス宣言では、埋め込みのツールバーに表示される埋め込みステータス バーのデータ メンバーを示します。 オーバーライドも示しています、`OnCreate`メンバー関数。  
  
 [!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]  
  
 ツールバーの作成は、`CMainFrame::OnCreate`です。 MFC 呼び出し[OnCreate](../mfc/reference/cwnd-class.md#oncreate)可視になりますが、そのフレームのウィンドウの作成後にします。 既定値`OnCreate`ツールバーの次のタスクには、アプリケーションのウィザードが生成されます。  
  
1.  呼び出し、`CToolBar`オブジェクトの[作成](../mfc/reference/ctoolbar-class.md#create)メンバー関数を作成、基になる[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクト。  
  
2.  呼び出し[LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar)ツール バー リソース情報を読み込めません。  
  
3.  ドッキング、フローティング、およびツール ヒントを有効にする関数を呼び出します。 これらの呼び出しに関する詳細については、「アーティクル[ドッキング ツールバーとフローティング ツールバー](../mfc/docking-and-floating-toolbars.md)です。  
  
> [!NOTE]
>  MFC 標準サンプル[DOCKTOOL](../visual-cpp-samples.md)新旧両方の MFC ツールバーの図が含まれています。 使用するツールバー`COldToolbar`に手順 2. で呼び出しが必要`LoadBitmap`(なく`LoadToolBar`) および`SetButtons`です。 新しいツールバーへの呼び出しを必要と`LoadToolBar`です。  
  
 ドッキング、フローティング、およびツール ヒントの呼び出しはオプションです。 これらの行を削除する`OnCreate`したい場合。 結果は、固定、フローティングやできず、ツール ヒントを表示できませんに残っているツールバーです。  
  
##  <a name="_core_editing_the_toolbar_resource"></a> ツール バー リソースの編集  
 アプリケーション ウィザードを使用して取得する既定のツールバーがに基づいて、 **RT_TOOLBAR**カスタム リソースを MFC バージョン 4.0 で導入されました。 このリソースを編集できる、[ツール バー エディター](../windows/toolbar-editor.md)です。 エディターでは、追加、削除、およびボタンを再配置を簡単にすることができます。 Visual C での一般的なグラフィックス エディターによく似ているボタン用のグラフィカル エディターが含まれています。 以前のバージョンの Visual C でツールバーを編集する場合がありますタスクはるかに簡単ようになりました。  
  
 ツール バー ボタンをコマンドに接続するにするなどの指定、ボタン コマンド ID`ID_MYCOMMAND`です。 ツール バー エディターのボタンのプロパティ ページで、コマンド ID を指定します。 コマンドのハンドラー関数を作成し、(を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)詳細については)。  
  
 新しい[CToolBar](../mfc/reference/ctoolbar-class.md)メンバー関数は、 **RT_TOOLBAR**リソース。 [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar)の場所では、 [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap)ツール バー ボタンのイメージ、ビットマップの読み込みと[SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons)ボタンのスタイルを設定し、ビットマップ イメージとボタンを接続します。  
  
 ツール バー エディターの使用に関する詳細については、「[ツール バー エディター](../windows/toolbar-editor.md)です。  
  
##  <a name="_core_multiple_toolbars"></a> 複数のツールバー  
 アプリケーションのウィザードは、1 つの既定のツールバーを提供します。 アプリケーションで複数のツールバーを必要がある場合、コード内の既定のツールバーのウィザードで生成されたコードに基づく追加のツールバーをモデル化できます。  
  
 コマンドの結果として、ツールバーを表示する場合は、する必要があります。  
  
-   ツールバー エディターを使って新しいツール バー リソースを作成および読み込むで`OnCreate`で、 [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar)メンバー関数。  
  
-   新しい埋め込み[CToolBar](../mfc/reference/ctoolbar-class.md)メイン フレーム ウィンドウ クラスのオブジェクト。  
  
-   適切な関数呼び出しに make`OnCreate`をドッキングまたはフローティング ツールバーのスタイルを設定します。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [MFC ツールバーの実装 (ツールバーに概要情報)](../mfc/mfc-toolbar-implementation.md)  
  
-   [ドッキングとフローティング ツールバー](../mfc/docking-and-floating-toolbars.md)  
  
-   [ツールバーのツール ヒント](../mfc/toolbar-tool-tips.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md)と[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)クラス  
  
-   [ツール バー コントロールの操作](../mfc/working-with-the-toolbar-control.md)  
  
-   [古いツールバーの使用方法](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)

