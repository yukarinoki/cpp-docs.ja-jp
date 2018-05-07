---
title: 既定の印刷を行う方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2cf5b4a9bda3506a9558d5b723020dfe6d43396
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-default-printing-is-done"></a>既定の印刷プロセス
この記事では、MFC フレームワークの観点から Windows の既定の印刷プロセスについて説明します。  
  
 ビュー クラスがという名前のメンバー関数を持つ MFC アプリケーションで`OnDraw`すべての描画コードを格納しています。 `OnDraw` ポインターを受け取り、 [CDC](../mfc/reference/cdc-class.md)オブジェクトをパラメーターとして。 ある`CDC`オブジェクトによって生成された画像を受信するデバイス コンテキストを表します`OnDraw`です。 ドキュメントを表示するウィンドウが受信すると、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージ、フレームワークによって`OnDraw`し、画面のデバイス コンテキストを渡します (、 [CPaintDC](../mfc/reference/cpaintdc-class.md)オブジェクトを特定する)。 したがって、`OnDraw`の出力が画面にします。  
  
 Windows 用のプログラミングでは、プリンターへの出力は、画面に出力を送信することをよく似ています。 これは、Windows グラフィックス デバイス インターフェイス (GDI) がハードウェアに依存しないのためです。 適切なデバイス コンテキストを使用して単に画面の表示または印刷の同じ GDI 関数を使用できます。 場合、`CDC`オブジェクトを`OnDraw`受信、プリンターを表す`OnDraw`移動の出力をプリンターにします。  
  
 これは、ユーザー側で余分な労力を必要とせず、MFC アプリケーションが簡単に印刷を実行する方法について説明します。 印刷 ダイアログ ボックスを表示して、プリンター デバイス コンテキストを作成するために、フレームワークによって行われます。 ビューがこのデバイス コンテキストを渡しますユーザーは、[ファイル] メニューから [印刷] コマンドを選択するときに`OnDraw`プリンターのドキュメントを描画します。  
  
 ただし、印刷と画面表示の重要な相違があります。 印刷すると、個別のページとに 1 つずつ、のどの部分を表示するのではなくはウィンドウに表示、表示、ドキュメントに分割する必要があります。 当然の結果としては、(かどうかはレター サイズ、リーガル サイズ、またはエンベロープ) 用紙のサイズを認識する必要があります。 横または縦モードなどのさまざまな向きに印刷することがあります。 Microsoft Foundation Class ライブラリでは、アプリケーションを処理する方法、これらの問題できるので、これらの機能を追加するためのプロトコルを予測できません。  
  
 プロトコルが、資料に記載されている[マルチページ ドキュメント](../mfc/multipage-documents.md)です。  
  
## <a name="see-also"></a>関連項目  
 [印刷](../mfc/printing.md)

