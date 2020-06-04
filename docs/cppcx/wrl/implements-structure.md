---
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
ms.openlocfilehash: 223f37d7cabbd0b8cd238582773c05d7b9eaabf6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371404"
---
# <a name="implements-structure"></a>Implements 構造体

指定した`QueryInterface`インターフェイス`GetIid`を実装し、そのインターフェイスを対象にします。

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
8 番目のインターフェイス ID。 (省略可能)

*I9*<br/>
9 番目のインターフェイス ID です  (省略可能)

*フラグ*<br/>
クラスの構成フラグ。 構造体で指定されている 1[つ以上](runtimeclasstype-enumeration.md)の[列挙型の列挙](runtimeclassflags-structure.md)体。

## <a name="remarks"></a>解説

指定したインターフェイスのリストから派生し、 および のヘルパー `QueryInterface` `GetIid`テンプレートを実装します。

I9*までの各* *I0*インターフェイス パラメータ`IUnknown`は`IInspectable`、 、または[ChainInterfaces](chaininterfaces-structure.md)テンプレートから派生する必要があります。 *flags*パラメーターは、サポートが 生成`IUnknown`される`IInspectable`かどうかを決定します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

| 名前        | 説明                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| `RuntimeClassFlags<WinRt>` と同義。 |

### <a name="protected-methods"></a>プロテクト メソッド

| 名前                                              | 説明                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [実装::CanCastTo](#cancastto)               | 指定したインターフェイスへのポインターを取得します。                                                                    |
| [実装::キャストが不明](#casttounknown)       | 基になる`IUnknown`インターフェイスへのポインターを取得します。                                                        |
| [実装::フィルアレイウィズIid](#fillarraywithiid) | 現在のゼロ番目のテンプレート パラメーターで指定されたインターフェイス ID を、指定した配列要素に挿入します。 |

### <a name="protected-constants"></a>保護定数

| 名前                              | 説明                                    |
| --------------------------------- | ---------------------------------------------- |
| [実装::Iidカウント](#iidcount) | 実装されたインターフェイス ID の数を保持します。 |

## <a name="inheritance-hierarchy"></a>継承階層

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** Microsoft::WRL

## <a name="implementscancastto"></a><a name="cancastto"></a>実装::CanCastTo

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

*Ppv*<br/>
正常に実行された場合は、 *riid*で指定されたインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、エラーを示す HRESULT (E_NOINTERFACEなど) を返します。

### <a name="remarks"></a>解説

これは、クエリ インターフェイス操作を実行する内部ヘルパー関数です。

## <a name="implementscasttounknown"></a><a name="casttounknown"></a>実装::キャストが不明

基になる`IUnknown`インターフェイスへのポインターを取得します。

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>戻り値

この操作は常に成功し、`IUnknown`ポインターを返します。

### <a name="remarks"></a>解説

内部ヘルパー関数。

## <a name="implementsfillarraywithiid"></a><a name="fillarraywithiid"></a>実装::フィルアレイウィズIid

現在のゼロ番目のテンプレート パラメーターで指定されたインターフェイス ID を、指定した配列要素に挿入します。

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>パラメーター

*index*<br/>
この操作の開始配列要素を示す 0 から始まるインデックス。 この操作が完了すると、*インデックス*は 1 ずつ増加します。

*Iid*<br/>
型の配列 IID。

### <a name="remarks"></a>解説

内部ヘルパー関数。

## <a name="implementsiidcount"></a><a name="iidcount"></a>実装::Iidカウント

実装されたインターフェイス ID の数を保持します。

```cpp
static const unsigned long IidCount;
```
