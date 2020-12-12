---
description: '詳細情報: コンパイラの警告 (レベル 3) C4290'
title: コンパイラの警告 (レベル 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 771eb01c23778a716aee22ca747ea6473909a8bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344069"
---
# <a name="compiler-warning-level-3-c4290"></a>コンパイラの警告 (レベル 3) C4290

関数が __declspec でないことを示す場合を除き、C++ 例外の指定は無視されました (nothrow)

関数が例外指定を使用して宣言されていますが、Visual C++ はを受け入れますが、を実装していません。 コンパイル中に無視される例外指定を含むコードは、例外指定をサポートする将来のバージョンで再コンパイルおよびリンクされる必要があります。

詳細については、「 [例外の指定 (throw)](../../cpp/exception-specifications-throw-cpp.md) 」を参照してください。

この警告を回避するには、 [warning](../../preprocessor/warning.md) プラグマを使用します。

```cpp
#pragma warning( disable : 4290 )
```

次のコード例では、C4290 が生成されます。

```cpp
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```
