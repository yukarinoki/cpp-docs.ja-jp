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
ms.openlocfilehash: 8300ec484bdb58919ce8e450b706dd07c275ceee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363687"
---
# <a name="platformobject-class"></a>Platform::Object クラス

Windows ランタイム アプリで ref クラスと ref 構造体に対する一般的な動作を提供します。 ref クラスと ref 構造体のインスタンスは、いずれも Platform::Object^ に暗黙的に変換可能で、仮想の ToString メソッドをオーバーライドできます。

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

### <a name="requirements"></a>必要条件

**ヘッダー:** vccorlib.h

**名前空間:** Platform

## <a name="objectequals-method"></a><a name="equals"></a>オブジェクト::等しいメソッド

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

オブジェクトが等しい場合は**true、** それ以外の場合は**false。**

## <a name="objectgethashcode-method"></a><a name="gethashcode"></a>オブジェクト::メソッドを取得します。

COM オブジェクトの場合は、このインスタンスの `IUnknown`* ID 値を返します。COM オブジェクトでない場合は、計算済みハッシュ値を返します。

### <a name="syntax"></a>構文

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>戻り値

このオブジェクトを一意に識別する数値。

### <a name="remarks"></a>解説

GetHashCode を使用してマップ内のオブジェクトのキーを作成できます。 ハッシュ コードは[、Object::Equals](#equals)を使用して比較できます。 コード パスが非常に重要であるときに、`GetHashCode` と `Equals` の実行速度が不十分な場合には、基になる COM レイヤーまで移動して `IUnknown` ネイティブ ポインターの比較を実行できます。

## <a name="objectgettype-method"></a><a name="gettype"></a>オブジェクト::GetType メソッド

オブジェクトのランタイム型を記述する[Platform::Type](../cppcx/platform-type-class.md)オブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

オブジェクトのランタイム型を記述する[プラットフォーム::型](../cppcx/platform-type-class.md)オブジェクト。

### <a name="remarks"></a>解説

静的[な型::GetTypeCode](../cppcx/platform-type-class.md#gettypecode)を使用して、現在の型を表す[プラットフォーム::TypeCode 列挙](../cppcx/platform-typecode-enumeration.md)値を取得できます。 これは主に、組み込み型に使用できます。 [プラットフォーム::文字列](../cppcx/platform-string-class.md)はオブジェクト (1) 以外の任意の ref クラスの型コード。

[Windows::UI::相互運用::TypeName](/uwp/api/windows.ui.xaml.interop.typename)クラスは、Windows コンポーネントとアプリ間で型情報を渡す言語に依存しない方法として、Windows API で使用されます。 T[プラットフォーム::型クラス](../cppcx/platform-type-class.md)には、 と`Type``TypeName`の間の変換演算子があります。

たとえば、XAML ページ間を移動`Platform::Type`する場合など、クラス名のオブジェクトを返すには[、typeid](../extensions/typeid-cpp-component-extensions.md)演算子を使用します。

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="objectobject-constructor"></a><a name="ctor"></a>オブジェクト::オブジェクトコンストラクタ

Object クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
public:Object();
```

## <a name="objectreferenceequals-method"></a><a name="referenceequals"></a>オブジェクト::参照等しいメソッド

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

2 つのオブジェクトが同じ場合は**true。** それ以外の場合**は false。**

## <a name="objecttostring-method-ccx"></a><a name="tostring"></a>オブジェクト::ToString メソッド (C++/CX)

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

[プラットフォーム名前空間](platform-namespace-c-cx.md)<br/>
[Platform::Type クラス](platform-type-class.md)<br/>
[型システム](type-system-c-cx.md)
