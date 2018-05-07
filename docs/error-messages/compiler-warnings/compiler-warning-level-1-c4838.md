---
title: コンパイラの警告 (レベル 1) C4838 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- C4838
dev_langs:
- C++
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1327ed8869c17701c6aa0a6ce2e3479b6109b8cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4838"></a>コンパイラの警告 (レベル 1) C4838
'type_1' から 'type_2' への変換で縮小変換が必要です。  
  
 集計またはリストの初期化を使用する場合、暗黙的な縮小変換が見つかりました。  
  
 割り当てと初期化、暗黙的な縮小変換により、C 言語および C++ ダイヤ、場合でも、多くのコード エラーの原因は、予期しない縮小します。 コードをより安全にするために、C++ 標準では、初期化リストで縮小変換が発生したときに、診断メッセージが必要です。 Visual c では、診断が[コンパイラ エラー C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) Visual Studio 2015 以降でサポートされている均一な初期化構文を使用する場合。 コンパイラは、リストまたは Visual Studio 2013 でサポートされている集約の初期化の構文を使用する場合は、C4838 を警告を生成します。  
  
 変換された値の有効範囲がターゲットに収まることがわかっている場合にも問題ありません縮小変換を指定できます。 この場合、わかってコンパイラよりも多くです。 縮小変換を意図的に作成する場合は、明示、意図静的キャストを使用します。 それ以外の場合、この警告メッセージほとんどの場合を示します、コード内のバグがあるか。 初期化するオブジェクトが型の入力を処理するのに十分な大きさであることを確認することで修正できます。  
  
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