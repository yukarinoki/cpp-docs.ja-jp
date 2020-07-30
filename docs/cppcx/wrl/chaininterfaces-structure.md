---
title: ChainInterfaces 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
- implements/Microsoft::WRL::ChainInterfaces::IidCount
- implements/Microsoft::WRL::ChainInterfaces::Verify
helpviewer_keywords:
- Microsoft::WRL::ChainInterfaces structure
- Microsoft::WRL::ChainInterfaces::CanCastTo method
- Microsoft::WRL::ChainInterfaces::CastToUnknown method
- Microsoft::WRL::ChainInterfaces::FillArrayWithIid method
- Microsoft::WRL::ChainInterfaces::IidCount constant
- Microsoft::WRL::ChainInterfaces::Verify method
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
ms.openlocfilehash: 48b663f2042ff0095466d83fe872ef6196112f76
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211542"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces 構造体

一連のインターフェイス ID に適用できる検証および初期化関数を指定します。

## <a name="syntax"></a>構文

```cpp
template <
    typename I0,
    typename I1,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct ChainInterfaces : I0;

template <
    typename DerivedType,
    typename BaseType,
    bool hasImplements,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8,
    typename I9
>
struct ChainInterfaces<
    MixIn<
        DerivedType,
        BaseType,
        hasImplements
    >, I1, I2, I3, I4, I5, I6, I7, I8, I9
>;
```

### <a name="parameters"></a>パラメーター

*I0*<br/>
必要インターフェイス ID 0。

*I1*<br/>
必要インターフェイス ID 1。

*I2*<br/>
Optionalインターフェイス ID 2。

*I3*<br/>
Optionalインターフェイス ID 3。

*I4*<br/>
Optionalインターフェイス ID 4。

*I5*<br/>
Optionalインターフェイス ID 5。

*I6*<br/>
Optionalインターフェイス ID 6。

*I7*<br/>
Optionalインターフェイス ID 7。

*I8*<br/>
Optionalインターフェイス ID 8。

*I9*<br/>
Optionalインターフェイス ID 9。

*DerivedType*<br/>
派生型。

*BaseType*<br/>
派生型の基本型。

*hasImplements*<br/>
ブール値。を指定すると、 **`true`** [実装](implements-structure.md)構造から派生していないクラスで[MixIn](mixin-structure.md)構造体を使用できないことを意味します。

## <a name="members"></a>メンバー

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                   | 説明
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ChainInterfaces:: CanCastTo](#cancastto)               | 指定されたインターフェイス ID を、テンプレートパラメーターによって定義された各特殊化にキャストできるかどうかを示し `ChainInterface` ます。
[ChainInterfaces:: CastToUnknown](#casttounknown)       | *I0* template パラメーターによって定義された型のインターフェイスポインターをへのポインターにキャストし `IUnknown` ます。
[ChainInterfaces:: FillArrayWithIid](#fillarraywithiid) | *I0* template パラメーターによって定義されたインターフェイス id を、指定したインターフェイス id の配列内の指定した位置に格納します。
[ChainInterfaces:: Verify](#verify)                     | テンプレートパラメーターによって定義されている各インターフェイスが*I0*から*I9*を継承している `IUnknown` かどうか、および `IInspectable` *I0*が*I1* ~ *I9*を継承していることを確認します。

### <a name="protected-constants"></a>プロテクト定数

名前                                   | 説明
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[ChainInterfaces:: IidCount](#iidcount) | テンプレートパラメーターによって指定されたインターフェイスに含まれるインターフェイス Id の合計数*I0*から*I9*です。

## <a name="inheritance-hierarchy"></a>継承階層

`I0`

`ChainInterfaces`

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="chaininterfacescancastto"></a><a name="cancastto"></a>ChainInterfaces:: CanCastTo

指定したインターフェイス ID を、既定以外のテンプレートパラメーターで定義されている各特殊化にキャストできるかどうかを示します。

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*ppv*<br/>
正常にキャストされた最後のインターフェイス ID へのポインター。

### <a name="return-value"></a>戻り値

**`true`** すべてのキャスト操作が成功した場合は。それ以外の場合は **`false`** 。

## <a name="chaininterfacescasttounknown"></a><a name="casttounknown"></a>ChainInterfaces:: CastToUnknown

*I0* template パラメーターによって定義された型のインターフェイスポインターをへのポインターにキャストし `IUnknown` ます。

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>戻り値

`IUnknown` を指すポインターです。

## <a name="chaininterfacesfillarraywithiid"></a><a name="fillarraywithiid"></a>ChainInterfaces:: FillArrayWithIid

*I0* template パラメーターによって定義されたインターフェイス id を、指定したインターフェイス id の配列内の指定した位置に格納します。

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>パラメーター

*インデックス*<br/>
*Iid が*配列へのインデックス値へのポインター。

*iid が*<br/>
インターフェイス Id の配列。

## <a name="chaininterfacesiidcount"></a><a name="iidcount"></a>ChainInterfaces:: IidCount

テンプレートパラメーターによって指定されたインターフェイスに含まれるインターフェイス Id の合計数*I0*から*I9*です。

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>戻り値

インターフェイス Id の合計数。

### <a name="remarks"></a>解説

テンプレートパラメーター *I0*と*I1*が必要です。また、 *I9* *からの*パラメーターは省略可能です。 各インターフェイスの IID カウントは通常1です。

## <a name="chaininterfacesverify"></a><a name="verify"></a>ChainInterfaces:: Verify

テンプレートパラメーターによって定義されている各インターフェイスが*I0*から*I9*を継承している `IUnknown` かどうか、および `IInspectable` *I0*が*I1* ~ *I9*を継承していることを確認します。

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>解説

検証操作が失敗した場合、は **`static_assert`** エラーを説明するエラーメッセージを出力します。

テンプレートパラメーター *I0*と*I1*が必要です。また、 *I9* *からの*パラメーターは省略可能です。
