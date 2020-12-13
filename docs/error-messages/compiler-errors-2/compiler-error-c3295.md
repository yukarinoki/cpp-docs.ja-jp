---
description: 詳細については、「コンパイラエラー C3295」を参照してください。
title: コンパイラ エラー C3295
ms.date: 11/04/2016
f1_keywords:
- C3295
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
ms.openlocfilehash: 55fab24088690f5d5bb92da0cc55442bcebeed01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144626"
---
# <a name="compiler-error-c3295"></a>コンパイラ エラー C3295

'#pragma pragma' は、グローバルまたは名前空間スコープでのみ使用できます

一部のプラグマは関数内では使用できません。  詳細について [は、「プラグマディレクティブ」と「__Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3295 が生成されます。

```cpp
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```
