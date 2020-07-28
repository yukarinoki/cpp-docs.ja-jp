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
ms.openlocfilehash: f92a3e14018cf8c02dec40b664b72a0956f6220e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220536"
---
# <a name="comptrref-class"></a>ComPtrRef クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
によって表されるインターフェイスだけでなく、 [Comptr \<T> ](comptr-class.md)型またはそれから派生した型 `ComPtr` 。

## <a name="remarks"></a>解説

型のオブジェクトへの参照を表し `ComPtr<T>` ます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                               | 説明
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[ComPtrRef:: ComPtrRef](#comptrref) | 別のオブジェクトへのポインターを指定して、クラスの新しいインスタンスを初期化し `ComPtrRef` `ComPtrRef` ます。

### <a name="public-methods"></a>パブリック メソッド

名前                                                         | 説明
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef:: GetAddressOf](#getaddressof)                     | 現在のオブジェクトによって表されるインターフェイスへのポインターのアドレスを取得し `ComPtrRef` ます。
[ComPtrRef:: ReleaseAndGetAddressOf](#releaseandgetaddressof) | 現在のオブジェクトを削除 `ComPtrRef` し、オブジェクトによって表されたインターフェイスへのポインターからポインターを返し `ComPtrRef` ます。

### <a name="public-operators"></a>パブリック演算子

名前                                                                     | 説明
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef:: operator InterfaceType * *](#operator-interfacetype-star-star) | 現在のオブジェクトを削除 `ComPtrRef` し、オブジェクトによって表されたインターフェイスへのポインターからポインターを返し `ComPtrRef` ます。
[ComPtrRef:: operator T *](#operator-t-star)                               | 現在の ComPtrRef オブジェクトの[ptr_](comptrrefbase-class.md#ptr)データメンバーの値を返します。
[ComPtrRef:: operator void * *](#operator-void-star-star)                   | 現在のオブジェクトを削除し、ポインターからポインターへの `ComPtrRef` ポインターとしてオブジェクトによって表されたインターフェイスへのポインターをキャスト `ComPtrRef` し、 **`void`** キャストポインターを返します。
[ComPtrRef:: operator *](#operator-star)                                   | 現在のオブジェクトによって表されるインターフェイスへのポインターを取得し `ComPtrRef` ます。
[ComPtrRef:: operator = =](#operator-equality)                              | 2 つの `ComPtrRef` オブジェクトが等しいかどうかを示します。
[ComPtrRef:: operator! =](#operator-inequality)                            | 2 つの `ComPtrRef` オブジェクトが等しくないかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="comptrrefcomptrref"></a><a name="comptrref"></a>ComPtrRef:: ComPtrRef

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>パラメーター

*ptr*<br/>
別のオブジェクトの基になる値 `ComPtrRef` 。

### <a name="remarks"></a>解説

別のオブジェクトへのポインターを指定して、クラスの新しいインスタンスを初期化し `ComPtrRef` `ComPtrRef` ます。

## <a name="comptrrefgetaddressof"></a><a name="getaddressof"></a>ComPtrRef:: GetAddressOf

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>戻り値

現在のオブジェクトによって表されるインターフェイスへのポインターのアドレス `ComPtrRef` 。

### <a name="remarks"></a>解説

現在のオブジェクトによって表されるインターフェイスへのポインターのアドレスを取得し `ComPtrRef` ます。

## <a name="comptrrefoperator"></a><a name="operator-equality"></a>ComPtrRef:: operator = =

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

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

*ある*<br/>
`ComPtrRef` オブジェクトへの参照です。

*b*<br/>
別のオブジェクトへの参照 `ComPtrRef` 、または匿名型 () へのポインター **`void*`** 。

### <a name="return-value"></a>戻り値

最初の演算子は、 **`true`** オブジェクト*a*がオブジェクト*b*と等しい場合はを生成します。それ以外の場合はを返し **`false`** ます。

2番目と3番目の演算子は、 **`true`** オブジェクト*a*がと等しい場合はを、 **`nullptr`** それ以外の場合はを生成します **`false`** 。

4番目と5番目の演算子は、 **`true`** オブジェクト*a*がオブジェクト*b*と等しい場合はを、それ以外の場合はを生成し **`false`** ます。

### <a name="remarks"></a>解説

2 つの `ComPtrRef` オブジェクトが等しいかどうかを示します。

## <a name="comptrrefoperator"></a><a name="operator-inequality"></a>ComPtrRef:: operator! =

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

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

*ある*<br/>
`ComPtrRef` オブジェクトへの参照です。

*b*<br/>
別のオブジェクトへの参照、 `ComPtrRef` または匿名オブジェクトへのポインター ( **`void*`** )。

### <a name="return-value"></a>戻り値

最初の演算子は、 **`true`** オブジェクト*a*がオブジェクト*b*と等しくない場合はを、それ以外の場合はを生成 **`false`** します。

2番目と3番目の演算子は、 **`true`** オブジェクト*a*がと等しくない場合はを、 **`nullptr`** それ以外の場合はを生成します **`false`** 。

4番目と5番目の演算子は、 **`true`** オブジェクト*a*がオブジェクト*b*と等しくない場合はを、それ以外の場合はを生成し **`false`** ます。

### <a name="remarks"></a>解説

2 つの `ComPtrRef` オブジェクトが等しくないかどうかを示します。

## <a name="comptrrefoperator-interfacetype"></a><a name="operator-interfacetype-star-star"></a>ComPtrRef:: operator InterfaceType\*\*

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>解説

現在のオブジェクトを削除 `ComPtrRef` し、オブジェクトによって表されたインターフェイスへのポインターからポインターを返し `ComPtrRef` ます。

## <a name="comptrrefoperator"></a><a name="operator-star"></a>ComPtrRef:: operator *

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>戻り値

現在のオブジェクトによって表されるインターフェイスへのポインター `ComPtrRef` 。

### <a name="remarks"></a>解説

現在のオブジェクトによって表されるインターフェイスへのポインターを取得し `ComPtrRef` ます。

## <a name="comptrrefoperator-t"></a><a name="operator-t-star"></a>ComPtrRef:: operator T *

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
operator T*();
```

### <a name="remarks"></a>解説

現在のオブジェクトの[ptr_](comptrrefbase-class.md#ptr)データメンバーの値を返し `ComPtrRef` ます。

## <a name="comptrrefoperator-void"></a><a name="operator-void-star-star"></a>ComPtrRef:: operator void\*\*

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
operator void**() const;
```

### <a name="remarks"></a>解説

現在のオブジェクトを削除し、ポインターからポインターへの `ComPtrRef` ポインターとしてオブジェクトによって表されたインターフェイスへのポインターをキャスト `ComPtrRef` し、 **`void`** キャストポインターを返します。

## <a name="comptrrefreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtrRef:: ReleaseAndGetAddressOf

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>戻り値

削除されたオブジェクトによって表されるインターフェイスへのポインター `ComPtrRef` 。

### <a name="remarks"></a>解説

現在のオブジェクトを削除 `ComPtrRef` し、オブジェクトによって表されたインターフェイスへのポインターからポインターを返し `ComPtrRef` ます。
