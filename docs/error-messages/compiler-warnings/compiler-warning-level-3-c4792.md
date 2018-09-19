---
title: コンパイラの警告 (レベル 3) C4792 |Microsoft Docs
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
ms.openlocfilehash: 4afb08cbe3203ff462f59fec4c1e712aa024c081
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136063"
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