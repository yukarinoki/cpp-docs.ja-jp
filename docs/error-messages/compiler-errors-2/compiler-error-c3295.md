---
title: コンパイラ エラー C3295 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3295
dev_langs:
- C++
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b8210aacf60c4c53faf50278e7494c90c58aa67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076425"
---
# <a name="compiler-error-c3295"></a>コンパイラ エラー C3295

'#pragma pragma' は、グローバルまたは名前空間スコープでのみ使用できます

一部のプラグマは関数内では使用できません。  参照してください[プラグマ ディレクティブと _ _pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)詳細についてはします。

## <a name="example"></a>例

次の例では C3295 が生成されます。

```
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```