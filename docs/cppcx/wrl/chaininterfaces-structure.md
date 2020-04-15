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
ms.openlocfilehash: dd1af3fb5c1079a40d8248dc71ae4972537aa856
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372659"
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
(必須)インターフェイス ID 0。

*I1*<br/>
(必須)インターフェイス ID 1。

*I2*<br/>
(オプション)インターフェイス ID 2。

*I3*<br/>
(オプション)インターフェイス ID 3。

*I4*<br/>
(オプション)インターフェイス ID 4。

*I5*<br/>
(オプション)インターフェイス ID 5。

*I6*<br/>
(オプション)インターフェイス ID 6。

*I7*<br/>
(オプション)インターフェイス ID 7。

*I8*<br/>
(オプション)インターフェイス ID 8。

*I9*<br/>
(オプション)インターフェイス ID 9。

*派生型*<br/>
派生型。

*BaseType*<br/>
派生型の基本型。

*を実装しています*<br/>
ブール値を指定すると **、実装**構造から派生していないクラスで[MixIn](mixin-structure.md)構造体[を](implements-structure.md)使用することはできません。

## <a name="members"></a>メンバー

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                   | 説明
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[チェーンインターフェイス::CanCastTo](#cancastto)               | `ChainInterface`指定されたインターフェイス ID を、テンプレート パラメーターで定義された各特殊化にキャストできるかどうかを示します。
[チェーンインターフェイス::キャストは不明](#casttounknown)       | *I0*テンプレート パラメーターで定義された型のインターフェイス ポインターを、 への`IUnknown`ポインターにキャストします。
[インターフェイス::フィルアレイウィズイッド](#fillarraywithiid) | *I0*テンプレート パラメーターで定義されたインターフェイス ID を、指定したインターフェイス ID の配列内の指定した場所に格納します。
[チェーンインターフェイス::検証](#verify)                     | テンプレート パラメータ*I0*から*I9*を通して定義された`IUnknown`各インターフェイスが`IInspectable`、 または から継承し、 *I0*が*I1*から*I9*を継承することを確認します。

### <a name="protected-constants"></a>保護定数

名前                                   | 説明
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[インターフェイス::Iidカウント](#iidcount) | テンプレート パラメータ*I0 から I9*で指定されたインターフェイスに含まれる*I9*インターフェイス ID の総数。

## <a name="inheritance-hierarchy"></a>継承階層

`I0`

`ChainInterfaces`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** Microsoft::WRL

## <a name="chaininterfacescancastto"></a><a name="cancastto"></a>チェーンインターフェイス::CanCastTo

既定以外のテンプレート パラメーターで定義された各特殊化に、指定したインターフェイス ID をキャストできるかどうかを示します。

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*Ppv*<br/>
正常にキャストされた最後のインターフェイス ID へのポインター。

### <a name="return-value"></a>戻り値

すべてのキャスト操作が成功した場合は**true。** それ以外の場合**は false。**

## <a name="chaininterfacescasttounknown"></a><a name="casttounknown"></a>チェーンインターフェイス::キャストは不明

*I0*テンプレート パラメーターで定義された型のインターフェイス ポインターを、 への`IUnknown`ポインターにキャストします。

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>戻り値

`IUnknown` を指すポインターです。

## <a name="chaininterfacesfillarraywithiid"></a><a name="fillarraywithiid"></a>インターフェイス::フィルアレイウィズイッド

*I0*テンプレート パラメーターで定義されたインターフェイス ID を、指定したインターフェイス ID の配列内の指定した場所に格納します。

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
*iids*配列へのインデックス値へのポインター。

*Iid*<br/>
インターフェイス ID の配列。

## <a name="chaininterfacesiidcount"></a><a name="iidcount"></a>インターフェイス::Iidカウント

テンプレート パラメータ*I0 から I9*で指定されたインターフェイスに含まれる*I9*インターフェイス ID の総数。

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>戻り値

インターフェイス ID の合計数。

### <a name="remarks"></a>解説

テンプレート パラメータ*I0*および*I1*は必須で、I2 から*I2**I9*までのパラメータはオプションです。 各インターフェイスの IID カウントは、通常 1 です。

## <a name="chaininterfacesverify"></a><a name="verify"></a>チェーンインターフェイス::検証

テンプレート パラメータ*I0*から*I9*を通して定義された`IUnknown`各インターフェイスが`IInspectable`、 または から継承し、 *I0*が*I1*から*I9*を継承することを確認します。

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>解説

検証操作が失敗すると、エラー`static_assert`を説明するエラー メッセージが出力されます。

テンプレート パラメータ*I0*および*I1*は必須で、I2 から*I2**I9*までのパラメータはオプションです。
