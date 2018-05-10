---
title: コンパイラ エラー C2146 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2146
dev_langs:
- C++
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73367284a8c13316d344a4cff87ccae4ee7c832d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2146"></a>コンパイラ エラー C2146
構文エラー: 識別子 'identifier' の前に ' token' がありません  
  
 コンパイラの想定`token`と見つかる`identifier`代わりにします。  以下の原因が考えられます。  
  
1.  スペルまたは大文字と小文字のエラーです。  
  
2.  識別子の宣言で型指定子がありません。  
  
 このエラーは、入力ミスによって発生する可能性があります。 エラー [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md)通常このエラーの前にします。  
  
## <a name="example"></a>例  
 次の例では、C2146 を生成します。  
  
```  
// C2146.cpp  
class CDeclaredClass {};  
  
class CMyClass {  
   CUndeclared m_myClass;   // C2146  
   CDeclaredClass m_myClass2;   // OK  
};  
  
int main() {  
   int x;  
   int t x;   // C2146 : missing semicolon before 'x'  
}  
```  
  
## <a name="example"></a>例  
 このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成することもできます。 見つからない`typename`キーワード。  
  
 次の例では、Visual Studio .NET 2002 でコンパイルは、Visual Studio .NET 2003 では失敗します。  
  
```  
// C2146b.cpp  
// compile with: /c  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
  
template <typename T>  
X<T>::Y func() { }   // C2146  
  
// OK  
template <typename T>  
typename X<T>::Y func() { }  
```  
  
## <a name="example"></a>例  
 Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として、このエラーが表示されます。 明示的な特殊化が不要になったプライマリ テンプレートからテンプレート パラメーターを検索します。  
  
 使用`T`プライマリ テンプレートからは、明示的な特殊化では許可されませんが。 コードを Visual Studio .NET 2003 および Visual Studio .NET のバージョンの Visual C で有効にするには、特殊化のテンプレート パラメーターのすべてのインスタンスを明示的に特殊な種類に置き換えます。  
  
 次の例では、Visual Studio .NET でコンパイルは、Visual Studio .NET 2003 では失敗します。  
  
```  
// C2146_c.cpp  
// compile with: /c  
template <class T>   
struct S;  
  
template <>   
struct S<int> {  
   T m_t;   // C2146  
   int m_t2;   // OK  
};  
```