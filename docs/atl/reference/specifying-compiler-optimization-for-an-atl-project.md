---
title: ATL プロジェクトのコンパイラの最適化を指定する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
dev_langs:
- C++
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0060437613bcdd6281ce5cceb112f5fd7f470bf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL プロジェクトのコンパイラの最適化を指定します。
既定では、 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)ATL_NO_VTABLE マクロを持つ新しいクラスを次のように生成されます。  
  
```  
class ATL_NO_VTABLE CProjName  
{  
 ...  
};  
```  
  
 ATL し、_ATL_NO_VTABLE を次のように定義します。  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
 #define ATL_NO_VTABLE  
#else  
 #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 ATL_NO_VTABLE マクロが展開 _ATL_DISABLE_NO_VTABLE を定義していない場合`declspec(novtable)`です。 使用して`declspec(novtable)`クラスで宣言防止 vtable ポインター クラスのコンス トラクターおよびデストラクター内で初期化されます。 プロジェクトをビルドするときに、リンカーは、vtable と vtable がポイントするすべての関数が解消されます。  
  
 ATL_NO_VTABLE を使用する必要があるあり、その結果`declspec(novtable)`、直接作成可能ではない基底クラスのみを持つ。 使用しないでください`declspec(novtable)`プロジェクトで、最派生クラスであるためこのクラス (通常[CComObject](../../atl/reference/ccomobject-class.md)、[すると](../../atl/reference/ccomaggobject-class.md)、または[CComPolyObject](../../atl/reference/ccompolyobject-class.md))プロジェクトの vtable ポインターを初期化します。  
  
 使用する任意のオブジェクトのコンス トラクターから仮想関数を呼び出す必要がありますいない`declspec(novtable)`です。 これらの呼び出しを移動する必要があります、 [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)メソッドです。  

  
 使用するかどうかがわからない場合、`declspec(novtable)`修飾子は、任意のクラス定義から ATL_NO_VTABLE マクロを削除するか、グローバルを無効にすることを指定します。  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 stdafx.h でその他のすべての ATL の前にヘッダー ファイルが含まれます。  
  
## <a name="see-also"></a>関連項目  
 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
 [Visual C プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

