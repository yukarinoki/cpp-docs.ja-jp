---
description: '詳細情報: ツールバーの基礎'
title: ツール バーに関する基本事項
ms.date: 11/04/2016
f1_keywords:
- RT_TOOLBAR
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
ms.openlocfilehash: ed52c5878482f2ff0fa1c31a133fd2948d21a76e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264389"
---
# <a name="toolbar-fundamentals"></a>ツール バーに関する基本事項

この記事では、アプリケーションウィザードでオプションを選択して、アプリケーションに既定のツールバーを追加できる基本的な MFC 実装について説明します。 取り上げるトピックは次のとおりです。

- [アプリケーションウィザードのツールバーオプション](#_core_the_appwizard_toolbar_option)

- [コードのツールバー](#_core_the_toolbar_in_code)

- [ツールバーリソースの編集](#_core_editing_the_toolbar_resource)

- [複数のツールバー](#_core_multiple_toolbars)

## <a name="the-application-wizard-toolbar-option"></a><a name="_core_the_appwizard_toolbar_option"></a> アプリケーションウィザードのツールバーオプション

既定のボタンを備えた単一のツールバーを取得するには、[ユーザーインターフェイス機能] というラベルの付いた [標準ドッキングツールバー] オプションを選択します。 これにより、次のようなコードがアプリケーションに追加されます。

- ツールバーオブジェクトを作成します。

- ドッキングまたはフローティングの機能など、ツールバーを管理します。

## <a name="the-toolbar-in-code"></a><a name="_core_the_toolbar_in_code"></a> コードのツールバー

ツールバーは、アプリケーションのクラスのデータメンバーとして宣言された [CToolBar](../mfc/reference/ctoolbar-class.md) オブジェクトです `CMainFrame` 。 つまり、ツールバーオブジェクトはメインフレームウィンドウオブジェクトに埋め込まれます。 これは、MFC がフレームウィンドウを作成するときにツールバーを作成し、フレームウィンドウを破棄するときにツールバーを破棄することを意味します。 次の部分クラス宣言は、マルチドキュメントインターフェイス (MDI) アプリケーションに対して、埋め込まれたツールバーと埋め込まれたステータスバーのデータメンバーを示しています。 また、メンバー関数のオーバーライドも示して `OnCreate` います。

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

ツールバーの作成は、で行わ `CMainFrame::OnCreate` れます。 MFC は、フレームのウィンドウを作成した後、表示される前に [OnCreate](../mfc/reference/cwnd-class.md#oncreate) を呼び出します。 `OnCreate`アプリケーションウィザードによって生成される既定のツールバーには、次のタスクがあります。

1. `CToolBar`オブジェクトの[create](../mfc/reference/ctoolbar-class.md#create) member 関数を呼び出して、基になる[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクトを作成します。

1. [Loadtoolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar)を呼び出して、ツールバーのリソース情報を読み込みます。

1. 関数を呼び出して、ドッキング、フローティング、およびツールのヒントを有効にします。 これらの呼び出しの詳細については、「 [ドッキングツールバーとフローティングツールバー](../mfc/docking-and-floating-toolbars.md)」を参照してください。

> [!NOTE]
> MFC の一般的なサンプル [DOCKTOOL](../overview/visual-cpp-samples.md) には、新旧両方の mfc ツールバーが含まれています。 を使用するツールバーでは、 `COldToolbar` 手順 2 `LoadBitmap` . から (ではなく `LoadToolBar` ) およびへの呼び出しが必要です `SetButtons` 。 新しいツールバーでは、を呼び出す必要があり `LoadToolBar` ます。

ドッキング、フローティング、およびツールヒントの呼び出しは省略可能です。 必要に応じて、からこれらの行を削除でき `OnCreate` ます。 結果は、固定されたままになっているツールバーで、float または redock できず、ツールヒントを表示できません。

## <a name="editing-the-toolbar-resource"></a><a name="_core_editing_the_toolbar_resource"></a> ツールバーリソースの編集

アプリケーションウィザードを使用して取得する既定のツールバーは、MFC バージョン4.0 で導入された **RT_TOOLBAR** カスタムリソースに基づいています。 このリソースは、 [ツールバーエディター](../windows/toolbar-editor.md)を使用して編集できます。 エディターでは、ボタンの追加、削除、再配置を簡単に行うことができます。 これには、Visual C++ の一般的なグラフィックエディターによく似たボタンのグラフィカルエディターが含まれています。 以前のバージョンの Visual C++ でツールバーを編集した場合は、今よりはるかに簡単にタスクを見つけることができます。

ツールバーボタンをコマンドに接続するには、ボタンにコマンド ID (など) を指定し `ID_MYCOMMAND` ます。 ツールバーエディターのボタンの [プロパティ] ページで、コマンド ID を指定します。 次に、コマンドのハンドラー関数を作成します (詳細については、「 [関数へのメッセージのマッピング](../mfc/reference/mapping-messages-to-functions.md) 」を参照してください)。

新しい [CToolBar](../mfc/reference/ctoolbar-class.md) メンバー関数は、 **RT_TOOLBAR** リソースを操作します。 [Loadtoolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) は、ツールバーボタンのイメージのビットマップを読み込むために [loadtoolbar](../mfc/reference/ctoolbar-class.md#loadbitmap) を使用するようになりました。また、ボタンのスタイルと接続ボタンをビットマップイメージに設定するための [setbuttons](../mfc/reference/ctoolbar-class.md#setbuttons) が使用されるようになりました。

ツールバーエディターの使用方法の詳細については、「 [ツールバーエディター](../windows/toolbar-editor.md)」を参照してください。

## <a name="multiple-toolbars"></a><a name="_core_multiple_toolbars"></a> 複数のツールバー

アプリケーションウィザードには、既定のツールバーが1つ用意されています。 アプリケーションに複数のツールバーが必要な場合は、ウィザードで生成された既定のツールバーのコードに基づいて、追加のツールバーのコードをモデル化できます。

コマンドの結果としてツールバーを表示する場合は、次のことを行う必要があります。

- ツールバーエディターを使用して新しいツールバーリソースを作成し、 `OnCreate` [loadtoolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) メンバー関数を使用して読み込みます。

- メインフレームウィンドウクラスに新しい [CToolBar](../mfc/reference/ctoolbar-class.md) オブジェクトを埋め込みます。

- に適切な関数を呼び出して、 `OnCreate` ツールバーのドッキングまたはフローティング、スタイルの設定などを行います。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [MFC ツールバーの実装 (ツールバーの概要情報)](../mfc/mfc-toolbar-implementation.md)

- [ツール バーのドッキングとフローティング](../mfc/docking-and-floating-toolbars.md)

- [ツール バーのツール ヒント](../mfc/toolbar-tool-tips.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md)クラスと[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)クラス

- [ToolBar コントロールの操作](../mfc/working-with-the-toolbar-control.md)

- [古い形式のツール バーの使用](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>関連項目

[MFC ツールバーの実装](../mfc/mfc-toolbar-implementation.md)
