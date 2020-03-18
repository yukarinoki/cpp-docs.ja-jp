---
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
ms.openlocfilehash: 77313f8c4dcc87fa9de852afe2d60e614f8fc3a3
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423670"
---
# <a name="platformobject-class"></a>Platform::Object クラス

Windows ランタイムアプリの ref クラスと ref 構造体に共通の動作を提供します。 ref クラスと ref 構造体のインスタンスは、いずれも Platform::Object^ に暗黙的に変換可能で、仮想の ToString メソッドをオーバーライドできます。

## <a name="syntax"></a>構文

```cpp
public ref class Object : Object
```

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[Object:: Object](#ctor)|Object クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[Object:: Equals](#equals)|指定されたオブジェクトが現在のオブジェクトと等しいかどうかを判断します。|
|[Object:: GetHashCode](#gethashcode)|このインスタンスのハッシュ コードを返します。|
|[Object:: ReferenceEquals](#referenceequals)|指定された Object インスタンスが同一のインスタンスかどうかを判断します。|
|[ToString](#tostring)|現在のオブジェクトを表す文字列を返します。 オーバーライドできます。|
|[GetType](#gettype)|現在のインスタンスを記述する [Platform::Type](../cppcx/platform-type-class.md) を取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`Object`

`Object`

### <a name="requirements"></a>必要条件

**ヘッダー:** vccorlib.h

**名前空間:** Platform

## <a name="equals"></a>Object:: Equals メソッド

指定されたオブジェクトが現在のオブジェクトと等しいかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
bool Equals(
    Object^ obj
)
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
比較するオブジェクト。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は**true** 、それ以外の場合は**false**。

## <a name="gethashcode"></a>Object:: GetHashCode メソッド

COM オブジェクトの場合は、このインスタンスの `IUnknown`* ID 値を返します。COM オブジェクトでない場合は、計算済みハッシュ値を返します。

### <a name="syntax"></a>構文

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>戻り値

このオブジェクトを一意に識別する数値。

### <a name="remarks"></a>解説

GetHashCode を使用してマップ内のオブジェクトのキーを作成できます。 [Object:: Equals](#equals)を使用すると、ハッシュコードを比較できます。 コード パスが非常に重要であるときに、`GetHashCode` と `Equals` の実行速度が不十分な場合には、基になる COM レイヤーまで移動して `IUnknown` ネイティブ ポインターの比較を実行できます。

## <a name="gettype"></a>Object:: GetType メソッド

オブジェクトのランタイム型を記述する[Platform:: Type](../cppcx/platform-type-class.md)オブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

オブジェクトのランタイム型を記述する[Platform:: Type](../cppcx/platform-type-class.md)オブジェクト。

### <a name="remarks"></a>解説

静的な[型:: gettypecode 種類](../cppcx/platform-type-class.md#gettypecode)を使用して、現在の型を表す[Platform::](../cppcx/platform-typecode-enumeration.md)の種類の列挙値を取得できます。 これは主に、組み込み型に使用できます。 [Platform:: String](../cppcx/platform-string-class.md)以外の ref クラスの型コードは Object (1) です。

Windows [:: UI:: Xaml:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename)クラスは、言語に依存せずに windows のコンポーネントとアプリの間で型情報を渡す方法として、windows api で使用されます。 T[Platform:: Type クラス](../cppcx/platform-type-class.md)には、`Type` と `TypeName`の間で変換を行うための演算子があります。

クラス名の `Platform::Type` オブジェクトを返すには、 [typeid](../extensions/typeid-cpp-component-extensions.md)演算子を使用します。たとえば、XAML ページ間を移動する場合は、次のようにします。

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="ctor"></a>Object:: Object コンストラクター

Object クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
public:Object();
```

## <a name="referenceequals"></a>Object:: ReferenceEquals メソッド

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

2つのオブジェクトが同じ場合は**true** 。それ以外の場合は**false**。

## <a name="tostring"></a>Object:: ToString メソッド (C++/cx)

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

## <a name="see-also"></a>参照

[Platform 名前空間](platform-namespace-c-cx.md)<br/>
[Platform::Type クラス](platform-type-class.md)<br/>
[型システム](type-system-c-cx.md)
