---
title: リンカ ツール エラー LNK2033 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2033
dev_langs:
- C++
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d03e8d2e0502d6e3664bff05c75fffb4f4ebd5da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301971"
---
# <a name="linker-tools-error-lnk2033"></a>リンカ ツール エラー LNK2033
'type' の未解決の typeref トークン (トークン)  
  
 MSIL のメタデータに型の定義がありません。  
  
 LNK2033 はでコンパイルするときに発生する可能性が **/clr:safe**が MSIL モジュールの MSIL モジュールの種類が参照されている場所にある種類の事前宣言のみが存在するとします。  
  
 型の下で定義する必要があります **/clr:safe**です。  
  
 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、LNK2033 が生成されます。  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```