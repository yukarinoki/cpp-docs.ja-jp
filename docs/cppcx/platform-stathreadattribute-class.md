---
description: '詳細情報: Platform:: STAThreadAttribute クラス'
title: Platform::STAThreadAttribute クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
helpviewer_keywords:
- Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
ms.openlocfilehash: a1c235ef9a171e650c960df184b081c4b6511cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308004"
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute クラス

アプリケーションのスレッド モデルがシングル スレッド アパートメント (STA) であることを示します。

## <a name="syntax"></a>構文

```
public ref class STAThreadAttribute sealed : Attribute
```

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[STAThreadAttribute コンストラクター 1](#ctor)|クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

STAThreadAttribute 属性は、 [Platform:: Object クラス](../cppcx/platform-object-class.md)から継承されます。 また STAThreadAttribute は次のメンバーもオーバーロードしたり、含んだりします。

|名前|説明|
|----------|-----------------|
|[STAThreadAttribute::Equals](#equals)|指定されたオブジェクトが現在のオブジェクトと等しいかどうかを判断します。|
|[STAThreadAttribute::GetHashCode](#gethashcode)|このインスタンスのハッシュ コードを返します。|
|[STAThreadAttribute::ToString](#tostring)|現在のオブジェクトを表す文字列を返します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Platform`

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Platform

## <a name="stathreadattribute-constructor"></a><a name="ctor"></a> STAThreadAttribute constructor

STAThreadAttribute クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
public:STAThreadAttribute();
```

## <a name="stathreadattributeequals"></a><a name="equals"></a> STAThreadAttribute:: Equals

指定されたオブジェクトが現在のオブジェクトと等しいかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
比較対象のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** オブジェクトが等しい場合は。それ以外の場合は **`false`** 。

## <a name="stathreadattributegethashcode"></a><a name="gethashcode"></a> STAThreadAttribute:: GetHashCode

このインスタンスのハッシュ コードを返します。

### <a name="syntax"></a>構文

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>戻り値

対象のインスタンスのハッシュ コード。

## <a name="stathreadattributetostring"></a><a name="tostring"></a> STAThreadAttribute:: ToString

現在のオブジェクトを表す文字列を返します。

### <a name="syntax"></a>構文

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>戻り値

現在のオブジェクトを表す文字列。

## <a name="see-also"></a>関連項目

[Platform 名前空間](platform-namespace-c-cx.md)
