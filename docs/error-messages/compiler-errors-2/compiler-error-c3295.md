---
title: コンパイラ エラー C3295 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3295
dev_langs:
- C++
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25fd1a04e0be46943b4fd183b470b369f810a0d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3295"></a>コンパイラ エラー C3295
'#pragma pragma' は、グローバルまたは名前空間スコープでのみ使用できます  
  
 一部のプラグマは関数内では使用できません。  参照してください[プラグマ ディレクティブと _ _pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C3295 が生成されます。  
  
```  
// C3295.cpp  
int main() {  
   #pragma managed   // C3295  
}  
```