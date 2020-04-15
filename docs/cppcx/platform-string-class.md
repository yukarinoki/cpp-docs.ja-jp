---
title: Platform::String クラス
ms.date: 10/16/2019
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
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
ms.openlocfilehash: 3f29c60d0d6a4618d97d8f750a048fcc18f976b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322112"
---
# <a name="platformstring-class"></a>Platform::String クラス

テキストを表現するために使用される Unicode 文字のシーケンシャル コレクションを表します。 詳細と例については、「[文字列](../cppcx/strings-c-cx.md)」を参照してください。

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

## <a name="members"></a>メンバー

String クラスは、Object、および IDisposable、IEquatable、および IPrintable interfaces の各インターフェイスから継承します。

String クラスには、次の種類のメンバーの種類もあります。

### <a name="constructors"></a>コンストラクター

|メンバー|説明|
|------------|-----------------|
|[文字列::文字列](#ctor)|String クラスの新しいインスタンスを初期化します。|

### <a name="methods"></a>メソッド

String クラスは、 [Platform::Object Class](../cppcx/platform-object-class.md)の Equals()、Finalize()、GetHashCode()、GetType()、MemberwiseClose()、および ToString() の各メソッドを継承します。 String には、次のメソッドもあります。

|Method|説明|
|------------|-----------------|
|[文字列::開始](#begin)|現在の文字列の先頭へのポインターを返します。|
|[文字列::比較オルディナル](#compareordinal)|オブジェクトによって表される 2 つの文字列値に含まれる、対応する文字列の数値を評価することにより、2 つの `String` オブジェクトを比較します。|
|[文字列::コンキャット](#concat)|指定された 2 つの String オブジェクトの値を連結します。|
|[文字列::Dタータ](#data)|現在の文字列の先頭へのポインターを返します。|
|[文字列::Dポーズ](#dispose)|リソースを解放またはリソースします。|
|[文字列::終了](#end)|現在の文字列の末尾を越えたポインターを返します。|
|[文字列::等しい](#equals)|指定されたオブジェクトが現在のオブジェクトと等しいかどうかを示します。|
|[文字列::ゲットハッシュコード](#gethashcode)|このインスタンスのハッシュ コードを返します。|
|[文字列::IsEmpty](#isempty)|現在の String オブジェクトが空かどうかを示します。|
|[文字列::IsFastPass](#isfastpass)|現在の String オブジェクトが*高速パス*操作に参加しているかどうかを示します。 高速渡し操作では、参照カウントは中断されます。|
|[文字列::長さ](#length)|現在の String オブジェクトの長さを取得します。|
|[文字列::文字列](#tostring)|値が現在の文字列と同じである String オブジェクトを返します。|

### <a name="operators"></a>オペレーター

String クラスには、次の演算子があります。

|メンバー|説明|
|------------|-----------------|
|[文字列::演算子== 演算子](#operator-equality)|指定した 2 つの String オブジェクトの値が同じかどうかを示します。|
|[operator+ Operator](#operator-plus)|2 つの String オブジェクトを連結して新しい String オブジェクトを作成します。|
|[文字列::演算子>演算子](#operator-greater-than)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より大きいかどうかを示します。|
|[文字列::演算子>= 演算子](#operator-greater-than-or-equals)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値以上かどうかを示します。|
|[文字列::演算子!= 演算子](#operator-inequality)|指定した 2 つの String オブジェクトの値が異なるかどうかを示します。|
|[文字列::演算子<演算子](#operator-less-than)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より小さいかどうかを示します。|

### <a name="requirements"></a>必要条件

**サポートされる最小クライアント:** ウィンドウズ 8

**サポートされる最小サーバー:** ウィンドウズ サーバー 2012

**名前空間:** Platform

**ヘッダー** vccorlib.h (既定でインクルードされる)

## <a name="stringbegin-method"></a><a name="begin"></a>文字列::メソッドを開始します。

現在の文字列の先頭へのポインターを返します。

### <a name="syntax"></a>構文

```cpp
char16* Begin();
```

### <a name="return-value"></a>戻り値

現在の文字列の先頭へのポインター。

## <a name="stringcompareordinal-method"></a><a name="compareordinal"></a>文字列::比較オルディナルメソッド

オブジェクトによって表される 2`String`つの文字列値の対応する文字の数値を評価することによって、2 つのオブジェクトを比較する静的メソッド。

### <a name="syntax"></a>構文

```cpp
static int CompareOrdinal( String^ str1, String^ str2 );
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

## <a name="stringconcat-method"></a><a name="concat"></a>文字列::連結メソッド

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

`str1` が `null` で、`str2` がそうでない場合は、`str1` が返されます。 `str2` が `null` で、`str1` がそうでない場合は、`str2` が返されます。 `str1` と `str2` の両方が `null` の場合は、空の文字列 (L"") が返されます。

## <a name="stringdata-method"></a><a name="data"></a>文字列::Data メソッド

`char16` (`wchar_t`) 要素の C スタイル配列としてオブジェクトのデータ バッファーの先頭へのポインターを返します。

### <a name="syntax"></a>構文

```cpp
const char16* Data();
```

### <a name="return-value"></a>戻り値

Unicode 文字の`const char16`配列の先頭へのポインター (`char16`の typedef`wchar_t`です。

### <a name="remarks"></a>解説

`Platform::String^` から `wchar_t*` に変換するには、このメソッドを使用します。 `String` オブジェクトがスコープ外に出ると、データ ポインターが有効であるという保証がなくなります。 元`String`のオブジェクトの有効期間を超えてデータを格納するには[、wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)を使用して、自分で割り当てたメモリに配列をコピーします。

## <a name="stringdispose-method"></a><a name="dispose"></a>文字列::Disposeメソッド

リソースを解放またはリソースします。

### <a name="syntax"></a>構文

```cpp
virtual override void Dispose();
```

## <a name="stringend-method"></a><a name="end"></a>文字列::終了メソッド

現在の文字列の末尾を越えたポインターを返します。

### <a name="syntax"></a>構文

```cpp
char16* End();
```

### <a name="return-value"></a>戻り値

現在の文字列の末尾を越えたポインター。

### <a name="remarks"></a>解説

End() は、開始関数と長さを返します。

## <a name="stringequals-method"></a><a name="equals"></a>文字列::等しいメソッド

指定された String に現在のオブジェクトと同じ値が存在するかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
比較するオブジェクト。

### <a name="return-value"></a>戻り値

**現在**の`str`オブジェクトと等しい場合は true。それ以外の場合**は false。**

### <a name="remarks"></a>解説

このメソッドは、静的[な文字列::比較Ordinalと同等です](#compareordinal)。 最初のオーバーロードでは、`str` パラメーターが String^ オブジェクトにキャストできることが想定されています。

## <a name="stringgethashcode-method"></a><a name="gethashcode"></a>文字列::メソッドを取得します。

このインスタンスのハッシュ コードを返します。

### <a name="syntax"></a>構文

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>戻り値

対象のインスタンスのハッシュ コード。

## <a name="stringisempty-method"></a><a name="isempty"></a>文字列::IsEmpty メソッド

現在の String オブジェクトが空かどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>戻り値

現在`String`のオブジェクトが**null**または空の文字列 (L"") の場合は**true。** それ以外の場合**は false。**

## <a name="stringisfastpass-method"></a><a name="isfastpass"></a>文字列::IsFastPassメソッド

現在の String オブジェクトが*高速パス*操作に参加しているかどうかを示します。 高速渡し操作では、参照カウントは中断されます。

### <a name="syntax"></a>構文

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>戻り値

現在`String`のオブジェクトが高速過去の場合は**true、** それ以外の場合**は false。**

### <a name="remarks"></a>解説

参照カウントを使用するオブジェクトがパラメーターであり、呼び出された関数がそのオブジェクトだけを読み取る場合の関数への呼び出しでは、コンパイラは安全に参照カウントを中断し、呼び出しのパフォーマンスを改善することができます。 このプロパティをコード内で活用することはできません。 システムがすべての詳細を処理します。

## <a name="stringlength-method"></a><a name="length"></a>文字列::長さのメソッド

現在`String`のオブジェクトの文字数を取得します。

### <a name="syntax"></a>構文

```cpp
unsigned int Length();
```

### <a name="return-value"></a>戻り値

現在`String`のオブジェクトの文字数。

### <a name="remarks"></a>解説

文字がない場合の String の長さはゼロです。 次の文字列は長さが 5 になります。

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

[String::Data](#data)によって返される文字配列には、末尾の NULL または '\0' という文字が 1 つ追加されています。 この文字は、長さが 2 バイトです。

## <a name="stringoperator-operator"></a><a name="operator-plus"></a>文字列::演算子+ 演算子

2 つの[String](../cppcx/platform-string-class.md)オブジェクトを連結して、新しい[String](../cppcx/platform-string-class.md)オブジェクトを作成します。

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

*str1*が*str2*と等しい場合は**true、** それ以外の場合**は false。**

### <a name="remarks"></a>解説

この演算子は、2 種類のオペランドのデータを含む `String^` オブジェクトを作成します。 パフォーマンスを極端に高める必要がない場合には、便宜上、この演算子を使用します。 関数で "`+`" を数回呼び出しても目立つことはないと思われますが、サイズの大きなオブジェクトまたはテキスト データを頻繁に操作するときには、標準的な C++ の機構と型を使用してください。

## <a name="stringoperator-operator"></a><a name="operator-equality"></a>文字列::演算子== 演算子

指定された 2 つの String オブジェクトのテキスト値が同じかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
比較する最初の `String` オブジェクトです。

*str2*<br/>
比較する 2 番目の `String` オブジェクトです。

### <a name="return-value"></a>戻り値

の内容`str1`が次の値に等`str2`しい場合は**true。** それ以外の場合**は false。**

### <a name="remarks"></a>解説

この演算子は[文字列::比較Ordinalと同等です](#compareordinal)。

## <a name="stringoperatorgt"></a><a name="operator-greater-than"></a>文字列::演算子&gt;

1 つの`String`オブジェクトの値が 2 番目`String`のオブジェクトの値より大きいかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の `String` オブジェクト。

*str2*<br/>
2 番目の `String` オブジェクト。

### <a name="return-value"></a>戻り値

**の**値`str1`がの値より大きい場合は`str2`true。それ以外の場合**は false。**

### <a name="remarks"></a>解説

この演算子は、明示的に[String::CompareOrdinal](#compareordinal)を呼び出し、結果が 0 より大きい場合と同じです。

## <a name="stringoperatorgt"></a><a name="operator-greater-than-or-equals"></a>文字列::演算子&gt;=

1 つの`String`オブジェクトの値が 2 番目`String`のオブジェクトの値以上かどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の `String` オブジェクト。

*str2*<br/>
2 番目の `String` オブジェクト。

### <a name="return-value"></a>戻り値

**の**値`str1`が、 の値以上の場合は`str2`true。それ以外の場合**は false。**

## <a name="stringoperator"></a><a name="operator-inequality"></a>文字列::演算子!=

指定した`String`2 つのオブジェクトの値が異なるかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
比較する最初の `String` オブジェクトです。

*str2*<br/>
比較する 2 番目の `String` オブジェクトです。

### <a name="return-value"></a>戻り値

**が**等`str1`しくない場合は`str2`true。それ以外の場合**は false。**

## <a name="stringoperatorlt"></a><a name="operator-less-than"></a>文字列::演算子&lt;

1 つの`String`オブジェクトの値が 2 番目`String`のオブジェクトの値より小さいかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の `String` オブジェクト。

*str2*<br/>
2 番目の `String` オブジェクト。

### <a name="return-value"></a>戻り値

*str1*の値が*str2*の値より小さい場合は**true。** それ以外の場合**は false。**

## <a name="stringstring-constructor"></a><a name="ctor"></a>文字列::文字列コンストラクタ

入力文字列データのコピーを使用`String`して、クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>パラメーター

*S*<br/>
文字列を初期化する一連のワイド文字。 char16

*n*<br/>
文字列の長さを指定する数値。

### <a name="remarks"></a>解説

パフォーマンスが重要で、ソース文字列の有効期間を制御する場合は、文字列の代わりに[プラットフォーム::文字列参照](../cppcx/platform-stringreference-class.md)を使用できます。

### <a name="example"></a>例

```cpp
String^ s = L"Hello!";
```

## <a name="stringtostring"></a><a name="tostring"></a>文字列::文字列

現在の`String`文字列と同じ値を持つオブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>戻り値

現在`String`の文字列と同じ値を持つオブジェクト。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
