---
title: 新機能、ATL コントロール ホスト API でしょうか。 | Microsoft Docs
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
ms.openlocfilehash: 2cc85c7ca47d5d1226ffc3089e01c0755ef6c6ac
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850555"
---
# <a name="what-is-the-atl-control-hosting-api"></a>新機能、ATL コントロール ホスト API でしょうか。
ATL のコントロール ホスト API は、ActiveX コントロール コンテナーとして機能する任意のウィンドウを許可する一連の関数。 これらの関数は静的または動的にソース コードとして利用できるため、プロジェクトにリンクされている、ATL90.dll によって公開されています。 コントロール ホスト関数は、次の表に表示されます。  
  
|関数|説明|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|ホスト オブジェクトを作成し、指定のウィンドウに接続し、既存のコントロールをアタッチします。|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|ホスト オブジェクトを作成する、指定のウィンドウに接続し、コントロールを読み込みます。|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|ライセンスされた ActiveX コントロールを作成し、それを初期化し、指定したウィンドウでホスト[して](reference/composite-control-global-functions.md#atlaxcreatecontrol)します。|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|ホスト オブジェクトを作成し、指定のウィンドウに接続し、コントロールを読み込みます (イベント シンクを設定するのには、許可も)。|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|ライセンスされた ActiveX コントロールを作成し、それを初期化し、指定したウィンドウでホスト[して](reference/composite-control-global-functions.md#atlaxcreatecontrollic)します。|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|ダイアログ リソースからモードレス ダイアログ ボックスを作成し、ウィンドウ ハンドルを返します。|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|ダイアログ リソースからモーダル ダイアログ ボックスを作成します。|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|返します、`IUnknown`ウィンドウでホストされるコントロールのインターフェイス ポインター。|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|返します、`IUnknown`ウィンドウに接続されているホスト オブジェクトのインターフェイス ポインター。|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|コントロール ホスト コードを初期化します。|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|コントロール ホスト コードは初期化されません。|  
  
 `HWND`最初の 3 つの関数のパラメーターは (ほとんど) すべての種類の既存のウィンドウである必要があります。 これら 3 つの関数のいずれかに明示的に呼び出す場合 (通常は、する必要はありません)、ホストとして既に動作しているウィンドウを識別するハンドルを渡さないでください (この場合、既存のホスト オブジェクト解放されない)。  
  
 最初の 7 つの関数を呼び出す[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)暗黙的にします。  
  
> [!NOTE]
>  コントロール ホスト API では、ActiveX コントロール サポートの ATL のサポートの基礎を形成します。 ただし、活用または ATL のラッパー クラスを最大限に活用する場合、これらの関数を直接呼び出す必要はほとんどありませんが、通常は。 詳細については、次を参照してください。[する ATL クラスを容易に ActiveX コントロール コンテインメント](which-atl-classes-facilitate-activex-control-containment-q.md)します。  
  
## <a name="see-also"></a>関連項目  
 [コントロール コンテインメント:](which-atl-classes-facilitate-activex-control-containment-q.md)
