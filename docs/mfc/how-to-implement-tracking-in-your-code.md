---
title: '方法: コード内の追跡を実装して |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bae9696be10ab00a076a73c14281a9baabe3d6d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349737"
---
# <a name="how-to-implement-tracking-in-your-code"></a>コードでのトラッカーの実装方法
OLE 項目を追跡するには、項目をクリックするか、ドキュメントのビューの更新などのアイテムに関連する特定のイベントを処理する必要があります。 すべてのケースでは、一時的なを宣言するための十分な[CRectTracker](../mfc/reference/crecttracker-class.md)オブジェクトをこのオブジェクトを使用して、項目を操作します。  
  
 ユーザーが項目を選択するか、メニュー コマンドを使用してオブジェクトを挿入、OLE 項目の状態を表すための適切なスタイルを使用してトラッカーを初期化する必要があります。 次の表では、OCLIENT サンプルで使用される規則について説明します。 これらのスタイルの詳細については、次を参照してください。`CRectTracker`です。  
  
### <a name="container-styles-and-states-of-the-ole-item"></a>コンテナーのスタイルと OLE 項目の状態  
  
|表示スタイル|OLE 項目の状態|  
|---------------------|-----------------------|  
|点線の枠|項目がリンクされています。|  
|実線の境界線|項目は、ドキュメントに埋め込まれます|  
|サイズ変更ハンドル|項目が現在選択されています。|  
|網掛け境界線|項目は現在、インプレース アクティブでは|  
|() の陰影パターン オーバーレイ項目|アイテムのサーバーが開いています。|  
  
 OLE 項目の状態を確認し、適切なスタイルを設定する手順を使用して簡単にこの初期化を処理することができます。 **SetupTracker** oclient で見つかった関数がトラッカーの初期化を示します。 この関数のパラメーターは、トラッカーのアドレス*pTracker*トラッカーに関連付けられているクライアント アイテムへのポインターです。 `pItem`; と四角形を指すポインター *pTrueRect*です。 この関数の完全な例は、MFC OLE サンプルを参照してください。 [OCLIENT](../visual-cpp-samples.md)です。  
  
 **SetupTracker**のコード例は、1 つの関数を提示します。 関数の行が、関数の機能の説明が混在しては。  
  
 [!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]  
  
 トラッカーの最小サイズを設定し、トラッカーのスタイルをクリアして初期化します。  
  
 [!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]  
  
 次の行は、項目が現在選択されているかどうかと、項目がそのドキュメントにリンクまたはそれに埋め込まれているかどうかを確認します。 境界線の内側にあるサイズ変更ハンドルは、項目が現在選択されていることを示す、スタイルに追加されます。 項目をドキュメントにリンク、ピリオドで区切られた罫線のスタイルが使用されます。 実線の境界線は、項目が埋め込まれている場合に使用されます。  
  
 [!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]  
  
 次のコード オーバーレイ場合は、アイテムは、現在のハッチ パターンを持つ項目を開きます。  
  
 [!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]  
  
 トラッカー必要があるたびに、この関数を呼び出すことができます。 たとえばからこの関数を呼び出して、`OnDraw`ビュー クラスの関数。 これにより、ビューが再描画されるたびに、トラッカーの状態が更新されます。 完全な例では、次を参照してください。、 **CMainView::OnDraw** MFC OLE サンプルの関数[OCLIENT](../visual-cpp-samples.md)です。  
  
 アプリケーションでは、サイズ変更、移動、またはヒットを検出するなどのトラッカー コードが必要なイベントが発生します。 これらのアクションでは、通常、しようとしましたがされるを取得したり、アイテムを移動を示します。 このような場合は、何をつかむが決定する必要があります: サイズ変更ハンドルまたはその一部の間の境界線のサイズ変更ハンドル。 `OnLButtonDown`メッセージ ハンドラーは、項目に関係するマウスの位置をテストするに適しています。 呼び出しを行う`CRectTracker::HitTest`です。 テストが以外の値を返す場合**CRectTracker::hitOutside**では、項目がサイズ変更または移動します。 したがってへの呼び出しをする必要があります、`Track`メンバー関数。 参照してください、 **CMainView::OnLButtonDown**関数は MFC OLE サンプルにある[OCLIENT](../visual-cpp-samples.md)完全な例です。  
  
 `CRectTracker`クラスには、操作が行われて、移動、サイズ変更、またはドラッグするかどうかを示すために使用するいくつかの別のカーソル図形が用意されています。 このイベントを処理するには、現在、マウス の下の項目が選択されているかどうかを確認します。 呼び出しを行う場合は、 `CRectTracker::SetCursor`、または既定のハンドラーを呼び出します。 次の例は、MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md):  
  
 [!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [トラッカー: OLE アプリケーションでのトラッカーの実装](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

