---
title: SafeInt クラス |Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt
- SafeInt::SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class
- SafeInt class, constructor
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b7d9c6b68f67185bb9cc529949fcc7c43e91d21e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081863"
---
# <a name="safeint-class"></a>SafeInt クラス

整数のオーバーフローを防ぐため、整数のプリミティブを拡張し、さまざまな種類の整数を比較することができます。

> [!NOTE] 
> このライブラリの最新バージョンは[ https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)します。

## <a name="syntax"></a>構文

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>パラメーター

テンプレート | 説明
-------- | -------------------------------------------------------------------
T        | 整数またはブール型パラメーターの型を`SafeInt`が置き換えられます。
E        | エラー処理ポリシーを定義する列挙型。
U        | 整数またはブール型パラメーターの第 2 オペランドの型。

パラメーター | 説明
--------- | ---------------------------------------------------------------------------------------------------------------------
*rhs*     | [in]スタンドアロンの関数をいくつかの演算子の右側にある値を表す入力パラメーター。
*i*       | [in]スタンドアロンの関数をいくつかの演算子の右側にある値を表す入力パラメーター。
*Bits*    | [in]スタンドアロンの関数をいくつかの演算子の右側にある値を表す入力パラメーター。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                         | 説明
---------------------------- | --------------------
[SafeInt::SafeInt](#safeint) | 既定のコンストラクター

### <a name="assignment-operators"></a>代入演算子

名前 | 構文
---- | ---------------------------------------------------------------------------------------
=    | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`
=    | `SafeInt<T,E>& operator= (const T& rhs) throw()`
=    | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`
=    | `SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`

### <a name="casting-operators"></a>キャスト演算子

名前             | 構文
---------------- | -----------------------------------
bool             | `operator bool() throw()`
char             | `operator char() const`
signed char      | `operator signed char() const`
unsigned char    | `operator unsigned char() const`
__int16          | `operator __int16() const`
unsigned __int16 | `operator unsigned __int16() const`
__int32          | `operator __int32() const`
unsigned __int32 | `operator unsigned __int32() const`
long             | `operator long() const`
unsigned long    | `operator unsigned long() const`
__int64          | `operator __int64() const`
unsigned __int64 | `operator unsigned __int64() const`
wchar_t          | `operator wchar_t() const`

### <a name="comparison-operators"></a>比較演算子

名前 | 構文
---- | --------------------------------------------------------------------------
<    | `template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`
<    | `bool operator< (SafeInt<T,E> rhs) const throw()`
>=   | `template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`
>=   | `Bool operator>= (SafeInt<T,E> rhs) const throw()`
>    | `template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`
>    | `Bool operator> (SafeInt<T,E> rhs) const throw()`
<=   | `template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`
<=   | `bool operator<= (SafeInt<T,E> rhs) const throw()`
==   | `template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`
==   | `bool operator== (bool rhs) const throw()`
==   | `bool operator== (SafeInt<T,E> rhs) const throw()`
!=   | `template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`
!=   | `bool operator!= (bool b) const throw()`
!=   | `bool operator!= (SafeInt<T,E> rhs) const throw()`

### <a name="arithmetic-operators"></a>算術演算子

名前 | 構文
---- | ---------------------------------------------------------------------------------
+    | `const SafeInt<T,E>& operator+ () const throw()`
-    | `SafeInt<T,E> operator- () const`
++   | `SafeInt<T,E>& operator++ ()`
--   | `SafeInt<T,E>& operator-- ()`
%    | `template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`
%    | `SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`
%=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`
%=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`
*    | `template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`
*    | `SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`
*=   | `SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`
*=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`
*=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`
/    | `template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`
/    | `SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`
/=   | `SafeInt<T,E>& operator/= (SafeInt<T,E> i)`
/=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`
/=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`
+    | `SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`
+    | `template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`
+=   | `SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`
+=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`
+=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`
-    | `template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`
-    | `SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`
-=   | `SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`
-=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`
-=   | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`

### <a name="logical-operators"></a>論理演算子

名前    | 構文
------- | -----------------------------------------------------------------------------------------------
!       | `bool operator !() const throw()`
~       | `SafeInt<T,E> operator~ () const throw()`
<<      | `template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`
<<      | `template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`
<<=     | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`
<<=     | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`
>>      | `template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`
>>      | `template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`
>>=     | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`
>>=     | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`
&       | `SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`
&       | `template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`
&=      | `SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`
&=      | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`
&=      | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`
^       | `SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`
^       | `template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`
^=      | `SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`
^=      | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`
^=      | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`
&#124;  | `SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`
&#124;  | `template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`
&#124;= | `SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`
&#124;= | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`
&#124;= | `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`

## <a name="remarks"></a>Remarks

`SafeInt`クラスは、算術演算で整数オーバーフローから保護します。 たとえば、2 つの 8 ビット整数を追加する: 200 の値を持つ 1 つと、2 つ目は、100 の値を持ちます。 適切な数学的演算は、200 + 100 = 300 になります。 ただし、8 ビット整数の制限のため、上位ビットが失われ、コンパイラは 44 を返します (300 2<sup>8</sup>)、結果として。 この数式に依存するすべての操作では、予期しない動作を生成します。

`SafeInt`クラスは、算術オーバーフローが発生したかどうか、またはコードが 0 で除算しようとしたかどうかをチェックします。 どちらの場合は、クラスは、潜在的な問題をプログラムに警告をエラー ハンドラーを呼び出します。

このクラスではいる限り、2 つの異なる型の整数を比較することもできます`SafeInt`オブジェクト。 通常、比較を実行するときに、同じ型である数値を最初変換する必要があります。 多くの場合、1 つの数値を別の型をキャストすると、データの損失がないことを確認するためのチェックが必要です。

このトピックで演算子の表でサポートされている数値と比較演算子の一覧、`SafeInt`クラス。 最も算術演算子を返す、`SafeInt`型のオブジェクト`T`します。

比較演算を`SafeInt`整数型をいずれかの方向で実行できます。 たとえば、両方とも`SafeInt<int>(x) < y`と`y> SafeInt<int>(x)`が有効であり、同じ結果が返されます。

多くの二項演算子は 2 つの異なる使用をサポートしていません`SafeInt`型。 この 1 つの例は、`&`演算子。 `SafeInt<T, E> & int` サポートされていますが、`SafeInt<T, E> & SafeInt<U, E>`はありません。 後者の例では、コンパイラは、返されるパラメーターの種類を認識しません。 この問題の解決策の 1 つ、基本データ型に 2 番目のパラメーターをキャストすることです。 同じパラメーターを使用すると、これを`SafeInt<T, E> & (U)SafeInt<U, E>`します。

> [!NOTE]
> すべてのビットごとの演算は、同じサイズが 2 つの異なるパラメーターにあります。 サイズが異なる場合、コンパイラがスローされます、 [ASSERT](../mfc/reference/diagnostic-services.md#assert)例外。 この操作の結果は正確である保証できません。 この問題を解決するが大きい方のパラメーターと同じサイズになるまで、小さい方のパラメーターをキャストします。

シフト演算子のテンプレートの種類の存在よりもより多くのビットをシフト ASSERT 例外がスローされます。 これは、効果はありませんリリース モードでします。 SafeInt パラメーターの 2 つの型を混在させると、戻り値の型が元の型と同じであるために、シフト演算子可能性があります。 演算子の右側にある数では、シフトするビット数だけを示します。

SafeInt オブジェクトでの論理比較を実行すると、比較では厳密に算術演算です。 たとえば、これらの式があるとします。

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

最初のステートメントに解決**true**に解決される 2 番目のステートメントが`false`します。 0 のビットごとの否定は、0 xffffffff です。 2 番目のステートメントでは、既定の比較演算子は、0 xffffffff を 0 xffffffff を比較し、両者を等しいと見なされます。 比較演算子、`SafeInt`クラスは、最初のパラメーターが署名されていないが、2 番目のパラメーターが負の値を認識しています。 そのため、ビット表現は同じですには、`SafeInt`論理演算子の符号なし整数が-1 より大きいことに気付きます。

使用する場合は注意してください、`SafeInt`クラスと組み合わせて、`?:`三項演算子。 次のコード行を検討してください。

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

コンパイラは、これに変換します。

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

場合`flag`は`false`、コンパイラが-1 の値を割り当てる代わりに例外をスロー`x`します。 したがって、この動作を避けるためには、使用する正しいコードは、次の行です。

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T` `U`ブール型、文字型または整数型に割り当てることができます。 整数型の符号付きまたは符号なしでき、8 ビットから 64 ビットの任意のサイズ。

> [!NOTE]
> ただし、`SafeInt`クラスは任意の整数、符号なしの型をより効率的に実行します。

`E` エラー処理機構を`SafeInt`を使用します。 SafeInt ライブラリを使用した 2 つのエラー処理メカニズムが提供されます。 既定のポリシーは`SafeIntErrorPolicy_SafeIntException`、どのがスローされます、 [SafeIntException クラス](../windows/safeintexception-class.md)例外、エラーが発生します。 他のポリシーは`SafeIntErrorPolicy_InvalidParameter`エラーが発生した場合、プログラムが停止します。

エラー ポリシーをカスタマイズする 2 つのオプションがあります。 最初のオプションは、パラメーターを設定する`E`を作成するとき、`SafeInt`します。 エラー処理ポリシーを 1 つのみを変更するときに、このオプションを使用`SafeInt`します。 その他のオプションは、_SAFEINT_DEFAULT_ERROR_POLICY をインクルードする前に、カスタマイズされたエラー処理クラスを定義する、`SafeInt`ライブラリ。 既定のエラー処理のすべてのインスタンスのポリシーを変更するときに、このオプションを使用、`SafeInt`コード内のクラス。

> [!NOTE]
> SafeInt ライブラリからエラーを処理するカスタマイズされたクラスは、エラー ハンドラーを呼び出したコードに制御を返しませんする必要があります。 エラー ハンドラーが呼び出された後の結果、`SafeInt`操作は、信頼することはできません。

## <a name="inheritance-hierarchy"></a>継承階層

`SafeInt`

## <a name="requirements"></a>必要条件

**ヘッダー:** safeint.h

**Namespace:** msl::utilities

## <a name="safeint"></a>Safeint::safeint

`SafeInt` オブジェクトを構築します。

```cpp
SafeInt() throw

SafeInt (
   const T& i
) throw ()

SafeInt (
   bool b
) throw ()

template <typename U>
SafeInt (
   const SafeInt <U, E>& u
)

I template <typename U>
SafeInt (
   const U& i
)
```

### <a name="parameters"></a>パラメーター

*i*<br/>
[in]新しい値`SafeInt`オブジェクト。 これには、コンス トラクターによって、型 T または U のパラメーターがあります。

*b*<br/>
[in]新しいブール値`SafeInt`オブジェクト。

*u*<br/>
[in]A`SafeInt`型 U の新しい`SafeInt`オブジェクトと同じ値になります*u*T 型になりますが、

U に格納されたデータの種類、`SafeInt`します。 ブール値、文字、または整数のいずれかの型を指定できます。 整数型の場合は、符号付きまたは符号なし 8 と 64 ビットの間であるとします。

### <a name="remarks"></a>Remarks

入力パラメーターをコンス トラクター、*は*または*u*、ブール値、文字、または整数型でなければなりません。 パラメーターの型を別の場合は、`SafeInt`クラスが呼び出す[static_assert](../cpp/static-assert.md)を無効な入力パラメーターを示します。

テンプレートの種類を使用するコンス トラクター`U`自動的に入力パラメーターで指定された型に変換できる`T`します。 `SafeInt`クラスのデータを失うことがなくデータを変換します。 エラー ハンドラーに報告`E`、データ型に変換できない場合`T`データ損失なし。

作成する場合、`SafeInt`ブール型のパラメーターから値をすぐに初期化する必要があります。 構築することはできません、`SafeInt`コードを使用して`SafeInt<bool> sb;`します。 これにより、コンパイル エラーが生成されます。
