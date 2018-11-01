---
title: SafeInt 関数
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeInt functions
- SafeAdd
- SafeCast
- SafeDivide
- SafeEquals
- SafeGreaterThan
- SafeGreaterThanEquals
- SafeLessThan
- SafeLessThanEquals
- SafeModulus
- SafeMultiply
- SafeNotEquals
- SafeSubtract
helpviewer_keywords:
- functions, SafeInt
- SafeAdd function
- SafeCast function
- SafeDivide function
- SafeEquals function
- SafeGreaterThan function
- SafeGreaterThanEquals function
- SafeLessThan function
- SafeLessThanEquals function
- SafeModulus function
- SafeMultiply function
- SafeNotEquals function
- SafeSubtract function
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
ms.openlocfilehash: 0cf1418e3bf00c037faaa67de2bc76ad2b7cc5e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578400"
---
# <a name="safeint-functions"></a>SafeInt 関数

SafeInt ライブラリのインスタンスを作成せずに使用できるいくつかの機能を提供する、 [SafeInt クラス](../windows/safeint-class.md)します。 単一の数値演算を整数のオーバーフローから保護する場合は、これらの関数を使用できます。 複数の数値演算を保護する場合は、作成する必要があります`SafeInt`オブジェクト。 作成する方が効率的です`SafeInt`にこれらの関数を複数回使用よりもオブジェクトです。

これらの関数を使用すると、比較または最初に、同じ型に変換することがなく 2 つの異なる型のパラメーターの算術演算を実行できます。

これらの各関数は、テンプレートの 2 つの種類:`T`と`U`します。 これらの型には、ブール値、文字、または整数型ができます。 整数型の符号付きまたは符号なしでき、あらゆるサイズを 8 ビットから 64 ビット。

> [!NOTE]
> このライブラリの最新バージョンは[ https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)します。

## <a name="in-this-section"></a>このセクションの内容

関数                      | 説明
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | 2 つの数値を追加し、オーバーフローから保護します。
[SafeCast](#safecast)         | 別の型パラメーターの型にキャストします。
[SafeDivide](#safedivide)     | 2 つの数値を除算し、0 で除算することを防ぎます。
[SafeEquals](#safeequals)、 [SafeGreaterThan](#safegreaterthan)、 [SafeGreaterThanEquals](#safegreaterthanequals)、 [SafeLessThan](#safelessthan)、 [SafeLessThanEquals](#safelessthanequals)、 [SafeNotEquals](#safenotequals) | 2 つの数値を比較します。 これらの関数を使用すると、その型を変更することがなく 2 つの異なる型の数値を比較できます。
[SafeModulus](#safemodulus)   | 2 つの数値に対して剰余演算を実行します。
[SafeMultiply](#safemultiply) | 2 つの数値を乗算し、オーバーフローを保護します。
[SafeSubtract](#safesubtract) | 2 つの数値を減算し、オーバーフローから保護します。

## <a name="related-sections"></a>関連項目

セクション                                                  | 説明
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](../windows/safeint-class.md)                   | `SafeInt` クラス
[SafeIntException](../windows/safeintexception-class.md) | SafeInt ライブラリに固有の例外クラスです。

## <a name="safeadd"></a>SafeAdd

オーバーフローに対する保護できる方法では、2 つの数値を追加します。

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]追加する最初の数値。 これは T 型である必要があります。

*u*<br/>
[in]追加する 2 番目の数値。 これは、型 U のある必要があります。

*結果*<br/>
[out]パラメーターで`SafeAdd`結果を格納します。

### <a name="return-value"></a>戻り値

**true**場合、エラーは発生しません。**false**エラーが発生した場合。

## <a name="safecast"></a>SafeCast

型の数値を別の型にキャストします。

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>パラメーター

*From*<br/>
[in]変換するソースの数。 これは、型でなければなりません`T`します。

*目的*<br/>
[out]新しい数値型への参照。 これは、型でなければなりません`U`します。

### <a name="return-value"></a>戻り値

**true**場合、エラーは発生しません。**false**エラーが発生した場合。

## <a name="safedivide"></a>SafeDivide

ゼロ除算に対して保護できる方法で 2 つの数値を除算します。

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]除数。 これは T 型である必要があります。

*u*<br/>
[in]被除数。 これは、型 U のある必要があります。

*結果*<br/>
[out]パラメーターで`SafeDivide`結果を格納します。

### <a name="return-value"></a>戻り値

**true**場合、エラーは発生しません。**false**エラーが発生した場合。

## <a name="safeequals"></a>SafeEquals

等しいかどうかを判断する 2 つの数値を比較します。

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]比較する最初の数値。 これは T 型である必要があります。

*u*<br/>
[in]比較する 2 番目の数値。 これは、型 U のある必要があります。

### <a name="return-value"></a>戻り値

**true**場合*t*と*u*はそれ以外の**false**します。

### <a name="remarks"></a>Remarks

メソッドを強化`==`ため`SafeEquals`2 つの異なる型の数値を比較することができます。

## <a name="safegreaterthan"></a>SafeGreaterThan

2 つの数値を比較します。

```cpp
template<typename T, typename U>
inline bool SafeGreaterThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]比較する最初の数値。 これは、型でなければなりません`T`します。

*u*<br/>
[in]比較する 2 番目の数値。 これは、型でなければなりません`U`します。

### <a name="return-value"></a>戻り値

**true**場合*t*がより大きい*u*。 そうしないと**false**します。

### <a name="remarks"></a>Remarks

`SafeGreaterThan` 2 つの異なる型の数値を比較することによって、正規表現の比較演算子を拡張します。

## <a name="safegreaterthanequals"></a>SafeGreaterThanEquals

2 つの数値を比較します。

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]比較する最初の数値。 これは、型でなければなりません`T`します。

*u*<br/>
[in]比較する 2 番目の数値。 これは、型でなければなりません`U`します。

### <a name="return-value"></a>戻り値

**true**場合*t*がより大きいまたは等しい*u*。 そうしないと**false**します。

### <a name="remarks"></a>Remarks

`SafeGreaterThanEquals` 2 つの異なる型の数値を比較することもできるため、標準的な比較演算子が向上します。

## <a name="safelessthan"></a>SafeLessThan

1 つの数値が他よりも小さいかどうかを判断します。

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]最初の数値。 これは、型でなければなりません`T`します。

*u*<br/>
[in]2 番目の数値。 これは、型でなければなりません`U`します。

### <a name="return-value"></a>戻り値

**true**場合*t*がより小さい*u*。 そうしないと**false**します。

### <a name="remarks"></a>Remarks

このメソッドでは、ため、標準的な比較演算子が強化されます`SafeLessThan`数の 2 つの異なる型を比較することができます。

## <a name="safelessthanequals"></a>SafeLessThanEquals

2 つの数値を比較します。

```cpp
template <typename T, typename U>
inline bool SafeLessThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]比較する最初の数値。 これは、型でなければなりません`T`します。

*u*<br/>
[in]比較する 2 番目の数値。 これは、型でなければなりません`U`します。

### <a name="return-value"></a>戻り値

**true**場合*t*に等しいまたはそれよりも小さい*u*。 そうしないと**false**します。

### <a name="remarks"></a>Remarks

`SafeLessThanEquals` 2 つの異なる型の数値を比較することによって、正規表現の比較演算子を拡張します。

## <a name="safemodulus"></a>SafeModulus

2 つの数値に対して剰余演算を実行します。

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]除数。 これは、型でなければなりません`T`します。

*u*<br/>
[in]被除数。 これは、型でなければなりません`U`します。

*結果*<br/>
[out]パラメーターで`SafeModulus`結果を格納します。

### <a name="return-value"></a>戻り値

**true**場合、エラーは発生しません。**false**エラーが発生した場合。

## <a name="safemultiply"></a>SafeMultiply

オーバーフローに対する保護できる方法で 2 つの数値を乗算します。

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]乗算する最初の数値。 これは、型でなければなりません`T`します。

*u*<br/>
[in]乗算する 2 番目の数値。 これは、型でなければなりません`U`します。

*結果*<br/>
[out]パラメーターで`SafeMultiply`結果を格納します。

### <a name="return-value"></a>戻り値

`true` エラーが発生しなかった場合`false`エラーが発生した場合。

## <a name="safenotequals"></a>SafeNotEquals

2 つの数値が等しくないかどうかを決定します。

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]比較する最初の数値。 これは、型でなければなりません`T`します。

*u*<br/>
[in]比較する 2 番目の数値。 これは、型でなければなりません`U`します。

### <a name="return-value"></a>戻り値

**true**場合*t*と*u*それ以外のない**false**します。

### <a name="remarks"></a>Remarks

メソッドを強化`!=`ため`SafeNotEquals`2 つの異なる型の数値を比較することができます。

## <a name="safesubtract"></a>SafeSubtract

オーバーフローに対する保護できる方法で 2 つの数値を減算します。

```cpp
template<typename T, typename U>
inline bool SafeSubtract (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*t*<br/>
[in]減算の最初の数値。 これは、型でなければなりません`T`します。

*u*<br/>
[in]減算する数値*t*します。 これは、型でなければなりません`U`します。

*結果*<br/>
[out]パラメーターで`SafeSubtract`結果を格納します。

### <a name="return-value"></a>戻り値

**true**場合、エラーは発生しません。**false**エラーが発生した場合。
