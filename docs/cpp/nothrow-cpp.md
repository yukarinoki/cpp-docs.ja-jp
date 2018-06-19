---
title: nothrow (C++) |Microsoft ドキュメント
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
ms.openlocfilehash: 69a706577cf112c3d8a3b7748f72679f7213936d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420658"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft 固有の仕様**

関数の宣言に使用できる `__declspec` 拡張属性。

## <a name="syntax"></a>構文  
  
> *戻り値の型*無視されます [*呼び出し規約*]*関数名*([*引数リスト*])。

## <a name="remarks"></a>コメント

すべての新しいコードを使用していることをお勧め、 [noexcept](noexcept-cpp.md)演算子なく`__declspec(nothrow)`です。

この属性は、宣言された関数、および、その呼び出す関数が例外をスローしないことをコンパイラに伝えます。 ただし、このディレクティブは適用されません。 つまり、これが、 [std::terminate](../standard-library/exception-functions.md#terminate)呼び出されるとは異なり`noexcept`、または**std:c:operator++ 17**モード (Visual Studio 2017 15.5 およびそれ以降のバージョン)、`throw()`です。

同期例外処理モデル (現在は既定のモデル) の場合、コンパイラはこのような関数で特定のアンワインド可能オブジェクトの有効期間を追跡する機構を削除して、コード サイズを大幅に小さくできます。 次のプリプロセッサ ディレクティブを指定するには、次の 3 つの関数の宣言と等価である **/std:c + + 14**モード。

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

**/Std:c + + 17**モード、`throw()`は、他のユーザーに使用する`__declspec(nothrow)`原因になるので`std::terminate`関数から例外がスローされた場合に呼び出されます。

`void __stdcall f3() throw();`宣言で、C++ 標準で定義されている構文を使用します。 C++ 17 で、`throw()`キーワードは推奨されなくなりました。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)  
[noexcept](noexcept-cpp.md)  
[キーワード](../cpp/keywords-cpp.md)  
