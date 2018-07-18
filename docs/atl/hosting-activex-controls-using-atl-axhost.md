---
title: ATL AXHost を使用して ActiveX コントロールのホスト |Microsoft Docs
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
ms.openlocfilehash: e26fd9e80b96c2b0196e3fd0e11b9c97f0f3bff3
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027207"
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost を使用して ActiveX コントロールのホスト
このトピックのサンプルでは、AXHost を作成する方法とさまざまな ATL 関数を使用して ActiveX コントロールをホストする方法を示します。 コントロールとシンク イベントにアクセスする方法も示します (を使用して[IDispEventImpl](../atl/reference/idispeventimpl-class.md)) ホストされているコントロールから。 このサンプルでは、メイン ウィンドウ、または子ウィンドウには、予定表コントロールをホストします。  
  
 USE_METHOD シンボルの定義に注目してください。 1 ~ 8 で変更するには、この記号の値を変更することができます。 シンボルの値は、コントロールの作成方法を決定します。  
  
-   USE_METHOD、ホストのサブクラスを作成するには、ウィンドウへの呼び出しの値が偶数とコントロールのホストに変換します。 奇数の値は、コードは、ホストとして機能する子ウィンドウを作成します。  
  
-   コントロールへのアクセスを 1 から 4 まで USE_METHOD の値と、呼び出しで行われます。 イベントのシンクをもホストを作成します。 5 ~ 8 の値は、ホストにインターフェイスを照会し、シンクをフックします。  
  
次に概要を示します。  
  
|USE_METHOD|ホスト|アクセスを制御し、イベント シンク|使用する関数|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|子ウィンドウ|1 つのステップ|CreateControlLicEx|  
|2|メイン ウィンドウ|1 つのステップ|AtlAxCreateControlLicEx|  
|3|子ウィンドウ|1 つのステップ|CreateControlEx|  
|4|メイン ウィンドウ|1 つのステップ|AtlAxCreateControlEx|  
|5|子ウィンドウ|複数のステップ|CreateControlLic|  
|6|メイン ウィンドウ|複数のステップ|AtlAxCreateControlLic|  
|7|子ウィンドウ|複数のステップ|CreateControl|  
|8|メイン ウィンドウ|複数のステップ|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [コントロール コンテインメント:](../atl/atl-control-containment-faq.md)   
 [して](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [行うに](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [して](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [CAxWindow2T クラス](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic インターフェイス](../atl/reference/iaxwinhostwindowlic-interface.md)

