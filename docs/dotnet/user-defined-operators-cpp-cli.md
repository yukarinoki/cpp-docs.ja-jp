---
title: ユーザー定義の演算子 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7cf5583b3ae896ea252d191fbeba86e202b56cef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="user-defined-operators-ccli"></a>ユーザー定義の演算子 (C++/CLI)
マネージ型の場合、ユーザー定義の演算子は、静的メンバーまたはインスタンス メンバーまたはグローバル スコープで許可されます。 ただし、Visual C 以外の言語で記述されたクライアントにメタデータを通じてアクセスできるは静的演算子のみです。  
  
 参照型でこれらのいずれかの静的ユーザー定義演算子のパラメーターの 1 つする必要があります。  
  
-   ハンドル (`type` ^) それを囲む型のインスタンスにします。  
  
-   参照型の間接参照 (`type`^ (& a) または型 ^ %)、それを囲む型のインスタンスへのハンドル。  
  
 値の型でこれらのいずれかの静的なユーザー定義演算子のパラメーターの 1 つする必要があります。  
  
-   外側の値の型と同じ型です。  
  
-   ポインター型の間接参照 (`type`^)、それを囲む型にします。  
  
-   参照型の間接参照 (`type`% または`type`&)、それを囲む型にします。  
  
-   参照型の間接参照 (`type`^ % または`type`^ (& a)) をハンドルします。  
  
 次の演算子を定義できます。  
  
|演算子|単項/バイナリ フォームしますか。|  
|--------------|--------------------------|  
|!|単項|  
|!=|2 項|  
|%|2 項|  
|&|単項演算子および 2 項演算子|  
|&&|2 項|  
|*|単項演算子および 2 項演算子|  
|+|単項演算子および 2 項演算子|  
|++|単項|  
|,|2 項|  
|-|単項演算子および 2 項演算子|  
|--|単項|  
|->|単項|  
|/|2 項|  
|<|2 項|  
|<<|2 項|  
|\<=|2 項|  
|=|2 項|  
|==|2 項|  
|>|2 項|  
|>=|2 項|  
|>>|2 項|  
|^|2 項|  
|False|単項|  
|true|単項|  
|&#124;|2 項|  
|&#124;&#124;|2 項|  
|~|単項|  
  
## <a name="example"></a>例  
  
```cpp  
// mcppv2_user-defined_operators.cpp  
// compile with: /clr  
using namespace System;  
public ref struct X {  
   X(int i) : m_i(i) {}  
   X() {}  
  
   int m_i;  
  
   // static, binary, user-defined operator  
   static X ^ operator + (X^ me, int i) {  
      return (gcnew X(me -> m_i + i));  
   }  
  
   // instance, binary, user-defined operator  
   X^ operator -( int i ) {  
      return gcnew X(this->m_i - i);  
   }  
  
   // instance, unary, user-defined pre-increment operator  
   X^ operator ++() {  
      return gcnew X(this->m_i++);  
   }  
  
   // instance, unary, user-defined post-increment operator  
   X^ operator ++(int i) {  
      return gcnew X(this->m_i++);  
   }  
  
   // static, unary user-defined pre- and post-increment operator  
   static X^ operator-- (X^ me) {  
      return (gcnew X(me -> m_i - 1));  
   }  
};  
  
int main() {  
   X ^hX = gcnew X(-5);  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX + 1;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX - (-1);  
   System::Console::WriteLine(hX -> m_i);  
  
   ++hX;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX++;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX--;  
   System::Console::WriteLine(hX -> m_i);  
  
   --hX;  
   System::Console::WriteLine(hX -> m_i);  
}  
```  
  
```Output  
-5  
-4  
-3  
-2  
-1  
-2  
-3  
```  
  
## <a name="example"></a>例  
 次の例は、使用する場合にのみ使用される演算子合成 **/clr**をコンパイルします。 複合演算子を使用する、バイナリ演算子の割り当てフォームを作成場合は 1 つが定義されていません、代入演算子の左側にあるが、CLR 型を持ちます。  
  
```cpp  
// mcppv2_user-defined_operators_2.cpp  
// compile with: /clr  
ref struct A {  
   A(int n) : m_n(n) {};  
   static A^ operator + (A^ r1, A^ r2) {  
      return gcnew A( r1->m_n + r2->m_n);  
   };  
   int m_n;  
};  
  
int main() {  
   A^ a1 = gcnew A(10);  
   A^ a2 = gcnew A(20);  
  
   a1 += a2;   // a1 = a1 + a2   += not defined in source  
   System::Console::WriteLine(a1->m_n);  
}  
```  
  
```Output  
30  
```  
  
## <a name="see-also"></a>関連項目  
 [クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)