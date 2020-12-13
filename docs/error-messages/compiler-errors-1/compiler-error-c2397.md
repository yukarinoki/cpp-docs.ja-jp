---
description: 詳細については、「コンパイラエラー C2397」を参照してください。
title: コンパイラエラー C2397
ms.date: 11/04/2016
f1_keywords:
- C2397
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
ms.openlocfilehash: 8e5f000b8d0881fd6a57bb4895afbdef0e7c598a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145380"
---
# <a name="compiler-error-c2397"></a>コンパイラエラー C2397

' type_1 ' から ' type_2 ' への変換には縮小変換が必要です

一様な初期化を使用するときに、暗黙的な縮小変換が見つかりました。

C 言語では、割り当てと初期化で暗黙的な縮小変換を使用できます。また、C++ では、予期しない縮小が多くのコードエラーの原因になっていても、C++ は同様に適合します。 コードをより安全にするには、C++ 標準で、初期化リストで縮小変換が発生したときに診断メッセージが必要になります。 Visual C++ では、Visual Studio 2015 以降でサポートされている一様な初期化構文を使用すると、診断はコンパイラエラー C2397 になります。 Visual Studio 2013 でサポートされているリストまたは集計の初期化構文を使用すると、コンパイラは [コンパイラの警告 (レベル 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) を生成します。

変換された値の範囲がターゲットに適合する可能性があることがわかっている場合は、縮小変換に対応できます。 この場合、コンパイラよりも多くのことがわかっています。 縮小変換を意図的に行う場合は、静的なキャストを使用して意図を明確にしてください。 それ以外の場合、このエラーメッセージは、ほとんどの場合、コードにバグがあることを示しています。 この問題を解決するには、初期化するオブジェクトに、入力を処理するのに十分な大きさの型があることを確認します。

次の例では、C2397 を生成し、その修正方法の1つを示しています。

```
// C2397.cpp -- C++ narrowing conversion diagnostics
// Compile by using: cl /EHsc C2397.cpp
#include <vector>

struct S1 {
    int m1;
    double m2, m3;
};

void function_C2397(double d1) {
    char c1 { 127 };          // OK
    char c2 { 513 };          // error C2397

    std::vector<S1> vS1;
    vS1.push_back({ d1, 2, 3 }); // error C2397

    // Possible fix if you know d1 always fits in an int
    vS1.push_back({ static_cast<int>(d1), 2, 3 });
}
```
