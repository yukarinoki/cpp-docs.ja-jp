---
title: ATL プロジェクトのコンパイラ最適化の指定 |Microsoft Docs
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
ms.openlocfilehash: 622c0720f55e638d6640094f095e59d2d5e5f931
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069340"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL プロジェクトのコンパイラ最適化を指定します。

既定で、 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)ATL_NO_VTABLE マクロでは、新しいクラスを次のように生成されます。

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

_ATL_DISABLE_NO_VTABLE を定義していない場合、ATL_NO_VTABLE マクロ展開`declspec(novtable)`します。 使用して`declspec(novtable)`クラスで宣言がクラスのコンス トラクターとデストラクターで初期化されない vtable ポインターを防止します。 プロジェクトをビルドするときに、リンカーは、vtable と vtable がポイントするすべての関数を排除します。

ATL_NO_VTABLE を使用する必要があり、その結果`declspec(novtable)`を直接作成可能でない基底クラスのみを持つ。 使用しないでください`declspec(novtable)`プロジェクトで、最も多く派生されたクラスを使用しているためこのクラス (通常は[CComObject](../../atl/reference/ccomobject-class.md)、 [CComAggObject](../../atl/reference/ccomaggobject-class.md)、または[CComPolyObject](../../atl/reference/ccompolyobject-class.md))プロジェクトの vtable ポインターを初期化します。

使用する任意のオブジェクトのコンス トラクターから仮想関数を呼び出す必要がありますいない`declspec(novtable)`します。 これらの呼び出しを移動する必要があります、 [finalconstruct 関数](ccomobjectrootex-class.md#finalconstruct)メソッド。  

使用する必要があるかどうかが不明の場合、`declspec(novtable)`修飾子は、任意のクラス定義から ATL_NO_VTABLE マクロを削除するかを指定してグローバルに無効にできます

```
#define _ATL_DISABLE_NO_VTABLE
```

stdafx.h に、その他のすべての ATL の前にヘッダー ファイルが含まれます。

## <a name="see-also"></a>関連項目

[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++ プロジェクトの種類](../../ide/visual-cpp-project-types.md)<br/>
[アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

