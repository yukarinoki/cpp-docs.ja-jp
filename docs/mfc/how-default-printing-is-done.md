---
title: 既定の印刷プロセス
ms.date: 11/04/2016
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
ms.openlocfilehash: 9ca79ec69037b960e7c455f6ab8abd8833b9a8a0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618581"
---
# <a name="how-default-printing-is-done"></a>既定の印刷プロセス

この記事では、MFC フレームワークに関して、Windows の既定の印刷プロセスについて説明します。

MFC アプリケーションでは、ビュークラスにという名前のメンバー関数があります。この関数には `OnDraw` 、すべての描画コードが含まれています。 `OnDraw`[CDC](reference/cdc-class.md)オブジェクトへのポインターをパラメーターとして取得します。 この `CDC` オブジェクトは、によって生成されるイメージを受け取るデバイスコンテキストを表し `OnDraw` ます。 ドキュメントを表示するウィンドウが[WM_PAINT](/windows/win32/gdi/wm-paint)メッセージを受信すると、フレームワークはを呼び出し、 `OnDraw` 画面のデバイスコンテキスト (具体的には[CPaintDC](reference/cpaintdc-class.md)オブジェクト) を渡します。 これにより、 `OnDraw` の出力が画面に移動します。

Windows のプログラミングでは、プリンターに出力を送信することは、画面に出力を送信することとよく似ています。 これは、Windows グラフィックデバイスインターフェイス (GDI) がハードウェアに依存しないためです。 画面表示や印刷には、適切なデバイスコンテキストを使用するだけで、同じ GDI 関数を使用できます。 を受け取るオブジェクトがプリンターを表している場合 `CDC` `OnDraw` 、 `OnDraw` の出力はプリンターに送られます。

ここでは、MFC アプリケーションで簡単な印刷を実行する方法について説明します。 フレームワークでは、[印刷] ダイアログボックスを表示し、プリンターのデバイスコンテキストを作成します。 ユーザーが [ファイル] メニューから [印刷] コマンドを選択すると、このデバイスコンテキストは、プリンター上のドキュメントを描画するに渡され `OnDraw` ます。

ただし、印刷と画面表示には大きな違いがいくつかあります。 印刷するときは、ウィンドウに表示されている部分を表示するのではなく、ドキュメントを個別のページに分割し、一度に1つずつ表示する必要があります。 当然のことながら、用紙のサイズ (レターサイズ、リーガルサイズ、または封筒) に注意する必要があります。 横または縦モードなど、異なる向きで印刷することができます。 Microsoft Foundation Class ライブラリは、アプリケーションがこれらの問題をどのように処理するかを予測できないため、これらの機能を追加するためのプロトコルを提供します。

このプロトコルの詳細については、「[マルチページドキュメント](multipage-documents.md)」を参照してください。

## <a name="see-also"></a>関連項目

[印刷](printing.md)
