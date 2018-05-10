---
title: ATL コントロール ホスト API しますか? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- APIs [C++], hosting
- control-hosting API
- controls [ATL], hosting APIs
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30b104e21259006da41c236c168431d85b43e0d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="what-is-the-atl-control-hosting-api"></a>ATL コントロール ホスト API しますか?
ATL のコントロール ホスト API は、ActiveX コントロール コンテナーとして機能する任意のウィンドウを許可する一連の関数。 これらの関数は静的または動的にソース コードとして使用されるので、プロジェクトにリンクを ATL90.dll によって公開されています。 コントロール ホスト関数は、次の表に表示されます。  
  
|関数|説明|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|ホスト オブジェクトを作成する、指定されたウィンドウに接続し、既存のコントロールをアタッチします。|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|ホスト オブジェクトを作成して接続し、指定されたウィンドウに、コントロールを読み込みます。|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|ライセンスされた ActiveX コントロールを作成、初期化、および指定したウィンドウでホスト[して](reference/composite-control-global-functions.md#atlaxcreatecontrol)です。|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|ホスト オブジェクトを作成して、指定されたウィンドウに接続し、コントロールを読み込みます (も許可するイベント シンクをセットアップする)。|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|ライセンスされた ActiveX コントロールを作成、初期化、および指定したウィンドウでホスト[して](reference/composite-control-global-functions.md#atlaxcreatecontrollic)です。|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|ダイアログ リソースからモードレス ダイアログ ボックスを作成し、ウィンドウのハンドルを返します。|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|ダイアログ リソースからモーダル ダイアログ ボックスを作成します。|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|返します、 **IUnknown**ウィンドウでホストされるコントロールのインターフェイス ポインター。|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|返します、 **IUnknown**そのホスト オブジェクトのインターフェイス ポインターをウィンドウに接続されています。|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|コントロール ホスト コードを初期化します。|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|コントロール ホスト コードを非初期化します。|  
  
 `HWND`最初の 3 つの関数のパラメーターは (ほとんど) 任意の型の既存のウィンドウである必要があります。 これらの関数のいずれかを明示的に呼び出す場合 (通常は、する必要はありません)、ホストとして既に動作しているウィンドウへのハンドルを渡さないでください (この場合、既存のホスト オブジェクト解放されない)。  
  
 最初の 7 つの関数呼び出しを行う[な](reference/composite-control-global-functions.md#atlaxwininit)暗黙的にします。  
  
> [!NOTE]
>  コントロール ホスト API では、ActiveX コントロール コンテインメントの ATL のサポートの基礎を形成します。 ただしが通常利用または ATL のラッパー クラスを最大限に活用する場合に、これらの関数を直接呼び出す必要はほとんどありません。 詳細については、次を参照してください。[する ATL クラスを容易に ActiveX コントロール コンテインメント](which-atl-classes-facilitate-activex-control-containment-q.md)です。  
  
## <a name="see-also"></a>関連項目  
 [コントロール コンテインメントよく寄せられる質問](which-atl-classes-facilitate-activex-control-containment-q.md)
