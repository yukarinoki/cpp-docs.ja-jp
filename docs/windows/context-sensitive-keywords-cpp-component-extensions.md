---
title: 状況依存のキーワード (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal_CPP
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ceea3242087d89b511f6309003efe38d155735d2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871524"
---
# <a name="context-sensitive-keywords--c-component-extensions"></a>状況依存のキーワード (C++ コンポーネント拡張)
*状況依存のキーワード*は特定のコンテキストでのみ認識される言語要素です。 特定のコンテキスト以外では、状況依存のキーワードをユーザー定義の記号として使用することができます。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 **解説**  
  
 以下は、状況依存のキーワードの一覧です。  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [event](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each、in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`   
  
-   [リテラル](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [プロパティ](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where` (一部の[ジェネリック](../windows/generics-cpp-component-extensions.md))  
  
 読みやすくするため、ユーザー定義シンボルとしての状況依存のキーワードの使用を制限することがあります。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 **解説**  
  
 (この機能のプラットフォーム固有の解説はありません。)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **解説**  
  
 (この機能のプラットフォーム固有の解説はありません。)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次のコード例は、適切なコンテキストでは、`property` 状況依存キーワードを使用してプロパティと変数を定義できることを示しています。  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **出力**  
  
```Output  
100  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)