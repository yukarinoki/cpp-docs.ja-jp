---
title: コンパイラ エラー C3295
ms.date: 11/04/2016
f1_keywords:
- C3295
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
ms.openlocfilehash: 63739989d737527e3f136bb3aac2269eda6231c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601696"
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