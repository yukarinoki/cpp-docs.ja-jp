---
title: コンパイラ エラー C2397 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- C2397
dev_langs:
- C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9d080450368618cc874de0ae96209e547847f8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196884"
---
# <a name="compiler-error-c2397"></a>コンパイラ エラー C2397
'type_1' から 'type_2' への変換で縮小変換が必要です。  
  
 均一な初期化を使用する場合、暗黙的な縮小変換が見つかりました。  
  
 割り当てと初期化、暗黙的な縮小変換により、C 言語および C++ ダイヤ、場合でも、多くのコード エラーの原因は、予期しない縮小します。 コードをより安全にするために、C++ 標準では、初期化リストで縮小変換が発生したときに、診断メッセージが必要です。 Visual c では、診断は、Visual Studio 2015 で均一な初期化のサポートされている構文の先頭を使用する場合にコンパイラ エラー C2397 です。 コンパイラは生成[コンパイラの警告 (レベル 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md)リストまたは Visual Studio 2013 でサポートされている集約の初期化の構文を使用する場合。  
  
 変換された値の有効範囲がターゲットに収まることがわかっている場合にも問題ありません縮小変換を指定できます。 この場合、わかってコンパイラよりも多くです。 縮小変換を意図的に作成する場合は、明示、意図静的キャストを使用します。 それ以外の場合、このエラー メッセージほとんどの場合を示します、コードにバグがあります。 初期化するオブジェクトが型の入力を処理するのに十分な大きさであることを確認することで修正できます。  
  
 次の例では、C2397 を生成し、その修正方法を示しています。  
  
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