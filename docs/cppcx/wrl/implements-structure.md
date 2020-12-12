---
description: '詳細情報: Implements 構造体'
title: Implements 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
- implements/Microsoft::WRL::Implements::CanCastTo
- implements/Microsoft::WRL::Implements::CastToUnknown
- implements/Microsoft::WRL::Implements::FillArrayWithIid
- implements/Microsoft::WRL::Implements::IidCount
helpviewer_keywords:
- Microsoft::WRL::Implements structure
- Microsoft::WRL::Implements::CanCastTo method
- Microsoft::WRL::Implements::CastToUnknown method
- Microsoft::WRL::Implements::FillArrayWithIid method
- Microsoft::WRL::Implements::IidCount method
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
ms.openlocfilehash: b438e012b23e34b08956c969ffe604878d3065fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249829"
---
# <a name="implements-structure"></a>Implements 構造体

`QueryInterface`指定し `GetIid` たインターフェイスに対しておよびを実装します。

## <a name="syntax"></a>構文

```cpp
template <
    typename I0,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct __declspec(novtable) Implements :
    Details::ImplementsHelper<
        RuntimeClassFlags<WinRt>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8, I9
        >::TypeT
    >,
    Details::ImplementsBase;

template <
    int flags,
    typename I0,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8
>
struct __declspec(novtable) Implements<
        RuntimeClassFlags<flags>,
        I0, I1, I2, I3, I4, I5, I6, I7, I8> :
    Details::ImplementsHelper<
        RuntimeClassFlags<flags>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8
        >::TypeT
    >,
    Details::ImplementsBase;
```

### <a name="parameters"></a>パラメーター

*I0*<br/>
0 番目のインターフェイス ID です  (必須)

*I1*<br/>
1 番目のインターフェイス ID です  (省略可能)

*I2*<br/>
2 番目のインターフェイス ID です  (省略可能)

*I3*<br/>
3 番目のインターフェイス ID です  (省略可能)

*I4*<br/>
4 番目のインターフェイス ID です  (省略可能)

*I5*<br/>
5 番目のインターフェイス ID です  (省略可能)

*I6*<br/>
6 番目のインターフェイス ID です  (省略可能)

*I7*<br/>
7 番目のインターフェイス ID です  (省略可能)

*I8*<br/>
8番目のインターフェイス ID。 (省略可能)

*I9*<br/>
9 番目のインターフェイス ID です  (省略可能)

*flags*<br/>
クラスの構成フラグ。 [RuntimeClassFlags](runtimeclassflags-structure.md)構造体で指定された1つ以上の[RuntimeClassType](runtimeclasstype-enumeration.md)列挙体。

## <a name="remarks"></a>解説

指定されたインターフェイスのリストから派生し、およびのヘルパーテンプレートを実装し `QueryInterface` `GetIid` ます。

各 *I0* *I9* interface パラメーターは `IUnknown` 、、 `IInspectable` 、または [ChainInterfaces](chaininterfaces-structure.md) テンプレートから派生する必要があります。 *Flags* パラメーターは、またはに対してサポートを生成するかどうかを決定し `IUnknown` `IInspectable` ます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

| 名前        | 説明                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| `RuntimeClassFlags<WinRt>` と同義。 |

### <a name="protected-methods"></a>プロテクト メソッド

| 名前                                              | 説明                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Implements:: CanCastTo](#cancastto)               | 指定したインターフェイスへのポインターを取得します。                                                                    |
| [Implements:: CastToUnknown](#casttounknown)       | 基になるインターフェイスへのポインターを取得し `IUnknown` ます。                                                        |
| [Implements:: FillArrayWithIid](#fillarraywithiid) | 現在の取り出し template パラメーターによって指定されたインターフェイス ID を、指定された配列要素に挿入します。 |

### <a name="protected-constants"></a>プロテクト定数

| 名前                              | 説明                                    |
| --------------------------------- | ---------------------------------------------- |
| [Implements:: IidCount](#iidcount) | 実装されているインターフェイス Id の数を保持します。 |

## <a name="inheritance-hierarchy"></a>継承階層

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="implementscancastto"></a><a name="cancastto"></a> Implements:: CanCastTo

指定したインターフェイスへのポインターを取得します。

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID への参照。

*ppv*<br/>
成功した場合は、 *riid* によって指定されたインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_NOINTERFACE などのエラーを示す HRESULT。

### <a name="remarks"></a>解説

これは、QueryInterface 操作を実行する内部ヘルパー関数です。

## <a name="implementscasttounknown"></a><a name="casttounknown"></a> Implements:: CastToUnknown

基になるインターフェイスへのポインターを取得し `IUnknown` ます。

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>戻り値

この操作は常に成功し、ポインターを返し `IUnknown` ます。

### <a name="remarks"></a>解説

内部ヘルパー関数。

## <a name="implementsfillarraywithiid"></a><a name="fillarraywithiid"></a> Implements:: FillArrayWithIid

現在の取り出し template パラメーターによって指定されたインターフェイス ID を、指定された配列要素に挿入します。

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>パラメーター

*インデックス*<br/>
この操作の開始配列要素を示す0から始まるインデックス。 この操作が完了すると、 *インデックス* は1ずつインクリメントされます。

*iid が*<br/>
IID 型の配列。

### <a name="remarks"></a>解説

内部ヘルパー関数。

## <a name="implementsiidcount"></a><a name="iidcount"></a> Implements:: IidCount

実装されているインターフェイス Id の数を保持します。

```cpp
static const unsigned long IidCount;
```
