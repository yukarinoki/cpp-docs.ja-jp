---
title: 標準 Windows メッセージのハンドラー
ms.date: 11/04/2016
f1_keywords:
- afx_msg
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
ms.openlocfilehash: 9a136caf3a1d22151cb9cfd48e1cd3f999ab51ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370501"
---
# <a name="handlers-for-standard-windows-messages"></a>標準 Windows メッセージのハンドラー

標準 Windows メッセージ (**WM_**) の既定`CWnd`のハンドラは、 クラス であらかじめ定義されています。 クラス ライブラリは、これらのハンドラーの名前をメッセージ名に基づいて作成します。 たとえば **、WM_PAINT**メッセージのハンドラーは次`CWnd`のように宣言されます。

`afx_msg void OnPaint();`

**afx_msg**キーワードは、他の`CWnd`メンバー関数とハンドラーを区別することによって、C++**仮想**キーワードの効果を示唆します。 ただし、これらの関数は実際には仮想ではありません。代わりに、メッセージ マップを使用して実装されます。 メッセージ マップは、C++ 言語の拡張機能ではなく、標準プリプロセッサ マクロのみに依存します。 **afx_msg**キーワードは、前処理後に空白文字に解決されます。

基本クラスで定義されたハンドラーをオーバーライドするには、派生クラスで同じプロトタイプを持つ関数を定義し、ハンドラーのメッセージ マップ エントリを作成するだけです。 ハンドラーは、クラスのいずれかの基本クラスで同じ名前のハンドラーを "オーバーライド" します。

場合によっては、基本クラスと Windows がメッセージを操作できるように、ハンドラーは基本クラスでオーバーライドされたハンドラーを呼び出す必要があります。 オーバーライドで基本クラス ハンドラーを呼び出す場所は、状況によって異なります。 場合によっては、基本クラスのハンドラーを最初に呼び出し、場合によっては最後に呼び出す必要があります。 メッセージを自分で処理しない場合は、条件付きで基本クラスのハンドラーを呼び出すことがあります。 場合によっては、基本クラス ハンドラーを呼び出し、基本クラス ハンドラーによって返される値または状態に応じて、条件付きで独自のハンドラー コードを実行する必要があります。

> [!CAUTION]
> ハンドラーに渡される引数を基本クラスのハンドラーに渡す場合は、その引数を変更しても安全ではありません。 たとえば、`OnChar`ハンドラの*nChar*引数を変更したいと思うかもしれません (たとえば、大文字に変換する)。 この動作は非常にあいまいですが、この効果を実現する必要がある場合は、`CWnd`代わりに`SendMessage`メンバー関数を使用します。

指定されたメッセージをオーバーライドする適切な方法を決定する方法は、[クラス ウィザード](reference/mfc-class-wizard.md)が特定のメッセージのハンドラ関数のスケルトン`OnCreate`**(WM_CREATE**のハンドラなど) を書き込むときに、推奨されるオーバーライドされたメンバー関数の形式でスケッチします。 次の例では、ハンドラーが最初に基本クラス ハンドラーを呼び出し、-1 を返さないという条件でのみ処理を続行することをお勧めします。

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

規則により、これらのハンドラの名前はプレフィックス"On"で始まります。 これらのハンドラの中には引数を取らないものもあれば、いくつかを取るものもあります。 void**以外の**戻り値の型を持つものもあります。 すべての**WM_** メッセージの既定のハンドラーは、名前が "On" で`CWnd`始まるクラスのメンバー関数として*MFC リファレンス*に記載されています。 のメンバー関数宣言`CWnd`には、 **afx_msg**が付けられます。

## <a name="see-also"></a>関連項目

[メッセージ ハンドラ関数の宣言](../mfc/declaring-message-handler-functions.md)
