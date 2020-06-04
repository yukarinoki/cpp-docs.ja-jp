---
title: 致命的なエラー C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: e57e4e0899a5f9d81e87a203b1b699cef0884f0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203269"
---
# <a name="fatal-error-c1311"></a>致命的なエラー C1311

COFF 形式では、' var ' をアドレスのバイト数で静的に初期化することはできません

コンパイル時に認識されない値を持つアドレスは、型が4バイト未満のストレージを持つ変数に静的に割り当てることはできません。

このエラーは、それ以外の場合に有効C++なコードで発生する可能性があります。

次の例は、C1311 の原因となる可能性がある1つの条件を示しています。

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```
