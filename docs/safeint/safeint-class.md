---
title: SafeInt クラス
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeInt
- SafeInt::SafeInt
- SafeInt.SafeInt
helpviewer_keywords:
- SafeInt class
- SafeInt class, constructor
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
ms.openlocfilehash: d61ce20a8644ca64d37c0eca605d52fb308c0863
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560962"
---
# <a name="safeint-class"></a>SafeInt クラス

整数オーバーフローを防ぐことができるように整数のプリミティブを拡張し、さまざまな種類の整数を比較してみましょう。

> [!NOTE]
> SafeInt ライブラリの最新バージョンは、にあり [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) ます。 SafeInt ライブラリを使用するには、リポジトリを複製し、 `#include "SafeInt.hpp"`

## <a name="syntax"></a>構文

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>パラメーター

*`T`*\
`SafeInt` で置き換えられる整数またはブール値パラメーターの型。

*`E`*\
エラー処理ポリシーを定義する列挙データ型。

*`U`*\
第 2 オペランドの整数またはブール値パラメーターの型。

*rhs*\
[in] いくつかのスタンドアロン関数で演算子の右側にある値を表す入力パラメーター。

*私*\
[in] いくつかのスタンドアロン関数で演算子の右側にある値を表す入力パラメーター。

*列*\
[in] いくつかのスタンドアロン関数で演算子の右側にある値を表す入力パラメーター。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

| 名前                          |  説明 |
|---------------------------|--------------------|
| [SafeInt:: SafeInt](#safeint)  |  既定のコンストラクターです。 |

### <a name="assignment-operators"></a>代入演算子

| 名前  |  構文 |
|----|---------|
| =     |  `template<typename U>`<br />`SafeInt<T,E>& operator= (const U& rhs)` |
| =     |  `SafeInt<T,E>& operator= (const T& rhs) throw()` |
| =     |  `template<typename U>`<br />`SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)` |
| =     |  `SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()` |

### <a name="casting-operators"></a>キャスト演算子

| 名前              |  構文 |
|------|---------------------------------|
| bool              |  `operator bool() throw()` |
| char              |  `operator char() const` |
| signed char       |  `operator signed char() const` |
| unsigned char     |  `operator unsigned char() const` |
| __int16           |  `operator __int16() const` |
| unsigned __int16  |  `operator unsigned __int16() const` |
| __int32           |  `operator __int32() const` |
| unsigned __int32  |  `operator unsigned __int32() const` |
| long              |  `operator long() const` |
| unsigned long     |  `operator unsigned long() const` |
| __int64           |  `operator __int64() const` |
| unsigned __int64  |  `operator unsigned __int64() const` |
| wchar_t           |  `operator wchar_t() const` |

### <a name="comparison-operators"></a>比較演算子

| 名前  |  構文 |
|----|----------------|
| \<     |  `template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()` |
| \<     |  `bool operator< (SafeInt<T,E> rhs) const throw()` |
| \>=    |  `template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()` |
| \>=    |  `Bool operator>= (SafeInt<T,E> rhs) const throw()` |
| \>     |  `template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()` |
| \>     |  `Bool operator> (SafeInt<T,E> rhs) const throw()` |
| \<=    |  `template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()` |
| \<=    |  `bool operator<= (SafeInt<T,E> rhs) const throw()` |
| ==    |  `template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()` |
| ==    |  `bool operator== (bool rhs) const throw()` |
| ==    |  `bool operator== (SafeInt<T,E> rhs) const throw()` |
| !=    |  `template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()` |
| !=    |  `bool operator!= (bool b) const throw()` |
| !=    |  `bool operator!= (SafeInt<T,E> rhs) const throw()` |

### <a name="arithmetic-operators"></a>算術演算子

| 名前  |  構文 |
|----|--------------|
| +     |  `const SafeInt<T,E>& operator+ () const throw()` |
| -     |  `SafeInt<T,E> operator- () const` |
| ++    |  `SafeInt<T,E>& operator++ ()` |
| --    |  `SafeInt<T,E>& operator-- ()` |
| %     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const` |
| %     |  `SafeInt<T,E> operator% (SafeInt<T,E> rhs) const` |
| %=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)` |
| %=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)` |
| \*     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const` |
| \*     |  `SafeInt<T,E> operator* (SafeInt<T,E> rhs) const` |
| \*=    |  `SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)` |
| \*=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)` |
| \*=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)` |
| /     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const` |
| /     |  `SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const` |
| /=    |  `SafeInt<T,E>& operator/= (SafeInt<T,E> i)` |
| /=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)` |
| /=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)` |
| +     |  `SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const` |
| +     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const` |
| +=    |  `SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)` |
| +=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)` |
| +=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)` |
| -     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const` |
| -     |  `SafeInt<T,E> operator- (SafeInt<T,E> rhs) const` |
| -=    |  `SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)` |
| -=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)` |
| -=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)` |

### <a name="logical-operators"></a>論理演算子

| 名前     |  構文 |
|------|--------------|
| !        |  `bool operator !() const throw()` |
| ~        |  `SafeInt<T,E> operator~ () const throw()` |
| \<\<       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()` |
| \<\<       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()` |
| \<\<=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()` |
| \<\<=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()` |
| \>\>       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()` |
| \>\>       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()` |
| \>\>=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()` |
| \>\>=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()` |
| &        |  `SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()` |
| &        |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()` |
| &=       |  `SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()` |
| &=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()` |
| &=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()` |
| ^        |  `SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()` |
| ^        |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()` |
| ^=       |  `SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()` |
| ^=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()` |
| ^=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()` |
| &#124;   |  `SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()` |
| &#124;   |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()` |
| &#124;=  |  `SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()` |
| &#124;=  |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()` |
| &#124;=  |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()` |

## <a name="remarks"></a>解説

`SafeInt` クラスは、数学演算での整数オーバーフローを防ぎます。 たとえば、2 つの 8 ビット整数を追加するとします。1 つは値が 200 であり、2 つ目は値が 100 です。 正しい数学演算は 200 + 100 = 300 です。 ただし、8 ビット整数の制限があるため、上位ビットは失われ、結果としてコンパイラから 44 (300 - 2<sup>8</sup>) が返されます。 この数式に依存するすべての演算では、予期しない動作が起こります。

`SafeInt` クラスでは、算術オーバーフローが発生するかどうか、またはコードがゼロ除算を試行しているかどうかが確認されます。 いずれの場合も、クラスからエラー ハンドラーが呼び出され、プログラムに潜在的な問題が警告されます。

このクラスを使用すると、`SafeInt` オブジェクトである限り、2 種類の整数を比較することもできます。 通常、比較を行う場合は、最初に数値を同じ型に変換する必要があります。 ある数値を別の型にキャストするには、多くの場合、データの損失がないことを確認するチェックが必要です。

このトピックの「演算子」一覧には、`SafeInt` クラスでサポートされている数学演算子と比較演算子がまとめられています。 ほとんどの数学演算子からは、型が `T` の `SafeInt` オブジェクトが返されます。

`SafeInt` と整数型との比較演算は、いずれの方向でも実行できます。 たとえば、`SafeInt<int>(x) < y` と `y> SafeInt<int>(x)` はどちらも有効であり、同じ結果が返されます。

多くの二項演算子は、2つの異なる型の使用をサポートしていません `SafeInt` 。 その一例は `&` 演算子です。 `SafeInt<T, E> & int` はサポートされますが、はサポートされていません `SafeInt<T, E> & SafeInt<U, E>` 。 後者の例では、コンパイラはどの型のパラメーターを返すべきかを認識していません。 この問題の解決策の 1 つは、2 つ目のパラメーターを基本データ型にキャストすることです。 同じパラメーターを使用して、`SafeInt<T, E> & (U)SafeInt<U, E>` でこれを実行できます。

> [!NOTE]
> どのようなビットごとの演算でも、2 つの異なるパラメーターのサイズを同じにする必要があります。 サイズが異なると、コンパイラからは [ASSERT](../mfc/reference/diagnostic-services.md#assert) 例外がスローされます。 この操作の結果は、正確であるとは限りません。 この問題を解決するには、より大きなパラメーターと同じサイズになるまで、小さい方のパラメーターをキャストします。

シフト演算子の場合、そのテンプレート型に存在するよりも多くのビットをシフトすると、ASSERT 例外がスローされます。 これはリリース モードには影響しません。 戻り値の型は元の型と同じなので、シフト演算子には 2 つの型の SafeInt パラメーターを混在させることができます。 演算子の右側側にある数値は、単にシフトするビット数を示しています。

SafeInt オブジェクトとの論理比較を行う場合、厳密には算術演算になります。 たとえば、以下の式があるとします。

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

最初のステートメントはに解決され **`true`** ますが、2番目のステートメントはに解決され **`false`** ます。 0 のビットごとの否定は 0xFFFFFFFF です。 2 つ目のステートメントでは、既定の比較演算子によって 0xFFFFFFFF と 0xFFFFFFFF が比較され、それらが等しいと見なされます。 `SafeInt` クラスの比較演算子は、2 つ目のパラメーターが負であり、1 つ目のパラメーターは符号なしであると認識しています。 そのため、ビット表現は同じですが、`SafeInt` 論理演算子は、符号なし整数が -1 よりも大きいと認識しています。

`SafeInt` クラスを `?:` 三項演算子と組み合わせて使用するときは注意してください。 次のコード行があるとします。

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

コンパイラでは、これが次のように変換されます。

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

がの場合 `flag` **`false`** 、コンパイラは、-1 の値をに割り当てる代わりに、例外をスローし `x` ます。 そのため、この動作を回避するには、次の行のように正しいコードを使用します。

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T` と `U` には、ブール型、文字型、または整数型を割り当てることができます。 整数型は、符号付きまたは符号なしで、8 ビットから 64 ビットの任意のサイズにすることができます。

> [!NOTE]
> `SafeInt` クラスはあらゆる種類の整数を受け取りますが、符号なしの型を使用するとより効率的に実行されます。

`E` は、`SafeInt` で使用されるエラー処理メカニズムです。 SafeInt ライブラリには、2 つのエラー処理メカニズムが用意されています。 既定のポリシーは `SafeIntErrorPolicy_SafeIntException` であり、エラーが発生したときに [SafeIntException クラス](safeintexception-class.md)例外がスローされます。 もう 1 つのポリシーは `SafeIntErrorPolicy_InvalidParameter` であり、エラーが発生した場合にプログラムが停止されます。

エラー ポリシーをカスタマイズするオプションは 2 つあります。 1 つ目のオプションは、`SafeInt` を作成するときにパラメーター `E` を設定することです。 エラー処理ポリシーを 1 つの `SafeInt` のみに変更する場合は、このオプションを使用します。 もう 1 つのオプションは、`SafeInt` ライブラリを組み込む前に、カスタマイズされたエラー処理クラスとして _SAFEINT_DEFAULT_ERROR_POLICY を定義することです。 コード内の `SafeInt` クラスのすべてのインスタンスで既定のエラー処理ポリシーを変更する場合は、このオプションを使用します。

> [!NOTE]
> SafeInt ライブラリからのエラーを処理するカスタマイズされたクラスでは、エラー ハンドラーを呼び出したコードに制御が返されません。 エラーハンドラーが呼び出された後、操作の結果を `SafeInt` 信頼することはできません。

## <a name="inheritance-hierarchy"></a>継承階層

`SafeInt`

## <a name="requirements"></a>必要条件

**ヘッダー:** SafeInt. hpp
> [!NOTE]
> このライブラリの最新バージョンは、にあり [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) ます。 ライブラリを複製し、safeint ライブラリを使用するために SafeInt をインクルードします。
> この github リポジトリを優先して、safeint> を <します。 これは <safeint. h> の最新バージョンであり、少数のバグ修正が含まれており、C++ の最新の機能を使用して、より効率的なコードを作成し、gcc、clang、または Intel コンパイラを使用して任意のプラットフォームに移植できます。

### <a name="example"></a>例

```c
#include "SafeInt.hpp" // set path to your clone of the SafeInt GitHub repo (https://github.com/dcleblanc/SafeInt)

int main()
{
    int divisor = 3;
    int dividend = 6;
    int result;

    bool success = SafeDivide(dividend, divisor, result); // result = 2
    success = SafeDivide(dividend, 0, result); // expect fail. result isn't modified.
}
```

**名前空間:** なし

## <a name="safeintsafeint"></a><a name="safeint"></a> SafeInt:: SafeInt

`SafeInt` オブジェクトを構築します。

```cpp
SafeInt() throw

SafeInt (const T& i) throw ()

SafeInt (bool b) throw ()

template <typename U>
SafeInt (const SafeInt <U, E>& u)

I template <typename U>
SafeInt (const U& i)
```

### <a name="parameters"></a>パラメーター

`i`<br/>
[in] 新しい `SafeInt` オブジェクトの値。 これは、コンストラクターに応じて、型 T または U のパラメーターにする必要があります。

`b`<br/>
[in] 新しい `SafeInt` オブジェクトのブール値。

`u`<br/>
[in] 型 U の `SafeInt`。新しい `SafeInt` オブジェクトは、*u* と同じ値になりますが、型は T になります。

`U` に格納されているデータの型 `SafeInt` 。 ブール型、文字型、または整数型のいずれかを使用できます。 整数型の場合は、符号付きまたは符号なしで、8 ~ 64 ビットの範囲で指定できます。

### <a name="remarks"></a>解説

コンストラクターの入力パラメーター *i* または *u* は、ブール型、文字型、または整数型にする必要があります。 別の型のパラメーターの場合、 `SafeInt` クラスは [static_assert](../cpp/static-assert.md) を呼び出して、無効な入力パラメーターを示します。

テンプレート型 `U` を使用するコンストラクターでは、入力パラメーターが `T` に指定された型に自動的に変換されます。 `SafeInt` クラスでは、データの損失なしでデータが変換されます。 データ `E` を失わずにデータを型に変換できない場合、エラーハンドラーに報告し `T` ます。

ブール値パラメーターから `SafeInt` を作成した場合は、すぐに値を初期化する必要があります。 `SafeInt`コードを使用してを構築することはできません `SafeInt<bool> sb;` 。 その結果、コンパイル エラーが発生します。
