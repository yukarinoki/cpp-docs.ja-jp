---
title: CComEnumOnSTL クラス
ms.date: 11/04/2016
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
ms.openlocfilehash: f9bf9c227984b2fdbf460f970357f395934b238c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779860"
---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL クラス

このクラスは、C++ 標準ライブラリ コレクションに基づいて COM 列挙子オブジェクトを定義します。

## <a name="syntax"></a>構文

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
T,
    Copy,
CollType>,
    public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>パラメーター

*ベース*<br/>
COM の列挙子。 参照してください[IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring)例についてはします。

*piid*<br/>
列挙子インターフェイスのインターフェイス ID へのポインター。

*T*<br/>
列挙子インターフェイスによって公開される項目の種類。

*コピー*<br/>
A[コピー ポリシー](../../atl/atl-copy-policy-classes.md)クラス。

*CollType*<br/>
C++ 標準ライブラリ コンテナー クラス。

## <a name="remarks"></a>Remarks

`CComEnumOnSTL` C++ 標準ライブラリ コレクションに基づいて COM 列挙子オブジェクトを定義します。 このクラスは、単独または組み合わせて使用できます[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)します。 このクラスを使用するための一般的な手順は次のとおりです。 詳細については、次を参照してください。 [ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)します。

## <a name="to-use-this-class-with-icollectiononstlimpl"></a>単独でこのクラスを使用します。

- **typedef**このクラスの特殊化します。

- 使用して、 **typedef**の特殊化で最終的なテンプレート引数として`ICollectionOnSTLImpl`します。

参照してください[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)例についてはします。

## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>ICollectionOnSTLImpl とは無関係に、このクラスを使用します。

- **typedef**このクラスの特殊化します。

- 使用して、 **typedef**の特殊化のテンプレート引数として`CComObject`します。

- インスタンスを作成、`CComObject`特殊化します。

- 列挙子オブジェクトを呼び出すことによって初期化[保ちます](../../atl/reference/ienumonstlimpl-class.md#init)します。

- 列挙子インターフェイスをクライアントに返します。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)

`CComEnumOnSTL`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="example"></a>例

次に示すコードでは、作成、列挙子オブジェクトの初期化を処理するジェネリック関数を提供します。

[!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]

このテンプレート関数を実装するために使用できます、`_NewEnum`次に示すように、コレクション インターフェイスのプロパティ。

[!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]

このコードを作成、 **typedef**の`CComEnumOnSTL`のベクターを公開する`CComVariant`の s、`IEnumVariant`インターフェイス。 `CVariantCollection`クラスは単に専門`CreateSTLEnumerator`この型の列挙子オブジェクトを操作します。

## <a name="see-also"></a>関連項目

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)<br/>
[ATLCollections サンプル:ICollectionOnSTLImpl、CComEnumOnSTL、およびカスタム コピー ポリシー クラスを示します](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[IEnumOnSTLImpl クラス](../../atl/reference/ienumonstlimpl-class.md)
