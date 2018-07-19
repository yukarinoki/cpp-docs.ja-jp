---
title: 出力 (デバイス コンテキスト) クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.output
dev_langs:
- C++
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85571e2173d9dc4e900d63e982a91571fafc103e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350485"
---
# <a name="output-device-context-classes"></a>出力 (デバイス コンテキスト) クラス
これらのクラスには、Windows で使用可能なデバイス コンテキストのさまざまな種類がカプセル化します。  
  
 次のクラスのほとんどは、Windows デバイス コンテキストへのハンドルをカプセル化します。 デバイス コンテキストは、ディスプレイやプリンターなどのデバイスの描画属性に関する情報を格納している Windows オブジェクトです。 デバイス コンテキスト オブジェクトを通じて、すべての描画呼び出しが行われます。 その他のクラスから派生した`CDC`Windows メタファイルのサポートなど、特殊化されたデバイス コンテキストの機能をカプセル化します。  
  
 [CDC](../mfc/reference/cdc-class.md)  
 デバイス コンテキストの基本クラスです。 画面全体にアクセスするためには、直接、プリンターなどのディスプレイ コンテキストにアクセスするために使用されます。  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md)  
 使用されるディスプレイ コンテキスト`OnPaint`windows のメンバー関数。 自動的に呼び出します`BeginPaint`コンス トラクターでと`EndPaint`破棄します。  
  
 [CClientDC](../mfc/reference/cclientdc-class.md)  
 Windows のクライアント領域のディスプレイ コンテキスト。 、たとえば、描画に使用するマウス イベントをすぐに応答します。  
  
 [CWindowDC](../mfc/reference/cwindowdc-class.md)  
 クライアントと非クライアント領域を含むウィンドウ全体のディスプレイ コンテキスト。  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md)  
 Windows メタファイル デバイス コンテキスト。 Windows のメタファイルには、イメージを作成するのには、再生できますグラフィックス デバイス インターフェイス (GDI) コマンドのシーケンスが含まれています。 メンバー関数への呼び出し、`CMetaFileDC`メタファイルに記録されます。  
  
## <a name="related-classes"></a>関連するクラス  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 ペアは座標 (x, y) を保持します。  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 距離、相対位置、または値のペアを保持します。  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 四角形領域の座標が保持されます。  
  
 [CRgn](../mfc/reference/crgn-class.md)  
 ウィンドウ内の楕円形を多角形、または不規則な領域を操作するため、GDI 領域をカプセル化します。 クラスのクリッピング メンバー関数と組み合わせて使用`CDC`です。  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 表示し、サイズ変更したり四角形のオブジェクトを移動するためのユーザー インターフェイスを処理します。  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 色を選択するためには、標準のダイアログ ボックスを提供します。  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 フォントを選択するためには、標準のダイアログ ボックスを提供します。  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 ファイルを印刷するためには、標準のダイアログ ボックスを提供します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

