---
title: コンパイラ エラー C2316 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2868d3a81fcbc94d8b20adcdc775363eb0a8eaeb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033018"
---
# <a name="compiler-error-c2316"></a>コンパイラ エラー C2316

> '*例外*': デストラクターまたはコピー コンス トラクターはアクセスできないためキャッチできません

値または参照によって例外がキャッチされましたが、コピー コンストラクターや代入演算子にアクセスできませんでした。

このコードでは、バージョンの Visual Studio 2003 では、前に Visual C によって承認されましたが、エラーになります。

Visual Studio 2015 の準拠に関する変更は、このエラーから派生した MFC 例外の不適切な catch ステートメントに適用を行った`CException`します。 `CException`継承されたプライベート コピー コンス トラクター、クラスとその派生クラスはコピー可能、され、それらの値によってキャッチできないことも意味値によって渡すことができません。 値は以前、実行時にキャッチされない例外の原因で MFC の例外をキャッチするステートメントが catch されますが、今すぐコンパイラ正しくこのような状況とレポート エラー C2316。 この問題を解決するには、独自の例外ハンドラーの記述がになっていない場合、コードに適した、MFC の例外をキャッチ参照渡しで代わりにではなく、MFC TRY/CATCH マクロの使用をお勧めします。

## <a name="example"></a>例

次の例では C2316 が生成されます。

```
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

extern "C" int printf_s(const char*, ...);

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&)
    {
    }
};

void f(const B&)
{
}

int main()
{
    try
    {
        B aB;
        f(aB);
    }
    catch (B b) {   // C2316
        printf_s("Caught an exception!\n");
    }
}
```