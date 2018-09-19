---
title: 致命的なエラー C1311 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d93aa28d0cef3c07fd469349d485c4009fa4771d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091063"
---
# <a name="fatal-error-c1311"></a>致命的なエラー C1311

COFF 形式は、'var' を数値のバイトのアドレスを静的に初期化できません。

アドレスの値がコンパイル時に不明は、型に 4 バイト未満のストレージを持つ変数に静的に割り当てることができません。

このエラーは、それ以外の場合は、コードで発生する可能性が有効な C++ です。

次の例では、C1311 を引き起こす可能性のある 1 つの条件を示します。

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```