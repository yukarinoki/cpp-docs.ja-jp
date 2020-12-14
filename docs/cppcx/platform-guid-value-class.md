---
description: '詳細情報: Platform:: Guid 値クラス'
title: Platform::Guid 値クラス
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 4c2ffc5096e6b40266fef0934acc562edf721c24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195191"
---
# <a name="platformguid-value-class"></a>Platform::Guid 値クラス

Windows ランタイム型システムの [GUID] (/windows/win32/api/guiddef/ns-guiddef-guid 型を表します。

## <a name="syntax"></a>構文

```cpp
public value struct Guid
```

### <a name="members"></a>メンバー

`Platform::Guid` には `Equals()` 、 `GetHashCode()` `ToString()` [Platform:: Object クラス](../cppcx/platform-object-class.md)から派生した、、およびの各メソッドと、 `GetTypeCode()` [platform:: Type クラス](../cppcx/platform-type-class.md)から派生したメソッドがあります。 `Platform::Guid` には次のメンバーもあります。

|メンバー|説明|
|------------|-----------------|
|[GUID](#ctor)|`Platform::Guid` の新しいインスタンスを初期化します。|
|[operator = =](#operator-equality)|等号演算子です。|
|[operator! =](#operator-inequality)|不等号演算子です。|
|[operator&lt;](#operator-less)|小なり演算子です。|
|[operator ()](#operator-call)|`Platform::Guid` を `GUID`に変換します。|

### <a name="remarks"></a>解説

新しいを生成するには、 `Platform::Guid` [Windows:: Foundation:: guidhelper:: CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid) 静的メソッドを使用します。

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform. winmd

## <a name="guidguid-constructors"></a><a name="ctor"></a> Guid:: Guid コンストラクター

`Platform::Guid` の新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>パラメーター

*ある*<br/>
の最初の4バイト `GUID` 。

*b*<br/>
の次の2バイト `GUID` 。

*c*<br/>
の次の2バイト `GUID` 。

*d*<br/>
`GUID` の次のバイト。

*e*<br/>
`GUID` の次のバイト。

*f*<br/>
`GUID` の次のバイト。

*g*<br/>
`GUID` の次のバイト。

*h*<br/>
`GUID` の次のバイト。

*i*<br/>
`GUID` の次のバイト。

*祭*<br/>
`GUID` の次のバイト。

*k*<br/>
`GUID` の次のバイト。

*m*<br/>
`GUID` [GUID 構造体](/windows/win32/api/guiddef/ns-guiddef-guid)の形式の。

*n*<br/>
の残りの8バイト `GUID` 。

## <a name="guidoperator-operator"></a><a name="operator-equality"></a> Guid:: operator = = 演算子

2 つの `Platform::Guid` インスタンスを比較し、相互に等価かどうかを判断します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる、最初の `Platform::Guid`。

*guid2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

2つの `Platform::Guid` インスタンスが等しい場合は True。

### <a name="remarks"></a>解説

`==` [Windows:: Foundation:: guidhelper:: Equals](/uwp/api/windows.foundation.guidhelper.equals)静的メソッドの代わりに演算子を使用することをお勧めします。

## <a name="guidoperator-operator"></a><a name="operator-inequality"></a> Guid:: operator! = 演算子

2 つの `Platform::Guid` インスタンスを比較し、等しくないかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる、最初の `Platform::Guid`。

*guid2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

2つの `Platform::Guid` インスタンスが等しくない場合は True。

## <a name="guidoperatorlt-operator"></a><a name="operator-less"></a> Guid:: operator &lt; 演算子

2つ `Platform::Guid` のインスタンスの順序を比較します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる、最初の `Platform::Guid`。

*guid2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

*Guid1* が *guid2* の前に並べ替えられている場合は True。 順序付けは、それぞれが `Platform::Guid` 4 32 ビットの符号なしの値の配列であるかのように処理した後、辞書式になります。 これは SQL Server または .NET Framework によって使用される順序ではなく、文字列形式による辞書式の順序付けと同じでもありません。

この演算子は `Guid` 、C++ 標準ライブラリがオブジェクトをより簡単に使用できるようにするために用意されています。

## <a name="guidoperator-operator"></a><a name="operator-call"></a> Guid:: operator () 演算子

を暗黙的 `Platform::Guid` に [GUID 構造体](/windows/win32/api/guiddef/ns-guiddef-guid)に変換します。

### <a name="syntax"></a>構文

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>戻り値

[GUID 構造体](/windows/win32/api/guiddef/ns-guiddef-guid)。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
