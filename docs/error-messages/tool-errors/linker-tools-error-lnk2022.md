---
title: リンカ ツール エラー LNK2022 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2022
dev_langs:
- C++
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7769bc28dc777ef8d7b82b91b9695356db05a682
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300889"
---
# <a name="linker-tools-error-lnk2022"></a>リンカ ツール エラー LNK2022  
  
> メタデータ操作に失敗しました (*HRESULT*): *error_message*  
  
リンカーでは、メタデータのマージ中にエラーが検出されました。 正常にリンクするメタデータのエラーを解決する必要があります。  
  
実行するにはこの問題を診断する方法**ildasm-トークン**にある種類を検索するオブジェクト ファイルで、トークンが一覧表示`error_message`、し、相違点を探します。  メタデータ、LayoutType の属性が異なる場合でもと同じ名前の 2 つのさまざまな種類が正しくありません。  
  
LNK2022 (構造体) などの型が、同じ名前ではなく、競合する定義は、複数のコンパイル単位に存在する場合とでコンパイルするときにいずれかの理由[/clr](../../build/reference/clr-common-language-runtime-compilation.md)です。  この場合、型が、すべてのコンパイル単位内の同一の定義を持つことを確認します。  型名が表示されて`error_message`です。  
  
LNK2022 の他の考えられる原因は、リンカーは、コンパイラに指定された数より、別の場所でメタデータ ファイルを見つけたとき (で[#using](../../preprocessor/hash-using-directive-cpp.md) )。 メタデータ ファイル (.dll または .netmodule) がリンカーに渡されるときに、同じ場所に、コンパイラに渡されたときに確認してください。  
  
ATL アプリケーション、マクロの使用を構築するときに`_ATL_MIXED`少なくとも 1 つで使用されている場合は、すべてのコンパイル単位が必要です。  
  
## <a name="example"></a>例  
  
次の例では、空の型を定義します。  
  
```cpp  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## <a name="example"></a>例  
  
このサンプルでは、名前が同じで異なる定義の型を含む 2 つのソース コード ファイルをリンクすることはできないことを示します。  
  
次の例では、LNK2022 が生成されます。  
  
```cpp  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```