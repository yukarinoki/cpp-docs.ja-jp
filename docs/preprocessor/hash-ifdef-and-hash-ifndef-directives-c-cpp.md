---
title: '#ifdef および #ifndef ディレクティブ (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#ifndef'
- '#ifdef'
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
ms.openlocfilehash: 418b19e844d56fa2f33cf91a1b072e9add771eb2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643795"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef および #ifndef ディレクティブ (C/C++)
**#Ifdef**と **#ifndef**ディレクティブと同じタスクを実行する、`#if`ディレクティブと共に使用するときに**定義**( *の識別子* ).

## <a name="syntax"></a>構文

```
#ifdef identifier
#ifndef identifier

// equivalent to
#if defined identifier
#if !defined identifier
```

## <a name="remarks"></a>Remarks

使用することができます、 **#ifdef**と **#ifndef**任意の場所ディレクティブ`#if`ことができます。 **#Ifdef** *識別子*ステートメントは等価`#if 1`とき*識別子*を定義した後と等価`#if 0`とき*識別子*が定義されていないか、定義していない、`#undef`ディレクティブ。 これらのディレクティブは、C または C++ ソース コードで宣言された識別子ではなく、`#define` で定義された識別子の有無を調べます。

これらのディレクティブは、言語の以前のバージョンとの互換性を維持するために用意されています。 **定義 (** *識別子* **)** で使用される定数式、`#if`ディレクティブをお勧めします。

**#Ifndef**ディレクティブが反対でチェックする条件のチェック **#ifdef**します。 識別子を定義していない (またはその定義を `#undef` で削除した) 場合、条件は true (ゼロ以外) です。 それ以外の場合、条件は False (0) です。

**Microsoft 固有の仕様**

*識別子*を使用して、コマンドラインから渡すことができます、`/D`オプション。 最大で 30 個のマクロで指定できる`/D`します。

定義をコマンド ラインから渡すことができるため、定義の有無を調べるために便利です。 例えば:

```cpp
// ifdef_ifndef.CPP
// compile with: /Dtest /c
#ifndef test
#define final
#endif
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)