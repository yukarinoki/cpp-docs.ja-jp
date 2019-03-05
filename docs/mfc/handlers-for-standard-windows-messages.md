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
ms.openlocfilehash: d60ae52225ddd993c1768d0b5ce1989ab0192e45
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275390"
---
# <a name="handlers-for-standard-windows-messages"></a>標準 Windows メッセージのハンドラー

既定の標準 Windows メッセージのハンドラー (**wm _ で始まる**) クラスで定義済み`CWnd`します。 クラス ライブラリでは、メッセージ名に基づいて、これらのハンドラーの名前を行います。 たとえば、ハンドラーを**WM_PAINT**でメッセージが宣言されている`CWnd`として。

`afx_msg void OnPaint();`

**Afx_msg**キーワードは C++ の効果を提案**仮想**他のハンドラーを区別することによってキーワード`CWnd`メンバー関数。 ただし、関数は実際には仮想; 関数代わりにメッセージ マップを通じて実装されます。 メッセージ マップは、C++ 言語の拡張機能ではなく、標準のプリプロセッサ マクロのみに依存します。 **Afx_msg**キーワードは、前処理した後、空白文字に解決されます。

基底クラスで定義されているハンドラーを上書きするには、ハンドラーのメッセージ マップ エントリを作成して、派生クラスで同じプロトタイプを持つ関数を定義します。 ハンドラーは、クラスの基底クラスのいずれかで同じ名前のいずれかのハンドラーを「上書き」。

場合によっては、ハンドラーは、基底クラスと Windows でメッセージを処理できるように、基本クラスでオーバーライドされたハンドラーを呼び出す必要があります。 オーバーライドで基本クラスのハンドラーを呼び出すことは、状況によって異なります。 場合があります基本クラスのハンドラーを最初に呼び出すし、最後のことがありますする必要があります。 呼び出すことも、基本クラス ハンドラー条件付きで、自分でメッセージを処理しないように選択する場合。 場合があります基本クラスのハンドラーを呼び出すし、条件付きで値や基本クラスのハンドラーによって返される状態によっては、独自のハンドラー コードを実行する必要があります。

> [!CAUTION]
>  基本クラスのハンドラーに渡す場合、ハンドラーに渡される引数を変更するのには安全ではありません。 などを変更したくなるかもしれません、 *nChar*の引数、`OnChar`ハンドラー (大文字に変換するなど)。 この動作は、あまり知られてが、この効果を実現する必要がある場合は、使用、`CWnd`メンバー関数は`SendMessage`代わりにします。

プロパティ ウィンドウは、特定のメッセージ ハンドラー関数のスケルトンを書き込むときに、特定のメッセージをオーバーライドする適切な方法を決定する —、`OnCreate`のハンドラー **WM_CREATE**、たとえば-の形式で、スケッチ推奨のオーバーライドされたメンバー関数。 次の例は、ハンドラーが最初に基底クラスのハンドラーを呼び出すし、のみするという条件で-1 が返されませんを続行ことをお勧めします。

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

慣例により、これらのハンドラーの名前プレフィックスで始まる、"On" これらのハンドラーの引数を受け取らず、他のユーザーがいくつか。 戻り値の型が他にもあるいくつかも**void**します。 すべての既定のハンドラー **wm _ で始まる**メッセージに記載されて、 *MFC リファレンス*クラスのメンバー関数として`CWnd`名前が"On"で始まる メンバー関数宣言`CWnd`が付いて**afx_msg**します。

## <a name="see-also"></a>関連項目

[メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
