---
title: Windows ランタイムおよびマネージ テンプレート (C +/cli および C++/cli CX) |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b83aa54b9f9697fddbefc6da29e7cf99d497cc12
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328299"
---
# <a name="windows-runtime-and-managed-templates-ccli-and-ccx"></a>Windows ランタイムおよびマネージ テンプレート (C +/cli および C++/cli CX)

テンプレートは、Windows ランタイムまたは共通言語ランタイム型では、プロトタイプを定義することを有効にして、別のテンプレート型パラメーターを使用してその型のバリエーションをインスタンス化し。

## <a name="all-runtimes"></a>すべてのランタイム

値または参照型からテンプレートを作成することができます。  値または参照型を作成する方法の詳細については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)します。

標準の C++ クラス テンプレートの詳細については、次を参照してください。[クラス テンプレート](../cpp/class-templates.md)します。

## <a name="windows-runtime"></a>Windows ランタイム

(この言語機能には Windows ランタイムのみに適用される特記事項がありません。)

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

次のコード例で説明するマネージ型をクラス テンプレートを作成するのには制限があります。

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

マネージ型テンプレート パラメーターを使用してジェネリック型のインスタンスを作成することができますが、ジェネリック型テンプレート パラメーターを持つ管理対象のテンプレートをインスタンス化することはできません。 これは、ジェネリック型は実行時に解決されるためです。 詳細については、次を参照してください。[ジェネリックとテンプレート (C +/cli CLI)](../windows/generics-and-templates-visual-cpp.md)します。

```cpp
// managed_templates.cpp
// compile with: /clr /c

generic<class T>
ref class R;

template<class T>
ref class Z {
   // Instantiate a generic with a template parameter.
   R<T>^ r;    // OK
};

generic<class T>
ref class R {
   // Cannot instantiate a template with a generic parameter.
   Z<T>^ z;   // C3231
};
```

管理対象のテンプレートでは、ジェネリック型または関数を入れ子にすることはできません。

```cpp
// managed_templates_2.cpp
// compile with: /clr /c

template<class T> public ref class R {
   generic<class T> ref class W {};   // C2959
};
```

C + を使用して参照されたアセンブリで定義されているテンプレートにアクセスすることはできません/cli が CLI 言語の構文は、リフレクションを使用できます。 テンプレートがインスタンス化されない場合、メタデータでは発生しません。 テンプレートがインスタンス化される場合は、参照されているメンバー関数のみがメタデータに表示されます。

```cpp
// managed_templates_3.cpp
// compile with: /clr

// Will not appear in metadata.
template<class T> public ref class A {};

// Will appear in metadata as a specialized type.
template<class T> public ref class R {
public:
   // Test is referenced, will appear in metadata
   void Test() {}

   // Test2 is not referenced, will not appear in metadata
   void Test2() {}
};

// Will appear in metadata.
generic<class T> public ref class G { };

public ref class S { };

int main() {
   R<int>^ r = gcnew R<int>;
   r->Test();
}
```

部分的特殊化またはクラス テンプレートの明示的な特殊化クラスのマネージ修飾子を変更できます。

```cpp
// managed_templates_4.cpp
// compile with: /clr /c

// class template
// ref class
template <class T>
ref class A {};

// partial template specialization
// value type
template <class T>
value class A <T *> {};

// partial template specialization
// interface
template <class T>
interface class A<T%> {};

// explicit template specialization
// native class
template <>
class A <int> {};
```

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)