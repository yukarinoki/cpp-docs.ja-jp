---
title: 既定の印刷を行う方法 |Microsoft Docs
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
ms.openlocfilehash: 90f6559459bed9376dba8b7d9059761e9ace5ac8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202831"
---
# <a name="how-default-printing-is-done"></a>既定の印刷プロセス
この記事では、MFC フレームワークの観点から Windows の既定の印刷プロセスについて説明します。  
  
 という名前のメンバー関数が、MFC アプリケーションでビュー クラス`OnDraw`すべての描画コードを格納しています。 `OnDraw` ポインターを受け取り、 [CDC](../mfc/reference/cdc-class.md)オブジェクトをパラメーターとして。 ある`CDC`オブジェクトによって生成された画像を受信するデバイス コンテキストを表します`OnDraw`します。 ドキュメントを表示するウィンドウが受信すると、 [WM_PAINT](/windows/desktop/gdi/wm-paint)メッセージ、フレームワークによって`OnDraw`し、画面のデバイス コンテキストを渡します (、 [CPaintDC](../mfc/reference/cpaintdc-class.md)に特定のオブジェクト)。 したがって、`OnDraw`の出力が画面にします。  
  
 Windows のプログラミングでプリンターへの出力は、画面に出力を送信するとよく似ています。 これは、Windows グラフィックス デバイス インターフェイス (GDI) がハードウェア非依存であるためです。 適切なデバイス コンテキストを使用するだけで画面の表示または印刷の同じ GDI 関数を使用できます。 場合、`CDC`オブジェクトを`OnDraw`受信プリンター、`OnDraw`の出力がプリンターにします。  
  
 これは、ユーザー側で余分な労力を必要とせず、MFC アプリケーションが簡単に印刷を実行する方法について説明します。 印刷 ダイアログ ボックスを表示して、プリンター デバイス コンテキストを作成するために、フレームワークによって行われます。 ユーザーは、[ファイル] メニューから [印刷] コマンドを選択するときにビューはこのデバイス コンテキストに渡します`OnDraw`プリンターのドキュメントを描画します。  
  
 ただし、いくつか印刷および画面表示の重要な違いがあります。 印刷すると、個別のページとに 1 つずつ、どのような部分を表示するのではなくがウィンドウに表示、表示、ドキュメントに分割する必要があります。 当然の結果として必要があります (かどうかはレター サイズ、リーガル サイズ、またはエンベロープ) 用紙のサイズに注意してください。 横または縦モードなどのさまざまな向きで印刷することがあります。 方法、アプリケーション処理するこれらの問題では、これらの機能を追加するためのプロトコルを提供できるように、Microsoft Foundation Class ライブラリを予測できません。  
  
 この記事でプロトコルが記述されている[マルチページ ドキュメント](../mfc/multipage-documents.md)します。  
  
## <a name="see-also"></a>関連項目  
 [印刷](../mfc/printing.md)

