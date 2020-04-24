---
title: Platform::Guid 値クラス
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 3849074f93424912b1dc5b93883482a6cb55892a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750659"
---
# <a name="platformguid-value-class"></a>Platform::Guid 値クラス

Windows ランタイム型システムの [GUID](/ウィンドウ/win32/api/guiddef/ns-guid-guid 型) を表します。

## <a name="syntax"></a>構文

```cpp
public value struct Guid
```

### <a name="members"></a>メンバー

`Platform::Guid`には`Equals()`、 `GetHashCode()`、 `ToString()` 、 、 、 および 、 プラットフォーム`GetTypeCode()`: オブジェクト[クラス](../cppcx/platform-object-class.md)から派生したメソッド[があります。](../cppcx/platform-type-class.md) `Platform::Guid`また、以下のメンバーを持っています。

|メンバー|説明|
|------------|-----------------|
|[Guid](#ctor)|`Platform::Guid` の新しいインスタンスを初期化します。|
|[演算子==](#operator-equality)|等号演算子です。|
|[演算子!=](#operator-inequality)|不等号演算子です。|
|[演算子&lt;](#operator-less)|小なり演算子です。|
|[Operator()](#operator-call)|`Platform::Guid` を `GUID`に変換します。|

### <a name="remarks"></a>解説

新しい`Platform::Guid`を生成するには、[静的](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid)メソッドを使用します。

### <a name="requirements"></a>必要条件

**サポートされる最小クライアント:** ウィンドウズ 8

**サポートされる最小サーバー:** ウィンドウズ サーバー 2012

**名前空間:** Platform

**メタデータ:** プラットフォーム.winmd

## <a name="guidguid-constructors"></a><a name="ctor"></a>Guid::Guidコンストラクタ

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

*A*<br/>
の最初の 4`GUID`バイト。

*B*<br/>
の次の 2`GUID`バイトです。

*C*<br/>
の次の 2`GUID`バイトです。

*D*<br/>
`GUID` の次のバイト。

*E*<br/>
`GUID` の次のバイト。

*F*<br/>
`GUID` の次のバイト。

*G*<br/>
`GUID` の次のバイト。

*H*<br/>
`GUID` の次のバイト。

*私*<br/>
`GUID` の次のバイト。

*J*<br/>
`GUID` の次のバイト。

*K*<br/>
`GUID` の次のバイト。

*M*<br/>
A`GUID`を GUID[構造体](/windows/win32/api/guiddef/ns-guiddef-guid)の形式で指定します。

*n*<br/>
残りの 8 バイト`GUID`の .

## <a name="guidoperator-operator"></a><a name="operator-equality"></a>誘導:演算子== 演算子

2 つの `Platform::Guid` インスタンスを比較し、相互に等価かどうかを判断します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる最初の `Platform::Guid`。

*ガイド2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

2 つの`Platform::Guid`インスタンスが等しい場合は True。

### <a name="remarks"></a>解説

静的メソッドの`==`代わりに演算子[を使用することをお好み](/uwp/api/windows.foundation.guidhelper.equals)で行います。

## <a name="guidoperator-operator"></a><a name="operator-inequality"></a>誘導:演算子!= 演算子

2 つの `Platform::Guid` インスタンスを比較し、等しくないかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる最初の `Platform::Guid`。

*ガイド2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

2 つの`Platform::Guid`インスタンスが等しくない場合は true。

## <a name="guidoperatorlt-operator"></a><a name="operator-less"></a>誘導:演算子&lt;

2 つの`Platform::Guid`インスタンスを並べ替え用に比較します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる最初の `Platform::Guid`。

*ガイド2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

*guid1*が*guid2*の前に並べ替えられた場合は True。 順序は、それぞれが`Platform::Guid`4 つの 32 ビット符号なし値の配列であるかのように処理した後の辞書式です。 これは、SQL Server や .NET Framework で使用される順序ではなく、文字列表現による辞書順と同じでもありません。

この演算子は`Guid`、C++ 標準ライブラリでオブジェクトをより簡単に使用できるように提供されています。

## <a name="guidoperator-operator"></a><a name="operator-call"></a>誘導:演算子() 演算子

暗黙的に、 を`Platform::Guid` [GUID 構造体](/windows/win32/api/guiddef/ns-guiddef-guid)に変換します。

### <a name="syntax"></a>構文

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>戻り値

[GUID 構造体](/windows/win32/api/guiddef/ns-guiddef-guid):

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
