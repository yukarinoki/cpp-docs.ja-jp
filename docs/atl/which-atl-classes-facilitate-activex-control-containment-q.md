---
title: ATL クラスは、ActiveX コントロール サポートを容易にしますか。 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f024e9929e916e15b110bfc32bc704c4aef755a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361954"
---
# <a name="which-atl-classes-facilitate-activex-control-containment"></a>ATL クラスは、ActiveX コントロール サポートを容易にしますか。
ATL のコントロール ホスト コードでは、ATL クラスを使用する必要としません。単に作成することができます、 **"AtlAxWin80"** ウィンドウおよび必要に応じてコントロール ホスト API を使用 (詳細については、次を参照してください。 **、ATL コントロール ホスト API は、どのような**します。 ただし、次のクラス包含機能を使いやすきます。  
  
|クラス|説明|  
|-----------|-----------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|ラップ、 **"AtlAxWin80"** ウィンドウで、ウィンドウの作成、コントロールの作成やウィンドウに表示するコントロールをアタッチして、そのホスト オブジェクトのインターフェイス ポインターを取得するためのメソッドを指定します。|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|ラップ、 **AtlAxWinLic80**ウィンドウで、ウィンドウの作成、コントロールを作成するやウィンドウで、ライセンスされたコントロールをアタッチすると、そのホスト オブジェクトのインターフェイス ポインターを取得する方法を提供します。|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|ダイアログ リソースに基づく ActiveX コントロール クラスの基底クラスとして機能します。 このようなコントロールは、その他の ActiveX コントロールを含めることができます。|  
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|ダイアログ リソースに基づくダイアログ クラスの基底クラスとして機能します。 このようなダイアログ ボックスでは、ActiveX コントロールを含めることができます。|  
|[CWindow](../atl/reference/cwindow-class.md)|メソッドを提供[GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol)、そのホスト ウィンドウの ID を指定し、コントロールのインターフェイス ポインターが返されます。 さらに、Windows API ラッパーをによって公開されている`CWindow`ウィンドウの管理を一般に容易です。|  
  
## <a name="see-also"></a>関連項目  
 [コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)

