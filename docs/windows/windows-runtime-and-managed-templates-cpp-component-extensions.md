---
title: Windows ランタイムおよびマネージ テンプレート (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: e9053b101428ac26e96446d9c6756ec5de35e06c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="windows-runtime-and-managed-templates-c-component-extensions"></a>Windows ランタイムおよびマネージ テンプレート (C++ コンポーネント拡張)
テンプレートは、使用すると、Windows ランタイムまたは共通言語ランタイムの型のプロトタイプを定義し、別のテンプレート型パラメーターを使用してその型のバリエーションをインスタンス化しできます。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 値または参照型からテンプレートを作成することができます。  値または参照型の作成の詳細については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
 標準の C++ クラス テンプレートの詳細については、次を参照してください。[クラス テンプレート](../cpp/class-templates.md)です。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 (この言語機能には Windows ランタイムのみに適用される特記事項がありません。)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 マネージ型は、次のコード例に示されている場合は、クラス テンプレートを作成するのには、制限があります。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 マネージ型テンプレート パラメーターを持つジェネリック型のインスタンスを作成できますが、ジェネリック型テンプレート パラメーターを持つマネージ テンプレートをインスタンス化することはできません。  これは、ジェネリック型は実行時に解決されるためです。  詳細については、次を参照してください。[ジェネリックとテンプレート (Visual c)](../windows/generics-and-templates-visual-cpp.md)です。  
  
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
  
 **例**  
  
 マネージ テンプレートでは、ジェネリック型または関数を入れ子にすることはできません。  
  
```cpp  
// managed_templates_2.cpp  
// compile with: /clr /c  
  
template<class T> public ref class R {  
   generic<class T> ref class W {};   // C2959  
};  
```  
  
 **例**  
  
 C + を使用して参照されたアセンブリで定義されているテンプレートにアクセスすることはできませんまたは CLI 言語の構文は、リフレクションを使用できます。  テンプレートがインスタンス化されない場合、メタデータでない生成されます。  テンプレートがインスタンス化される場合は、参照されたメンバー関数のみがメタデータに表示されます。  
  
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
  
 **例**  
  
 部分的特殊化またはクラス テンプレートの明示的な特殊化でクラスのマネージ修飾子を変更することができます。  
  
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
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)