---
title: クラスと構造体 (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9863786e5e017b69217f984e3aa6d1db597e74d3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864916"
---
# <a name="classes-and-structs--c-component-extensions"></a>クラスと構造体 (C++ コンポーネント拡張)
クラスまたは構造体の宣言が*オブジェクトの有効期間*自動的に管理されます。 Visual C++ では、オブジェクトがアクセス不能になるかスコープ外になると、そのオブジェクトに割り当てられているメモリを自動的に破棄します。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 **構文**  
  
```  
  
      class_access  
      ref class  
      name  
      modifier :  inherit_accessbase_type {};  
class_accessref structnamemodifier :  inherit_accessbase_type {};  
class_accessvalue classnamemodifier :  inherit_accessbase_type {};  
class_accessvalue structnamemodifier :  inherit_accessbase_type {};  
  
```  
  
 **パラメーター**  
  
 *class_access* (省略可能)  
 アセンブリの外部にあるクラスまたは構造体のアクセシビリティ。 指定できる値は**パブリック**と`private`(`private`既定値です)。 入れ子になったクラスまたは構造体を持つことはできません、 *class_access*指定子。  
  
 *name*  
 クラスまたは構造体の名前。  
  
 *修飾子*(省略可能)  
 [抽象](../windows/abstract-cpp-component-extensions.md)と[シール](../windows/sealed-cpp-component-extensions.md)は有効な修飾子。  
  
 *inherit_access* (省略可能)  
 `base_type` のアクセシビリティ。 許可されているアクセシビリティは `public` のみです (既定値は `public`)。  
  
 *base_type* (省略可能)  
 基本型。 ただし、値型を基本型として使用することはできません。  
  
 詳細については、Windows ランタイムと共通言語 Runtimesections で、このパラメーターの言語固有の説明を参照してください。  
  
 **解説**  
  
 宣言されたオブジェクトの既定のメンバー アクセシビリティ**ref クラス**または**値クラス**は`private`します。 宣言されたオブジェクトの既定のメンバー アクセシビリティと**ref 構造体**または**値構造体**は`public`します。  
  
 基本クラスの仮想関数が明示的にオーバーライドされる必要があります、参照型を別の参照型から継承するとき (で[オーバーライド](../windows/override-cpp-component-extensions.md)) または非表示 (で[new (の新しいスロット vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md))。 派生クラスの関数は、明示的に `virtual` と指定する必要があります。  
  
 型がであるかどうかは、コンパイル時に検出するために、`ref class`または`ref struct`、または`value class`または`value struct`を使用して`__is_ref_class (type)`、 `__is_value_class (type)`、または`__is_simple_value_class (type)`です。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)です。  
  
 クラスと構造体の詳細については、以下のページを参照してください。  
  
-   [クラスと構造体をインスタンス化します。](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)  
  
 
  
-   [参照型の C++ スタック セマンティクス](../dotnet/cpp-stack-semantics-for-reference-types.md)  
  
-   [クラス、構造、および共用体](../cpp/classes-and-structs-cpp.md)  
  
-   [デストラクターとファイナライザーを使用する方法: を定義およびクラスと構造体を使用 (C + + CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)  
  
-   [ユーザー定義の演算子 (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)  
  
-   [ユーザー定義変換 (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)  
  
-   [方法: ネイティブ クラスを C# で使用できるようにラップする](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
-   [ジェネリック クラス (C++/CLI)](../windows/generic-classes-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 **解説**  
  
 参照してください[Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)と[値クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699861.aspx)です。  
  
 **パラメーター**  
  
 *base_type* (省略可能)  
 基本型。 `ref class` または `ref struct` は、0 個以上のインターフェイスおよび 0 個または 1 個の `ref` 型から継承できます。 `value class` または `value struct` は、0 個以上のインターフェイスからのみ継承できます。  
  
 `ref class` キーワードまたは `ref struct` キーワードを使用してオブジェクトを宣言する場合、オブジェクトに対するハンドル (オブジェクトへの参照カウンター ポインター) を使用してオブジェクトにアクセスします。 宣言された変数がスコープ外になると、コンパイラは自動的に基になるオブジェクトを削除します。 そのオブジェクトが呼び出しのパラメーターとして使用されているか、変数に格納されている場合は、実際にそのオブジェクトのハンドルが渡されるか格納されます。  
  
 `value class` キーワードまたは `value struct` キーワードを使用してオブジェクトを宣言すると、宣言されたオブジェクトのオブジェクト有効期間は監視されません。 このオブジェクトは、C++ の他の標準のクラスや構造体と同様です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **解説**  
  
 次の表に示すように、構文の違い、**すべてのランタイム**に C + 固有のセクション + CLI です。  
  
 **パラメーター**  
  
 *base_type* (省略可能)  
 基本型。 `ref class` または `ref struct` は、0 個以上のマネージ インターフェイスおよび 0 個または 1 個の ref 型から継承できます。 `value class` または `value struct` は、0 個以上のマネージ インターフェイスからのみ継承できます。  
  
 `ref class` と `ref struct` キーワードを指定すると、コンパイラはクラスまたは構造体をヒープに割り当てます。 そのオブジェクトが呼び出しのパラメーターとして使用されているか、変数に格納されている場合は、実際にそのオブジェクトへの参照が渡されるか格納されます。  
  
 `value class`と`value struct`キーワード、コンパイラは、割り当てられているクラスまたは構造体の値が関数に渡されるか、メンバーに格納されていること。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)