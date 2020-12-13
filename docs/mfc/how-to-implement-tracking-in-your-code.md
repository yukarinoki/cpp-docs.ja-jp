---
description: '詳細については、「方法: コードで追跡を実装する」を参照してください。'
title: コードでのトラッカーの実装方法
ms.date: 11/04/2016
helpviewer_keywords:
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
ms.openlocfilehash: 1b9211978c6ba5169a2d55e272b7e3ddf0678fd6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330203"
---
# <a name="how-to-implement-tracking-in-your-code"></a>コードでのトラッカーの実装方法

OLE アイテムを追跡するには、アイテムをクリックしたり、ドキュメントのビューを更新したりするなど、アイテムに関連する特定のイベントを処理する必要があります。 どのような場合でも、一時的な [CRectTracker](reference/crecttracker-class.md) オブジェクトを宣言し、このオブジェクトを使って項目を操作するだけで十分です。

ユーザーがメニューコマンドを使用して項目を選択したり、オブジェクトを挿入したりするときには、OLE 項目の状態を表す適切なスタイルでトラッカーを初期化する必要があります。 次の表は、OCLIENT サンプルで使用される規則の概要を示しています。 これらのスタイルの詳細については、「」を参照してください `CRectTracker` 。

### <a name="container-styles-and-states-of-the-ole-item"></a>OLE 項目のコンテナーのスタイルと状態

|表示されるスタイル|OLE 項目の状態|
|---------------------|-----------------------|
|点線の枠線|項目がリンクされています|
|純枠線|項目はドキュメントに埋め込まれています|
|サイズ変更ハンドル|項目は現在選択されています|
|ハッチ境界線|項目は現在アクティブになっています|
|陰影パターンのオーバーレイ項目|項目のサーバーが開いています|

OLE 項目の状態を確認し、適切なスタイルを設定するプロシージャを使用すると、この初期化を簡単に処理できます。 `SetupTracker`OCLIENT サンプルに含まれている関数は、tracker の初期化を示しています。 この関数のパラメーターは tracker、 *ptracker*; のアドレスです。トラッカー *pItem* に関連するクライアントアイテムへのポインター。四角形を指すポインター *pTrueRect* です。 この関数の完全な例については、「MFC OLE サンプル [OCLIENT](../overview/visual-cpp-samples.md)」を参照してください。

**Setuptracker** コード例では、1つの関数を示します。関数の行には、関数の特徴の説明が含まれています。

[!code-cpp[NVC_MFCOClient#1](codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]

トラッカーは、最小サイズを設定し、トラッカーのスタイルをオフにすることによって初期化されます。

[!code-cpp[NVC_MFCOClient#2](codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]

次の行では、項目が現在選択されているかどうか、および項目がドキュメントにリンクされているか、ドキュメントに埋め込まれているかを確認します。 境界線の内側にあるサイズ変更ハンドルがスタイルに追加され、その項目が現在選択されていることを示します。 項目がドキュメントにリンクされている場合は、点線の境界線スタイルが使用されます。 項目が埋め込まれている場合は、純色の境界線が使用されます。

[!code-cpp[NVC_MFCOClient#3](codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]

次のコードは、項目が現在開いている場合に、その項目をハッチパターンでオーバーレイします。

[!code-cpp[NVC_MFCOClient#4](codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]

トラッカーを表示する必要がある場合は、この関数を呼び出すことができます。 たとえば、ビュークラスの関数からこの関数を呼び出し `OnDraw` ます。 これにより、ビューが再描画されるたびにトラッカーの外観が更新されます。 完全な例については、 `CMainView::OnDraw` MFC OLE サンプル [OCLIENT](../overview/visual-cpp-samples.md)の関数を参照してください。

アプリケーションでは、サイズ変更、移動、またはヒット検出などのトラッカーコードを必要とするイベントが発生します。 これらのアクションは、通常、項目を取得または移動しようとしたことを示します。 このような場合は、サイズ変更ハンドル、またはサイズ変更ハンドル間の境界の一部を、どのようにグラブされたかを決定する必要があります。 `OnLButtonDown`メッセージハンドラーは、項目に対するマウスの位置をテストするのに適した場所です。 を呼び出し `CRectTracker::HitTest` ます。 テストで以外の値が返された場合、 `CRectTracker::hitOutside` その項目はサイズ変更または移動されます。 したがって、メンバー関数の呼び出しを行う必要があり `Track` ます。 完全な `CMainView::OnLButtonDown` 例については、MFC OLE サンプル [OCLIENT](../overview/visual-cpp-samples.md) にある関数を参照してください。

クラスには、 `CRectTracker` 移動、サイズ変更、またはドラッグ操作が行われているかどうかを示すために使用されるさまざまなカーソル図形が用意されています。 このイベントを処理するには、現在マウスの下にある項目が選択されているかどうかを確認します。 の場合は、を呼び出す `CRectTracker::SetCursor` か、既定のハンドラーを呼び出します。 次の例は、MFC OLE サンプル [OCLIENT](../overview/visual-cpp-samples.md)からのものです。

[!code-cpp[NVC_MFCOClient#5](codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]

## <a name="see-also"></a>関連項目

[トラッカー: OLE アプリケーションでのトラッカーの実装](trackers-implementing-trackers-in-your-ole-application.md)
