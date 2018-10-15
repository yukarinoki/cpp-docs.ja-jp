---
title: 抽象 (C +/cli および C++/cli CX) |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
dev_langs:
- C++
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78a5b42de6b0ac54d060bb6369566aa446863289
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328195"
---
# <a name="abstract--ccli-and-ccx"></a>抽象 (C +/cli および C++/cli CX)

**抽象**キーワードは、いずれかを宣言します。

- 型を基本データ型として使用できるが、型自体はインスタンス化できない。

- 型のメンバー関数を派生型でのみ定義できる。

## <a name="all-platforms"></a>すべてのプラットフォーム

### <a name="syntax"></a>構文

*クラス宣言**クラス識別子***抽象 {}**

**仮想***戻り値の型**メンバー関数の識別子* **; () の概要**

### <a name="remarks"></a>Remarks

最初の例の構文では、abstract (抽象) にするクラスを宣言します。 *クラス宣言*コンポーネントは、いずれかのネイティブの C++ 宣言を指定できます (**クラス**または**構造体**)、または C++ の拡張機能の宣言 (**のrefクラス**または**ref 構造体**) 場合、`/ZW`または`/clr`コンパイラ オプションを指定します。

2 つ目の例の構文では、仮想メンバー関数を抽象として宣言します。 関数を抽象として宣言することは、純粋仮想関数として宣言することと同じです。 メンバー関数を抽象として宣言すると、外側のクラスも抽象として宣言されます。

**抽象**キーワードがネイティブとプラットフォーム固有のコードでサポートされている; は、コンパイルできます有無にかかわらず、`/ZW`または`/clr`コンパイラ オプション。

型が抽象の場合、コンパイル時に検出できます、`__is_abstract(type)`型の特徴です。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)します。

**抽象**キーワードは状況依存のオーバーライド指定子。 状況依存のキーワードの詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)します。 オーバーライド指定子の詳細については、次を参照してください。[方法: オーバーライド指定子を宣言ネイティブ コンパイルで](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)します。

## <a name="windows-runtime"></a>Windows ランタイム

詳細については、次を参照してください。 [Ref クラスと構造体](../cppcx/ref-classes-and-structs-c-cx.md)します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

次のコード例では、ため、エラーが生成されますクラス`X`がマークされている**抽象**します。

```cpp
// abstract_keyword.cpp
// compile with: /clr
ref class X abstract {
public:
   virtual void f() {}
};

int main() {
   X ^ MyX = gcnew X;   // C3622
}
```

次のコード例では、マークされているネイティブ クラスをインスタンス化ため、エラーが生成されます**抽象**します。 このエラーは `/clr` コンパイラ オプションの有無にかかわらず発生します。

```cpp
// abstract_keyword_2.cpp
class X abstract {
public:
   virtual void f() {}
};

int main() {
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'
                    // cannot be instantiated. See declaration of 'X'}
```

次のコード例では、ため、エラーが生成されます関数`f`定義が含まれていますが、設定されて**抽象**します。 この例の最後のステートメントで、抽象仮想関数を宣言することは純粋仮想関数を宣言することと同じであることを示しています。

```cpp
// abstract_keyword_3.cpp
// compile with: /clr
ref class X {
public:
   virtual void f() abstract {}   // C3634
   virtual void g() = 0 {}   // C3634
};
```

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)
