---
title: Platform::MTAThreadAttribute クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::MTAThreadAttribute::Equals
- VCCORLIB/Platform::MTAThreadAttribute::GetHashCode
- VCCORLIB/Platform::MTAThreadAttribute::ToString
helpviewer_keywords:
- Platform::MTAThreadAttribute Class
ms.assetid: bfc546a7-4333-4407-85b4-4721565e1f44
ms.openlocfilehash: 700eeae226be48c1f6659d621f2f5c0ed397bb7f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213048"
---
# <a name="platformmtathreadattribute-class"></a>Platform::MTAThreadAttribute クラス

アプリケーションのスレッド モデルがマルチスレッド アパートメント (MTA) であることを示します。

## <a name="syntax"></a>構文

```
public ref class MTAThreadAttribute sealed : Attribute
```

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[MTAThreadAttribute コンストラクター 1](#ctor)コンストラクター|クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

MTAThreadAttribute 属性は、 [Platform:: Object クラス](../cppcx/platform-object-class.md)から継承されます。 また MTAThreadAttribute は次のメンバーをオーバーロードしたり、含んだりします。

|名前|説明|
|----------|-----------------|
|[MTAThreadAttribute::Equals](#equals)|指定されたオブジェクトが現在のオブジェクトと等しいかどうかを判断します。|
|[MTAThreadAttribute::GetHashCode](#gethashcode)|このインスタンスのハッシュ コードを返します。|
|[MTAThreadAttribute::ToString](#tostring)|現在のオブジェクトを表す文字列を返します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Platform`

### <a name="requirements"></a>必要条件

**メタデータ:** platform. winmd

**名前空間:** Platform

## <a name="mtathreadattribute-constructor"></a><a name="ctor"></a>MTAThreadAttribute コンストラクター

MTAThreadAttribute クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
public:MTAThreadAttribute();
```

## <a name="mtathreadattributeequals"></a><a name="equals"></a>MTAThreadAttribute:: Equals

指定されたオブジェクトが現在のオブジェクトと等しいかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
比較するオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** オブジェクトが等しい場合は。それ以外の場合は **`false`** 。

## <a name="mtathreadattributegethashcode"></a><a name="gethashcode"></a>MTAThreadAttribute:: GetHashCode

このインスタンスのハッシュ コードを返します。

### <a name="syntax"></a>構文

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>戻り値

対象のインスタンスのハッシュ コード。

## <a name="mtathreadattributetostring"></a><a name="tostring"></a>MTAThreadAttribute:: ToString

現在のオブジェクトを表す文字列を返します。

### <a name="syntax"></a>構文

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>戻り値

現在のオブジェクトを表す文字列。

## <a name="see-also"></a>関連項目

[Platform 名前空間](platform-namespace-c-cx.md)
