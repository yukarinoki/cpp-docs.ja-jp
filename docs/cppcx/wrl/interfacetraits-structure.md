---
description: '詳細情報: InterfaceTraits 構造体'
title: InterfaceTraits 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
- implements/Microsoft::WRL::Details::InterfaceTraits::IidCount
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::InterfaceTraits structure
- Microsoft::WRL::Details::InterfaceTraits::CanCastTo method
- Microsoft::WRL::Details::InterfaceTraits::CastToBase method
- Microsoft::WRL::Details::InterfaceTraits::CastToUnknown method
- Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid method
- Microsoft::WRL::Details::InterfaceTraits::IidCount constant
- Microsoft::WRL::Details::InterfaceTraits::Verify method
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
ms.openlocfilehash: 8dfa540119b0a120ea7b8d9365a0e8b8203939b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124528"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename I0>
struct __declspec(novtable) InterfaceTraits;

template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<
    CloakedIid<CloakedType>
>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>パラメーター

*I0*<br/>
インターフェイスの名前。

*Cloaの種類*<br/>
、、およびの場合 `RuntimeClass` `Implements` `ChainInterfaces` 、サポートされているインターフェイス id のリストに含まれないインターフェイス。

## <a name="remarks"></a>解説

インターフェイスの一般的な特性を実装します。

2番目のテンプレートは、クロークされたインターフェイスの特殊化です。 3番目のテンプレートは、Nil パラメーターの特殊化です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a><a name="public-typedefs"></a> パブリック Typedef

名前   | 説明
------ | ------------------------------------------
`Base` | *I0* template パラメーターのシノニム。

### <a name="public-methods"></a>パブリック メソッド

名前                                                   | 説明
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[InterfaceTraits:: CanCastTo](#cancastto)               | 指定したポインターをへのポインターにキャストできるかどうかを示し `Base` ます。
[InterfaceTraits:: CastToBase](#casttobase)             | 指定したポインターをへのポインターにキャストし `Base` ます。
[InterfaceTraits:: CastToUnknown](#casttounknown)       | 指定したポインターをへのポインターにキャストし `IUnknown` ます。
[InterfaceTraits:: FillArrayWithIid](#fillarraywithiid) | のインターフェイス ID を、 `Base` index 引数で指定された配列要素に割り当てます。
[InterfaceTraits:: Verify](#verify)                     | が適切に派生していることを確認 `Base` します。

### <a name="public-constants"></a>パブリック定数

名前                                   | 説明
-------------------------------------- | ---------------------------------------------------------------------------------------
[InterfaceTraits:: IidCount](#iidcount) | 現在のオブジェクトに関連付けられているインターフェイス Id の数を保持し `InterfaceTraits` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`InterfaceTraits`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="interfacetraitscancastto"></a><a name="cancastto"></a> InterfaceTraits:: CanCastTo

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*ptr*<br/>
型へのポインターの名前。

*riid*<br/>
のインターフェイス ID `Base` 。

*ppv*<br/>
この操作が成功した場合、 *ppv* はによって指定されたインターフェイスをポイントし `Base` ます。 それ以外の場合、 *ppv* はに設定され **`nullptr`** ます。

### <a name="return-value"></a>戻り値

**`true`** この操作が成功し、 *ptr* がへのポインターにキャストされている場合は `Base` 。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

指定したポインターをへのポインターにキャストできるかどうかを示し `Base` ます。

の詳細については `Base` 、「 [パブリック typedef](#public-typedefs) 」セクションを参照してください。

## <a name="interfacetraitscasttobase"></a><a name="casttobase"></a> InterfaceTraits:: CastToBase

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
パラメーター *ptr* の型。

*ptr*<br/>
型 *T* へのポインター。

### <a name="return-value"></a>戻り値

`Base` を指すポインターです。

### <a name="remarks"></a>解説

指定したポインターをへのポインターにキャストし `Base` ます。

の詳細については `Base` 、「 [パブリック typedef](#public-typedefs) 」セクションを参照してください。

## <a name="interfacetraitscasttounknown"></a><a name="casttounknown"></a> InterfaceTraits:: CastToUnknown

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
パラメーター *ptr* の型。

*ptr*<br/>
*T* 型へのポインター。

### <a name="return-value"></a>戻り値

の派生元である IUnknown へのポインター `Base` 。

### <a name="remarks"></a>解説

指定したポインターをへのポインターにキャストし `IUnknown` ます。

の詳細については `Base` 、「 [パブリック typedef](#public-typedefs) 」セクションを参照してください。

## <a name="interfacetraitsfillarraywithiid"></a><a name="fillarraywithiid"></a> InterfaceTraits:: FillArrayWithIid

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>パラメーター

*インデックス*<br/>
0から始まるインデックス値を格納しているフィールドへのポインター。

*iid が*<br/>
インターフェイス Id の配列。

### <a name="remarks"></a>解説

のインターフェイス ID を、 `Base` index 引数で指定された配列要素に割り当てます。

この API の名前とは対照的に、1つの配列要素のみが変更されます。配列全体ではありません。

の詳細については `Base` 、「 [パブリック typedef](#public-typedefs) 」セクションを参照してください。

## <a name="interfacetraitsiidcount"></a><a name="iidcount"></a> InterfaceTraits:: IidCount

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>解説

現在のオブジェクトに関連付けられているインターフェイス Id の数を保持し `InterfaceTraits` ます。

## <a name="interfacetraitsverify"></a><a name="verify"></a> InterfaceTraits:: Verify

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>解説

が適切に派生していることを確認 `Base` します。

の詳細については `Base` 、「 [パブリック typedef](#public-typedefs) 」セクションを参照してください。
