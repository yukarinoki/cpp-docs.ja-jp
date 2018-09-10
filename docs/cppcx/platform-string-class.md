---
title: Platform::string Class |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::String::String
- VCCORLIB/Platform::String::Begin
- VCCORLIB/Platform::String::CompareOrdinal
- VCCORLIB/Platform::String::Concat
- VCCORLIB/Platform::String::Data
- VCCORLIB/Platform::String::Dispose
- VCCORLIB/Platform::String::End
- VCCORLIB/Platform::String::Equals
- VCCORLIB/Platform::String::GetHashCode
- VCCORLIB/Platform::String::IsEmpty
- VCCORLIB/Platform::String::IsFastPass
- VCCORLIB/Platform::String::Length
- VCCORLIB/Platform::String::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3777116bf2a641a4fdc220306680c0150d5ba2d0
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106415"
---
# <a name="platformstring-class"></a>Platform::String クラス

テキストを表現するために使用される Unicode 文字のシーケンシャル コレクションを表します。 詳細と例については、次を参照してください。[文字列](../cppcx/strings-c-cx.md)します。

## <a name="syntax"></a>構文

```cpp
public ref class String sealed : Object,
    IDisposable,
    IEquatable,
    IPrintable
```

## <a name="iterators"></a>Iterators

String クラスのメンバーではない 2 つの反復子関数を `std::for_each` テンプレート関数で使用して、String オブジェクトの文字列を列挙できます。

|メンバー|説明|
|------------|-----------------|
|`const char16* begin(String^ s)`|指定された String オブジェクトの始まりへのポインターを返します。|
|`const char16* end(String^ s)`|指定された String オブジェクトの末尾を越えたポインターを返します。|

### <a name="members"></a>メンバー

String クラスは、Object、および IDisposable、IEquatable、および IPrintable interfaces の各インターフェイスから継承します。

String クラスには、次の種類のメンバーの種類もあります。

**コンストラクター**

|メンバー|説明|
|------------|-----------------|
|[String::String](#ctor)|String クラスの新しいインスタンスを初期化します。|

**メソッド**

String クラスは、 [Platform::Object Class](../cppcx/platform-object-class.md)の Equals()、Finalize()、GetHashCode()、GetType()、MemberwiseClose()、および ToString() の各メソッドを継承します。 String には、次のメソッドもあります。

|メソッド|説明|
|------------|-----------------|
|[String::begin](#begin)|現在の文字列の先頭へのポインターを返します。|
|[String::CompareOrdinal](#compareordinal)|オブジェクトによって表される 2 つの文字列値に含まれる、対応する文字列の数値を評価することにより、2 つの `String` オブジェクトを比較します。|
|[String::Concat](#concat)|指定された 2 つの String オブジェクトの値を連結します。|
|[String::data](#data)|現在の文字列の先頭へのポインターを返します。|
|[String::dispose](#dispose)|リソースを解放またはリソースします。|
|[String::End](#end)|現在の文字列の末尾を越えたポインターを返します。|
|[String::Equals](#equals)|指定されたオブジェクトが現在のオブジェクトと等しいかどうかを示します。|
|[String::GetHashCode](#gethashcode)|このインスタンスのハッシュ コードを返します。|
|[String::IsEmpty](#isempty)|現在の String オブジェクトが空かどうかを示します。|
|[String::IsFastPass](#isfastpass)|現在の String オブジェクトが参加しているかどうかを示す、*高速渡し*操作。 高速渡し操作では、参照カウントは中断されます。|
|[String::Length](#length)|現在の String オブジェクトの長さを取得します。|
|[String::ToString](#tostring)|値が現在の文字列と同じである String オブジェクトを返します。|

**演算子**

文字列クラスには、次の演算子があります。

|メンバー|説明|
|------------|-----------------|
|[String::operator = 演算子](#operator-equality)|指定された 2 つの String オブジェクトの値が同じかどうかを示します。|
|[operator+ Operator](#operator-plus)|2 つの String オブジェクトを連結して新しい String オブジェクトを作成します。|
|[String::operator > 演算子](#operator-greater-than)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より大きいかどうかを示します。|
|[String::operator > = 演算子](#operator-greater-than-or-equals)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値以上かどうかを示します。|
|[String::operator! = 演算子](#operator-inequality)|指定された 2 つの String オブジェクトの値が異なるかどうかを示します。|
|[String::operator < 演算子](#operator-less-than)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より小さいかどうかを示します。|

### <a name="requirements"></a>要件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**ヘッダー** vccorlib.h (既定でインクルードされる)

## <a name="begin"></a>  String::begin メソッド

現在の文字列の先頭へのポインターを返します。

### <a name="syntax"></a>構文

```cpp
char16* Begin();
```

### <a name="return-value"></a>戻り値

現在の文字列の先頭へのポインター。

## <a name="compareordinal"></a>  String::compareordinal メソッド

オブジェクトによって表される 2 つの文字列値に含まれる、対応する文字列の数値を評価することにより、2 つの `String` オブジェクトを比較します。

### <a name="syntax"></a>構文

```cpp
int CompareOrdinal( String^ str1, String^ str2 );
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
1 つ目の String オブジェクト。

*str2*<br/>
2 つ目の String オブジェクト。

### <a name="return-value"></a>戻り値

2 つの比較対照値の構文上の関係を示す整数。 次の表は、可能性のある戻り値の一覧です。

|[値]|条件|
|-----------|---------------|
|-1|`str1` は `str2` より小さい値です。|
|0|`str1` は `str2` と等価。|
|1|`str1` が `str2` より大きくなっています。|

## <a name="concat"></a>  String::concat メソッド

指定された 2 つの String オブジェクトの値を連結します。

### <a name="syntax"></a>構文

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
1 つ目の String オブジェクト、または `null`。

*str2*<br/>
2 つ目の String オブジェクト、または `null`。

### <a name="return-value"></a>戻り値

`str1` と `str2` を連結した値を持つ新しい String^ オブジェクト。

場合`str1`は`null`と`str2`ない`str1`が返されます。 場合`str2`は`null`と`str1`ない`str2`が返されます。 `str1` と `str2` の両方が `null` の場合は、空の文字列 (L"") が返されます。

## <a name="data"></a>  String::data メソッド

`char16` (`wchar_t`) 要素の C スタイル配列としてオブジェクトのデータ バッファーの先頭へのポインターを返します。

### <a name="syntax"></a>構文

```
const char16* Data();
```

### <a name="return-value"></a>戻り値

先頭へのポインターを`const char16`Unicode 文字の配列 (`char16`の typedef は、 `wchar_t`)。

### <a name="remarks"></a>Remarks

`Platform::String^` から `wchar_t*` に変換するには、このメソッドを使用します。 `String` オブジェクトがスコープ外に出ると、データ ポインターが有効であるという保証がなくなります。 元の有効期間を超えてデータを格納する`String`オブジェクトを使用して[wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)を自分で割り当てたメモリに、配列にコピーします。

## <a name="dispose"></a>  String::dispose メソッド

リソースを解放またはリソースします。

### <a name="syntax"></a>構文

```cpp
virtual override void Dispose();
```

## <a name="end"></a>  String::end メソッド

現在の文字列の末尾を越えたポインターを返します。

### <a name="syntax"></a>構文

```cpp
char16* End();
```

### <a name="return-value"></a>戻り値

現在の文字列の末尾を越えたポインター。

### <a name="remarks"></a>Remarks

End() は Begin() + Length を返します。

## <a name="equals"></a>  String::equals メソッド

指定された String に現在のオブジェクトと同じ値が存在するかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
比較対象のオブジェクト。

### <a name="return-value"></a>戻り値

`true` が現在のオブジェクトに等しい場合は `str`。それ以外の場合は、`false`。

### <a name="remarks"></a>Remarks

このメソッドは、 [string::compareordinal](#compareordinal)します。 最初のオーバーロードでは、`str` パラメーターが String^ オブジェクトにキャストできることが想定されています。

## <a name="gethashcode"></a>  String::gethashcode メソッド

このインスタンスのハッシュ コードを返します。

### <a name="syntax"></a>構文

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>戻り値

対象のインスタンスのハッシュ コード。

## <a name="isempty"></a>  String::isempty メソッド

現在の String オブジェクトが空かどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>戻り値

現在の String オブジェクトが `true` または空の文字列 ("") の場合は `null`。それ以外の場合は `false`。

## <a name="isfastpass"></a>  String::isfastpass メソッド

現在の String オブジェクトが参加しているかどうかを示す、*高速渡し*操作。 高速渡し操作では、参照カウントは中断されます。

### <a name="syntax"></a>構文

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>戻り値

現在の文字列オブジェクトが高速渡しの場合は `true`。それ以外の場合は `false`。

### <a name="remarks"></a>Remarks

参照カウントを使用するオブジェクトがパラメーターであり、呼び出された関数がそのオブジェクトだけを読み取る場合の関数への呼び出しでは、コンパイラは安全に参照カウントを中断し、呼び出しのパフォーマンスを改善することができます。 このプロパティをコード内で活用することはできません。 システムがすべての詳細を処理します。

## <a name="length"></a>  String::length メソッド

現在の String オブジェクト内の文字数を取得します。

### <a name="syntax"></a>構文

```cpp
unsigned int Length();
```

### <a name="return-value"></a>戻り値

現在の String オブジェクト内の文字数。

### <a name="remarks"></a>Remarks

文字がない場合の String の長さはゼロです。 次の文字列は長さが 5 になります。

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

によって返される文字の配列、 [string::data](#data)終端の NULL または '\0' は、1 つの追加の文字があります。 この文字は、長さが 2 バイトです。

## <a name="operator-plus"></a>  String::operator + 演算子

2 つ連結[文字列](../cppcx/platform-string-class.md)オブジェクトを新しい[文字列](../cppcx/platform-string-class.md)オブジェクト。

### <a name="syntax"></a>構文

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の `String` オブジェクト。

*str2*<br/>
内容が `String` に追加される 2 番目の `str1` オブジェクト。

### <a name="return-value"></a>戻り値

`true` が `str1` に等しい場合は `str2`。それ以外の場合は `false`。

### <a name="remarks"></a>Remarks

この演算子は、2 種類のオペランドのデータを含む `String^` オブジェクトを作成します。 パフォーマンスを極端に高める必要がない場合には、便宜上、この演算子を使用します。 関数で "`+`" を数回呼び出しても目立つことはないと思われますが、サイズの大きなオブジェクトまたはテキスト データを頻繁に操作するときには、標準的な C++ の機構と型を使用してください。

##  <a name="operator-equality"></a> String::operator = 演算子

指定された 2 つの String オブジェクトのテキスト値が同じかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
比較する最初の String オブジェクト。

*str2*<br/>
比較する 2 番目の String オブジェクト。

### <a name="return-value"></a>戻り値

`true` の中身が `str1` と等しい場合は `str2`。それ以外の場合は `false`。

### <a name="remarks"></a>Remarks

この演算子に等価[string::compareordinal](#compareordinal)します。

##  <a name="operator-greater-than"></a>  String::operator&gt;

1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より大きいかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
1 つ目の String オブジェクト。

*str2*<br/>
2 つ目の String オブジェクト。

### <a name="return-value"></a>戻り値

`str1` の値が `str2` の値より大きい場合は `true`。それ以外の場合は `false`。

### <a name="remarks"></a>Remarks

この演算子は明示的に呼び出す等価[string::compareordinal](#compareordinal)と結果を 0 より大きい値を取得します。

## <a name="operator-greater-than-or-equals"></a> String::operator&gt;=

1 つの String オブジェクトの値が、2 番目の String オブジェクトの値以上かどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
1 つ目の String オブジェクト。

*str2*<br/>
2 つ目の String オブジェクト。

### <a name="return-value"></a>戻り値

`str1` の値が `str2` の値以上の場合は `true`。それ以外の場合は `false`。

## <a name="operator-inequality"></a> String::operator! =

指定された 2 つの String オブジェクトの値が異なるかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
比較する最初の String オブジェクト。

*str2*<br/>
比較する 2 番目の String オブジェクト。

### <a name="return-value"></a>戻り値

`true` が `str1` と等しくない場合は `str2`。それ以外の場合は `false`。

## <a name="operator-less-than"></a> String::operator&lt;

1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より小さいかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
1 つ目の String オブジェクト。

*str2*<br/>
2 つ目の String オブジェクト。

### <a name="return-value"></a>戻り値

`true` の値が `str1` の値より小さい場合は `str2`。それ以外の場合は `false`。

## <a name="ctor"></a> String::string コンス トラクター

入力文字列データのコピーで String クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>パラメーター

*s*<br/>
文字列を初期化する一連のワイド文字。 char16

*n*<br/>
文字列の長さを指定する数値。

### <a name="remarks"></a>Remarks

使用することがパフォーマンスが重要です。 ソース文字列の有効期間を制御する場合は、 [platform::stringreference](../cppcx/platform-stringreference-class.md)文字列の代わりにします。
### <a name="example"></a>例

```cpp
String^ s = L"Hello!";
```

## <a name="tostring"></a> String::tostring

値が現在の文字列と同じである String オブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>戻り値

値が現在の文字列と同じである文字列オブジェクト。

## <a name="see-also"></a>関連項目

[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)
