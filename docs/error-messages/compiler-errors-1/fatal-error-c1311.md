---
description: '詳細情報: 致命的なエラー C1311'
title: 致命的なエラー C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: d6049bfedd01be02e8b3f26163fe062e9023bd78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177745"
---
# <a name="fatal-error-c1311"></a>致命的なエラー C1311

COFF 形式では、' var ' をアドレスのバイト数で静的に初期化することはできません

コンパイル時に認識されない値を持つアドレスは、型が4バイト未満のストレージを持つ変数に静的に割り当てることはできません。

このエラーは、それ以外の有効な C++ のコードで発生する可能性があります。

次の例は、C1311 の原因となる可能性がある1つの条件を示しています。

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```
