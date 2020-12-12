---
description: '詳細情報: テクニカルノート 17: ウィンドウオブジェクトの破棄'
title: 'テクニカル ノート 17: ウィンドウ オブジェクトの破棄'
ms.date: 11/04/2016
f1_keywords:
- vc.objects
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
ms.openlocfilehash: 86ce1255055db98a247ac8997aa7d146eb135583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215912"
---
# <a name="tn017-destroying-window-objects"></a>テクニカル ノート 17: ウィンドウ オブジェクトの破棄

このメモでは、 [CWnd::P ostncdestroy](../mfc/reference/cwnd-class.md#postncdestroy) メソッドの使用について説明します。 派生オブジェクトのカスタマイズされた割り当てを行う場合は、このメソッドを使用し `CWnd` ます。 このメモでは、 [CWnd::D estroywindow](../mfc/reference/cwnd-class.md#destroywindow) を使用して、演算子ではなく C++ Windows オブジェクトを破棄する必要がある理由についても説明し **`delete`** ます。

このトピックのガイドラインに従うと、クリーンアップの問題がほとんど発生しません。 これらの問題は、C++ メモリの削除/解放、のようなシステムリソースの解放、オブジェクトの解放などの問題が原因で発生する可能性が `HWND` あります。

## <a name="the-problem"></a>問題

各 windows オブジェクト (から派生したクラスのオブジェクト `CWnd` ) は、C++ オブジェクトとの両方を表し `HWND` ます。 C++ オブジェクトはアプリケーションのヒープに割り当てられ、 `HWND` はウィンドウマネージャーによってシステムリソースに割り当てられます。 ウィンドウオブジェクトを破棄するにはいくつかの方法があるため、システムリソースやメモリリークを防ぐ一連のルールを用意する必要があります。 また、これらのルールでは、オブジェクトと Windows ハンドルが複数回破棄されるのを防ぐ必要があります。

## <a name="destroying-windows"></a>破棄 (ウィンドウを)

Windows オブジェクトを破棄するには、次の2つの許可された方法があります。

- `CWnd::DestroyWindow`または WINDOWS API を呼び出して `DestroyWindow` います。

- 演算子を使用して明示的に削除 **`delete`** します。

最初のケースは、最も一般的なものです。 このケースは、コードがを直接呼び出していない場合でも適用さ `DestroyWindow` れます。 ユーザーがフレームウィンドウを直接閉じると、この操作によって WM_CLOSE メッセージが生成されます。このメッセージに対する既定の応答は、 `DestroyWindow.` 親ウィンドウが破棄されたときに呼び出され、 `DestroyWindow` そのすべての子に対して Windows が呼び出されます。

2番目のケースでは、 **`delete`** Windows オブジェクトに対して演算子を使用することはめったにありません。 次に、を使用する場合に適切な選択を行うケースをいくつか示し **`delete`** ます。

## <a name="auto-cleanup-with-cwndpostncdestroy"></a>CWnd を使用した自動クリーンアップ::P ostNcDestroy

システムが Windows ウィンドウを破棄すると、ウィンドウに最後に送信された Windows メッセージが WM_NCDESTROY されます。 `CWnd`そのメッセージの既定のハンドラーは、 [CWnd:: OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)です。 `OnNcDestroy` は、 `HWND` C++ オブジェクトからをデタッチし、仮想関数を呼び出し `PostNcDestroy` ます。 一部のクラスでは、この関数をオーバーライドして C++ オブジェクトを削除しています。

の既定の実装で `CWnd::PostNcDestroy` は何も実行されません。これは、スタックフレームに割り当てられているウィンドウオブジェクト、または他のオブジェクトに埋め込まれたウィンドウオブジェクトに適しています。 これは、他のオブジェクトを使用せずにヒープに割り当てられるように設計されたウィンドウオブジェクトには適していません。 言い換えると、他の C++ オブジェクトに埋め込まれていないウィンドウオブジェクトには適していません。

ヒープに対してのみ割り当てられるように設計されたクラスは、メソッドをオーバーライドして、 `PostNcDestroy` **削除** を実行します。 このステートメントは、C++ オブジェクトに関連付けられているメモリを解放します。 `CWnd`M_hWnd が NULL 以外の場合に既定のデストラクターがを呼び出す場合でも `DestroyWindow` 、クリーンアップフェーズ中にハンドルがデタッチされ、NULL になるため、無限再帰は発生しません。 

> [!NOTE]
> システムは通常、 `CWnd::PostNcDestroy` Windows WM_NCDESTROY メッセージを処理した後にを呼び出し、 `HWND` と C++ ウィンドウオブジェクトが接続されなくなります。 システムは、 `CWnd::PostNcDestroy` エラーが発生した場合に、ほとんどの [CWnd:: Create](../mfc/reference/cwnd-class.md#create) 呼び出しの実装でもを呼び出します。 自動クリーンアップの規則については、このトピックの後半で説明します。

## <a name="auto-cleanup-classes"></a>自動クリーンアップクラス

次のクラスは自動クリーンアップ用には設計されていません。 これらは通常、他の C++ オブジェクトまたはスタックに埋め込まれています。

- すべての標準の Windows コントロール ( `CStatic` 、、 `CEdit` `CListBox` など)。

- から直接派生した子ウィンドウ `CWnd` (カスタムコントロールなど)。

- 分割ウィンドウ ( `CSplitterWnd` )。

- 既定のコントロールバー (から派生したクラス `CControlBar` 、コントロールバーオブジェクトの自動削除を有効にするための [テクニカルノート 31](../mfc/tn031-control-bars.md) を参照)。

- ダイアログ ( `CDialog` ) は、スタックフレームのモーダルダイアログ用に設計されています。

- を除くすべての標準ダイアログ `CFindReplaceDialog` 。

- ClassWizard によって作成された既定のダイアログ。

次のクラスは自動クリーンアップ用に設計されています。 通常、ヒープに対して割り当てられます。

- メインフレームウィンドウ (から直接または間接的に派生 `CFrameWnd` )。

- (から直接または間接的に派生した) ウィンドウを表示 `CView` します。

これらの規則を解除する場合は、派生クラスのメソッドをオーバーライドする必要があり `PostNcDestroy` ます。 クラスに自動クリーンアップを追加するには、基底クラスを呼び出してから、 **このを削除** します。 自動クリーンアップをクラスから削除するには、直接 `CWnd::PostNcDestroy` `PostNcDestroy` 基底クラスのメソッドではなく、直接を呼び出します。

自動クリーンアップ動作を変更する最も一般的な方法は、ヒープに割り当てることができるモードレスダイアログを作成することです。

## <a name="when-to-call-delete"></a>Delete を呼び出すタイミング

を呼び出して、 `DestroyWindow` C++ メソッドまたはグローバル API のいずれかで Windows オブジェクトを破棄することをお勧めし `DestroyWindow` ます。

`DestroyWindow`MDI 子ウィンドウを破棄するために、グローバル API を呼び出さないでください。 代わりに、仮想メソッドを使用する必要があり `CWnd::DestroyWindow` ます。

自動クリーンアップを実行しない C++ ウィンドウオブジェクトの場合、演算子を使用する **`delete`** と、 `DestroyWindow` VTBL が `CWnd::~CWnd` 正しく派生したクラスを指していない場合にデストラクターでを呼び出そうとすると、メモリリークが発生する可能性があります。 これは、システムが適切な破棄メソッドを見つけて呼び出すことができないために発生します。 で `DestroyWindow` はなくを使用すると、 **`delete`** これらの問題を回避できます。 これは微妙なエラーである可能性があるため、デバッグモードでコンパイルすると、リスクが発生した場合に次の警告が生成されます。

```
Warning: calling DestroyWindow in CWnd::~CWnd
    OnDestroy or PostNcDestroy in derived class will not be called
```

自動クリーンアップを実行する C++ Windows オブジェクトの場合は、を呼び出す必要があり `DestroyWindow` ます。 演算子を直接使用する場合は **`delete`** 、メモリを2回解放することを示す MFC 診断メモリアロケーターが通知されます。 最初の明示的な呼び出しと、の自動クリーンアップの実装で **このを削除** する間接呼び出しの2回が発生し `PostNcDestroy` ます。

`DestroyWindow`非自動クリーンアップオブジェクトでを呼び出した後も、C++ オブジェクトは引き続き使用されますが、 *M_HWND* は NULL になります。 自動クリーンアップオブジェクトでを呼び出すと、 `DestroyWindow` c++ オブジェクトが失われ、の自動クリーンアップ実装で c++ delete 演算子によって解放され `PostNcDestroy` ます。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
