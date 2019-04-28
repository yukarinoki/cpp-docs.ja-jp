---
title: 式の配列
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
ms.openlocfilehash: 0f2ef43c2a5bc4f8a44378c21d6d53b14f07ea07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184381"
---
# <a name="arrays-in-expressions"></a>式の配列

配列型の識別子が表示されたら、式で他にも`sizeof`、アドレスの (**&**)、または初期化の参照、配列の最初の要素へのポインターに変換されます。 例えば:

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

ポインター `psz` は、配列 `szError1` の最初の要素をポイントします。 配列は、ポインターとは異なり、変更できる左辺値ではないことに注意してください。 したがって、次の割り当ては正しくありません。

```cpp
szError1 = psz;
```

## <a name="see-also"></a>関連項目

[配列](../cpp/arrays-cpp.md)