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
ms.openlocfilehash: d7908670b67df7dbf7b2b74e98f8b59cf30f8e96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184944"
---
# <a name="implementshelper-structure"></a>ImplementsHelper 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>パラメーター

*RuntimeClassFlagsT*<br/>
1つ以上の[RuntimeClassType](runtimeclasstype-enumeration.md)列挙子を指定するフラグのフィールドです。

*ILst*<br/>
インターフェイス Id のリスト。

*IsDelegateToClass*<br/>
**`true`** の現在のインスタンスが、 `Implements` *ilst*の最初のインターフェイス ID の基本クラスである場合はを指定します。それ以外の場合はを指定し **`false`** ます。

## <a name="remarks"></a>解説

[Implements](implements-structure.md)構造体を実装するのに役立ちます。

このテンプレートは、インターフェイスの一覧を走査し、基本クラスとして、およびを有効にするために必要な情報として追加し `QueryInterface` ます。

## <a name="members"></a>メンバー

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                    | 説明
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[ImplementsHelper:: CanCastTo](#cancastto)               | 指定したインターフェイス ID へのポインターを取得します。
[ImplementsHelper:: CastToUnknown](#casttounknown)       | 現在の構造体の基になるインターフェイスへのポインターを取得し `IUnknown` `Implements` ます。
[ImplementsHelper:: FillArrayWithIid](#fillarraywithiid) | 現在の取り出し template パラメーターによって指定されたインターフェイス ID を、指定された配列要素に挿入します。
[ImplementsHelper:: IidCount](#iidcount)                 | 現在のオブジェクト内の実装されたインターフェイス Id の数を保持し `Implements` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`ImplementsHelper`

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="implementshelpercancastto"></a><a name="cancastto"></a>ImplementsHelper:: CanCastTo

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

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

*ppv*<br/>
この操作が成功した場合は、 *riid*または*iid*によって指定されたインターフェイスへのポインター。

*iid*<br/>
インターフェイス ID への参照。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

指定したインターフェイス ID へのポインターを取得します。

## <a name="implementshelpercasttounknown"></a><a name="casttounknown"></a>ImplementsHelper:: CastToUnknown

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>戻り値

基になるインターフェイスへのポインター `IUnknown` 。

### <a name="remarks"></a>解説

現在の構造体の基になるインターフェイスへのポインターを取得し `IUnknown` `Implements` ます。

## <a name="implementshelperfillarraywithiid"></a><a name="fillarraywithiid"></a>ImplementsHelper:: FillArrayWithIid

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>パラメーター

*インデックス*<br/>
この操作の開始配列要素を示す0から始まるインデックス。 この操作が完了すると、*インデックス*は1ずつインクリメントされます。

*iid が*<br/>
Iid が型の配列。

### <a name="remarks"></a>解説

現在の取り出し template パラメーターによって指定されたインターフェイス ID を、指定された配列要素に挿入します。

## <a name="implementshelperiidcount"></a><a name="iidcount"></a>ImplementsHelper:: IidCount

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>解説

現在のオブジェクト内の実装されたインターフェイス Id の数を保持し `Implements` ます。
