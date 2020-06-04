---
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
ms.openlocfilehash: 17f743a38af3ddc600a55e38905d19868d076a22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371371"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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

*クロークタイプ*<br/>
および の場合`RuntimeClass`、サポートされているインターフェイス ID の一覧に含めないインターフェイス。 `Implements` `ChainInterfaces`

## <a name="remarks"></a>解説

インターフェイスの共通の特性を実装します。

2 番目のテンプレートは、クロークされたインターフェイスの特殊化です。 3 番目のテンプレートは、Nil パラメータの特殊化です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a><a name="public-typedefs"></a>パブリック型定義

名前   | 説明
------ | ------------------------------------------
`Base` | *I0*テンプレート パラメーターの同義語。

### <a name="public-methods"></a>パブリック メソッド

名前                                                   | 説明
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[インターフェイストレイト::CanCastTo](#cancastto)               | 指定したポインターを へのポインターにキャストできるかどうかを示します`Base`。
[インターフェイストレイツ::キャストトベース](#casttobase)             | 指定したポインターを へのポインターにキャスト`Base`します。
[インターフェイストレイト::キャストは不明](#casttounknown)       | 指定したポインターを へのポインターにキャスト`IUnknown`します。
[インターフェイストレイト::フィルアレイウィズイッド](#fillarraywithiid) | index 引数で指定された`Base`配列要素にのインターフェイス ID を割り当てます。
[インターフェイストレイツ::検証](#verify)                     | 正しく派生`Base`していることを確認します。

### <a name="public-constants"></a>パブリック定数

名前                                   | 説明
-------------------------------------- | ---------------------------------------------------------------------------------------
[インターフェイストレイツ::Iidカウント](#iidcount) | 現在`InterfaceTraits`のオブジェクトに関連付けられているインターフェイス ID の数を保持します。

## <a name="inheritance-hierarchy"></a>継承階層

`InterfaceTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="interfacetraitscancastto"></a><a name="cancastto"></a>インターフェイストレイト::CanCastTo

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*Ptr*<br/>
型へのポインターの名前。

*riid*<br/>
のインターフェイス`Base`ID。

*Ppv*<br/>
この操作が成功すると、 *ppv*は で指定`Base`されたインターフェイスを指します。 それ以外の場合 *、ppv*は に`nullptr`設定されます。

### <a name="return-value"></a>戻り値

この操作が成功し *、ptr*がポインタにキャストされる場合`Base`は**true。** それ以外の場合**は false。**

### <a name="remarks"></a>解説

指定したポインターを へのポインターにキャストできるかどうかを示します`Base`。

の詳細については`Base`、「[パブリック型定義](#public-typedefs)」セクションを参照してください。

## <a name="interfacetraitscasttobase"></a><a name="casttobase"></a>インターフェイストレイツ::キャストトベース

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
*パラメータ ptr*の型。

*Ptr*<br/>
*型*T へのポインター。

### <a name="return-value"></a>戻り値

`Base` を指すポインターです。

### <a name="remarks"></a>解説

指定したポインターを へのポインターにキャスト`Base`します。

の詳細については`Base`、「[パブリック型定義](#public-typedefs)」セクションを参照してください。

## <a name="interfacetraitscasttounknown"></a><a name="casttounknown"></a>インターフェイストレイト::キャストは不明

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
*パラメータ ptr*の型。

*Ptr*<br/>
*T*型へのポインター 。

### <a name="return-value"></a>戻り値

派生元の IUnknown`Base`へのポインター。

### <a name="remarks"></a>解説

指定したポインターを へのポインターにキャスト`IUnknown`します。

の詳細については`Base`、「[パブリック型定義](#public-typedefs)」セクションを参照してください。

## <a name="interfacetraitsfillarraywithiid"></a><a name="fillarraywithiid"></a>インターフェイストレイト::フィルアレイウィズイッド

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
0 から始まるインデックス値を含むフィールドへのポインター。

*Iid*<br/>
インターフェイス ID の配列。

### <a name="remarks"></a>解説

index 引数で指定された`Base`配列要素にのインターフェイス ID を割り当てます。

この API の名前とは対照的に、1 つの配列要素のみが変更されます。配列全体ではありません。

の詳細については`Base`、「[パブリック型定義](#public-typedefs)」セクションを参照してください。

## <a name="interfacetraitsiidcount"></a><a name="iidcount"></a>インターフェイストレイツ::Iidカウント

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>解説

現在`InterfaceTraits`のオブジェクトに関連付けられているインターフェイス ID の数を保持します。

## <a name="interfacetraitsverify"></a><a name="verify"></a>インターフェイストレイツ::検証

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>解説

正しく派生`Base`していることを確認します。

の詳細については`Base`、「[パブリック型定義](#public-typedefs)」セクションを参照してください。
