---
title: ATL AXHost を使用して ActiveX コントロールをホストしている |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2T class
- Calendar control (ActiveX), hosting with ATL AXHost
- Calendar control (ActiveX)
- ActiveX controls [C++], hosting
- hosting ActiveX controls
- AXHost method
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5057a077e8e778fa3d943b736d51d19af8f60fc6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost を使用して ActiveX コントロールをホストしています。
このトピックのサンプルでは、AXHost を作成する方法と ATL のさまざまな機能を使用して ActiveX コントロールをホストする方法を示します。 コントロールとシンク イベントにアクセスする方法も示しています (を使用して[IDispEventImpl](../atl/reference/idispeventimpl-class.md)) でホストされるコントロールからです。 このサンプルでは、メイン ウィンドウ、または子ウィンドウで、カレンダー コントロールをホストします。  
  
 定義に注意してください、`USE_METHOD`シンボル。 1 ~ 8 で変更するには、この記号の値を変更することができます。 記号の値は、コントロールの作成方法を決定します。  
  
-   値が偶数`USE_METHOD`ウィンドウのホストのサブクラスを作成する呼び出し、コントロールのホストに変換します。 奇数の値には、コードは、ホストとして機能する子ウィンドウを作成します。  
  
-   値が`USE_METHOD`コントロールへのアクセスを 1 4 から、およびイベント シンクもホストを作成する呼び出しで行われます。 値は 5 ~ 8 では、ホストにインターフェイスを照会し、シンクをフックします。  
  
 次に概要を示します。  
  
|USE_METHOD|ホスト|アクセス制御とイベント シンク|使用する関数|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|子ウィンドウ|1 つの手順|CreateControlLicEx|  
|2|メイン ウィンドウ|1 つの手順|AtlAxCreateControlLicEx|  
|3|子ウィンドウ|1 つの手順|CreateControlEx|  
|4|メイン ウィンドウ|1 つの手順|AtlAxCreateControlEx|  
|5|子ウィンドウ|複数のステップ|CreateControlLic|  
|6|メイン ウィンドウ|複数のステップ|AtlAxCreateControlLic|  
|7|子ウィンドウ|複数のステップ|CreateControl|  
|8|メイン ウィンドウ|複数のステップ|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)   
 [して](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [行うに](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [して](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [CAxWindow2T クラス](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic インターフェイス](../atl/reference/iaxwinhostwindowlic-interface.md)

