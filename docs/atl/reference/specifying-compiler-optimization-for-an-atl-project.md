---
description: '詳細情報: ATL プロジェクトのコンパイラ最適化の指定'
title: ATL プロジェクトのコンパイラ最適化の指定
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
ms.openlocfilehash: d0650cfebdeb74caeb78a0ab4f138f4896865fc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138802"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL プロジェクトのコンパイラ最適化の指定

既定では、 [ATL コントロールウィザード](../../atl/reference/atl-control-wizard.md) では、次のように ATL_NO_VTABLE マクロを使用して新しいクラスが生成されます。

```
class ATL_NO_VTABLE CProjName
{
...
};
```

ATL では、次のように _ATL_NO_VTABLE を定義します。

```
#ifdef _ATL_DISABLE_NO_VTABLE
#define ATL_NO_VTABLE
#else
#define ATL_NO_VTABLE __declspec(novtable)
#endif
```

_ATL_DISABLE_NO_VTABLE を定義しない場合、ATL_NO_VTABLE マクロはに展開され `declspec(novtable)` ます。 `declspec(novtable)`クラス宣言でを使用すると、vtable ポインターがクラスコンストラクターとデストラクターで初期化されるのを防ぐことができます。 プロジェクトをビルドすると、vtable が指す vtable とすべての関数がリンカーによって除去されます。

ATL_NO_VTABLE を使用し、その結果 `declspec(novtable)` 、直接作成できない基本クラスのみを使用する必要があります。 `declspec(novtable)`このクラス (通常は[CComObject](../../atl/reference/ccomobject-class.md)、 [CComAggObject](../../atl/reference/ccomaggobject-class.md)、または[CComPolyObject](../../atl/reference/ccompolyobject-class.md)) がプロジェクトの vtable ポインターを初期化するため、プロジェクト内で最も派生クラスでを使用することはできません。

を使用するすべてのオブジェクトのコンストラクターから仮想関数を呼び出すことはできません `declspec(novtable)` 。 これらの呼び出しは、 [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) メソッドに移動する必要があります。

修飾子を使用する必要があるかどうかわからない場合は、 `declspec(novtable)` 任意のクラス定義から ATL_NO_VTABLE マクロを削除するか、を指定してグローバルに無効にすることができます。

```
#define _ATL_DISABLE_NO_VTABLE
```

*.pch* (Visual Studio 2017 以前の場合は *stdafx.h* ) で、他のすべての ATL ヘッダーファイルが含まれる前。

## <a name="see-also"></a>関連項目

[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio の C++ プロジェクトの種類](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL および C Run-Time コードを使用したプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[既定の ATL プロジェクト構成](../../atl/reference/default-atl-project-configurations.md)
