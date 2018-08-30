---
title: クラスと構造体 (C++ コンポーネント拡張) |Microsoft Docs
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
ms.openlocfilehash: e29b141ff89a37cee59f55624d7fecadbe6acc4c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215871"
---
# <a name="classes-and-structs--c-component-extensions"></a>クラスと構造体 (C++ コンポーネント拡張)

クラスまたは構造体の宣言が*オブジェクトの有効期間*自動的に管理されます。 Visual C++ では、オブジェクトがアクセス不能になるかスコープ外になると、そのオブジェクトに割り当てられているメモリを自動的に破棄します。

## <a name="all-runtimes"></a>すべてのランタイム

### <a name="syntax"></a>構文

```cpp
      class_access
      ref class
      name
      modifier :  inherit_accessbase_type {};
class_accessref structnamemodifier :  inherit_accessbase_type {};
class_accessvalue classnamemodifier :  inherit_accessbase_type {};
class_accessvalue structnamemodifier :  inherit_accessbase_type {};

```

### <a name="parameters"></a>パラメーター

*class_access* (省略可能)  
アセンブリの外部にあるクラスまたは構造体のアクセシビリティ。 指定できる値は**パブリック**と**プライベート**(**プライベート**は既定です)。 入れ子になったクラスまたは構造体を含めることはできません、 *class_access*指定子。

*name*  
クラスまたは構造体の名前。

*修飾子*(省略可能)  
[抽象](../windows/abstract-cpp-component-extensions.md)と[シール](../windows/sealed-cpp-component-extensions.md)は有効な修飾子。

*inherit_access* (省略可能)  
ユーザー補助*base_type*します。 のみ許可されているアクセシビリティが**パブリック**(**パブリック**は既定です)。

*base_type* (省略可能)  
基本型。 ただし、値型を基本型として使用することはできません。

詳細については、Windows ランタイムと共通言語 Runtimesections で、このパラメーターの言語固有の説明を参照してください。

### <a name="remarks"></a>Remarks

宣言されたオブジェクトの既定のメンバー アクセシビリティ**ref クラス**または**値クラス**は**プライベート**します。 宣言されたオブジェクトの既定のメンバー アクセシビリティと**ref 構造体**または**値構造体**は**パブリック**します。

基底クラスで仮想関数が明示的にオーバーライドされる必要があります、参照型を別の参照型から継承するとき (で[オーバーライド](../windows/override-cpp-component-extensions.md)) または非表示 (で[new (新規のスロット vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md))。 派生クラスの関数も明示的にマークするとして**仮想**します。

型があるかどうかは、コンパイル時に検出するために、 **ref クラス**または**ref 構造体**、または**値クラス**または**値構造体**を使用して、 `__is_ref_class (type)`、`__is_value_class (type)`、または`__is_simple_value_class (type)`します。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)します。

クラスと構造体の詳細については、以下のページを参照してください。

- [クラスと構造体をインスタンス化します。](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)

- [参照型の C++ スタック セマンティクス](../dotnet/cpp-stack-semantics-for-reference-types.md)

- [クラス、構造、および共用体](../cpp/classes-and-structs-cpp.md)

- [方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C +/cli CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)

- [ユーザー定義の演算子 (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)

- [ユーザー定義変換 (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)

- [方法: ネイティブ クラスを C# で使用できるようにラップする](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

- [ジェネリック クラス (C++/CLI)](../windows/generic-classes-cpp-cli.md)

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="remarks"></a>Remarks

参照してください[Ref クラスと構造体](../cppcx/ref-classes-and-structs-c-cx.md)と[値クラスと構造体](https://msdn.microsoft.com/library/windows/apps/hh699861.aspx)します。

### <a name="parameters"></a>パラメーター

*base_type* (省略可能)  
基本型。 A **ref クラス**または**ref 構造体**0 個以上のインターフェイスと 0 または 1 個から継承できます**ref**型。 A**値クラス**または**値構造体**0 個以上のインターフェイスからのみ継承できます。

使用してオブジェクトを宣言するときに、 **ref クラス**または**ref 構造体**キーワードによって、オブジェクトにアクセス オブジェクトを識別するハンドル。 つまり、オブジェクトへの参照カウンター ポインター。 宣言された変数がスコープ外になると、コンパイラは自動的に基になるオブジェクトを削除します。 そのオブジェクトが呼び出しのパラメーターとして使用されているか、変数に格納されている場合は、実際にそのオブジェクトのハンドルが渡されるか格納されます。

使用してオブジェクトを宣言するときに、**値クラス**または**値構造体**キーワード、宣言されたオブジェクトのオブジェクトの有効期間は監視対象外です。 このオブジェクトは、C++ の他の標準のクラスや構造体と同様です。

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>Remarks

次の表に示すように、構文の違い、**すべてのランタイム**に C + 固有のセクション/cli CLI。

### <a name="parameters"></a>パラメーター

*base_type* (省略可能)  
基本型。 A **ref クラス**または**ref 構造体**0 から継承できますまたは複数の管理対象インターフェイスおよび 0 個または 1 つの ref 型。 A**値クラス**または**値構造体**0 個以上のマネージ インターフェイスからのみ継承できます。

**Ref クラス**と**ref 構造体**キーワードをクラスまたは構造体は、ヒープに割り当てられるように、コンパイラに指示します。 そのオブジェクトが呼び出しのパラメーターとして使用されているか、変数に格納されている場合は、実際にそのオブジェクトへの参照が渡されるか格納されます。

**値クラス**と**値構造体**割り当てられているクラスまたは構造体の値が関数に渡されるか、メンバーに格納されていることのキーワードがコンパイラに指示します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

## <a name="see-also"></a>関連項目

[ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)