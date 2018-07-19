---
title: リテラル (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
dev_langs:
- C++
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6871f02a1c37def05b6450e7ffad18f6fa45b461
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879358"
---
# <a name="literal-c-component-extensions"></a>リテラル (C++ コンポーネント拡張)
としてマークされている変数 (データ メンバー)`literal`で、 **/clr**コンパイルに等しいネイティブな`static const`変数。  
  
## <a name="all-platforms"></a>すべてのプラットフォーム  
 **解説**  
  
 (この言語機能にはランタイムに適用される特記事項がありません。)  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 **解説**  
  
 (この言語機能には Windows ランタイムのみに適用される特記事項がありません。)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
  
## <a name="remarks"></a>コメント  
 としてマークされているデータ メンバー`literal`宣言時に初期化する必要があります、値が定数の整数型、列挙型、または文字列型にする必要があります。 初期化式の型から const static データ メンバーの種類への変換では、ユーザー定義の変換は必要ありません必要があります。  
  
 実行時以外にリテラル フィールドに対して割り当てられたメモリがありません。コンパイラは、クラスのメタデータにのみその値を挿入します。  
  
 変数のマーク`static const`は他のコンパイラをメタデータに使用できません。  
  
 詳細については、次を参照してください。[静的](../cpp/storage-classes-cpp.md)と[const](../cpp/const-cpp.md)です。  
  
 `literal` は状況依存のキーワードです。 参照してください[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例、`literal`変数意味`static`です。  
  
```  
// mcppv2_literal.cpp  
// compile with: /clr  
ref struct X {  
   literal int i = 4;  
};  
  
int main() {  
   int value = X::i;  
}  
```  
  
## <a name="example"></a>例  
 次の例は、メタデータには、リテラルの影響を示しています。  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 メタデータの違いに注意してください`sc`と`lit`:`modopt`にディレクティブが適用される`sc`、他のコンパイラが無視できることを意味します。  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## <a name="example"></a>例  
 C# で作成されたため、次の例は前の例で作成されたメタデータを参照しての影響を示します`literal`と`static const`変数。  
  
```  
// mcppv2_literal3.cs  
// compile with: /reference:mcppv2_literal2.dll  
// A C# program  
class B {  
   public static void Main() {  
      // OK  
      System.Console.WriteLine(A.lit);  
      System.Console.WriteLine(A.sc);  
  
      // C# does not enforce C++ const  
      A.sc = 9;  
      System.Console.WriteLine(A.sc);  
  
      // C# enforces const for a literal  
      A.lit = 9;   // CS0131  
  
      // you can assign a C++ literal variable to a C# const variable  
      const int i = A.lit;  
      System.Console.WriteLine(i);  
  
      // but you cannot assign a C++ static const variable  
      // to a C# const variable  
      const int j = A.sc;   // CS0133  
      System.Console.WriteLine(j);  
   }  
}  
```  
  
## <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)