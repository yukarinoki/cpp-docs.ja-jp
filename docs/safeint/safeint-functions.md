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
ms.openlocfilehash: c1c5593aee19254d4348d4e8658ffe9c3f0cf1b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368253"
---
# <a name="safeint-functions"></a>SafeInt 関数

SafeInt ライブラリには、[SafeInt クラス](../safeint/safeint-class.md)のインスタンスを作成せずに使える関数がいくつか用意されています。 1 つの数値演算を整数のオーバーフローから保護したい場合、これらの関数を使えます。 複数の数値演算を保護したい場合は、`SafeInt` オブジェクトを作成する必要があります。 これらの関数を複数回使うよりも、`SafeInt` オブジェクトを作成する方が効率的です。

これらの関数を使うと、2 つの異なる型のパラメーターを比較したり、それらで数値演算を実行したりできます。最初に同じ型に変換する必要はありません。

これらの各関数は、2 つのテンプレート型 `T` と `U` を持っています。 これらの型にはそれぞれ、ブール値、文字、または整数型を指定できます。 整数型は、符号付きまたは符号なしで、8 ビットから 64 ビットの任意のサイズにすることができます。

> [!NOTE]
> このライブラリの最新バージョンは に[https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)にあります。

## <a name="in-this-section"></a>このセクションの内容

機能                      | 説明
----------------------------- | --------------------------------------------------------------
[安全に追加](#safeadd)           | 2 つの数値を加算し、オーバーフローから保護します。
[Safecast](#safecast)         | ある型のパラメーターを別の型にキャストします。
[セーフディバイド](#safedivide)     | 2 つの数値を除算し、ゼロ除算から保護します。
[SafeEquals](#safeequals)、[SafeGreaterThan](#safegreaterthan)、[SafeGreaterThanEquals](#safegreaterthanequals)、[SafeLessThan](#safelessthan)、[SafeLessThanEquals](#safelessthanequals)、[SafeNotEquals](#safenotequals) | 2 つの数値を比較します。 これらの関数を使うと、異なる型の 2 つの数値を、その型を変更することなく比較できます。
[セーフモジュラス](#safemodulus)   | 2 つの数値に対して剰余演算を実行します。
[セーフ乗算](#safemultiply) | 2 つの数値を乗算し、オーバーフローから保護します。
[セーフ減算](#safesubtract) | 2 つの数値を減算し、オーバーフローから保護します。

## <a name="related-sections"></a>関連項目

Section                                                  | 説明
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](../safeint/safeint-class.md)                   | `SafeInt` クラスです。
[SafeIntException](../safeint/safeintexception-class.md) | SafeInt ライブラリに固有の例外クラスです。

## <a name="safeadd"></a><a name="safeadd"></a>安全に追加

オーバーフローから保護される方法で 2 つの数値を加算します。

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 加算する最初の数値。 これは T 型である必要があります。

*U*<br/>
[入力] 加算する 2 番目の数値。 これは U 型である必要があります。

*result*<br/>
[出力] `SafeAdd` の結果が格納されるパラメーター。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は **true**。エラーが発生した場合は **false**。

## <a name="safecast"></a><a name="safecast"></a>Safecast

ある型の数値を別の型にキャストします。

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>パラメーター

*From*<br/>
[入力] 変換元の数値。 これは `T` 型である必要があります。

*To*<br/>
[出力] 新しい数値型への参照。 これは `U` 型である必要があります。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は **true**。エラーが発生した場合は **false**。

## <a name="safedivide"></a><a name="safedivide"></a>セーフディバイド

ゼロ除算から保護される方法で 2 つの数値を除算します。

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 除数。 これは T 型である必要があります。

*U*<br/>
[入力] 被除数。 これは U 型である必要があります。

*result*<br/>
[出力] `SafeDivide` の結果が格納されるパラメーター。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は **true**。エラーが発生した場合は **false**。

## <a name="safeequals"></a><a name="safeequals"></a>セーフイコール

2 つの数値を比較し、それらが等しいかどうかを判定します。

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 比較する最初の数値。 これは T 型である必要があります。

*U*<br/>
[入力] 比較する 2 番目の数値。 これは U 型である必要があります。

### <a name="return-value"></a>戻り値

*t* と *u* が等しい場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>解説

このメソッドでは `==` が強化されます。`SafeEquals` を使うと、2 つの異なる型の数値を比較できるためです。

## <a name="safegreaterthan"></a><a name="safegreaterthan"></a>セーフグレータータン

2 つの数値を比較します。

```cpp
template<typename T, typename U>
inline bool SafeGreaterThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 比較する最初の数値。 これは `T` 型である必要があります。

*U*<br/>
[入力] 比較する 2 番目の数値。 これは `U` 型である必要があります。

### <a name="return-value"></a>戻り値

*t* が *u* よりも大きい場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>解説

`SafeGreaterThan` では通常の比較演算子が拡張され、2 つの異なる型の数値を比較できます。

## <a name="safegreaterthanequals"></a><a name="safegreaterthanequals"></a>セーフグレータータンコッツ

2 つの数値を比較します。

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 比較する最初の数値。 これは `T` 型である必要があります。

*U*<br/>
[入力] 比較する 2 番目の数値。 これは `U` 型である必要があります。

### <a name="return-value"></a>戻り値

*t* が *u* よりも大きいか等しい場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>解説

`SafeGreaterThanEquals` では標準の比較演算子が強化され、2 つの異なる型の数値を比較できます。

## <a name="safelessthan"></a><a name="safelessthan"></a>セーフレスタン

一方の数値がもう一方の数値よりも小さいかどうかを判定します。

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 最初の数値。 これは `T` 型である必要があります。

*U*<br/>
[入力] 2 番目の数値。 これは `U` 型である必要があります。

### <a name="return-value"></a>戻り値

*t* が *u* よりも小さい場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>解説

このメソッドでは標準の比較演算子が強化されます。`SafeLessThan` を使うと、2 つの異なる型の数値を比較できるためです。

## <a name="safelessthanequals"></a><a name="safelessthanequals"></a>セーフレスタン・イコールズ

2 つの数値を比較します。

```cpp
template <typename T, typename U>
inline bool SafeLessThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 比較する最初の数値。 これは `T` 型である必要があります。

*U*<br/>
[入力] 比較する 2 番目の数値。 これは `U` 型である必要があります。

### <a name="return-value"></a>戻り値

*t* が *u* よりも小さいか等しい場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>解説

`SafeLessThanEquals` では通常の比較演算子が拡張され、2 つの異なる型の数値を比較できます。

## <a name="safemodulus"></a><a name="safemodulus"></a>セーフモジュラス

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

*T*<br/>
[入力] 除数。 これは `T` 型である必要があります。

*U*<br/>
[入力] 被除数。 これは `U` 型である必要があります。

*result*<br/>
[出力] `SafeModulus` の結果が格納されるパラメーター。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は **true**。エラーが発生した場合は **false**。

## <a name="safemultiply"></a><a name="safemultiply"></a>セーフ乗算

オーバーフローから保護される方法で 2 つの数値を乗算します。

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 乗算する最初の数値。 これは `T` 型である必要があります。

*U*<br/>
[入力] 乗算する 2 番目の数値。 これは `U` 型である必要があります。

*result*<br/>
[出力] `SafeMultiply` の結果が格納されるパラメーター。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は `true`。エラーが発生した場合は `false`。

## <a name="safenotequals"></a><a name="safenotequals"></a>セーフ・イス・イコール

2 つの数値が等しくないかどうかを判定します。

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 比較する最初の数値。 これは `T` 型である必要があります。

*U*<br/>
[入力] 比較する 2 番目の数値。 これは `U` 型である必要があります。

### <a name="return-value"></a>戻り値

*t* と *u* が等しくない場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>解説

このメソッドでは `!=` が強化されます。`SafeNotEquals` を使うと、2 つの異なる型の数値を比較できるためです。

## <a name="safesubtract"></a><a name="safesubtract"></a>セーフ減算

オーバーフローから保護される方法で 2 つの数値を減算します。

```cpp
template<typename T, typename U>
inline bool SafeSubtract (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[入力] 減算の最初の数値。 これは `T` 型である必要があります。

*U*<br/>
[入力] *t* から減算する数値。 これは `U` 型である必要があります。

*result*<br/>
[出力] `SafeSubtract` の結果が格納されるパラメーター。

### <a name="return-value"></a>戻り値

エラーが発生しなかった場合は **true**。エラーが発生した場合は **false**。
