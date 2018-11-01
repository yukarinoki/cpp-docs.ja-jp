---
title: ジェネリックとテンプレート (C +/cli CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generics [C++], vs. templates
- templates, C++
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
ms.openlocfilehash: 81b2812faa2fcb7acfdc272474d22039afa24655
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660049"
---
# <a name="generics-and-templates-ccli"></a>ジェネリックとテンプレート (C +/cli CLI)

ジェネリックとテンプレートは、パラメーター化された型のサポートを提供する両方の言語機能です。 ただし、それらが異なると、さまざまな用途があります。 このトピックでは、多くの違いの概要を示します。

詳細については、次を参照してください。 [Windows ランタイムおよびマネージ テンプレート](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)します。

## <a name="comparing-templates-and-generics"></a>テンプレートとジェネリックを比較します。

ジェネリックと C++ テンプレートの主な違い:

- ジェネリックは、実行時にそれらに置き換え、種類までジェネリックです。 実行時にまだパラメーター化された型ではないために、コンパイル時にテンプレートが特殊化します。

- 具体的には、共通言語ランタイムは、MSIL でジェネリックをサポートします。 ジェネリック型を含むアセンブリを参照するときに、ランタイムは、ジェネリック型については、ため、ジェネリック型の特定の種類を置き換えられますことができます。 テンプレートはこれに対し、通常の型にコンパイル時に解決して、結果の型が他のアセンブリで特殊化していない可能性があります。

- ジェネリックを専門に 2 つの異なるアセンブリと同じ型の引数には、同じ型。 テンプレートは、2 つの異なるアセンブリと同じ型引数は、ランタイムによって、さまざまな型であると見なされますの特殊化します。

- ジェネリックは、1 つのすべての参照型の引数が (これは、値の種類ごとに固有の実装を保持する値型の場合は true) に使用される実行可能コードとして生成されます。 JIT コンパイラでは、ジェネリックの概要を知っているし、型引数として使用される参照または値の型のコードを最適化することが。 テンプレートは、それぞれの特殊化用の個別のランタイム コードを生成します。

- ジェネリックできないようにする、非型テンプレート パラメーターなど`template <int i> C {}`します。 テンプレートを使用すると、それらが。

- ジェネリックでは、明示的な特殊化 (特定の種類のテンプレートのカスタム実装) は許可されません。 テンプレートの操作を行います。

- ジェネリックでは、部分的特殊化 (のカスタム実装をサブセットに対して型引数) は許可されません。 テンプレートの操作を行います。

- ジェネリックでは、ジェネリック型の基底クラスとして使用する型パラメーターは許可されません。 テンプレートの操作を行います。

- テンプレートがテンプレートのテンプレート パラメーターをサポート (例: `template<template<class T> class X> class MyClass`)、そうでないジェネリック。

## <a name="combining-templates-and-generics"></a>結合のテンプレートとジェネリック

ジェネリックの基本的な違いは、テンプレートとジェネリックに統合するアプリケーションを構築するための影響を与えます。 たとえば、テンプレート クラスをジェネリックとして他の言語には、そのテンプレートを公開する汎用ラッパーを作成したいがあるとします。 ジェネリックにとると、テンプレートは、コンパイル時に、その型パラメーターがある必要があるためには、テンプレートには、渡される型パラメーターを含めることはできませんが、ジェネリックでは、型パラメーターが実行時まで解決しません。 ジェネリックの内側のテンプレートの入れ子は機能しませんいずれかの実行時にインスタンス化することが任意のジェネリック型のコンパイル時に、テンプレートを展開する方法はありませんので。

## <a name="example"></a>例

### <a name="description"></a>説明

次の例では、テンプレートとジェネリックを一緒に使用する単純な例を示します。 この例では、テンプレート クラスは、ジェネリック型にを通じてそのパラメーターを渡します。 逆はできません。

C + ローカル テンプレート コードで、既存の汎用的な API をビルドするときに、この手法を使用できます/cli CLI アセンブリ、またはサポート b を実行するテンプレートの特定の機能を活用するジェネリック型にパラメーター化のレイヤーを追加する必要がある場合y のジェネリック。

### <a name="code"></a>コード

```cpp
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

```Output
F
```

## <a name="see-also"></a>関連項目

[ジェネリック](../windows/generics-cpp-component-extensions.md)