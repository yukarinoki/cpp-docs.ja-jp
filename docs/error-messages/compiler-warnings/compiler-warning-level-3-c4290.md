---
title: コンパイラの警告 (レベル 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 5970aa439a450bda4c1a2036da299d5c3cfbdb7a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198901"
---
# <a name="compiler-warning-level-3-c4290"></a>コンパイラの警告 (レベル 3) C4290

C++関数が __declspec でないことを示す場合を除き、例外の指定は無視されました (nothrow)

関数が例外指定を使用して宣言さC++れていますが、これはビジュアルが受け入れるが実装していません。 コンパイル中に無視される例外指定を含むコードは、例外指定をサポートする将来のバージョンで再コンパイルおよびリンクされる必要があります。

詳細については、「[例外の指定 (throw)](../../cpp/exception-specifications-throw-cpp.md) 」を参照してください。

この警告を回避するには、 [warning](../../preprocessor/warning.md)プラグマを使用します。

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
