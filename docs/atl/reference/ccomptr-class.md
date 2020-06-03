---
title: CComPtr クラス
description: Microsoft C++ アクティブ テンプレート ライブラリ (ATL) クラス CComPtr のリファレンス ガイド。
ms.date: 02/07/2020
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 855466225db2672755658dcbbc9a266d09e0e7be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327519"
---
# <a name="ccomptr-class"></a>CComPtr クラス

COM インターフェイス ポインターを管理するためのスマート ポインター クラス。

## <a name="syntax"></a>構文

```cpp
template<class T>
class CComPtr
```

### <a name="parameters"></a>パラメーター

*T*<br/>
格納するポインターの型を指定する COM インターフェイス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コムプター::CComPtr](#ccomptr)|コンストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComPtr::演算子 =](#operator_eq)|メンバ ポインタにポインタを割り当てます。|

## <a name="remarks"></a>解説

ATL`CComPtr`は COM インターフェイス ポインタを管理するために[使用し、CComQIPtr](../../atl/reference/ccomqiptr-class.md)を使用します。 どちらも[CComPtrBase](../../atl/reference/ccomptrbase-class.md)から派生し、どちらも自動参照カウントを行います。

`CComPtr` [CComQIPtr クラスと CComQIPtr](../../atl/reference/ccomqiptr-class.md)クラスは、自動参照カウントを実行することでメモリ リークを排除するのに役立ちます。  次の関数は、どちらも同じ論理演算を実行します。 ただし、2 番目のバージョンでは`CComPtr`クラスを使用するため、エラーが発生しにくい可能性があります。

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

デバッグ ビルドで、コード トレース用に atlsd.lib をリンクします。

## <a name="inheritance-hierarchy"></a>継承階層

[コムプトルベース](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomptrccomptr"></a><a name="ccomptr"></a>コムプター::CComPtr

コンストラクターです。

```cpp
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>パラメーター

*Lp*<br/>
インターフェイス ポインターを初期化するために使用します。

*T*<br/>
COM インターフェイス。

### <a name="remarks"></a>解説

引数を受け取るコンストラクターは`AddRef`、引数を受け取る*場合は、null*ポインターでない場合は、lp を呼び出します。 Null 以外の所有オブジェクトは、CComPtr オブジェクトの破棄、または新しいオブジェクトが CComPtr オブジェクトに割り当てられている場合に`Release`呼び出しを受け取ります。

## <a name="ccomptroperator-"></a><a name="operator_eq"></a>CComPtr::演算子 =

代入演算子。

```cpp
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>戻り値

更新された`CComPtr`オブジェクトへのポインターを返します。

### <a name="remarks"></a>解説

この操作は、新しいオブジェクトを AddRef し、既存のオブジェクトが存在する場合は、そのオブジェクトを解放します。

## <a name="see-also"></a>関連項目

[コムプター::CComPtr](#ccomptr)<br/>
[CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
