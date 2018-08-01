---
title: nothrow (C++) |Microsoft Docs
ms.custom: ''
ms.date: 01/03/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0261ed9d1e84849f408c3d764693cb95ac7019d2
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408067"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft 固有の仕様**

A **_ _declspec**関数の宣言で使用できる拡張属性。

## <a name="syntax"></a>構文  
  
> *戻り値の型*無視されます [*呼び出し規約*]*関数名*([*引数リスト*])。

## <a name="remarks"></a>Remarks

すべての新しいコードを使用していることをお勧めします。、 [noexcept](noexcept-cpp.md)演算子なく`__declspec(nothrow)`します。

この属性は、宣言された関数、および、その呼び出す関数が例外をスローしないことをコンパイラに伝えます。 ただし、このディレクティブは適用されません。 しないと、つまり、 [std::terminate](../standard-library/exception-functions.md#terminate)呼び出されるとは異なり`noexcept`、または **/std:c + + 17**モード (Visual Studio 2017 バージョン 15.5 以降)、`throw()`します。

同期例外処理モデル (現在は既定のモデル) の場合、コンパイラはこのような関数で特定のアンワインド可能オブジェクトの有効期間を追跡する機構を削除して、コード サイズを大幅に小さくできます。 次のプリプロセッサ ディレクティブを指定するには、次の 3 つの関数の宣言が同じ **/std:c + + 14**モード。

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

**/Std:c + + 17**モード、`throw()`を使用すると、他と等価でない`__declspec(nothrow)`原因になるので`std::terminate`関数から例外がスローされた場合に呼び出されます。

`void __stdcall f3() throw();`宣言は、C++ 標準で定義されている構文を使用します。 C++ 17 で、`throw()`キーワードは非推奨とされました。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目
 [__declspec](../cpp/declspec.md)  
 [noexcept](noexcept-cpp.md)  
 [キーワード](../cpp/keywords-cpp.md)  