---
description: '詳細情報: Platform:: Object クラス'
title: Platform::Object クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
helpviewer_keywords:
- Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
ms.openlocfilehash: a190d5a56bb27fb95ac2c2c8bd2ba0e0d0572427
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308251"
---
# <a name="platformobject-class"></a>Platform::Object クラス

Windows ランタイムアプリの ref クラスと ref 構造体に共通の動作を提供します。 ref クラスと ref 構造体のインスタンスは、いずれも Platform::Object^ に暗黙的に変換可能で、仮想の ToString メソッドをオーバーライドできます。

## <a name="syntax"></a>構文

```cpp
public ref class Object : Object
```

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Object::Object](#ctor)|Object クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Object::Equals](#equals)|指定されたオブジェクトが現在のオブジェクトと等しいかどうかを判断します。|
|[Object::GetHashCode](#gethashcode)|このインスタンスのハッシュ コードを返します。|
|[Object::ReferenceEquals](#referenceequals)|指定された Object インスタンスが同一のインスタンスかどうかを判断します。|
|[ToString](#tostring)|現在のオブジェクトを表す文字列を返します。 オーバーライドできます。|
|[GetType](#gettype)|現在のインスタンスを記述する [Platform::Type](../cppcx/platform-type-class.md) を取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Object`

`Object`

### <a name="requirements"></a>要件

**ヘッダー:** vccorlib.h

**名前空間:** Platform

## <a name="objectequals-method"></a><a name="equals"></a> Object:: Equals メソッド

指定されたオブジェクトが現在のオブジェクトと等しいかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
bool Equals(
    Object^ obj
)
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
比較対象のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** オブジェクトが等しい場合は。それ以外の場合は **`false`** 。

## <a name="objectgethashcode-method"></a><a name="gethashcode"></a> Object:: GetHashCode メソッド

COM オブジェクトの場合は、このインスタンスの `IUnknown`* ID 値を返します。COM オブジェクトでない場合は、計算済みハッシュ値を返します。

### <a name="syntax"></a>構文

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>戻り値

このオブジェクトを一意に識別する数値。

### <a name="remarks"></a>解説

GetHashCode を使用してマップ内のオブジェクトのキーを作成できます。 [Object:: Equals](#equals)を使用すると、ハッシュコードを比較できます。 コード パスが非常に重要であるときに、`GetHashCode` と `Equals` の実行速度が不十分な場合には、基になる COM レイヤーまで移動して `IUnknown` ネイティブ ポインターの比較を実行できます。

## <a name="objectgettype-method"></a><a name="gettype"></a> Object:: GetType メソッド

オブジェクトのランタイム型を記述する [Platform:: Type](../cppcx/platform-type-class.md) オブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

オブジェクトのランタイム型を記述する [Platform:: Type](../cppcx/platform-type-class.md) オブジェクト。

### <a name="remarks"></a>解説

静的な [型:: gettypecode 種類](../cppcx/platform-type-class.md#gettypecode) を使用して、現在の型を表す [Platform::](../cppcx/platform-typecode-enumeration.md) の種類の列挙値を取得できます。 これは主に、組み込み型に使用できます。 [Platform:: String](../cppcx/platform-string-class.md)以外の ref クラスの型コードは Object (1) です。

Windows [:: UI:: Xaml:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename) クラスは、言語に依存せずに windows のコンポーネントとアプリの間で型情報を渡す方法として、windows api で使用されます。 T[Platform:: Type クラス](../cppcx/platform-type-class.md) には、との間で変換を行うための演算子があり `Type` `TypeName` ます。

クラス名のオブジェクトを返すには、 [typeid](../extensions/typeid-cpp-component-extensions.md) 演算子を使用し `Platform::Type` ます。たとえば、XAML ページ間を移動する場合は、次のようにします。

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="objectobject-constructor"></a><a name="ctor"></a> Object:: Object コンストラクター

Object クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
public:Object();
```

## <a name="objectreferenceequals-method"></a><a name="referenceequals"></a> Object:: ReferenceEquals メソッド

指定された Object インスタンスが同一のインスタンスかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2);
```

### <a name="parameters"></a>パラメーター

*obj1*<br/>
比較する最初のオブジェクト。

*obj2*<br/>
比較する 2 番目のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 2つのオブジェクトが同じ場合は。それ以外の場合は **`false`** 。

## <a name="objecttostring-method-ccx"></a><a name="tostring"></a> Object:: ToString メソッド (C++/CX)

現在のオブジェクトを表す文字列を返します。

### <a name="syntax"></a>構文

```cpp
public:
virtual String^ ToString();
```

### <a name="return-value"></a>戻り値

現在のオブジェクトを表す文字列。 ref クラスまたは構造体内でカスタム文字列メッセージを表示するために、このメソッドをオーバーライドすることもできます:

```cpp
public ref class Tree sealed
{
public:
    Tree(){}
    virtual Platform::String^ ToString() override
    {
      return "I’m a Tree";
    };
};
```

## <a name="see-also"></a>関連項目

[Platform 名前空間](platform-namespace-c-cx.md)<br/>
[Platform:: Type クラス](platform-type-class.md)<br/>
[型システム](type-system-c-cx.md)
