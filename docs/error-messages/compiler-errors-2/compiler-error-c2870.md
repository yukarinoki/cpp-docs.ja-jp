---
title: コンパイラ エラー C2870 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fe9f47a96422493d6d731a18add8c23ff683f14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243490"
---
# <a name="compiler-error-c2870"></a>コンパイラ エラー C2870
'name': 名前空間の定義は、ファイル スコープ、またはすぐに別の名前空間の定義内に表示される必要があります  
  
 名前空間を定義した`name`が正しくないです。 名前空間を (すべてのブロックとクラス) の外部のファイル スコープで定義する必要がありますまたは別の名前空間内ですぐにします。  
  
 次の例では、C2870 が生成されます。  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```