---
title: コンパイラの警告 (レベル 1) C4743 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4743
dev_langs:
- C++
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84b4d5f3aa465257d7efcf9f95584612214165b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4743"></a>コンパイラの警告 (レベル 1) C4743
'*型*'別のサイズが、'*file1*'および'*file2*':*数*と*数*バイト  
  
 外部変数参照または 2 つのファイルで定義されているが、それらのファイルのさまざまな種類と、コンパイラは、ことを確認で変数のサイズ*file1*内の変数のサイズと異なります*file2*.  
  
 C++ の場合、この警告を出力できる場合に重要な場合は。 宣言が同じでない場合、それらの宣言には、仮想関数が含まれている場合に 2 つのファイルで同じ名前を持つ同じ型を宣言する場合、コンパイラは警告 C4744 仮想関数テーブルを生成できます。 同じ型の 2 つの異なるサイズの仮想関数テーブルがあるし、リンカーは、実行可能ファイルに組み込むことのいずれかを選択する必要がありますので、警告が発生します。  これが、間違った仮想関数を呼び出して、プログラムで発生することができることができます。  
  
 この警告を解決するのには、同じ種類の定義を使用するか、または異なる名前、型または変数を使用します。  
  
## <a name="example"></a>例  
 このサンプルには、型の 1 つの定義が含まれています。  
  
```  
// C4743a.cpp  
// compile with: /c  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
};  
  
void C::f1(void) {}  
void C::f2(void) {}  
void C::f3(void) {}  
C q;  
```  
  
## <a name="example"></a>例  
 次の例では、C4743 を生成します。  
  
```  
// C4743b.cpp  
// compile with: C4743a.cpp /W1 /GL /O2  
// C4743 expected  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
    virtual void f4(void);  
    virtual void f5(void);  
};  
  
void C::f4(void) {}  
void C::f5(void) {}  
C x;  
  
int main() {}   
```