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
ms.openlocfilehash: d967341cdb0197f1157ab9d253072f3d0d7aa46f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223149"
---
# <a name="handlers-for-standard-windows-messages"></a>標準 Windows メッセージのハンドラー

標準の Windows メッセージの既定のハンドラー (**WM_**) は、クラスで事前に定義されてい `CWnd` ます。 クラスライブラリは、これらのハンドラーの名前をメッセージ名に基づいて指定します。 たとえば、 **WM_PAINT**メッセージのハンドラーは、次のように `CWnd` として宣言されます。

`afx_msg void OnPaint();`

**Afx_msg**キーワードは、 **`virtual`** 他のメンバー関数からハンドラーを区別することによって、C++ のキーワードの効果を提案し `CWnd` ます。 ただし、これらの関数は実際には仮想ではないことに注意してください。代わりに、メッセージマップを使用して実装されます。 メッセージマップは、C++ 言語の拡張機能ではなく、標準のプリプロセッサマクロにのみ依存します。 **Afx_msg**キーワードは、前処理後に空白に解決されます。

基底クラスで定義されたハンドラーをオーバーライドするには、派生クラスで同じプロトタイプを持つ関数を定義し、ハンドラーのメッセージマップエントリを作成するだけです。 ハンドラーは、クラスの基底クラスにある同じ名前の任意のハンドラーを "オーバーライド" します。

場合によっては、ハンドラーが基底クラスのオーバーライドされたハンドラーを呼び出す必要があります。これにより、基本クラスと Windows がメッセージに対して動作できるようになります。 オーバーライドで基底クラスのハンドラーを呼び出す場所は、状況によって異なります。 場合によっては、最初に基底クラスのハンドラーを呼び出す必要があります。 自分でメッセージを処理しないことを選択した場合は、基本クラスのハンドラーを条件付きで呼び出すことがあります。 基本クラスのハンドラーによって返される値または状態に応じて、基本クラスのハンドラーを呼び出し、条件付きで独自のハンドラーコードを実行する必要がある場合があります。

> [!CAUTION]
> ハンドラーに渡される引数を基底クラスのハンドラーに渡す場合、その引数を変更するのは安全ではありません。 たとえば、ハンドラーの*nChar*引数を変更する場合があり `OnChar` ます (大文字に変換するなど)。 この動作はかなり不明瞭ですが、この効果を実現する必要がある場合は、 `CWnd` 代わりにメンバー関数を使用し `SendMessage` ます。

[クラスウィザード](reference/mfc-class-wizard.md)で特定のメッセージのハンドラー関数のスケルトン (たとえば、WM_CREATE のハンドラー) を書き込むときに、特定のメッセージをオーバーライドする適切な方法を決定する方法を `OnCreate` 次に示します。これは、推奨されるオーバーライドされるメンバー関数の形式でスケッチします。 **WM_CREATE** 次の例では、ハンドラーが最初に基底クラスのハンドラーを呼び出し、-1 を返さない条件に対してのみ処理を続行することをお勧めします。

[!code-cpp[NVC_MFCMessageHandling#3](codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

慣例により、これらのハンドラーの名前はプレフィックス "On" で始まります。 これらのハンドラーの中には引数を取らないものもあれば、いくつかのハンドラーがあります。 また、に以外の戻り値の型もあり **`void`** ます。 すべての**WM_** メッセージの既定のハンドラーは、"On" で始まる名前を持つクラスのメンバー関数として、 *MFC リファレンス*に記載されてい `CWnd` ます。 のメンバー関数宣言の `CWnd` 先頭には**afx_msg**が付きます。

## <a name="see-also"></a>関連項目

[メッセージハンドラー関数の宣言](declaring-message-handler-functions.md)
