---
title: リンカ ツール エラー LNK1312 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 748276ed8fa459c41174f23d32bcef127cbdd510
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300447"
---
# <a name="linker-tools-error-lnk1312"></a>リンカ ツール エラー LNK1312
ファイルが無効か破損しています: アセンブリをインポートできません。  
  
 アセンブリ、モジュールまたはしてコンパイルされたアセンブリではないファイルを作成するときに **/clr**に渡された、 **/ASSEMBLYMODULE**リンカー オプション。  オブジェクト ファイルが渡された場合 **/ASSEMBLYMODULE**、のみ、オブジェクトに直接渡す、リンカーの代わりを **/ASSEMBLYMODULE**です。  
  
## <a name="example"></a>例  
 次の例では、.obj ファイルを作成します。  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## <a name="example"></a>例  
 次の例では、LNK1312 が生成されます。  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```