---
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
ms.openlocfilehash: d4e8793337beb2eed533fe04daf549ec21efc61d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373473"
---
# <a name="toolbar-fundamentals"></a>ツール バーに関する基本事項

この資料では、アプリケーション ウィザードでオプションを選択して、アプリケーションに既定のツール バーを追加できるようにする基本的な MFC 実装について説明します。 取り上げるトピックは次のとおりです。

- [アプリケーション ウィザードのツール バー オプション](#_core_the_appwizard_toolbar_option)

- [コード内のツールバー](#_core_the_toolbar_in_code)

- [ツール バー リソースの編集](#_core_editing_the_toolbar_resource)

- [複数のツールバー](#_core_multiple_toolbars)

## <a name="the-application-wizard-toolbar-option"></a><a name="_core_the_appwizard_toolbar_option"></a>アプリケーション ウィザードのツール バー オプション

既定のボタンを持つ単一のツールバーを取得するには、[ユーザー インターフェイス機能] というラベルの付いたページで [標準ドッキング] ツール バー オプションを選択します。 これにより、次のコードがアプリケーションに追加されます。

- ツール バー オブジェクトを作成します。

- ドッキング機能や浮動機能など、ツール バーを管理します。

## <a name="the-toolbar-in-code"></a><a name="_core_the_toolbar_in_code"></a>コード内のツールバー

ツール バーは、アプリケーションのクラスのデータ メンバーとして宣言された[CToolBar](../mfc/reference/ctoolbar-class.md)オブジェクトです`CMainFrame`。 つまり、ツールバー オブジェクトは、メイン フレーム ウィンドウ オブジェクトに埋め込まれます。 つまり、MFC は、フレーム ウィンドウを作成するときにツール バーを作成し、フレーム ウィンドウを破棄するときにツール バーを破棄します。 マルチ ドキュメント インターフェイス (MDI) アプリケーションの次の部分クラス宣言は、埋め込みツール バーと埋め込みステータス バーのデータ メンバーを示しています。 また、メンバー関数のオーバーライドも`OnCreate`示します。

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

ツールバーの作成は`CMainFrame::OnCreate`で行われます。 MFC は、フレームのウィンドウを作成した後、表示される前に[OnCreate](../mfc/reference/cwnd-class.md#oncreate)を呼び出します。 アプリケーション`OnCreate`ウィザードによって生成される既定のツール バー タスクは、次のとおりです。

1. `CToolBar`基になる[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクトを作成するオブジェクトの[作成](../mfc/reference/ctoolbar-class.md#create)メンバー関数を呼び出します。

1. ツール バー リソース情報を読み込むために[、LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar)を呼び出します。

1. ドッキング、フローティング、およびツール ヒントを有効にする関数を呼び出します。 これらの呼び出しの詳細については、「[ドッキング ツール バーとフローティング ツール バー](../mfc/docking-and-floating-toolbars.md)」を参照してください。

> [!NOTE]
> MFC の一般的なサンプル[DOCKTOOL](../overview/visual-cpp-samples.md)には、古い MFC ツール バーと新しい MFC ツール バーの両方の図が含まれています。 を使用`COldToolbar`するツールバーでは、手順 2 の`LoadBitmap`呼び出`LoadToolBar`し (`SetButtons`ではなく ) と に対する 呼び出しが必要です。 新しいツールバーには、 を`LoadToolBar`呼び出す必要があります。

ドッキング、フローティング、およびツール ヒントの呼び出しはオプションです。 必要に応じて、これらの`OnCreate`行を削除できます。 結果として、固定されたままのツール バーが浮き出したり再ドッキングしたりできず、ツール ヒントを表示できなくなります。

## <a name="editing-the-toolbar-resource"></a><a name="_core_editing_the_toolbar_resource"></a>ツールバー リソースの編集

アプリケーション ウィザードで使用する既定のツール バーは、MFC Version 4.0 で導入された**RT_TOOLBAR**カスタム リソースに基づいています。 このリソースは、 ツール[バー エディタ](../windows/toolbar-editor.md)で編集できます。 このエディタを使用すると、ボタンの追加、削除、再配置を簡単に行うことができます。 Visual C++ の一般的なグラフィックス エディターとよく似たボタンのグラフィカル エディターが含まれています。 以前のバージョンの Visual C++ でツールバーを編集した場合、この作業は簡単に行えます。

ツールバー ボタンをコマンドに接続するには、ボタンにコマンド ID (など`ID_MYCOMMAND`) を指定します。 ツールバー エディタのボタンのプロパティ ページで、コマンド ID を指定します。 次に、コマンドのハンドラー関数を作成します (詳細については[、「関数へのメッセージのマッピング](../mfc/reference/mapping-messages-to-functions.md)」を参照してください)。

新しい[CToolBar](../mfc/reference/ctoolbar-class.md)メンバー関数は **、RT_TOOLBAR**リソースを操作します。 [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar)は、ツール バー ボタン イメージのビットマップを読み込む[LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap)の代わりとなり、ボタンスタイルを設定し、ボタンをビットマップ イメージに接続する[SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons)を使用します。

ツールバー エディタの使用の詳細については、「[ツールバー エディタ](../windows/toolbar-editor.md)」を参照してください。

## <a name="multiple-toolbars"></a><a name="_core_multiple_toolbars"></a>複数のツールバー

アプリケーション ウィザードには、既定のツール バーが 1 つ用意されています。 アプリケーションに複数のツールバーが必要な場合は、ウィザードによって生成された既定のツールバーのコードに基づいて、追加のツール バーのコードをモデル化できます。

コマンドの結果としてツールバーを表示する場合は、次の手順を実行する必要があります。

- ツール バー エディターを使用して新しいツール バー`OnCreate`リソースを作成し、[それを LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar)メンバー関数で読み込みます。

- メイン フレーム ウィンドウ クラスに新しい[CToolBar](../mfc/reference/ctoolbar-class.md)オブジェクトを埋め込みます。

- 適切な関数呼び出`OnCreate`しを行って、ツールバーをドッキングまたはフロートしたり、スタイルを設定したりします。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [MFC ツール バーの実装 (ツール バーの概要情報)](../mfc/mfc-toolbar-implementation.md)

- [ツール バーのフローティングとドッキング](../mfc/docking-and-floating-toolbars.md)

- [ツールバーのツールヒント](../mfc/toolbar-tool-tips.md)

- [クラス](../mfc/reference/ctoolbar-class.md)[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [ToolBar コントロールの操作](../mfc/working-with-the-toolbar-control.md)

- [古い形式のツール バーの使用](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>関連項目

[MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)
