---
title: 上記のクラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17046239cf4ca5cc95afbc709f10b9c8aedaa9fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ccomenum-class"></a>上記のクラス
このクラスは、配列に基づいた COM 列挙子オブジェクトを定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>  
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
 T,
    Copy>,
 public CComObjectRootEx<ThreadModel>
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 COM の列挙子 ([として](https://msdn.microsoft.com/library/ms680089.aspx)) インターフェイス。  
  
 `piid`  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 `T`  
 列挙子インターフェイスによって公開されている項目の種類。  
  
 `Copy`  
 同種[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)です。  
  
 `ThreadModel`  
 クラスのスレッド モデルです。 このパラメーターの既定値は、プロジェクトで使用されるグローバル オブジェクト スレッド モデルです。  
  
## <a name="remarks"></a>コメント  
 `CComEnum` 配列に基づいた COM 列挙子オブジェクトを定義します。 このクラスと似ています[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) C++ 標準ライブラリのコンテナーに基づく列挙子を実装します。 このクラスを使用するための一般的な手順は次のとおりです。 詳細については、次を参照してください。 [ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)です。  
  
## <a name="to-use-this-class"></a>このクラスを使用します。  
  
- `typedef` このクラスの特殊化です。  
  
-   使用して、`typedef`の特殊化のテンプレート引数として`CComObject`です。  
  
-   インスタンスを作成、`CComObject`特殊化です。  
  
-   呼び出して列挙子オブジェクトを初期化する[保ちます](../../atl/reference/ccomenumimpl-class.md#init)です。  
  
-   列挙子インターフェイスをクライアントに返します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
## <a name="example"></a>例  
 以下に示すコードでは、作成して、列挙子オブジェクトの初期化の再利用可能な機能を提供します。  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 このテンプレート関数を実装するために使用できる、`_NewEnum`次に示すように、コレクション インターフェイスのプロパティ。  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 このコードを作成、`typedef`の`CComEnum`のベクターを公開する**バリアント**を通じて s、 **IEnumVariant**インターフェイスです。 **CVariantArrayCollection**クラスを特化するだけ**CreateEnumerator**この型と、必要な引数のパスの列挙子オブジェクトを使用します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [CComEnumImpl クラス](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)
