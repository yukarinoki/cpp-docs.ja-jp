---
title: コンパイラの警告 (レベル 1) C4838
ms.date: 11/04/2016
f1_keywords:
- C4838
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
ms.openlocfilehash: dcb7062c751320a9f9c612b42caf6d018047d8d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532965"
---
# <a name="compiler-warning-level-1-c4838"></a>コンパイラの警告 (レベル 1) C4838

'type_1' から 'type_2' への変換で縮小変換が必要です。

集計またはリストの初期化を使用する場合、暗黙的な縮小変換が見つかりました。

C 言語での割り当てと初期化、暗黙的な縮小変換を許可して、C++ ダイヤ、場合でも、多くのコード エラーの原因は、予期しない縮小します。 コードを安全にするために、C++ 標準では、初期化リストで縮小変換が発生したときに、診断メッセージが必要です。 Visual C では、診断が[コンパイラ エラー C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md)以降 Visual Studio 2015 ではサポートされている均一な初期化構文を使用する場合。 コンパイラでは、リストまたは Visual Studio 2013 でサポートされている集約の初期化の構文を使用する場合は、C4838 を警告が生成されます。

縮小変換は、ターゲットで変換された値の有効範囲に収まることがわかっている場合に、できることができます。 この場合は、知っている、コンパイラがより。 意図的に縮小変換を行うと場合、静的キャストを使用して明示的なの開発者の意図をください。 それ以外の場合、この警告メッセージほとんどの場合を示します、コードにバグがあること。 初期化するオブジェクトの入力を処理するために十分な大きさである型であることを確認して修正できます。

次の例では、C4838 を生成し、その修正方法を示しています。

```
// C4838.cpp -- C++ narrowing conversion diagnostics
// Compile by using: cl /EHsc C4838.cpp

struct S1 {
    int m1;
    double m2, m3;
};

void function_C4838(double d1) {
    double ad[] = { 1, d1 }; // OK
    int ai[] = { 1, d1 };    // warning C4838
    S1 s11 = { 1, 2, d1 };   // OK
    S1 s12 { d1, 2, 3 };     // warning C4838
    S1 s13 { static_cast<int>(d1), 2, 3 }; // possible fix for C4838
}
```