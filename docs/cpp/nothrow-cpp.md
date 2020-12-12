---
description: '詳細情報: nothrow (C++)'
title: nothrow (C++)
ms.date: 01/03/2018
f1_keywords:
- nothrow_cpp
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
ms.openlocfilehash: 7e438541221fe097aefb2e52d190e223fa1cf2fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146251"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft 固有の仕様**

**`__declspec`** 関数の宣言で使用できる拡張属性。

## <a name="syntax"></a>構文

> *戻り値の型* __declspec (nothrow) [*呼び出し規約*] *関数名* ([*引数リスト*])

## <a name="remarks"></a>解説

新しいコードでは、ではなく [noexcept](noexcept-cpp.md) 演算子を使用することをお勧め `__declspec(nothrow)` します。

この属性は、宣言された関数、および、その呼び出す関数が例外をスローしないことをコンパイラに伝えます。 ただし、ディレクティブは適用されません。 つまり、std: [: terminate](../standard-library/exception-functions.md#terminate) は、とは異なり、 **`noexcept`** または **std: C++ 17** モード (Visual Studio 2017 バージョン15.5 以降) では呼び出されません `throw()` 。

同期例外処理モデル (現在は既定のモデル) の場合、コンパイラはこのような関数で特定のアンワインド可能オブジェクトの有効期間を追跡する機構を削除して、コード サイズを大幅に小さくできます。 次のプリプロセッサディレクティブを指定した場合、次の3つの関数宣言は、 **/std: c++ 14** モードでは同じです。

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

**/Std: c++ 17** モードで `throw()` は、は、 `__declspec(nothrow)` `std::terminate` 関数から例外がスローされた場合にが呼び出されるため、を使用する他のモードと同じではありません。

宣言は、 `void __stdcall f3() throw();` C++ 標準で定義されている構文を使用します。 C++ 17 では、 `throw()` キーワードは非推奨とされました。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
