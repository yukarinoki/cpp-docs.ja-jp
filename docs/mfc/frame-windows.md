---
description: 詳細については、「フレームウィンドウ」を参照してください。
title: フレーム ウィンドウ
ms.date: 11/19/2018
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame windows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
ms.openlocfilehash: ee993b7f8314c28dba38c9ca607366f6fb93da1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193501"
---
# <a name="frame-windows"></a>フレーム ウィンドウ

Windows でアプリケーションを実行すると、ユーザーはフレームウィンドウに表示されるドキュメントを操作します。 ドキュメントフレームウィンドウには、フレームとフレーム内のコンテンツという2つの主要なコンポーネントがあります。 ドキュメントフレームウィンドウは、 [シングルドキュメントインターフェイス](sdi-and-mdi.md) (SDI) フレームウィンドウでも、 [マルチドキュメントインターフェイス](sdi-and-mdi.md) (MDI) 子ウィンドウでもかまいません。 ウィンドウは、ウィンドウの移動とサイズ変更、終了、最小化、最大化など、フレームウィンドウとのほとんどのユーザー操作を管理します。 フレーム内のコンテンツを管理します。

## <a name="frame-windows-and-views"></a>フレームウィンドウとビュー

MFC フレームワークは、フレームウィンドウを使用してビューを格納します。 2つのコンポーネント (フレームとコンテンツ) は、MFC の2つの異なるクラスによって表され、管理されます。 フレームウィンドウクラスはフレームを管理し、ビュークラスはコンテンツを管理します。 [ビュー] ウィンドウは、フレームウィンドウの子です。 ドキュメントを使用した描画とその他のユーザー操作は、フレームウィンドウのクライアント領域ではなく、ビューのクライアント領域で行われます。 フレームウィンドウは、ビューの周囲に表示されるフレームを提供します。これには、キャプションバーと、コントロールメニューなどの標準ウィンドウコントロール、ウィンドウを最小化および最大化するためのボタン、ウィンドウのサイズを変更するためのコントロールがあります。 "コンテンツ" はウィンドウのクライアント領域で構成され、子ウィンドウ (ビュー) によって完全に占有されます。 次の図は、フレームウィンドウとビューの関係を示しています。

![フレームウィンドウビュー](../mfc/media/vc37fx1.gif "フレーム ウィンドウ ビュー") <br/>
フレーム ウィンドウとビュー

## <a name="frame-windows-and-splitter-windows"></a>フレームウィンドウと分割ウィンドウ

もう1つの一般的な配置は、フレームウィンドウで複数のビューをフレームに分割することです。通常は [分割ウィンドウ](multiple-document-types-views-and-frame-windows.md)を使用します。 分割ウィンドウでは、フレームウィンドウのクライアント領域がスプリッターウィンドウによって使用されます。このウィンドウには、ペインと呼ばれる複数の子ウィンドウが表示されます。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

**一般的なフレームウィンドウのトピック**

- [ウィンドウ オブジェクト](window-objects.md)

- [フレームウィンドウクラス](frame-window-classes.md)

- [アプリケーションウィザードによって作成される Frame-Window クラス](frame-window-classes-created-by-the-application-wizard.md)

- [フレームウィンドウのスタイル](frame-window-styles-cpp.md)

- [フレーム ウィンドウの機能](what-frame-windows-do.md)

**フレームウィンドウの使用に関するトピック**

- [フレーム ウィンドウの使用](using-frame-windows.md)

- [ドキュメント フレーム ウィンドウの作成](creating-document-frame-windows.md)

- [フレーム ウィンドウの破棄](destroying-frame-windows.md)

- [MDI 子ウィンドウの管理](managing-mdi-child-windows.md)

- 複数のビューを含むフレームウィンドウでの[現在のビューの管理](managing-the-current-view.md)

- [メニュー、コントロールバー、およびアクセラレータ (フレームウィンドウのスペースを共有するその他のオブジェクト) の管理](managing-menus-control-bars-and-accelerators.md)

**特殊なフレームウィンドウ機能に関するトピック**

- ファイルエクスプローラーまたはファイルマネージャーからフレームウィンドウへの[ファイルのドラッグアンドドロップ](dragging-and-dropping-files-in-a-frame-window.md)

- [ダイナミックデータエクスチェンジ (DDE) への応答](responding-to-dynamic-data-exchange-dde.md)

- [Semimodal states: 状況依存の Windows ヘルプ (他のウィンドウアクションの調整)](orchestrating-other-window-actions.md)

- [Semimodal states: 印刷と印刷プレビュー (他のウィンドウアクションの調整)](orchestrating-other-window-actions.md)

**その他の種類のウィンドウに関するトピック**

- [ビューの使用](using-views.md)

- [ダイアログ ボックス](dialog-boxes.md)

- [コントロール](controls-mfc.md)

## <a name="see-also"></a>関連項目

[Windows](windows.md)
