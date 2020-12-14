---
description: '詳細については、「ActiveX コントロールコンテナー: ダイアログ以外のコンテナーでのコントロールの使用」を参照してください。'
title: 'ActiveX コントロール コンテナー : ダイアログ ベースではないコンテナーでのコントロールの使用'
ms.date: 11/04/2016
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
ms.openlocfilehash: 699f1faa5c88eb965a320c210de6e5e6c2ee94ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197674"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX コントロール コンテナー : ダイアログ ベースではないコンテナーでのコントロールの使用

SDI アプリケーションや MDI アプリケーションなどの一部のアプリケーションでは、アプリケーションのウィンドウにコントロールを埋め込む必要があります。 Visual C++ によって挿入されたラッパークラスの **create** member 関数を使用すると、ダイアログボックスを必要とせずに、コントロールのインスタンスを動的に作成できます。

**Create** member 関数には、次のパラメーターがあります。

*lpszWindowName*<br/>
コントロールのテキストまたはキャプションプロパティ (存在する場合) に表示されるテキストへのポインター。

*dwStyle*<br/>
Windows スタイル。 完全な一覧については、「 [CWnd:: CreateControl](reference/cwnd-class.md#createcontrol)」を参照してください。

*rect*<br/>
コントロールのサイズと位置を指定します。

*pParentWnd*<br/>
コントロールの親ウィンドウ (通常は) を指定し `CDialog` ます。 **NULL** にすることはできません。

*nID*<br/>
コントロール ID を指定します。これは、コントロールを参照するためにコンテナーによって使用されます。

この関数を使用して ActiveX コントロールを動的に作成する例の1つは、SDI アプリケーションのフォームビューです。 その後、アプリケーションのハンドラーにコントロールのインスタンスを作成でき `WM_CREATE` ます。

この例で `CMyView` は、はメインビュークラス、 `CCirc` はラッパークラス、CIRC です。H はヘッダー () です。H) を、ラッパークラスのファイルにします。

この機能の実装は、4つの手順からなるプロセスです。

### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>非ダイアログウィンドウで ActiveX コントロールを動的に作成するには

1. CIRC を挿入します。CMYVIEW の H。H は、クラス定義の直前に `CMyView` あります。

   [!code-cpp[NVC_MFC_AxCont#12](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]

1. `CCirc`CMYVIEW にあるクラス定義の protected セクションに、メンバー変数 (型) を追加し `CMyView` ます。始め

   [!code-cpp[NVC_MFC_AxCont#13](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]
    [!code-cpp[NVC_MFC_AxCont#14](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]

1. `WM_CREATE`メッセージハンドラーをクラスに追加 `CMyView` します。

1. ハンドラー関数で、 `CMyView::OnCreate` `Create` 親ウィンドウとしてポインターを使用して、コントロールの関数を呼び出し **`this`** ます。

   [!code-cpp[NVC_MFC_AxCont#15](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]

1. プロジェクトをリビルドします。 アプリケーションのビューが作成されるたびに、Circ コントロールが動的に作成されます。

## <a name="see-also"></a>関連項目

[ActiveX コントロールコンテナー](activex-control-containers.md)
