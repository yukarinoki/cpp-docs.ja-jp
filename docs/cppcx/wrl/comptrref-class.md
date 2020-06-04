---
title: ComPtrRef クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
- client/Microsoft::WRL::Details::ComPtrRef::operator==
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
- client/Microsoft::WRL::Details::ComPtrRef::operator*
- client/Microsoft::WRL::Details::ComPtrRef::operator T*
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRef class
- Microsoft::WRL::Details::ComPtrRef::ComPtrRef, constructor
- Microsoft::WRL::Details::ComPtrRef::GetAddressOf method
- Microsoft::WRL::Details::ComPtrRef::operator== operator
- Microsoft::WRL::Details::ComPtrRef::operator!= operator
- Microsoft::WRL::Details::ComPtrRef::operator InterfaceType** operator
- Microsoft::WRL::Details::ComPtrRef::operator* operator
- Microsoft::WRL::Details::ComPtrRef::operator T* operator
- Microsoft::WRL::Details::ComPtrRef::operator void** operator
- Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf method
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
ms.openlocfilehash: df9ded817227547493c04035e0abc3d948e24495
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372635"
---
# <a name="comptrref-class"></a>ComPtrRef クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[ComPtr\<T>](comptr-class.md)型、または この型から派生した型は、 で表されるインターフェイスだけではありません。 `ComPtr`

## <a name="remarks"></a>解説

型のオブジェクトへの参照を表します`ComPtr<T>`。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                               | 説明
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[コンプトルレフ::コムプトルレフ](#comptrref) | 指定したポインターから別`ComPtrRef``ComPtrRef`のオブジェクトへのクラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                         | 説明
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[を見る](#getaddressof)                     | 現在`ComPtrRef`のオブジェクトによって表されるインターフェイスへのポインターのアドレスを取得します。
[を見る](#releaseandgetaddressof) | 現在`ComPtrRef`のオブジェクトを削除し、オブジェクトによって表されたインターフェイスへのポインターを`ComPtrRef`返します。

### <a name="public-operators"></a>パブリック演算子

名前                                                                     | 説明
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[インターフェイスタイプ**](#operator-interfacetype-star-star) | 現在`ComPtrRef`のオブジェクトを削除し、オブジェクトによって表されたインターフェイスへのポインターを`ComPtrRef`返します。
[オペレーター T*](#operator-t-star)                               | 現在の ComPtrRef オブジェクトの[ptr_](comptrrefbase-class.md#ptr)データ メンバーの値を返します。
[オペレーターボイド**](#operator-void-star-star)                   | 現在`ComPtrRef`のオブジェクトを削除し、オブジェクトがポインターからポインターへのポインターとして表した`ComPtrRef`インターフェイスにポインターを`void`キャストし、キャスト ポインターを返します。
[演算子*](#operator-star)                                   | 現在`ComPtrRef`のオブジェクトによって表されるインターフェイスへのポインターを取得します。
[を参照します。](#operator-equality)                              | 2 つの `ComPtrRef` オブジェクトが等しいかどうかを示します。
[を参照してください。:演算子!=](#operator-inequality)                            | 2 つの `ComPtrRef` オブジェクトが等しくないかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="comptrrefcomptrref"></a><a name="comptrref"></a>コンプトルレフ::コムプトルレフ

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>パラメーター

*Ptr*<br/>
別`ComPtrRef`のオブジェクトの基になる値。

### <a name="remarks"></a>解説

指定したポインターから別`ComPtrRef``ComPtrRef`のオブジェクトへのクラスの新しいインスタンスを初期化します。

## <a name="comptrrefgetaddressof"></a><a name="getaddressof"></a>を見る

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>戻り値

現在`ComPtrRef`のオブジェクトによって表されるインターフェイスへのポインターのアドレス。

### <a name="remarks"></a>解説

現在`ComPtrRef`のオブジェクトによって表されるインターフェイスへのポインターのアドレスを取得します。

## <a name="comptrrefoperator"></a><a name="operator-equality"></a>を参照します。

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>パラメーター

*A*<br/>
`ComPtrRef` オブジェクトへの参照です。

*B*<br/>
別`ComPtrRef`のオブジェクトへの参照、または匿名型へのポインター (`void*`) 。

### <a name="return-value"></a>戻り値

最初の演算子は **、** オブジェクト*a*がオブジェクト*b*と等しい場合に true を返します。それ以外の場合**は false。**

2 番目と 3 番目の演算子は、オブジェクト*a*が**nullptr**と等しい場合は**true**を返します。それ以外の場合**は false。**

4 番目と 5 番目の演算子は、オブジェクト*a*がオブジェクト*b*と等しい場合は**true**を返します。それ以外の場合**は false。**

### <a name="remarks"></a>解説

2 つの `ComPtrRef` オブジェクトが等しいかどうかを示します。

## <a name="comptrrefoperator"></a><a name="operator-inequality"></a>を参照してください。:演算子!=

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>パラメーター

*A*<br/>
`ComPtrRef` オブジェクトへの参照です。

*B*<br/>
別`ComPtrRef`のオブジェクトへの参照、または匿名オブジェクトへのポインタ (`void*`)

### <a name="return-value"></a>戻り値

最初の演算子は **、** オブジェクト*a*がオブジェクト*b*と等しくない場合に true を返します。それ以外の場合**は false。**

2 番目と 3 番目の演算子は、オブジェクト*a*が**nullptr**と等しくない場合は**true**を返します。それ以外の場合**は false。**

4 番目と 5 番目の演算子は、オブジェクト*a*がオブジェクト*b*と等しくない場合は**true**を返します。それ以外の場合**は false。**

### <a name="remarks"></a>解説

2 つの `ComPtrRef` オブジェクトが等しくないかどうかを示します。

## <a name="comptrrefoperator-interfacetype"></a><a name="operator-interfacetype-star-star"></a>インターフェイスタイプ**

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>解説

現在`ComPtrRef`のオブジェクトを削除し、オブジェクトによって表されたインターフェイスへのポインターを`ComPtrRef`返します。

## <a name="comptrrefoperator"></a><a name="operator-star"></a>演算子*

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>戻り値

現在`ComPtrRef`のオブジェクトによって表されるインターフェイスへのポインター。

### <a name="remarks"></a>解説

現在`ComPtrRef`のオブジェクトによって表されるインターフェイスへのポインターを取得します。

## <a name="comptrrefoperator-t"></a><a name="operator-t-star"></a>オペレーター T*

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
operator T*();
```

### <a name="remarks"></a>解説

現在`ComPtrRef`のオブジェクトの[ptr_](comptrrefbase-class.md#ptr)データ メンバーの値を返します。

## <a name="comptrrefoperator-void"></a><a name="operator-void-star-star"></a>オペレーターボイド\*\*

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
operator void**() const;
```

### <a name="remarks"></a>解説

現在`ComPtrRef`のオブジェクトを削除し、オブジェクトがポインターからポインターへのポインターとして表した`ComPtrRef`インターフェイスにポインターを`void`キャストし、キャスト ポインターを返します。

## <a name="comptrrefreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>を見る

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>戻り値

削除された`ComPtrRef`オブジェクトによって表されたインターフェイスへのポインター。

### <a name="remarks"></a>解説

現在`ComPtrRef`のオブジェクトを削除し、オブジェクトによって表されたインターフェイスへのポインターを`ComPtrRef`返します。
