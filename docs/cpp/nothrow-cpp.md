---
title: nothrow (C++)
ms.date: 01/03/2018
f1_keywords:
- nothrow_cpp
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
ms.openlocfilehash: 8164f47190267627bdaf7c7ee2f03f22f65c8f50
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161062"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft 固有の仕様**

関数の宣言で使用できる **__declspec**拡張属性。

## <a name="syntax"></a>構文

> *戻り値の型*__declspec (nothrow) [*呼び出し規約*]*関数名*([*引数リスト*])

## <a name="remarks"></a>解説

すべての新しいコードでは、`__declspec(nothrow)`ではなく、 [noexcept](noexcept-cpp.md)演算子を使用することをお勧めします。

この属性は、宣言された関数、および、その呼び出す関数が例外をスローしないことをコンパイラに伝えます。 ただし、ディレクティブは適用されません。 言い換えると、std [:: terminate](../standard-library/exception-functions.md#terminate)は、`noexcept`とは異なり、または**std: c++ 17**モード (Visual Studio 2017 バージョン15.5 以降) では呼び出されません。 `throw()`。

同期例外処理モデル (現在は既定のモデル) の場合、コンパイラはこのような関数で特定のアンワインド可能オブジェクトの有効期間を追跡する機構を削除して、コード サイズを大幅に小さくできます。 次のプリプロセッサディレクティブを指定した場合、次の3つの関数宣言は、 **/std: c++ 14**モードでは同じです。

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

**/Std: c++ 17**モードでは、関数から例外がスローされた場合に `std::terminate` が呼び出されるため、`__declspec(nothrow)` を使用する他の `throw()` とは異なります。

`void __stdcall f3() throw();` 宣言では、 C++標準によって定義された構文を使用します。 C++ 17 では、`throw()` キーワードは非推奨とされました。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
