---
title: 'テクニカル ノート 17: ウィンドウ オブジェクトの破棄'
ms.date: 11/04/2016
f1_keywords:
- vc.objects
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
ms.openlocfilehash: 9802669468cbbba89f23b8ac127358d1fc15ec9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370422"
---
# <a name="tn017-destroying-window-objects"></a>テクニカル ノート 17: ウィンドウ オブジェクトの破棄

この注では[、CWnd::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)メソッドの使用方法について説明します。 派生オブジェクトの`CWnd`割り当てをカスタマイズする場合は、このメソッドを使用します。 このメモでは、削除**演算子の**代わりに C++ Windows オブジェクトを破棄するために[CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)を使用する理由についても説明します。

このトピックのガイドラインに従うと、クリーンアップの問題はほとんどありません。 これらの問題は、C++ メモリの削除/解放を忘れたり、s などの`HWND`システム リソースを解放したり、オブジェクトを何度も解放したりすることが原因で発生する可能性があります。

## <a name="the-problem"></a>問題

各 Windows オブジェクト ( 派生`CWnd`クラスのオブジェクト ) は、C++`HWND`オブジェクトと . C++ オブジェクトはアプリケーションのヒープに割り当てられ`HWND`、ウィンドウ マネージャーによってシステム リソースに割り当てられます。 ウィンドウ オブジェクトを破棄する方法は複数あるため、システム リソースやメモリ リークを防ぐ一連の規則を用意する必要があります。 これらのルールは、オブジェクトと Windows ハンドルが複数回破棄されないようにする必要もあります。

## <a name="destroying-windows"></a>ウィンドウの破棄

Windows オブジェクトを破棄する 2 つの方法を次に示します。

- 呼`CWnd::DestroyWindow`び出しまたは`DestroyWindow`Windows API を呼び出します。

- 削除演算子を使用して明示的に**削除**します。

最初のケースは、はるかに一般的です。 このケースは、コードが直接呼び出`DestroyWindow`さない場合でも適用されます。 ユーザーがフレーム ウィンドウを直接閉じると、このアクションはWM_CLOSE メッセージを生成し、このメッセージに対する既定の`DestroyWindow.`応答は、親ウィンドウが破棄されると、Windows はすべての子を呼び出`DestroyWindow`します。

2 番目のケースは、Windows オブジェクトで**の delete**演算子の使用はまれです。 以下は **、delete**を使用することが正しい場合です。

## <a name="auto-cleanup-with-cwndpostncdestroy"></a>CWnd::PostNcdestroy を使用した自動クリーンアップ

システムが Windows ウィンドウを破棄すると、ウィンドウに最後に送信された Windows メッセージがWM_NCDESTROY。 そのメッセージ`CWnd`のデフォルトハンドラは[CWnd::OnNcDestroy です](../mfc/reference/cwnd-class.md#onncdestroy)。 `OnNcDestroy`は C++ オブジェクト`HWND`からデタッチし、仮想関数`PostNcDestroy`を呼び出します。 一部のクラスは、C++ オブジェクトを削除するためにこの関数をオーバーライドします。

の既定の実装`CWnd::PostNcDestroy`では、スタック フレームに割り当てられたウィンドウ オブジェクトや他のオブジェクトに埋め込まれているウィンドウ オブジェクトに適した、何も行いません。 これは、他のオブジェクトを使用せずにヒープに割り当てるように設計されたウィンドウ オブジェクトには適していません。 つまり、他の C++ オブジェクトに埋め込まれていないウィンドウ オブジェクトには適していません。

ヒープ上で単独で割り当てるように設計されたクラスは、`PostNcDestroy`このメソッドをオーバーライドして**この削除**を実行します。 このステートメントは、C++ オブジェクトに関連付けられているすべてのメモリを解放します。 既定`CWnd`のデストラクター呼び出`DestroyWindow`しm_hWnd NULL 以外*の場合でも*、クリーンアップ フェーズ中にハンドルがデタッチされ NULL になるため、無限再帰は行われません。

> [!NOTE]
> 通常、システムは`CWnd::PostNcDestroy`Windows WM_NCDESTROY メッセージを処理した後`HWND`に呼び出し、および C++ ウィンドウ オブジェクトが接続されなくなりました。 システムは、ほとんどの`CWnd::PostNcDestroy`[CWnd::Create](../mfc/reference/cwnd-class.md#create)呼び出しの実装で、障害が発生した場合にも呼び出します。 自動クリーンアップ規則については、このトピックで後述します。

## <a name="auto-cleanup-classes"></a>自動クリーンアップ クラス

次のクラスは自動クリーンアップ用に設計されていません。 通常、これらは他の C++ オブジェクトまたはスタックに埋め込まれます。

- すべての標準 Windows`CStatic`コントロール`CEdit` `CListBox`( 、 、、など )

- 直接派生した子ウィンドウ`CWnd`(カスタム コントロールなど)。

- 分割ウィンドウ (`CSplitterWnd`)

- 既定のコントロール バー (`CControlBar`コントロール バー オブジェクトの自動削除を有効にするための[テクニカル ノート 31](../mfc/tn031-control-bars.md)を参照してください)。

- スタック フレーム`CDialog`のモーダル ダイアログ用に設計されたダイアログ ( )

- を除くすべての`CFindReplaceDialog`標準ダイアログ

- クラス ウィザードによって作成される既定のダイアログ ボックス。

次のクラスは、自動クリーンアップ用に設計されています。 通常、ヒープ上に自分自身で割り当てられます。

- メイン フレーム ウィンドウ (直接または間接`CFrameWnd`に派生)。

- ビュー ウィンドウ (直接または間接的に`CView`から派生します)。

これらの規則を破る場合は、派生クラスのメソッド`PostNcDestroy`をオーバーライドする必要があります。 クラスに自動クリーンアップを追加するには、基本クラスを呼び出して **、このを削除**します。 クラスから自動クリーンアップを削除するには、直接基本`CWnd::PostNcDestroy`クラスの`PostNcDestroy`メソッドの代わりに直接呼び出します。

自動クリーンアップ動作を変更する最も一般的な用途は、ヒープに割り当てることができるモードレス ダイアログを作成することです。

## <a name="when-to-call-delete"></a>削除を呼び出すタイミング

C++ メソッドまたは`DestroyWindow`グローバル`DestroyWindow`API のいずれか、Windows オブジェクトを破棄するために呼び出すことをお勧めします。

MDI 子ウィンドウ`DestroyWindow`を破棄するためにグローバル API を呼び出しません。 代わりに仮想メソッド`CWnd::DestroyWindow`を使用する必要があります。

自動クリーンアップを実行しない C++ ウィンドウ オブジェクトの場合 **、VTBL**が正しい派生クラスを指していない場合`DestroyWindow`、`CWnd::~CWnd`デストラクターを呼び出そうとすると、delete 演算子を使用するとメモリ リークが発生する可能性があります。 これは、システムが呼び出す適切な破棄メソッドを見つけることができないために発生します。 削除`DestroyWindow`の代**delete**わりに使用すると、これらの問題を回避できます。 これは微妙なエラーになる可能性があるため、デバッグ モードでコンパイルすると、危険がある場合は次の警告が生成されます。

```
Warning: calling DestroyWindow in CWnd::~CWnd
    OnDestroy or PostNcDestroy in derived class will not be called
```

自動クリーンアップを実行する C++ Windows オブジェクトの場合は、 を`DestroyWindow`呼び出す必要があります。 **delete**演算子を直接使用すると、MFC 診断メモリ アロケータは、メモリを 2 回解放することを通知します。 2 つのオカレンスは、最初の明示的な呼び出しと、自動クリーンアップの実装で**のこれを削除**するための間接的な呼び出しです`PostNcDestroy`。

非自動`DestroyWindow`クリーンアップ オブジェクトを呼び出した後も C++ オブジェクトはそのままですが *、m_hWnd* NULL になります。 自動クリーンアップ`DestroyWindow`オブジェクトを呼び出すと、C++ オブジェクトはなくなり、C++ の自動クリーンアップ実装の delete 演算子によって解放`PostNcDestroy`されます。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
