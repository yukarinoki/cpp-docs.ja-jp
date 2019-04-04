---
title: CComEnum クラス
ms.date: 11/04/2016
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
ms.openlocfilehash: 4d83b06f37c132c0d2325304e2cc155ccb490690
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290366"
---
# <a name="ccomenum-class"></a>CComEnum クラス

このクラスは、配列ベースの COM の列挙子オブジェクトを定義します。

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

*ベース*<br/>
COM の列挙子インターフェイス。 参照してください[IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring)例についてはします。

*piid*<br/>
列挙子インターフェイスのインターフェイス ID へのポインター。

*T*<br/>
列挙子インターフェイスによって公開される項目の種類。

*コピー*<br/>
同種[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)します。

*表*<br/>
クラスのスレッド処理モデル。 このパラメーターの既定値は、プロジェクトで使用されるグローバル オブジェクト スレッド モデルです。

## <a name="remarks"></a>Remarks

`CComEnum` 配列に基づいて、COM の列挙子オブジェクトを定義します。 このクラスに似ています[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) C++ 標準ライブラリ コンテナーに基づく列挙子を実装します。 このクラスを使用するための一般的な手順は次のとおりです。 詳細については、[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)を参照してください。

## <a name="to-use-this-class"></a>このクラスを使用します。

- **typedef**このクラスの特殊化します。

- 使用して、 **typedef**の特殊化のテンプレート引数として`CComObject`します。

- インスタンスを作成、`CComObject`特殊化します。

- 列挙子オブジェクトを呼び出すことによって初期化[保ちます](../../atl/reference/ccomenumimpl-class.md#init)します。

- 列挙子インターフェイスをクライアントに返します。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)

`CComEnum`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="example"></a>例

次に示すコードでは、再利用可能な関数を作成して列挙子オブジェクトの初期化を提供します。

[!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]

このテンプレート関数を実装するために使用できます、`_NewEnum`次に示すように、コレクション インターフェイスのプロパティ。

[!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]

このコードを作成、 **typedef**の`CComEnum`を通じてバリアントのベクターを公開する、`IEnumVariant`インターフェイス。 `CVariantArrayCollection`クラスは単に専門`CreateEnumerator`この型と、必要な引数のパスの列挙子オブジェクトを操作します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[CComEnumImpl クラス](../../atl/reference/ccomenumimpl-class.md)<br/>
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)
