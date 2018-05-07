---
title: コンパイラの警告 (レベル 4) C4001 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc728fa5c66fb4b42c8fe4a785f36048ffbaed4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4001"></a>コンパイラの警告 (レベル 4) C4001
標準の拡張機能 '単一行コメントが使用されました  

> [!NOTE] 
> この警告は、単一行コメントは C99 に標準的なために、Visual Studio 2017 15.5 のバージョンで削除されます。
  
 単一行コメントは、C++ の標準 standard C の C99 で起動します。 厳密な ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、単一行コメントが含まれている C ファイルは、標準の拡張機能の使用状況のため C4001 を生成します。 単一行コメントが C++ の標準的なため、単一行コメントを含む C ファイル生成しない C4001 Microsoft 拡張機能 (/Ze) でコンパイルするときにします。  
  
## <a name="example"></a>例  
 警告を無効にするにコメントを解除[#pragma warning(disable:4001)](../../preprocessor/warning.md)です。  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```