---
title: コンパイラ エラー C2989 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2989
dev_langs:
- C++
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7831f9255485ede8db9d853ca5fe89dc9a4c2a65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2989"></a>コンパイラ エラー C2989
'class': クラス型が非クラスの種類として既に宣言されています  
  
 ジェネリック クラスまたはテンプレートには、非テンプレートまたは非ジェネリック クラスが再定義します。 競合のヘッダー ファイルを確認してください。  
  
 クラス テンプレートの部分的な特殊化を使用している場合は、サポート技術情報記事 Q240866 を参照してください。  
  
 次の例では、C2989 が生成されます。  
  
```  
// C2989.cpp  
// compile with: /c  
class C{};  
  
template <class T>  
class C{};  // C2989  
class C2{};  
```  
  
 C2989 は、ジェネリックを使用するときにも発生することができます。  
  
```  
// C2989b.cpp  
// compile with: /clr /c  
ref class GC1;  
  
generic <typename T> ref class GC1;   // C2989  
template <typename T> ref class GC2;  
  
generic <typename T> ref class GC2;   // C2989  
generic <typename T> ref class GCb;  
template <typename T> ref class GC2;  
generic <typename T> ref class GCc;  
```