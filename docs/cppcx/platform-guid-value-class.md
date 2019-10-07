---
title: Platform::Guid 値クラス
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: f63b2bb4fd5f809861622a4f6b255ee3725564b6
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816589"
---
# <a name="platformguid-value-class"></a>Platform::Guid 値クラス

[GUID](/previous-versions/cc317743(v%3dmsdn.10)) の種類を、Windows ランタイムの型システムで表します。

## <a name="syntax"></a>構文

```cpp
public value struct Guid
```

### <a name="members"></a>メンバー

`Platform::Guid` には、 [platform:: Object クラス](../cppcx/platform-object-class.md)から派生した `Equals()`、@no__t 2、および @no__t 3 の各メソッドと、 [Platform:: Type クラス](../cppcx/platform-type-class.md)から派生した @no__t 5 メソッドがあります。 `Platform::Guid` には、次のメンバーもあります。

|メンバー|説明|
|------------|-----------------|
|[Guid](#ctor)|`Platform::Guid` の新しいインスタンスを初期化します。|
|[operator==](#operator-equality)|等値演算子。|
|[operator!=](#operator-inequality)|非等値演算子。|
|[operator&lt;](#operator-less)|小なり演算子。|
|[operator()](#operator-call)|`Platform::Guid` を `GUID`に変換します。|

### <a name="remarks"></a>コメント

新しい @no__t 0 を生成するには、 [Windows:: Foundation:: GuidHelper:: CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid)静的メソッドを使用します。

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** プラットフォーム

**メタデータ:** platform.winmd

## <a name="ctor"></a>Guid:: Guid コンストラクター

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

*a*<br/>
@No__t の最初の4バイト。

*b*<br/>
@No__t の次の2バイト (0)。

*c*<br/>
@No__t の次の2バイト (0)。

*d*<br/>
@No__t の次のバイト数-0。

*e*<br/>
@No__t の次のバイト数-0。

*f*<br/>
@No__t の次のバイト数-0。

*g*<br/>
@No__t の次のバイト数-0。

*h*<br/>
@No__t の次のバイト数-0。

*i*<br/>
@No__t の次のバイト数-0。

*祭*<br/>
@No__t の次のバイト数-0。

*k*<br/>
@No__t の次のバイト数-0。

*m*<br/>
[GUID 構造体](/previous-versions/cc317743(v%3dmsdn.10))の形式の `GUID`。

*n*<br/>
@No__t の残りの8バイト。-0。

## <a name="operator-equality"></a>Guid:: operator = = 演算子

2 つの `Platform::Guid` インスタンスを比較し、相互に等価かどうかを判断します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる最初の `Platform::Guid`。

*guid2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

2つの @no__t 0 インスタンスが等しい場合は True。

### <a name="remarks"></a>コメント

[Windows:: Foundation:: GuidHelper:: Equals](/uwp/api/windows.foundation.guidhelper.equals)静的メソッドの代わりに `==` 演算子を使用することをお勧めします。

## <a name="operator-inequality"></a>Guid:: operator! = 演算子

2つの @no__t 0 のインスタンスを比較して等しくないかどうかを比較します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる最初の `Platform::Guid`。

*guid2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

2つの @no__t 0 インスタンスが等しくない場合は True。

## <a name="operator-less"></a>Guid:: operator @ no__t 演算子

2つの @no__t 0 インスタンスの順序付けを比較します。

### <a name="syntax"></a>構文

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>パラメーター

*guid1*<br/>
比較対象となる最初の `Platform::Guid`。

*guid2*<br/>
比較対象となる 2 番目の `Platform::Guid`。

### <a name="return-value"></a>戻り値

*Guid1*が*guid2*の前に並べ替えられている場合は True。 順序付けは、4 32 ビットの符号なしの値の配列であるかのように各 `Platform::Guid` を扱うと、辞書式になります。 これは SQL Server または .NET Framework によって使用される順序ではなく、文字列形式による辞書式の順序付けと同じでもありません。

この演算子は、 C++標準ライブラリで @no__t 0 オブジェクトをより簡単に使用できるようにするために用意されています。

## <a name="operator-call"></a>Guid:: operator () 演算子

@No__t 0 を[GUID 構造体](/previous-versions/cc317743(v%3dmsdn.10))に暗黙的に変換します。

### <a name="syntax"></a>構文

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>戻り値

[GUID 構造体](/previous-versions/cc317743(v%3dmsdn.10))。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
