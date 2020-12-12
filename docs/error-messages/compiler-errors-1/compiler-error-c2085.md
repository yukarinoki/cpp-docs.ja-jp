---
description: 詳細については、「コンパイラエラー C2085」を参照してください。
title: コンパイラエラー C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: 2cd828c9a18c06c5794bef01ba861f702af2e096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252117"
---
# <a name="compiler-error-c2085"></a>コンパイラエラー C2085

' identifier ': 仮パラメーターリスト内にありません

識別子が関数定義で宣言されていますが、仮パラメーターリストでは宣言されていません。 (ANSI C のみ)

次の例では、C2085 が生成されます。

```c
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

考えられる解決策:

```c
// C2085b.c
void func1( void );
int main( void ) {}
```

セミコロンがない場合、 `func1()` はプロトタイプではなく関数定義のように見え `main` ます。したがって、は内で定義され `func1()` 、識別子のエラー C2085 を生成し `main` ます。
