---
title: コンパイラの警告 (レベル 1) C4364 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4364
dev_langs:
- C++
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb3bfb8075d618a6d2ea9b733b01d8b456fdc0e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283762"
---
# <a name="compiler-warning-level-1-c4364"></a>コンパイラの警告 (レベル 1) C4364
\#アセンブリ 'file' location(line_number); as_friend 属性なしで以前に確認されたの使用as_friend は適用されません。  
  
 A`#using`ディレクティブが指定したメタデータ ファイルは、繰り返されましたが、`as_friend`修飾子が最初に見つかった位置で使用されていない以外の場合は、コンパイラは、2 つ目を無視`as_friend`です。  
  
 詳細については、次を参照してください。[フレンド アセンブリ (C++)](../../dotnet/friend-assemblies-cpp.md)です。  
  
## <a name="example"></a>例  
 コンポーネントを作成する例を次に示します。  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## <a name="example"></a>例  
 次の例では、C4364 を生成します。  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```