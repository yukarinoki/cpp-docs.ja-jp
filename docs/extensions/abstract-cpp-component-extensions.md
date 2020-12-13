---
description: '詳細情報: abstract (C++/CLI および C++/CX)'
title: abstract (C++/CLI および C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
ms.openlocfilehash: e40d0d0c03bbf97b684d9e011f4bf614f6a44332
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177121"
---
# <a name="abstract--ccli-and-ccx"></a>abstract (C++/CLI および C++/CX)

**abstract** キーワードは、次のいずれかを宣言します。

- 型を基本データ型として使用できるが、型自体はインスタンス化できない。

- 型のメンバー関数を派生型でのみ定義できる。

## <a name="all-platforms"></a>すべてのプラットフォーム

### <a name="syntax"></a>構文

*class-declaration* *class-identifier* **abstract {}**

**`virtual`***戻り値の型* の *メンバー-関数識別子* **() abstract;**

### <a name="remarks"></a>解説

最初の例の構文では、abstract (抽象) にするクラスを宣言します。 *クラス宣言* コンポーネントには、ネイティブ c++ 宣言 (**`class` * * * * または)、または **`struct`**** コンパイラオプションが指定されている場合は c++ 拡張宣言 (ref クラス * * または **ref 構造体**) のいずれかを `/ZW` 指定でき `/clr` ます。

2 つ目の例の構文では、仮想メンバー関数を抽象として宣言します。 関数を抽象として宣言することは、純粋仮想関数として宣言することと同じです。 メンバー関数を抽象として宣言すると、外側のクラスも抽象として宣言されます。

**abstract** キーワードはネイティブ コードとプラットフォーム固有のコードでサポートされます。つまり、`/ZW` または `/clr` コンパイラ オプション を指定してもしなくてもコンパイルできます。

コンパイル時に、型の特徴が `__is_abstract(type)` である抽象型であるかどうかを検出できます。 詳細については、「[型の特徴のコンパイラ サポート](compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。

**abstract** キーワードは状況依存のオーバーライド指定子です。 状況依存キーワードの詳細については、「[状況依存キーワード](context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。 オーバーライド指定子の詳細については、「 [方法: ネイティブコンパイルでオーバーライド指定子を宣言](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)する」を参照してください。

## <a name="windows-runtime"></a>Windows ランタイム

詳細については、「[Ref クラスと構造体](../cppcx/ref-classes-and-structs-c-cx.md)」を参照してください。

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>例

次のコード例では、`X` クラスが **abstract** とマークされているため、エラーが生成されます。

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

次のコード例では、**abstract** とマークされたネイティブ クラスがインスタンス化されるため、エラーが生成されます。 このエラーは `/clr` コンパイラ オプションの有無にかかわらず発生します。

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

次のコード例では、関数 `f` に定義が含まれていますが、**abstract** とマークされているため、エラーが生成されます。 この例の最後のステートメントで、抽象仮想関数を宣言することは純粋仮想関数を宣言することと同じであることを示しています。

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

[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)
