---
title: コンパイラの警告 (レベル 1) C4788 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a43fb9d79c63637b2bff9a27661a9f848ef6dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284200"
---
# <a name="compiler-warning-level-1-c4788"></a>コンパイラの警告 (レベル 1) C4788
'識別子' : 識別子は '数値' 文字に切り詰められました  
  
 コンパイラによって、関数名に使用できる最大文字数が制限されます。 いくつかのテキストに関数名を付加することによって作成された funclet 名を形成、コンパイラは、コードの funclets を生成するとき、"_ _catch"、"\__unwind"、または別の文字列。  
  
 作成された funclet 名が長すぎる場合、コンパイラはこれを切り捨てて C4788 を生成します。  
  
 この警告を解決するには、元の関数名を短くします。 関数が C++ テンプレート関数またはメソッドの場合は、名前の一部に typedef を使用します。 例えば:  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 これは次のように置換されます。  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 この警告は [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] コンパイラでのみ出力されます。