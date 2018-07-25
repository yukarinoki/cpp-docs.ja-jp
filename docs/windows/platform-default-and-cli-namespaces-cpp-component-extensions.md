---
title: プラットフォーム、既定値、および cli 名前空間 (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- lang
- cli
dev_langs:
- C++
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b466a94aba9f19907a5438a8b8e623d65aa0ac2d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880749"
---
# <a name="platform-default-and-cli-namespaces--c-component-extensions"></a>プラットフォーム、既定、および cli 名前空間 (C++ コンポーネント拡張)
言語要素の名前は名前空間によって修飾されるため、それ以外は同じである名前と、ソース コードの別の部分で競合することはありません。 たとえば、名前の衝突されない可能性があります、コンパイラを認識し[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)です。 名前空間はコンパイラによって使用されますが、コンパイルされたアセンブリでは保持されません。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 Visual C++ では、プロジェクトの作成時に、既定の名前空間がプロジェクトに与えられます。 ルート名前空間の名前に一致する必要があります Windows ランタイムで、.winmd ファイルの名前が手動で、名前空間を変更できます。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 詳細については、次を参照してください。[名前空間と型の可視性 (C + + CX)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **構文**  
  
```  
using namespace cli;  
```  
  
 **解説**  
  
 C + + CLI をサポートしている、`cli`名前空間。 コンパイルするときに **/clr**、 `using` 「構文」セクション内ステートメント暗黙的に指定します。  
  
 次の言語機能は、`cli` 名前空間に含まれます。  
  
-   [配列](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次のコード例は、`cli` 名前空間のシンボルをユーザー定義シンボルとしてコードで使用できることを示します。  ただし、この場合は、同じ名前の `cli` 言語要素への参照を明示的または暗黙的に修飾する必要があります。  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)