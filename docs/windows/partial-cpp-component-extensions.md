---
title: partial (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- partial_CPP
dev_langs:
- C++
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 71c0fc9739e7ef8e1e68c5678ce56fcec4a250c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="partial--c-component-extensions"></a>Partial (C++ コンポーネント拡張)
`partial`キーワードとは独立して、および異なるファイル内に作成される同じ ref クラスのさまざまな部分を有効にします。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 (この言語機能は、Windows ランタイムのみに適用されます)。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 2 つの部分定義を持つ ref クラスの`partial`の定義の最初に出現するキーワードが適用され、これは、通常、自動生成されたコードでヒューマン コードの作成者が非常に多くの場合、キーワードを使用しないようにします。 後続部分のすべての定義、クラス、省略、`partial`から修飾子、*クラス キー*キーワードとクラスの識別子。 以前に定義した ref クラスとクラス識別子がない、コンパイラが検出した場合`partial`キーワード、ref クラス定義を複数の定義を 1 つの部分のすべてを内部的に結合します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
partial class-key identifier {  
   /* The first part of the partial class definition. 
      This is typically auto-generated */  
}  
// ...  
class-key identifier {  
   /* The subsequent part(s) of the class definition. The same 
      identifier is specified, but the "partial" keyword is omitted. */  
}  
```  
  
### <a name="parameters"></a>パラメーター  
 *クラス キー*  
 クラスまたは Windows ランタイムでサポートされている構造体を宣言するキーワードです。 いずれか`ref class`、 `value class`、 `ref struct`、または`value struct`です。  
  
 *identifier*  
 定義済みの型の名前。  
  
### <a name="remarks"></a>コメント  
 部分クラスは、1 つのファイル サービスおよび自動コード生成ソフトウェア内のクラス定義の 1 つの部分を変更するシナリオをサポートしています: XAML デザイナーなど-別のファイルで同じクラスにコードを変更します。 部分クラスを使用するには、コードを上書きしてから、自動コード ジェネレーターができなくなります。 Visual Studio プロジェクトでは、生成されたファイルに `partial` 修飾子が自動的に適用されます。  
  
 内容: 2 つの例外を除き、部分クラス定義含めることができる場合、完全クラス定義を含む可能性のあるもの、`partial`キーワードを省略します。 ただし、クラスのアクセシビリティを指定することはできません (たとえば、 `public partial class X { ... };`)、または`declspec`です。  
  
 アクセス指定子の部分クラス定義で使用される*識別子*、既定のユーザー補助機能の後続の部分的または完全クラス定義には影響しません*識別子*です。 静的データ メンバーのインライン定義が許可されます。  
  
 宣言: クラスの部分定義*識別子*という名前のみ説明*識別子*が*識別子*クラスが必要な方法では使用できません定義です。 名前*識別子*のサイズを知るには使用できません*識別子*、または基底クラスまたはのメンバーを使用する*識別子*まで、コンパイラでの完全定義が発生した後*識別子*です。  
  
 数字と順序。 0 個以上の部分クラス定義をできる*識別子*です。 すべての部分クラス定義*識別子*の 1 つの完全定義の前に構文的にする必要があります*識別子*(です完全な定義がある場合、それ以外の場合、クラス以外は使用できません、。事前宣言) の事前宣言の前をする必要がありますが、*識別子*です。 すべてのクラス キーが一致する必要があります。  
  
 完全な定義: クラスの完全定義の点で*識別子*、動作は同じとしての定義*識別子*すべて基底クラスやメンバーなどの順序で宣言されています。発生しましたがおよび、部分クラスで定義されています。  
  
 テンプレート: 部分クラスは、テンプレートになることはできません。  
  
 ジェネリック: 完全定義がジェネリックにする場合、部分クラスでジェネリック型を指定できます。 すべての部分と完全クラスには正確に同じジェネリック パラメーター、仮パラメーター名を含む必要があります。  
  
 使用する方法についての詳細、`partial`キーワードを参照してください[部分クラス (C + + CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 (この言語機能は適用されませんを共通言語ランタイム。)  
  
## <a name="see-also"></a>関連項目  
 [部分クラス (C + + CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)