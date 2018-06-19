---
title: ジェネリックとテンプレート (Visual C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generics [C++], vs. templates
- templates, C++
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d6dc0a64c5d225f6e80a21dc008e5a2486ad3d9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878906"
---
# <a name="generics-and-templates-visual-c"></a>ジェネリックとテンプレート (Visual C++)
ジェネリックとテンプレートは、両方のパラメーター化された型をサポートする言語の機能です。 ただし、それらが異なり、さまざまな用途があります。 このトピックでは、多くの違いの概要を示します。  
  
 詳細については、次を参照してください。 [Windows ランタイムおよびマネージ テンプレート](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)です。  
  
## <a name="comparing-templates-and-generics"></a>比較するテンプレートとジェネリック  
 ジェネリックと C++ テンプレートの主な違いは:  
  
-   ジェネリックは一般的なまで、実行時にそれらの型に置き換えられます。 実行時にまだパラメーター化された型ではないために、テンプレートはコンパイル時に特殊化します。  
  
-   具体的には、共通言語ランタイムは、MSIL でジェネリックをサポートします。 ジェネリック型を含むアセンブリを参照するときに、ランタイムは、ジェネリックの概要認識している、ためのジェネリック型の特定の種類を置き換えられることができます。 テンプレートはこれに対し、通常の型にコンパイル時に解決して、結果の型を他のアセンブリの特化することはできません。  
  
-   2 つのアセンブリを専門にジェネリックと同じ型の引数が同じ型です。 テンプレートは、2 つの異なるアセンブリと同じ型引数は、ランタイムによって、異なる型であると見なされますの特殊化です。  
  
-   ジェネリックは、1 つのすべての参照型引数 (これはない値の型ごとに一意の実装である必要が値型の場合は true) に使用される実行可能コードとして生成されます。 JIT コンパイラでは、ジェネリックの概要を知っているし、型引数として使用される参照または値の型のコードを最適化することがします。 テンプレートは、それぞれの特殊化の個別のランタイム コードを生成します。  
  
-   ジェネリック許可しない非型テンプレート パラメーターなど`template <int i> C {}`です。 テンプレートは、それらを使用します。  
  
-   ジェネリックでは、明示的な特殊化 (つまり、特定の種類のテンプレートのカスタム実装) は許可されません。 テンプレートにしないでください。  
  
-   ジェネリックでは、部分的特殊化 (カスタム実装サブセットに対して型引数の型) は許可されません。 テンプレートにしないでください。  
  
-   ジェネリックでは、型パラメーター、ジェネリック型の基底クラスとして使用するのには許可されません。 テンプレートにしないでください。  
  
-   テンプレートがテンプレートのテンプレート パラメーターをサポート (例: `template<template<class T> class X> class MyClass`)、そうでないジェネリックです。  
  
## <a name="combining-templates-and-generics"></a>結合のテンプレートとジェネリック  
  
-   ジェネリックの基本的な違いは、テンプレートとジェネリックに統合するアプリケーションを構築するための影響を与えます。 たとえば、テンプレート クラスをジェネリックとして他の言語には、そのテンプレートを公開する汎用ラッパーを作成するがあるとします。 ジェネリック take テンプレートは、コンパイル時に、その型パラメーターがある必要があるためには、テンプレートにも、渡される型パラメーターを持つことはできませんが、ジェネリックは、実行時まで、型パラメーターを解決しません。 ジェネリック型の内側のテンプレートを入れ子ために、機能しませんいずれかの実行時にインスタンス化することが任意のジェネリック型のコンパイル時に、テンプレートを展開する方法はありません。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例では、テンプレートとジェネリックを一緒に使用する簡単な例を示します。 この例では、テンプレート クラスは、ジェネリック型にを通じてそのパラメーターを渡します。 逆はできません。  
  
 既存ジェネリック API は、Visual C のアセンブリのローカル テンプレート コードが上に構築するとき、またはテンプレートいない supporte の特定の機能を活用するために、ジェネリック型にパラメーター化の強化を追加する必要がある場合、この表現方法を使用する可能性があります。ジェネリックによって d.  
  
### <a name="code"></a>コード  
  
```  
// templates_and_generics.cpp  
// compile with: /clr  
using namespace System;  
  
generic <class ItemType>  
ref class MyGeneric {  
   ItemType m_item;  
  
public:  
   MyGeneric(ItemType item) : m_item(item) {}  
   void F() {   
      Console::WriteLine("F");   
   }  
};  
  
template <class T>  
public ref class MyRef {  
MyGeneric<T>^ ig;  
  
public:  
   MyRef(T t) {  
      ig = gcnew MyGeneric<T>(t);  
      ig->F();  
    }      
};  
  
int main() {  
   // instantiate the template  
   MyRef<int>^ mref = gcnew MyRef<int>(11);  
}  
```  
  
### <a name="output"></a>出力  
  
```  
F  
```  
  
## <a name="see-also"></a>関連項目  
 [ジェネリック](../windows/generics-cpp-component-extensions.md)