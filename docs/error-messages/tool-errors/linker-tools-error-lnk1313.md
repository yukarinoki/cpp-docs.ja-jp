---
title: リンカ ツール エラー LNK1313 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1313
dev_langs:
- C++
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 613c2069443e580fb581798d9e1cc6d5781d7c91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1313"></a>リンカ ツール エラー LNK1313
ijw/ネイティブ モジュールが検出されました。純粋なモジュールとリンクできません。  
  
 現在のバージョンの Visual C がでコンパイルされた .obj ファイルのネイティブまたは混合マネージ/ネイティブ .obj ファイルのリンクをサポートしていない **/clr: 純粋な**します。  
  
## <a name="example"></a>例  
  
```  
// LNK1313.cpp  
// compile with: /c /clr:pure  
// a pure module  
int main() {}  
```  
  
## <a name="example"></a>例  
  
```  
// LNK1313_b.cpp  
// compile with: /c /clr  
// an IJW module  
void test(){}  
```  
  
## <a name="example"></a>例  
 次の例では lnk1313 エラーが生成されます。  
  
```  
// LNK1313_c.cpp  
// compile with: /link LNK1313.obj LNK1313_b.obj  
// LNK1313 warning expected  
```