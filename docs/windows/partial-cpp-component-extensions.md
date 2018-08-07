---
title: partial (C++ コンポーネント拡張) |Microsoft Docs
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
ms.openlocfilehash: 82bd3baab698e013b3bfe506877bbdbf0021794b
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605933"
---
# <a name="partial--c-component-extensions"></a>Partial (C++ コンポーネント拡張)
**部分**キーワードは、同じ ref クラスとは独立して、複数のファイルが作成のさまざまな部分を使用します。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 (この言語機能は、Windows ランタイムにのみ適用されます)。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 2 つの部分定義を持つ ref クラスの**部分**キーワードが最初に見つかった位置の定義に適用され、これは、通常、自動生成されたコードで人間のプログラマが非常に多くの場合、キーワードを使用しないようにします。 後続部分のすべての定義、クラス、省略、**部分**から修飾子、*クラス キー*キーワードとクラス識別子。 以前に定義した ref クラスとクラス識別子は、コンパイラが検出した場合**部分**キーワード、1 つの定義には、ref クラスの定義の部分のすべてを内部的に結合します。  
  
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
 クラスまたは Windows ランタイムでサポートされている構造体を宣言するキーワード。 いずれか**ref クラス**、**値クラス**、 **ref 構造体**、または**値構造体**します。  
  
 *identifier*  
 定義された型の名前。  
  
### <a name="remarks"></a>Remarks  
 部分クラスは、1 つのファイルと自動のコードを生成するソフトウェアを使用して、クラス定義の 1 つの一部を変更するシナリオをサポートしています: XAML デザイナーなど、別のファイルで同じクラス内のコードを変更します。 部分クラスを使用すると、自動コード ジェネレーターを防ぐため、コードが上書きされないことができます。 Visual Studio プロジェクトで、**部分**修飾子は、生成されたファイルに自動的に適用されます。  
  
 内容: 2 つの例外を除き、部分クラス定義を含めることができる場合に完全クラス定義を含む可能性のあるもの、**部分**キーワードを省略します。 ただし、クラスのアクセシビリティを指定することはできません (たとえば、 `public partial class X { ... };`)、または**declspec**します。  
  
 アクセス指定子の部分クラス定義で使用される*識別子*の後続の部分的または完全なクラス定義で既定のアクセシビリティは影響しません*識別子*します。 静的データ メンバーのインライン定義が許可されます。  
  
 次の宣言はクラスの部分定義*識別子*という名前のみ説明*識別子*、が*識別子*クラスを必要とする方法では使用できません定義。 名前*識別子*のサイズを知るには使用できません*識別子*、またはベースまたはのメンバーを使用する*識別子*まで、コンパイラは、の完全な定義を検出した後*識別子*します。  
  
 数字と順序: に対して 0 個以上の部分クラス定義できる*識別子*します。 すべての部分クラス定義*識別子*構文の 1 つの完全定義の前にする必要があります*識別子*(完全な定義がある場合、それ以外の場合、クラスは使用できません以外として。事前宣言) の事前宣言の前に必要がありますが、*識別子*します。 すべてのクラス キーが一致する必要があります。  
  
 完全な定義: クラスの完全な定義の時点で*識別子*、動作は、同じ場合は、定義*識別子*すべての基底クラス、メンバー、順序などを宣言する必要があります。発生し、部分クラスで定義されている、でした。  
  
 テンプレート: 部分クラスをテンプレートにすることはできません。  
  
 ジェネリック: 完全な定義がジェネリックにする場合、部分クラスでジェネリックを指定できます。 すべての部分と完全なクラスに正確に同じジェネリック パラメーター、仮パラメーター名を含む必要があります。  
  
 使用する方法についての詳細、**部分**キーワードを参照してください[部分クラス (C +/cli CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)します。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/ZW`  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 (この言語機能は適用されませんを共通言語ランタイム。)  
  
## <a name="see-also"></a>関連項目  
 [部分クラス (C + + CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)