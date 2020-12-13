---
description: '詳細情報: コンパイラの警告 (レベル 1) C4612'
title: コンパイラの警告 (レベル 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: 2844b54c592f5c4c4817cfec97d57c41fa2055b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341725"
---
# <a name="compiler-warning-level-1-c4612"></a>コンパイラの警告 (レベル 1) C4612

> インクルード ファイル名にエラーがあります

## <a name="remarks"></a>解説

この警告は、ファイル名が正しくないか、不足している場合に、 **#pragma include_alias** で発生します。

**#Pragma include_alias** ステートメントの引数は、引用符形式 ("*filename*") または山かっこ形式 () を使用でき \<*filename*> ますが、両方とも同じ形式を使用する必要があります。

## <a name="example"></a>例

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```
