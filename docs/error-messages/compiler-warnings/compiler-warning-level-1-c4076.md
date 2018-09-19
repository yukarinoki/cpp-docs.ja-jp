---
title: コンパイラの警告 (レベル 1) C4076 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4076
dev_langs:
- C++
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f0a8066b8e79b75f3d5ede37f4e5ad6b61db168
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037880"
---
# <a name="compiler-warning-level-1-c4076"></a>コンパイラの警告 (レベル 1) C4076

> '*型修飾子*': 型を使用することはできません'*typename*'

## <a name="remarks"></a>Remarks

型修飾子、かどうかは**署名**または**符号なし**、整数以外の型では使用できません。 *型修飾子*は無視されます。

## <a name="example"></a>例

次の例は C4076 が生成されます。これを修正するには、削除、**符号なし**型修飾子。

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```