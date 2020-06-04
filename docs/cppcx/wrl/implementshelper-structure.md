---
title: ImplementsHelper 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
ms.openlocfilehash: e33842f574df5617fb40c5b3f6bb8324d5ba7c1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371394"
---
# <a name="implementshelper-structure"></a>ImplementsHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>パラメーター

*クラスフラグT*<br/>
1 つ以上の[ランタイムクラスタイプ](runtimeclasstype-enumeration.md)列挙子を指定するフラグのフィールド。

*イルスト*<br/>
インターフェイス ID のリスト。

*クラスをデリゲートします。*<br/>
の**true**現在のインスタンス`Implements`が *、最初*のインターフェイス ID の基本クラスである場合は true を指定します。それ以外の場合**は false。**

## <a name="remarks"></a>解説

[実装構造体の実装に](implements-structure.md)役立ちます。

このテンプレートは、インターフェイスのリストを走査し、それらを基本クラスとして追加し、有効にするために必要`QueryInterface`な情報として追加します。

## <a name="members"></a>メンバー

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                    | 説明
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[ヘルパーを実装します。:CanCastTo](#cancastto)               | 指定したインターフェイス ID へのポインターを取得します。
[ヘルパーを実装します。:キャストを知らない](#casttounknown)       | 現在`Implements`の構造体の基になる`IUnknown`インターフェイスへのポインターを取得します。
[ヘルパーを実装します。:フィルアレイウィズイド](#fillarraywithiid) | 現在のゼロ番目のテンプレート パラメーターで指定されたインターフェイス ID を、指定した配列要素に挿入します。
[ヘルパーを実装します::Iidカウント](#iidcount)                 | 現在`Implements`のオブジェクトに実装されているインターフェイス ID の数を保持します。

## <a name="inheritance-hierarchy"></a>継承階層

`ImplementsHelper`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="implementshelpercancastto"></a><a name="cancastto"></a>ヘルパーを実装します。:CanCastTo

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);

HRESULT CanCastTo(
   _In_ const IID &iid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID への参照。

*Ppv*<br/>
この操作が成功した場合は *、riid*または*iid*で指定されたインターフェイスへのポインタ。

*Iid*<br/>
インターフェイス ID への参照。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

指定したインターフェイス ID へのポインターを取得します。

## <a name="implementshelpercasttounknown"></a><a name="casttounknown"></a>ヘルパーを実装します。:キャストを知らない

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>戻り値

基になる`IUnknown`インターフェイスへのポインター。

### <a name="remarks"></a>解説

現在`Implements`の構造体の基になる`IUnknown`インターフェイスへのポインターを取得します。

## <a name="implementshelperfillarraywithiid"></a><a name="fillarraywithiid"></a>ヘルパーを実装します。:フィルアレイウィズイド

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>パラメーター

*index*<br/>
この操作の開始配列要素を示す 0 から始まるインデックス。 この操作が完了すると、*インデックス*は 1 ずつ増加します。

*Iid*<br/>
型 IID の配列。

### <a name="remarks"></a>解説

現在のゼロ番目のテンプレート パラメーターで指定されたインターフェイス ID を、指定した配列要素に挿入します。

## <a name="implementshelperiidcount"></a><a name="iidcount"></a>ヘルパーを実装します::Iidカウント

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>解説

現在`Implements`のオブジェクトに実装されているインターフェイス ID の数を保持します。
