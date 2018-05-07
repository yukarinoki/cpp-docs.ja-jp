---
title: Rebar コントロールの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1deb33adc104775cf9b76daf75d4ee08b6475f0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-rebar-control"></a>Rebar コントロールの作成
[CReBarCtrl](../mfc/reference/crebarctrl-class.md)親オブジェクトを表示する前に、オブジェクトを作成する必要があります。 これには、描画上の問題の可能性が最小限に抑えます。  
  
 たとえば、rebar コントロール (フレーム ウィンドウのオブジェクトで使用) は、ツール バー コントロールの親ウィンドウとして使用よくされます。 そのため、rebar コントロールの親は、フレーム ウィンドウ オブジェクトです。 フレーム ウィンドウ オブジェクトが、親であるため、 `OnCreate` (親) のメンバー関数は、最適な場所を rebar コントロールを作成します。  
  
 使用する、`CReBarCtrl`オブジェクトは通常これらの手順を行います。  
  
### <a name="to-use-a-crebarctrl-object"></a>CReBarCtrl オブジェクトを使用するには  
  
1.  構築、 [CReBarCtrl](../mfc/reference/crebarctrl-class.md)オブジェクト。  
  
2.  呼び出す[作成](../mfc/reference/crebarctrl-class.md#create)Windows rebar のコモン コントロールを作成しをアタッチする、`CReBarCtrl`任意のスタイルを指定するオブジェクト。  
  
3.  呼び出して、ビットマップを読み込んで[CBitmap::LoadBitmap](../mfc/reference/cbitmap-class.md#loadbitmap)、rebar コントロール オブジェクトの背景として使用します。  
  
4.  作成し、rebar コントロール オブジェクトが含まれる子ウィンドウ オブジェクト (ツールバー、ダイアログ コントロール) を初期化します。  
  
5.  初期化、 **REBARBANDINFO**挿入される直前に帯域外に必要な情報を含む構造体。  
  
6.  呼び出す[InsertBand](../mfc/reference/crebarctrl-class.md#insertband)を既存の子ウィンドウを挿入する (など`m_wndReToolBar`)、新しい rebar コントロールにします。 Rebar の既存のコントロールへバンドの挿入の詳細については、次を参照してください。 [Rebar コントロールとバンド](../mfc/rebar-controls-and-bands.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CReBarCtrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

