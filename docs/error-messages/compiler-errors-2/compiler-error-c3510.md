---
title: コンパイラ エラー C3510 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abb58d8d4fb9008b07579ef7fbc0066d00bcea57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3510"></a>コンパイラ エラー C3510
依存タイプ ライブラリ 'type_lib' を見つけることができません。  
  
 [no_registry](../../preprocessor/no-registry.md)と[auto_search](../../preprocessor/auto-search.md)に渡された`#import`が、コンパイラが参照されるタイプ ライブラリを検索することができませんでした。  
  
 このエラーを解決するには、すべてのタイプ ライブラリおよび参照タイプ ライブラリがコンパイラに利用できることを確認します。  
  
 次の例では、C3510 が生成されます。  
  
 します。 次の 2 つのタイプ ライブラリがビルドされた C3510a.tlb が削除されたか、パスではなくです。  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 ソース コードの 2 つ目のタイプ ライブラリ:  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 クライアント コード:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```