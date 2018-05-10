---
title: コンパイラの警告 (レベル 3) C4792 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4792
dev_langs:
- C++
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4b0867305c56fc551e55680b6ed48bdb701cc09
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4792"></a>コンパイラの警告 (レベル 3) C4792
sysimport を使用して関数 'function' が宣言され、ネイティブ コードから参照されました。インポート ライブラリはリンクする必要があります  
  
 DllImport を使用してプログラムにインポートされたネイティブ関数が、アンマネージ関数から呼び出されました。 そのため、DLL のインポート ライブラリにリンクする必要があります。  
  
 コード内、またはコンパイル方法の変更でこの警告を解決することはできません。 この警告を無効にするには、 [warning](../../preprocessor/warning.md) プラグマを使用します。  
  
 次の例では C4792 が生成されます。  
  
```  
// C4792.cpp  
// compile with: /clr /W3  
// C4792 expected  
using namespace System::Runtime::InteropServices;  
[DllImport("msvcrt")]  
extern "C" int __cdecl puts(const char *);  
int main() {}  
  
// Uncomment the following line to resolve.  
// #pragma warning(disable : 4792)  
#pragma unmanaged  
void func(void){  
   puts("test");  
}  
```