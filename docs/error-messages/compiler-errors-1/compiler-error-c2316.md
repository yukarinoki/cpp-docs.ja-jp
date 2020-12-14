---
description: 詳細については、「コンパイラエラー C2316」を参照してください。
title: コンパイラ エラー C2316
ms.date: 07/08/2019
f1_keywords:
- C2316
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
ms.openlocfilehash: 0e2f528b3f13964a971b88fca110980947bd7d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282198"
---
# <a name="compiler-error-c2316"></a>コンパイラ エラー C2316

> '*class_type*': デストラクターまたはコピーコンストラクターにアクセスできないか削除されているため、キャッチできません

値または参照によって例外がキャッチされましたが、コピーコンストラクター、代入演算子、またはその両方にアクセスできませんでした。

## <a name="remarks"></a>解説

Visual Studio 2015 での準拠の変更。このエラーは、から派生した MFC 例外の不適切な catch ステートメントに適用さ `CException` れます。 `CException`には継承されたプライベートコピーコンストラクターがあるため、クラスとその派生クラスはコピーできず、値で渡すこともできません。これは、値でキャッチできないことを意味します。 MFC 例外を値によってキャッチした Catch ステートメントは、実行時にキャッチされていない例外を引き起こしました。 これで、コンパイラはこの状況を正しく識別し、エラー C2316 を報告します。 この問題を解決するには、独自の例外ハンドラーを記述するのではなく、MFC の TRY/CATCH マクロを使用することをお勧めします。 コードに適していない場合は、代わりに参照渡しで MFC 例外をキャッチします。

## <a name="example"></a>例

次の例では、C2316 を生成し、その修正方法を示しています。

```cpp
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&) {}
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
    catch (B b)    // C2316
    {
        printf_s("Caught an exception!\n");
    }
}
```
